---
title: 如何：從 bool? 安全轉型到 bool (C# 程式設計手冊)
ms.date: 07/20/2015
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
ms.openlocfilehash: e04e34abd477730f9dd01486ec6bddcde4943edc
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457473"
---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a>如何：從 bool? 安全轉型到 bool (C# 程式設計手冊)
`bool?` 可為 Null 的型別可以包含三個不同的值︰`true`、`false` 和 `null`。 因此，`bool?` 類型不能用在有 `if`、`for` 或 `while` 的條件中。 例如，下列程式碼會導致編譯器錯誤。  
  
```csharp  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 這不被允許，因為不清楚 `null` 在條件內容中代表什麼。 若要在條件陳述式中使用 `bool?`，請先檢查其 <xref:System.Nullable%601.HasValue%2A> 屬性，確定其值不是 `null`，再將它轉換成 `bool`。 如需詳細資訊，請參閱 [bool](../../../csharp/language-reference/keywords/bool.md)。 如果您在值為 `null` 的 `bool?` 上執行轉換，則條件測試會擲回 <xref:System.InvalidOperationException>。 下例示範從 `bool?` 安全轉型至 `bool` 的一種方法：  
  
## <a name="example"></a>範例  
  
```csharp  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## <a name="see-also"></a>請參閱  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [常值關鍵字](../../../csharp/language-reference/keywords/literal-keywords.md)  
 [可為 Null 的型別](../../../csharp/programming-guide/nullable-types/index.md)  
 [??運算子](../../../csharp/language-reference/operators/null-coalescing-operator.md)
