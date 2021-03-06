---
title: 如何：取得指標變數值 (C# 程式設計手冊)
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: c53026149837681235c6d1001707a25b9c8b40b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322948"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a>如何：取得指標變數值 (C# 程式設計手冊)
您可以使用指標間接運算子來取得指標所指向位置的變數。 運算式會採用下列格式，其中 `p` 是指標類型：  
  
```  
*p;  
```  
  
 您無法在非指標類型之任何類型的運算式上使用一元間接運算子。 此外，也無法將它套用至 [void](../../../csharp/language-reference/keywords/void.md) 指標。  
  
 當您將間接運算子套用至 [null](../../../csharp/language-reference/keywords/null.md) 指標時，結果會取決於實作。  
  
## <a name="example"></a>範例  
 在下列範例中，`char` 類型的變數會使用不同類型的指標來存取。 請注意，`theChar` 的位址會因執行而異，原因是配置給變數的實體位址可能會變更。  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
 **值為 theChar = Z**  
**位址為 theChar = 12F718**  
**值為 pChar = Z**   
**值為 pInt = 90**    
## <a name="see-also"></a>請參閱  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [指標運算式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [指標型別](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [型別](../../../csharp/language-reference/keywords/types.md)  
 [Unsafe.DangerousAPI](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed 陳述式](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
