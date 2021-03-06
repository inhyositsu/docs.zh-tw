---
title: 如何：將自訂位置加入至檔案對話方塊
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 7a6ace385f7594a467785fbc677517c8a6e1ab53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525735"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>如何：將自訂位置加入至檔案對話方塊
[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] 上的預設開啟和儲存對話方塊，在 [最愛的連結] 對話方塊左側有一個區域。 這個區域稱為自訂位置。 <xref:System.Windows.Forms.OpenFileDialog>和<xref:System.Windows.Forms.SaveFileDialog>類別可讓您加入資料夾來<xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>集合。  
  
> [!NOTE]
>  為了讓自訂的位置，才會出現在<xref:System.Windows.Forms.OpenFileDialog>或<xref:System.Windows.Forms.SaveFileDialog>、<xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A>屬性必須設定為`true`（預設值）。  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>將自訂位置新增至檔案對話方塊  
  
-   新增已知資料夾 GUID 路徑，或<xref:System.Windows.Forms.FileDialogCustomPlace>物件<xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>對話框的集合。  
  
     下列程式碼範例示範如何新增路徑：  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Forms.FileDialog>  
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>  
 [檔案對話方塊自訂位置的已知資料夾 GUID](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)
