---
title: "IMetaDataEmit::DefineSecurityAttributeSet 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineSecurityAttributeSet
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 79d5bb7240305d06d916e969765606ddc2ddf9b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="ce306-102">IMetaDataEmit::DefineSecurityAttributeSet 方法</span><span class="sxs-lookup"><span data-stu-id="ce306-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="ce306-103">建立一組安全性權限，將附加到指定的語彙基元所參考的物件。</span><span class="sxs-lookup"><span data-stu-id="ce306-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce306-104">語法</span><span class="sxs-lookup"><span data-stu-id="ce306-104">Syntax</span></span>  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce306-105">參數</span><span class="sxs-lookup"><span data-stu-id="ce306-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="ce306-106">[in]要附加的安全性資訊的語彙基元。</span><span class="sxs-lookup"><span data-stu-id="ce306-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="ce306-107">[in]陣列`COR_SECATTR`結構。</span><span class="sxs-lookup"><span data-stu-id="ce306-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="ce306-108">[in]中的項目數`rSecAttrs`。</span><span class="sxs-lookup"><span data-stu-id="ce306-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="ce306-109">[out]如果方法失敗，會指定在索引`rSecAttrs`造成問題的項目。</span><span class="sxs-lookup"><span data-stu-id="ce306-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce306-110">需求</span><span class="sxs-lookup"><span data-stu-id="ce306-110">Requirements</span></span>  
 <span data-ttu-id="ce306-111">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce306-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce306-112">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ce306-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce306-113">**程式庫：**做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="ce306-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce306-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce306-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce306-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ce306-115">See Also</span></span>  
 [<span data-ttu-id="ce306-116">IMetaDataEmit 介面</span><span class="sxs-lookup"><span data-stu-id="ce306-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="ce306-117">IMetaDataEmit2 介面</span><span class="sxs-lookup"><span data-stu-id="ce306-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)