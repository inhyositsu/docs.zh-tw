---
title: "載入 DOM 時處理泛空白字元和顯著泛空白字元 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# 載入 DOM 時處理泛空白字元和顯著泛空白字元
載入文件時，您可以設定選項來保留泛空白字元，並且在文件樹狀結構中建立 **XmlWhitespace** 節點。  若要建立泛空白字元節點，請將 **PreserveWhitespace** 屬性設為 True。  如果屬性設為預設的 **false**，就不會建立泛空白字元節點。  顯著泛空白字元節點一定會被保留，而且 **XmlSignificantWhitespace** 節點一律會建立於記憶體中以表示這個資料，無論 **PreserveWhitespace** 旗標的設定為何。  
  
 若文件是從讀取器載入，則只有在 **XmlTextReader** 的 **WhitespaceHandling** 屬性設為 **WhitespaceHandling.None** 時，**XmlDocument** 類別的 **PreserveWhitespace** 旗標屬性設定才會影響 **XmlWhitespace** 節點的建立。  優先順序高於 **XmlDocument** 之旗標設定的，是讀取器上的 **WhitespaceHandling** 屬性值。  如需 **XmlSignificantWhitespace** 的詳細資訊，請參閱 [XmlSignificantWhitespace 類別](frlrfSystemXmlXmlSignificantWhitespaceClassTopic)。  
  
## 請參閱  
 [XML 文件物件模型 \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)