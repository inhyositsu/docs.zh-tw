---
title: PrintPreviewDialog 控制項概觀 (Windows Form)
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0946220017fb78775f045bb225d84ea95aecd06b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538333"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>PrintPreviewDialog 控制項概觀 (Windows Form)
Windows Form<xref:System.Windows.Forms.PrintPreviewDialog>控制項是預先設定的對話方塊，用來顯示如何[PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)列印時。 該應用程式中使用 windows 做為簡單的解決方案，而不是設定您自己的對話方塊。 這個控制項包含列印、放大、顯示一或多頁及關閉對話方塊等按鈕。  
  
## <a name="key-properties-and-methods"></a>索引鍵屬性和方法  
 控制項的索引鍵屬性是<xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>，它會設定要預覽的文件。 必須是文件<xref:System.Drawing.Printing.PrintDocument>物件。 為了顯示對話方塊，您必須呼叫其<xref:System.Windows.Forms.Form.ShowDialog%2A>方法。 消除鋸齒可以讓文字出現較平滑，但是它可以讓較慢; 顯示若要使用它，<xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A>屬性`true`。  
  
 某些屬性都是透過<xref:System.Windows.Forms.PrintPreviewControl>，<xref:System.Windows.Forms.PrintPreviewDialog>包含。 (您沒有加入此<xref:System.Windows.Forms.PrintPreviewControl>表單; 它會自動包含在<xref:System.Windows.Forms.PrintPreviewDialog>將對話方塊加入至表單。)可透過使用屬性的範例<xref:System.Windows.Forms.PrintPreviewControl>是<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>和<xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>屬性，判斷在控制項上顯示水平及垂直的頁數。 您可以存取<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>屬性做為`PrintPreviewDialog1.PrintPreviewControl.Columns`在 Visual Basic 中`printPreviewDialog1.PrintPreviewControl.Columns`Visual C# 中，或`printPreviewDialog1->PrintPreviewControl->Columns`中[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]。  
  
## <a name="printpreviewdialog-performance"></a>PrintPreviewDialog 效能

在下列情況中，<xref:System.Windows.Forms.PrintPreviewDialog>控制項非常緩慢初始化：

- 會使用網路印表機。
- 會修改此印表機，雙面列印設定，例如使用者喜好設定。
  
在.NET Framework 4.5.2 上執行的應用程式，您可以加入下列機碼\<appSettings > 您的組態檔，以改善效能的區段<xref:System.Windows.Forms.PrintPreviewDialog>控制初始設定：

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
如果`EnablePrintPreviewOptimization`機碼設為任何其他值，或如果索引鍵不存在，最佳化不會套用。

.NET Framework 4.6 或更新版本上執行的應用程式，您可以加入下列參數： 要[ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)中的項目[\<執行階段 >](../../configure-apps/file-schema/runtime/index.md)您的應用程式組態檔區段：

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
如果參數不存在，或是設定為任何其他值，不會套用最佳化。 

如果您使用<xref:System.Drawing.Printing.PrintDocument.QueryPageSettings>修改印表機設定、 效能事件<xref:System.Windows.Forms.PrintPreviewDialog>控制項不會改善，即使已設定最佳化組態參數。  

## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [PrintPreviewControl 控制項概觀](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [PrintPreviewDialog 控制項](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [對話方塊控制項和元件](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
