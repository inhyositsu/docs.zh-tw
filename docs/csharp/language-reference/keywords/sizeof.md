---
title: sizeof (C# 參考)
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 83038255160ec778c71120566cf8f99092761add
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270574"
---
# <a name="sizeof-c-reference"></a>sizeof (C# 參考)
用來取得 Unmanaged 類型的大小 (以位元組為單位)。 Unmanaged 類型包含下表所列的內建類型，也包含下列項目：  
  
-   列舉型別  
  
-   指標類型  
  
-   未包含本身為參考類型的任何欄位或屬性的使用者定義結構  
  
 下列範例示範如何擷取 `int` 的大小：  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a>備註  
 從 C# 2.0 版開始，將 `sizeof` 套用至內建類型不再需要使用 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 模式。  
  
 無法多載 `sizeof` 運算子。 `sizeof` 運算子所傳回值的類型為 `int`。 下表所顯示的常數值會替代將特定內建類型當作運算元的 `sizeof` 運算式。  
  
|運算式|常數值|  
|----------------|--------------------|  
|`sizeof(sbyte)`|1|  
|`sizeof(byte)`|1|  
|`sizeof(short)`|2|  
|`sizeof(ushort)`|2|  
|`sizeof(int)`|4|  
|`sizeof(uint)`|4|  
|`sizeof(long)`|8|  
|`sizeof(ulong)`|8|  
|`sizeof(char)`|2 (Unicode)|  
|`sizeof(float)`|4|  
|`sizeof(double)`|8|  
|`sizeof(decimal)`|16|  
|`sizeof(bool)`|1|  
  
 對於所有其他類型 (包含結構)，`sizeof` 運算子都只能用於 unsafe 程式碼區塊。 雖然您可以使用 <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 方法，但是這種方法所傳回的值不一定與 `sizeof` 所傳回的值相同。 封送處理類型之後，<xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 會傳回大小，而 `sizeof` 會傳回 Common Language Runtime 所配置的大小，包括任何填補字元。  
  
## <a name="example"></a>範例  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a>C# 語言規格  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>請參閱  
 [C# 參考](../../../csharp/language-reference/index.md)  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [C# 關鍵字](../../../csharp/language-reference/keywords/index.md)  
 [運算子關鍵字](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [enum](../../../csharp/language-reference/keywords/enum.md)  
 [Unsafe 程式碼和指標](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [結構](../../../csharp/programming-guide/classes-and-structs/structs.md)  
 [常數](../../../csharp/programming-guide/classes-and-structs/constants.md)
