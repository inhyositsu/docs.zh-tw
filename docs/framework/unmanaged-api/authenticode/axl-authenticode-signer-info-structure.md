---
title: AXL_AUTHENTICODE_SIGNER_INFO 結構
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd07707b5a80ec0980fc50b27caddf0a24398fd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400441"
---
# <a name="axlauthenticodesignerinfo-structure"></a>AXL_AUTHENTICODE_SIGNER_INFO 結構
定義 Authenticode 簽署人資訊。  
  
## <a name="syntax"></a>語法  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a>成員  
  
|成員|描述|  
|------------|-----------------|  
|`cbSize`|此結構的大小。|  
|`dwError`|錯誤碼。|  
|`algHash`|雜湊演算法。|  
|`pwszHash`|雜湊。|  
|`pwszDescription`|描述。|  
|`pwszDescriptionUrl`|描述的 URL。|  
|`pChainContext`|簽署人的鏈結內容。 請參閱[CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx)結構。|  
  
## <a name="see-also"></a>另請參閱  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
