---
title: "字串插值 (Visual Basic)"
ms.date: 10/31/2017
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f865d5a7167847bf869d70a39570413dac271a2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-visual-basic-reference"></a>字串插值 （Visual Basic 參考）

可用來建構字串。  字串插值類似包含「插入運算式」的範本字串。  字串插值會傳回一個字串，以將內含的插入運算式取代為運算式的字串表示。 Visual Basic 14 和更新版本中使用這項功能。

字串插值的引數比[複合格式字串](../../../../standard/base-types/composite-formatting.md#composite-format-string)更容易了解。  例如，字串插值  
  
```vb  
Console.WriteLine($"Name = {name}, hours = {hours:hh}")
```  
包含兩個插入運算式 '{name}' 和 '{hours:hh}'。 對等的複合格式字串為：

```vb
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

字串插值的結構為：  
  
```vb  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

其中： 

- *field-width* 是帶正負號的整數，表示欄位中的字元數。 如果是正數，則欄位會靠右對齊；如果是負數，則會靠左對齊。 

- *format-string* 是一個格式字串，適用於將格式化的物件類型。 例如，對於<xref:System.DateTime>值，它可能是[標準日期和時間格式字串](~/docs/standard/base-types/standard-date-and-time-format-strings.md)例如"D"或"d"。

> [!IMPORTANT]
> 您不能有任何空白字元之間`$`和`"`開頭的字串。 這樣做會讓編譯器錯誤。

 您可以在使用字串常值的任何位置使用字串插值。  每次執行含有字串插值的程式碼時，都會評估字串插值。 這可讓您分開定義和評估字串插值。  
  
 若要在字串插值中包含大括弧 ("{" 或 "}")，請使用雙大括弧 "{{" 或 "}}"。  如需詳細資訊，請參閱＜隱含轉換＞一節。  

當字串插值包含在字串插值中具有特殊意義的其他字元時 (例如引號 (")、冒號 (:) 或逗號 (,))，如果這些字元出現在常值文字中，則必須將它逸出；如果這些字元是包含在插入運算式中的語言項目，則必須加入以括號分隔的運算式。 下列範例會將引號逸出，以在結果字串中包含這些引號，而且會使用括號來分隔運算式 `(age == 1 ? "" : "s")`，以防止將冒號解譯為格式字串的開頭。

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]  

## <a name="implicit-conversions"></a>隱含轉換  

有三個來自字串插值的隱含型別轉換：  

1. 將字串插值轉換成 <xref:System.String>。 下列範例會傳回一個字串，其字串插值運算式已取代為運算式的字串表示。 例如: 

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]  

   這是字串解譯的最終結果。 所有出現的雙大括弧 ("{{" 和 "}}") 都會轉換成單一大括弧。 

2. 將字串插值轉換成 <xref:System.IFormattable> 變數，可讓您從單一 <xref:System.IFormattable> 執行個體建立多個具有特定文化特性內容的結果字串。 若要加入個別文化特性的正確數值和日期格式等項目時，這樣做會很有用。  在您明確或隱含呼叫 <xref:System.Object.ToString> 方法以格式化字串之前，所有出現的雙大括弧 ("{{" 和 "}}") 會保持為雙大括弧。  所有包含插值運算式會轉換成 {0}、\{1\} 等。  

   下列範例使用反映來顯示成員，以及從字串插值建立之 <xref:System.IFormattable> 變數的欄位和屬性值。 它也會傳遞<xref:System.IFormattable>變數設為<xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>方法。

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]  

   請注意，只能使用反映來檢查字串插值。 如果將它傳遞為字串，例如格式化方法<xref:System.Console.WriteLine(System.String)>、 它的格式項目都已解決，而且傳回的結果字串。 

3. 轉換至字串插值的<xref:System.FormattableString>代表複合格式字串的變數。 檢查複合格式字串及其如何轉譯為結果字串有助於在建立查詢時，防止插入式攻擊。 A<xref:System.FormattableString>還包括：

      - A<xref:System.FormattableString.ToString>產生的結果字串的多載<xref:System.Globalization.CultureInfo.CurrentCulture>。
      
      - A<xref:System.FormattableString.Invariant%2A>方法所產生的字串<xref:System.Globalization.CultureInfo.InvariantCulture>。
      
      - A<xref:System.FormattableString.ToString(System.IFormatProvider)>產生的結果字串會指定文化特性的方法。 
  
    所有出現的雙大括弧 ("{{"和"}}") 保持為雙大括弧，直到您格式化為止。  所有包含插值運算式會轉換成 {0}、\{1\} 等。  

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]  

## <a name="see-also"></a>另請參閱  
f<xref:System.IFormattable?displayProperty=nameWithType>   
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [Visual Basic 語言參考](index.md)  
 