---
title: ICorDebugValue3 介面
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d70a6f5c1df771c514f5f91770b4c53c55fec364
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420656"
---
# <a name="icordebugvalue3-interface"></a>ICorDebugValue3 介面
擴充的 」 ICorDebugValue"和"ICorDebugValue2 」 介面以支援大於 2 GB 的陣列。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetSize64 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|取得以位元組為單位，這個大小，`ICorDebugValue3`物件。|  
  
## <a name="remarks"></a>備註  
 [Icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)方法會傳回物件大小，範圍從 0 到 2,147,483,647 個位元組。 在[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，陣列大小可以超過 2 GB。 `ICorDebugValue3`介面可讓您判斷這些陣列的大小。  
  
## <a name="requirements"></a>需求  
 **平台：** 看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorDebug.idl、 CorDebug.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
    
    
 [偵錯介面](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [偵錯](../../../../docs/framework/unmanaged-api/debugging/index.md)
