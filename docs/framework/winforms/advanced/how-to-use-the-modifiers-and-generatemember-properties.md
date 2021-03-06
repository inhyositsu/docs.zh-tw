---
title: 如何：使用修飾詞和 GenerateMember 屬性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 451c54bf6272b4fbff46b5298ba5b6a9290656e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523990"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a>如何：使用修飾詞和 GenerateMember 屬性
當您將元件放在 Windows Form 上時，提供兩個屬性，以在設計環境：`GenerateMember`和`Modifiers`。 `GenerateMember`屬性會指定當 Windows Form 設計工具產生元件的成員變數。 `Modifiers`屬性是指派給該成員變數的存取修飾詞。 如果值`GenerateMember`屬性是`false`，值`Modifiers`屬性沒有任何作用。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱 [在 Visual Studio 中自訂開發設定](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a>若要指定元件是否為表單的成員  
  
1.  在 Windows Form 設計工具中，開啟您的表單。  
  
2.  開啟**工具箱**，並在表單中，將三個<xref:System.Windows.Forms.Button>控制項。  
  
3.  設定`GenerateMember`和`Modifiers`每個屬性<xref:System.Windows.Forms.Button>根據下表的控制項。  
  
    |按鈕名稱|GenerateMember 值|修飾詞值|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|沒有變更|  
  
4.  建置方案。  
  
5.  在方案總管中，按一下 [顯示所有檔案] 按鈕。  
  
6.  開啟**Form1**  節點，然後在**程式碼編輯器**，開啟**Form1.Designer.vb**或**Form1.Designer.cs**檔案。 此檔案包含 Windows Form 設計工具所發出的程式碼。  
  
7.  尋找三個按鈕的宣告。 下列程式碼範例顯示所指定的差異`GenerateMember`和`Modifiers`屬性。  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  根據預設，Windows Form 設計工具會指派`private`(`Friend`在 Visual Basic 中) 類似容器控制項的修飾詞<xref:System.Windows.Forms.Panel>。 如果您的基底<xref:System.Windows.Forms.UserControl>或<xref:System.Windows.Forms.Form>有容器的控制項，就不會接受繼承的控制項和表單中的新子系。 解決方法是將基底容器控制項的修飾詞變更`protected`或`public`。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Forms.Button>  
 [Windows Forms 視覺繼承](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [逐步解說：示範視覺化繼承](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 [如何：繼承 Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)
