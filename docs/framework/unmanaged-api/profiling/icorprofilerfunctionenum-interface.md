---
title: ICorProfilerFunctionEnum 介面
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1e55c7e6deff3928e69861541aa1a924dac263f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455058"
---
# <a name="icorprofilerfunctionenum-interface"></a>ICorProfilerFunctionEnum 介面
提供方法以循序逐一查看 Common Language Runtime 中的函式集合。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Clone 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|取得這個 `ICorProfilerFunctionEnum` 介面複本的介面指標。|  
|[GetCount 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|取得應用程式已載入的或分析工具強制載入的函式數目。|  
|[Next 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|於循序函式集合中，從序列中列舉值的目前位置開始，取得指定連續函式數目。|  
|[Reset 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|將列舉值的資料指標移至序列的開始位置。|  
|[Skip 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|將列舉值的資料指標從其目前位置前移，以略過指定數目的項目。|  
  
## <a name="remarks"></a>備註  
 `ICorProfilerFunctionEnum` 介面是列舉值。 它可讓陣列的接收端以適合接收端的速率，從傳送端提取項目。 換句話說，接收端能夠明確控制陣列項目的流程，因此可避免與傳遞大型陣列做為方法參數相關的問題發生。  
  
 `ICorProfilerFunctionEnum` 列舉早已 JIT 編譯的函式，但此函式不包含從 Ngen.exe 產生的原生影像載入之函式。  
  
## <a name="requirements"></a>需求  
 **平台：** 看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorProf.idl、CorProf.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [ICorProfilerInfo 介面](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [分析介面](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [EnumJITedFunctions 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
