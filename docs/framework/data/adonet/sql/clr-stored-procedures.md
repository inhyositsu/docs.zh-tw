---
title: CLR 預存程序
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: c0a318d2d11788d274da637cd1846f72159cd013
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358585"
---
# <a name="clr-stored-procedures"></a>CLR 預存程序
預存程序是無法在純量運算式中使用的常式。 它們可將表格式結果及訊息傳回到用戶端、叫用資料定義語言 (DDL) 及資料操作語言 (DML) 陳述式，並傳回輸出參數。  
  
> [!NOTE]
>  Microsoft Visual Basic 支援輸出參數的方式，與 Microsoft Visual C# 所使用的方式不同。 您必須指定傳址方式傳遞參數，並套用\<Out() > 屬性以表示 output 參數，如下所示：  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 如需詳細資訊，請參閱您所使用之 SQL Server 版本的《SQL Server 線上叢書》版本。  
  
 **SQL Server 線上叢書**  
  
1.  [CLR 預存程序](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>另請參閱  
 [在 Managed 程式碼中建立 SQL Server 2005 物件](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [ADO.NET Managed 提供者和 DataSet 開發人員中心](http://go.microsoft.com/fwlink/?LinkId=217917)
