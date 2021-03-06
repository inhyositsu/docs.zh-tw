---
title: 最佳化效能：物件行為
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interface virtualization [WPF]
- dependency properties [WPF], performance
- event handlers [WPF]
- object performance considerations [WPF]
- Freezable objects [WPF], performance
ms.assetid: 73aa2f47-1d73-439a-be1f-78dc4ba2b5bd
ms.openlocfilehash: 2e1f56dec87de7a22aa8a0bfefe84222d74ba085
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549213"
---
# <a name="optimizing-performance-object-behavior"></a>最佳化效能：物件行為
了解 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 物件的內建行為有助您做出功能和效能之間的正確取捨。  
  

  
<a name="Not_Removing_Event_Handlers"></a>   
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>不移除物件的事件處理常式可能會保持物件運作  
 物件傳遞給其事件的委派實際上是對該物件的參考。 因此，事件處理常式可以讓物件保持運作時間超出預期。 在對已註冊要接聽物件事件的物件執行清除時，務必要在釋放物件之前先移除該委派。 讓不需要的物件保持運行狀態會增加應用程式的記憶體使用量。 特別是當物件是邏輯樹狀結構或視覺化樹狀結構的根目錄時。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 針對適用於來源與接聽程式之間物件存留期關係難以追蹤的情況的事件，引進了弱式事件接聽程式模式。 某些現有的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 事件會使用此模式。 如果您正在以自訂事件實作物件，這個模式可能對您有用。 如需詳細資訊，請參閱[弱式事件模式](../../../../docs/framework/wpf/advanced/weak-event-patterns.md)。  
  
 有數個工具，例如 CLR 分析工具和工作集檢視器，可以提供有關指定處理序的記憶體使用量資訊。 CLR 分析工具包含許多配置設定檔的極有用檢視，包括已配置類型長條圖、配置和呼叫圖形、顯示各種層代記憶體回收的時間線和回收之後產生的 managed 堆積狀態，以及顯示每個方法配置和組件載入的呼叫樹狀結構。 如需詳細資訊，請參閱 [.NET Framework Developer Center](http://go.microsoft.com/fwlink/?LinkId=117435) (.NET Framework 開發人員中心)。  
  
<a name="DPs_and_Objects"></a>   
## <a name="dependency-properties-and-objects"></a>相依性屬性與物件  
 一般情況下，存取 相依性屬性的<xref:System.Windows.DependencyObject>不低於存取[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]屬性。 雖然設定屬性值會有小小的效能負荷，但取得值就像取得 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 屬性的值一樣快。 小小效能負荷的補償是相依性屬性可支援強大的功能，例如資料繫結、動畫、繼承和樣式。 如需詳細資訊，請參閱[相依性屬性概觀](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。  
  
### <a name="dependencyproperty-optimizations"></a>DependencyProperty 最佳化  
 您應該在應用程式中非常小心地定義相依性屬性。 如果您<xref:System.Windows.DependencyProperty>影響是只轉譯型別中繼資料 選項，而不是其他中繼資料 選項例如<xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>，您應該將它標示為藉由覆寫它的中繼資料。 如需覆寫或取得屬性中繼資料的詳細資訊，請參閱[相依性屬性中繼資料](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)。  
  
 如果並非所有屬性變更都會實際上影響測量、排列與轉譯，手動讓屬性變更處理常式使測量、排列與轉譯階段失效，可能會更有效率。 比方說，您可能決定只有在值大於設定的限制時，才重新轉譯背景。 在此情況下，您的屬性變更處理常式只會在值超過設定的限制時使轉譯器失效。  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>使 DependencyProperty 成為可繼承不是免費的  
 根據預設，已註冊的相依性屬性是不可繼承的。 不過，您可以明確地使任何屬性成為可繼承。 雖然這是很有用的功能，但將屬性轉換為可繼承會影響效能，因為會增加屬性失效的時間長度。  
  
### <a name="use-registerclasshandler-carefully"></a>小心使用 RegisterClassHandler  
 呼叫<xref:System.Windows.EventManager.RegisterClassHandler%2A>可讓您儲存您的執行個體狀態，請務必留意呼叫此處理常式時，會在每個執行個體，可能會造成效能問題。 只使用<xref:System.Windows.EventManager.RegisterClassHandler%2A>應用程式需要您儲存執行個體狀態。  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>在註冊期間設定 DependencyProperty 的預設值  
 建立時<xref:System.Windows.DependencyProperty>需要預設值，使用預設的中繼資料當做參數傳遞的值設<xref:System.Windows.DependencyProperty.Register%2A>方法<xref:System.Windows.DependencyProperty>。 使用這項技術，而不是在建構函式或項目的每個執行個體上設定屬性值。  
  
### <a name="set-the-propertymetadata-value-using-register"></a>使用 Register 設定 PropertyMetadata 值  
 建立時<xref:System.Windows.DependencyProperty>，您可以選擇設定<xref:System.Windows.PropertyMetadata>使用<xref:System.Windows.DependencyProperty.Register%2A>或<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>方法。 雖然您的物件可能會有靜態的建構函式，呼叫<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>，這不是最好的解決方案，而且將會影響效能。 為了達到最佳效能，設定<xref:System.Windows.PropertyMetadata>的呼叫期間<xref:System.Windows.DependencyProperty.Register%2A>。  
  
<a name="Freezable_Objects"></a>   
## <a name="freezable-objects"></a>Freezable 物件  
 A<xref:System.Windows.Freezable>是特殊類型的物件，具有兩種狀態： 解除凍結但卻凍結。 盡可能凍結物件可以提升應用程式的效能，並縮減其工作集。 如需詳細資訊，請參閱 [Freezable 物件概觀](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。  
  
 每個<xref:System.Windows.Freezable>具有<xref:System.Windows.Freezable.Changed>變更時引發的事件。 不過，變更通知會嚴重降低應用程式效能。  
  
 請考慮下列範例中的每個<xref:System.Windows.Shapes.Rectangle>會使用相同<xref:System.Windows.Media.Brush>物件：  
  
 [!code-csharp[Performance#PerformanceSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 根據預設，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供的事件處理常式<xref:System.Windows.Media.SolidColorBrush>物件的<xref:System.Windows.Freezable.Changed>事件才能使<xref:System.Windows.Shapes.Rectangle>物件的<xref:System.Windows.Shapes.Shape.Fill%2A>屬性。 在此情況下，每次<xref:System.Windows.Media.SolidColorBrush>已引發其<xref:System.Windows.Freezable.Changed>事件必須為每個叫用的回呼函式<xref:System.Windows.Shapes.Rectangle>— 這些回呼函式引動過程的累積造成顯著的效能負面影響。 此外，在此時新增和移除處理常式會相當耗損效能，因為應用程式必須周遊整個清單才能執行這項操作。 如果您的應用程式案例絕對不會改變<xref:System.Windows.Media.SolidColorBrush>，您將支付的維護成本<xref:System.Windows.Freezable.Changed>事件處理常式不必要地。  
  
 凍結<xref:System.Windows.Freezable>可以提升效能，因為它不再需要展開上維護變更通知的資源。 下表顯示簡單的大小<xref:System.Windows.Media.SolidColorBrush>時其<xref:System.Windows.Freezable.IsFrozen%2A>屬性設定為`true`、 比較時不。 這是假設套用一筆刷<xref:System.Windows.Shapes.Shape.Fill%2A>屬性十個<xref:System.Windows.Shapes.Rectangle>物件。  
  
|**狀態**|**Size**|  
|---------------|--------------|  
|凍結 <xref:System.Windows.Media.SolidColorBrush>|212 個位元組|  
|非凍結 <xref:System.Windows.Media.SolidColorBrush>|972 個位元組|  
  
 下列程式碼範例說明此概念：  
  
 [!code-csharp[Performance#PerformanceSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>未凍結的 Freezable 上的已變更處理常式可能會保持物件運作  
 物件會傳遞至委派<xref:System.Windows.Freezable>物件的<xref:System.Windows.Freezable.Changed>事件實際上就是該物件的參考。 因此，<xref:System.Windows.Freezable.Changed>事件處理常式可以讓物件保持運作時間超出預期。 執行清除時之物件的已註冊至接聽<xref:System.Windows.Freezable>物件的<xref:System.Windows.Freezable.Changed>事件時，務必要釋放物件之前，先移除該委派。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 連結也<xref:System.Windows.Freezable.Changed>事件在內部。 例如，所有相依性屬性需要<xref:System.Windows.Freezable>為值，將接聽<xref:System.Windows.Freezable.Changed>事件自動。 <xref:System.Windows.Shapes.Shape.Fill%2A>屬性，其中需要<xref:System.Windows.Media.Brush>，說明這個概念。  
  
 [!code-csharp[Performance#PerformanceSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 指派上`myBrush`至`myRectangle.Fill`、 回指向委派<xref:System.Windows.Shapes.Rectangle>物件將會加入至<xref:System.Windows.Media.SolidColorBrush>物件的<xref:System.Windows.Freezable.Changed>事件。 這表示下列程式碼實際上不會讓 `myRect` 符合記憶體回收資格︰  
  
 [!code-csharp[Performance#PerformanceSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 在此情況下`myBrush`仍保留`myRectangle`運作，而且會呼叫回它時引發其<xref:System.Windows.Freezable.Changed>事件。 請注意，指定`myBrush`至<xref:System.Windows.Shapes.Shape.Fill%2A>屬性的新<xref:System.Windows.Shapes.Rectangle>只會加入另一個事件處理常式來`myBrush`。  
  
 若要清除這些類型的物件的建議的方式是移除<xref:System.Windows.Media.Brush>從<xref:System.Windows.Shapes.Shape.Fill%2A>屬性，依序將會移除<xref:System.Windows.Freezable.Changed>事件處理常式。  
  
 [!code-csharp[Performance#PerformanceSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## <a name="user-interface-virtualization"></a>使用者介面虛擬化  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 也會提供一種<xref:System.Windows.Controls.StackPanel>自動 「 虛擬化 」 資料繫結子內容的項目。 在此內容中，「虛擬化」一字係指一種技術，藉由這種技術，將可從較大量的資料項目，根據畫面上可見的項目來產生物件子集。 當在指定的時間內畫面上只能有幾個 UI 項目時，不論是就記憶體還是處理器而言，產生大量 UI 項目都會相當耗費資源。 <xref:System.Windows.Controls.VirtualizingStackPanel> (透過所提供的功能<xref:System.Windows.Controls.VirtualizingPanel>) 計算的可見項目，並搭配<xref:System.Windows.Controls.ItemContainerGenerator>從<xref:System.Windows.Controls.ItemsControl>(例如<xref:System.Windows.Controls.ListBox>或<xref:System.Windows.Controls.ListView>) 只建立可見的項目項目。  
  
 作為效能最佳化，只有在這些項目的視覺物件顯示在螢幕上時才會產生或保持這些項目的視覺物件運作。 如果視覺物件不再位於控制項的可檢視區域中，可能會移除視覺物件。 這並不會與資料虛擬化混淆，在資料虛擬化中，資料物件不會全都在本機集合，而是視需要進行資料流處理。  
  
 下表顯示所經過的時間加入與轉譯 5000<xref:System.Windows.Controls.TextBlock>項目<xref:System.Windows.Controls.StackPanel>和<xref:System.Windows.Controls.VirtualizingStackPanel>。 在此案例中，度量代表附加到文字字串之間的時間<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>屬性<xref:System.Windows.Controls.ItemsControl>面板項目時顯示的文字字串的時間的物件。  
  
|**主面板**|**轉譯時間 (毫秒)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>另請參閱  
 [最佳化 WPF 應用程式效能](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [應用程式效能規劃](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [運用硬體](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [版面配置與設計](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D 圖形和影像處理](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [應用程式資源](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [資料繫結](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [其他效能建議](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
