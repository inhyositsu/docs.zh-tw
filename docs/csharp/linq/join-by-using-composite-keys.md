---
title: 使用複合索引鍵執行聯結
description: 如何使用複合索引鍵執行聯結。
ms.date: 12/1/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: e40f4d147886c07913c761bb5df83ee34d23eaba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271210"
---
# <a name="join-by-using-composite-keys"></a>使用複合索引鍵執行聯結

此範例示範如何執行聯結作業，您想要在其中使用多個索引鍵來定義比對項目。 使用複合索引鍵便可完成這項定義。 您會將複合索引鍵建立成匿名型別，或是包含要比較之值的具名型別。 如果將跨方法界限傳遞查詢變數，請使用可覆寫索引鍵之 <xref:System.Object.Equals%2A> 和 <xref:System.Object.GetHashCode%2A> 的具名類型。 在每個索引鍵中，這些屬性的名稱及其出現的順序都必須相同。  
  
## <a name="example"></a>範例  
 下列範例示範如何使用複合索引鍵來聯結來自三個資料表的資料：  
  
```csharp  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,        d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 複合索引鍵上的型別推斷，會根據索引鍵中的屬性名稱及其出現的順序來進行。 如果來源序列中的屬性沒有相同名稱，您就必須在索引鍵中指派新的名稱。 例如，如果 `Orders` 資料表和 `OrderDetails` 資料表分別對其資料行使用不同的名稱，您就可以在匿名型別中指派相同的名稱以建立複合索引鍵：  
  
```csharp  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 複合索引鍵也可用於 `group` 子句。  

## <a name="see-also"></a>另請參閱  
 [LINQ 查詢運算式](index.md)  
 [join 子句](../language-reference/keywords/join-clause.md)  
 [group 子句](../language-reference/keywords/group-clause.md)
