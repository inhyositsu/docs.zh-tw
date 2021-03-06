---
title: 如何：旋轉、反射和傾斜影像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 7f580b4d3016f1ecedc33302fe57caeec5698aeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523451"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>如何：旋轉、反射和傾斜影像
您可以旋轉、 反射和傾斜影像藉由指定目的端座標點的原始影像的左上角、 右上角和左下角。 這三個目的點決定仿射轉換平行四邊形對應原始矩形的映像。  
  
## <a name="example"></a>範例  
 例如，假設在原始圖像是在左上角的矩形 （0，0），在右上角 （100，0），以及在左下角 （0，50）。 現在假設您將這些對應三個點至目的地點，如下所示。  
  
|原始的點|目的地點|  
|--------------------|-----------------------|  
|左上方 （0，0）|(200, 20)|  
|右上方 （100，0）|(110, 100)|  
|左下方 （0，50）|(250, 30)|  
  
 下圖顯示原始的映像和對應的平行四邊形的映像。 原始的映像具有已有所偏差、 反映、 旋轉和轉譯。 原始的映像的上邊緣 x 軸會對應至逐步執行一行 （200，20） 和 110 (100）。 原始的映像的左邊緣沿著 y 軸會對應至逐步執行一行 （200，20） 和 250 (30）。  
  
 ![等量分散](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 下圖顯示類似的轉換套用至相片的映像。  
  
 ![轉換的 Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 下圖顯示類似的轉換套用到中繼檔。  
  
 ![轉換中繼檔](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 下列範例會產生第一個圖例中所顯示的影像。  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 上述範例設計用於搭配 Windows Form，且其需要<xref:System.Windows.Forms.PaintEventArgs> `e`，這是參數的<xref:System.Windows.Forms.Control.Paint>事件處理常式。 請務必取代`Stripes.bmp`與適用於您的系統映像的路徑。  
  
## <a name="see-also"></a>另請參閱  
 [使用影像、點陣圖、圖示和中繼檔](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
