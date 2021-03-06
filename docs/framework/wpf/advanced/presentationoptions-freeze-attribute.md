---
title: PresentationOptions:Freeze 屬性
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: 896f7b24599b68f178d2a006e5ddc07278564bde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546067"
---
# <a name="presentationoptionsfreeze-attribute"></a>PresentationOptions:Freeze 屬性
設定<xref:System.Windows.Freezable.IsFrozen%2A>狀態`true`上包含<xref:System.Windows.Freezable>項目。 預設行為<xref:System.Windows.Freezable>不含`PresentationOptions:Freeze`指定屬性是<xref:System.Windows.Freezable.IsFrozen%2A>是`false`在載入時間，取決於一般<xref:System.Windows.Freezable>在執行階段行為。  
  
## <a name="xaml-attribute-usage"></a>XAML Attribute Usage  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`PresentationOptions`|XML 命名空間前置詞，它可以是任何有效的前置詞字串，根據 XML 1.0 規格。 前置詞`PresentationOptions`用於識別這個文件中。|  
|`freezableElement`|具現化任何元素的衍生類別<xref:System.Windows.Freezable>。|  
  
## <a name="remarks"></a>備註  
 `Freeze`屬性是唯一的屬性，或是其他程式設計項目中定義`http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`XML 命名空間。 `Freeze`屬性存在這個特殊的命名空間中，特別是，以便將它指定為可忽略，使用[mc: Ignorable 屬性](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)做為根項目宣告的一部分。 原因，`Freeze`必須能夠被忽略因為不是所有[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]處理器實作可凍結<xref:System.Windows.Freezable>在載入時間; 這項功能不屬於[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]規格。  
  
 處理能力`Freeze`屬性特別內建[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]處理器處理[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]用於編譯的應用程式。 屬性不支援的任何類別，且屬性語法可延伸或可修改。 如果您要實作您自己[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]處理器平行的凍結行為時，您可以選擇[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]處理器處理時`Freeze`屬性<xref:System.Windows.Freezable>在載入時間的項目。  
  
 任何值`Freeze`屬性以外`true`（不區分大小寫） 會產生載入時間錯誤。 (指定`Freeze`屬性做為`false`不是錯誤，但已經預設值，因此將設定為`false`不做任何動作)。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Freezable>  
 [Freezable 物件概觀](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [mc:Ignorable 屬性](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
