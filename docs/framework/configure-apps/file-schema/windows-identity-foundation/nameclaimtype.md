---
title: '&lt;nameClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e403667f16e316004f766b8476e20eca9bd1c988
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755093"
---
# <a name="ltnameclaimtypegt"></a>&lt;nameClaimType&gt;
設定指定的宣告型別<xref:System.Security.Principal.IIdentity.Name%2A>屬性。 宣告類型用來搜尋<xref:System.Security.Claims.Claim>集合中的<xref:System.Security.Claims.ClaimsIdentity>所傳回的物件<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>此語彙基元處理常式的方法。 比對的宣告值會設定為名稱的<xref:System.Security.Principal.IIdentity>產生從這個語彙基元處理常式。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<add>  
\<samlSecurityTokenRequirement >  
\<nameClaimType >  
  
## <a name="syntax"></a>語法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|value|字串，指定代表要用於宣告的宣告類型 URI<xref:System.Security.Principal.IIdentity.Name%2A>屬性。 必要。|  
  
### <a name="child-elements"></a>子項目  
 無  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|提供組態<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>類別<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>類別或衍生的類別中的這些類別的其中一個。|  
  
## <a name="remarks"></a>備註  
 `<nameClaimType>`項目集合<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>屬性時<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>從設定初始化物件。  
  
## <a name="example"></a>範例  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
