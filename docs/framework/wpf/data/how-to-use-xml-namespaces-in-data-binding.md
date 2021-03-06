---
title: 操作說明：在資料繫結中使用 XML 命名空間
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 483b59bb7cea25617c832b96690f742b8b64b3e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556896"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>操作說明：在資料繫結中使用 XML 命名空間
## <a name="example"></a>範例  
 這個範例顯示如何處理 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 繫結來源中指定的命名空間。  
  
 如果您的 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 資料具有下列 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空間定義：  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 您可以使用<xref:System.Windows.Data.XmlNamespaceMapping>命名空間對應至的項目<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>，如下列範例所示。 然後您可以使用<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>指[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]命名空間。 <xref:System.Windows.Controls.ListBox>在此範例會顯示*標題*和*dc:date*每個*項目*。  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 請注意，<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>您指定不需要符合用於[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]來源; 如果前置詞中變更[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]來源對應仍能運作。  
  
 在此特定範例中，[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]資料來自 web 服務，但<xref:System.Windows.Data.XmlNamespaceMapping>項目也會搭配內嵌[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]或[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]內嵌檔案中的資料。  
  
## <a name="see-also"></a>另請參閱  
 [使用 XMLDataProvider 和 XPath 查詢繫結至 XML 資料](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [資料繫結概觀](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [HOW-TO 主題](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
