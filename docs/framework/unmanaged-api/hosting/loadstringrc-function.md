---
title: LoadStringRC 函式
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 463bcf451574700d02f933d024ea5c24cedd259d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441811"
---
# <a name="loadstringrc-function"></a>LoadStringRC 函式
使用目前執行緒的預設文化特性，將 HRESULT 值轉譯成錯誤訊息。  
  
 此函式中已被取代[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
#### <a name="parameters"></a>參數  
 `iResourceID`  
 [in]HRESULT。  
  
 `szBuffer`  
 [out]包含成功完成時的錯誤訊息的緩衝區。  
  
 `iMax`  
 [in]錯誤訊息緩衝區的大小。  
  
 `bQuiet`  
 [in]略過。  
  
## <a name="return-value"></a>傳回值  
 這個方法會傳回標準的元件物件模型 (COM) 的錯誤代碼，除了下列的值定義了 WinError.h 中。  
  
|傳回碼|描述|  
|-----------------|-----------------|  
|S_OK|已成功完成命令。|  
|E_INVALIDARG|`szBuffer` 為 null 或`iMax`為零 (0)。|  
  
## <a name="remarks"></a>備註  
 如果方法沒有成功完成`szBuffer`包含空字串。  
  
## <a name="requirements"></a>需求  
 **平台：** 看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** MSCorEE.h  
  
 **程式庫：** MSCorEE.dll 和 Mscorwks.dll。 使用而不是 Mscorwks.dll 的 MSCorEE.dll，以確保您設為目標的.NET framework 正確版本。  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [LoadStringRCEx 函式](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 [已被取代的 CLR 裝載函式](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
