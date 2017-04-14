---
title: "raceOnRCWCleanup MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "RCW"
  - "managed debugging assistants (MDAs), RCWs"
  - "race on RCW cleanup"
  - "MDAs (managed debugging assistants), RCWs"
  - "RaceOnRCWCleanup MDA"
  - "runtime callable wrappers"
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# raceOnRCWCleanup MDA
當使用 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName> 方法等命令呼叫釋放[執行階段可呼叫包裝函式](../../../docs/framework/interop/runtime-callable-wrapper.md) \(RCW\) 時，如果 Common Language Runtime \(CLR\) 偵測到 RCW 正在使用中，則會啟動 `raceOnRCWCleanup` Managed 偵錯助理 \(MDA\)。  
  
## 徵兆  
 使用 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 或類似方法釋放 RCW 期間或之後，發生存取違規或記憶體損毀的情況。  
  
## 原因  
 另一個執行緒正在使用這個 RCW，或釋放執行緒堆疊時正在使用這個 RCW。  無法釋放使用中的 RCW。  
  
## 解決方式  
 請勿釋放目前執行緒或其他執行緒可能正在使用的 RCW。  
  
## 對執行階段的影響  
 此 MDA 對 CLR 沒有影響。  
  
## 輸出  
 描述錯誤的訊息。  
  
## 組態  
  
```  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## 請參閱  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop 封送處理](../../../docs/framework/interop/interop-marshaling.md)