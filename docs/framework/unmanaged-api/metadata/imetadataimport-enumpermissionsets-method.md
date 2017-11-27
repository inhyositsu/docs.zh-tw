---
title: "IMetaDataImport::EnumPermissionSets 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumPermissionSets
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 031e97ad1b8180a64bc789ae52e141932d600782
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="ea69f-102">IMetaDataImport::EnumPermissionSets 方法</span><span class="sxs-lookup"><span data-stu-id="ea69f-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="ea69f-103">列舉指定中繼資料範圍內的物件權限。</span><span class="sxs-lookup"><span data-stu-id="ea69f-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea69f-104">語法</span><span class="sxs-lookup"><span data-stu-id="ea69f-104">Syntax</span></span>  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea69f-105">參數</span><span class="sxs-lookup"><span data-stu-id="ea69f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ea69f-106">[in、 out]列舉值的指標。</span><span class="sxs-lookup"><span data-stu-id="ea69f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ea69f-107">這必須是 NULL 的第一個呼叫此方法。</span><span class="sxs-lookup"><span data-stu-id="ea69f-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="ea69f-108">[in]搜尋或為 NULL，搜尋可能的最大範圍的範圍限制中繼資料語彙基元。</span><span class="sxs-lookup"><span data-stu-id="ea69f-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="ea69f-109">[in]加上旗標代表<xref:System.Security.Permissions.SecurityAction>值併入`rPermission`，或是零則表示傳回所有動作。</span><span class="sxs-lookup"><span data-stu-id="ea69f-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="ea69f-110">[out]用來儲存權限 token 的陣列。</span><span class="sxs-lookup"><span data-stu-id="ea69f-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ea69f-111">[in] `rPermission` 陣列的大小上限。</span><span class="sxs-lookup"><span data-stu-id="ea69f-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ea69f-112">[out]權限語彙基元中傳回的數目`rPermission`。</span><span class="sxs-lookup"><span data-stu-id="ea69f-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea69f-113">傳回值</span><span class="sxs-lookup"><span data-stu-id="ea69f-113">Return Value</span></span>  
  
|<span data-ttu-id="ea69f-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea69f-114">HRESULT</span></span>|<span data-ttu-id="ea69f-115">說明</span><span class="sxs-lookup"><span data-stu-id="ea69f-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ea69f-116">`EnumPermissionSets`已成功傳回。</span><span class="sxs-lookup"><span data-stu-id="ea69f-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ea69f-117">沒有列舉語彙基元。</span><span class="sxs-lookup"><span data-stu-id="ea69f-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="ea69f-118">在此情況下，`pcTokens`為零。</span><span class="sxs-lookup"><span data-stu-id="ea69f-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea69f-119">需求</span><span class="sxs-lookup"><span data-stu-id="ea69f-119">Requirements</span></span>  
 <span data-ttu-id="ea69f-120">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea69f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea69f-121">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ea69f-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea69f-122">**程式庫：**包含做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="ea69f-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea69f-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea69f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea69f-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ea69f-124">See Also</span></span>  
 [<span data-ttu-id="ea69f-125">IMetaDataImport 介面</span><span class="sxs-lookup"><span data-stu-id="ea69f-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ea69f-126">IMetaDataImport2 介面</span><span class="sxs-lookup"><span data-stu-id="ea69f-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)