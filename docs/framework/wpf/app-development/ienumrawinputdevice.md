---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 2030ad0ac00419280b45555ff11495c74e4274e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547781"
---
# <a name="ienumrawinputdevice"></a>IEnumRAWINPUTDEVICE
此介面列舉未經處理的輸入裝置，並且只供 PresentationHost.exe 使用。  
  
> [!NOTE]
>  僅限在本機用戶端電腦上使用及支援此 API  
  
## <a name="members"></a>成員  
  
|成員|描述|  
|------------|-----------------|  
|[IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)|在列舉程式的清單中列舉下一個 `celt` 項目 (也就是 RAWINPUTDEVICE 結構)，連帶 `rgelt` 中列舉項目的實際數目，將這些項目傳回在 `pceltFetched` 中。|  
|[IEnumRAWINPUTDEVIC:Skip](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-skip.md)|略過下一個列舉值會指示`celt`列舉中的項目，因此下次呼叫[IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)不會傳回這些項目。|  
|[IEnumRAWINPUTDEVIC:Reset](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-reset.md)|將列舉序列重設為開頭。|  
|[IEnumRAWINPUTDEVIC:Clone](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-clone.md)|使用與目前列舉程式相同的狀態，來建立另一個未經處理的輸入裝置列舉程式，以反覆查看相同的清單。|  
  
## <a name="see-also"></a>另請參閱  
 [關於原始輸入](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/aboutrawinput.asp)
