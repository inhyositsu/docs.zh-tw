---
title: "ICLRTask::GetMemStats 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.GetMemStats
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11537989765d721830c33cb137d1814327b02e14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="a9923-102">ICLRTask::GetMemStats 方法</span><span class="sxs-lookup"><span data-stu-id="a9923-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="a9923-103">取得與工作相關的統計的記憶體使用量資訊的目前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)執行個體所表示。</span><span class="sxs-lookup"><span data-stu-id="a9923-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9923-104">語法</span><span class="sxs-lookup"><span data-stu-id="a9923-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9923-105">參數</span><span class="sxs-lookup"><span data-stu-id="a9923-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="a9923-106">[out]指標[COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)執行個體，其中包含有關的工作，包括配置的位元組數目的記憶體使用量詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a9923-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9923-107">傳回值</span><span class="sxs-lookup"><span data-stu-id="a9923-107">Return Value</span></span>  
  
|<span data-ttu-id="a9923-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9923-108">HRESULT</span></span>|<span data-ttu-id="a9923-109">描述</span><span class="sxs-lookup"><span data-stu-id="a9923-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9923-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9923-110">S_OK</span></span>|<span data-ttu-id="a9923-111">`GetMemStats`已成功傳回。</span><span class="sxs-lookup"><span data-stu-id="a9923-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="a9923-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9923-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a9923-113">Common language runtime (CLR) 尚未載入到處理程序，或 CLR 正在中它無法執行 managed 程式碼，或成功地處理呼叫的狀態。</span><span class="sxs-lookup"><span data-stu-id="a9923-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a9923-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a9923-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a9923-115">呼叫已逾時。</span><span class="sxs-lookup"><span data-stu-id="a9923-115">The call timed out.</span></span>|  
|<span data-ttu-id="a9923-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a9923-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a9923-117">呼叫端未擁有鎖定。</span><span class="sxs-lookup"><span data-stu-id="a9923-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a9923-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a9923-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a9923-119">事件已取消時封鎖的執行緒或 fiber 等候它。</span><span class="sxs-lookup"><span data-stu-id="a9923-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a9923-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a9923-120">E_FAIL</span></span>|<span data-ttu-id="a9923-121">發生未知的嚴重失敗。</span><span class="sxs-lookup"><span data-stu-id="a9923-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a9923-122">方法會傳回 E_FAIL CLR 已不再可用的處理序內。</span><span class="sxs-lookup"><span data-stu-id="a9923-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a9923-123">裝載方法的後續呼叫會傳回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a9923-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9923-124">需求</span><span class="sxs-lookup"><span data-stu-id="a9923-124">Requirements</span></span>  
 <span data-ttu-id="a9923-125">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9923-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9923-126">**標頭：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a9923-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9923-127">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="a9923-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9923-128">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9923-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9923-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a9923-129">See Also</span></span>  
 [<span data-ttu-id="a9923-130">ICLRTask 介面</span><span class="sxs-lookup"><span data-stu-id="a9923-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="a9923-131">ICLRTaskManager 介面</span><span class="sxs-lookup"><span data-stu-id="a9923-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="a9923-132">IHostTask 介面</span><span class="sxs-lookup"><span data-stu-id="a9923-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="a9923-133">IHostTaskManager 介面</span><span class="sxs-lookup"><span data-stu-id="a9923-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)