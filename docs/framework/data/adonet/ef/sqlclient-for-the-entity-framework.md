---
title: 適用於 Entity Framework 的 SqlClient
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: 159cada00c523a1b417f5c6f4d0fac43a80f5db9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765083"
---
# <a name="sqlclient-for-the-entity-framework"></a>適用於 Entity Framework 的 SqlClient
本節將描述可讓 Entity Framework 透過 Microsoft SQL Server 運作的 .NET Framework Data Provider for SQL Server (SqlClient)。  
  
## <a name="provider-schema-attribute"></a>Provider 結構描述屬性  
 在存放結構定義語言 (SSDL) 中，`Provider` 是 `Schema` 項目的屬性。  
  
 若要使用 SqlClient，請將字串 "System.Data.SqlClient" 指派給 `Provider` 項目的 `Schema` 屬性。  
  
## <a name="providermanifesttoken-schema-attribute"></a>ProviderManifestToken 結構描述屬性  
 在 SSDL 中，`ProviderManifestToken` 是 `Schema` 項目的必要屬性。 這個語彙基元 (Token) 是用來載入提供者資訊清單以供離線案例使用。 如需有關`ProviderManifestToken`屬性，請參閱[結構描述項目 (SSDL)](http://msdn.microsoft.com/library/fec75ae4-7f16-4421-9265-9dac61509222)。  
  
 SqlClient 可當做資料提供者的不同版本的 SQL Server。 這些版本具有不同的功能。 例如，[!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] 不支援 `varchar(max)` 所導入的 `nvarchar(max)` 和 [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)] 型別。  
  
 SqlClient 會針對不同的 SQL Server 版本，產生並接受下列提供者資訊清單語彙基元。  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|-|-|-|  
|2000|2005|2008|  
  
> [!NOTE]
>  開始使用 Visual Studio 2010， [ADO.NET 實體資料模型工具](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)不支援 SQL Server 2000。  
  
## <a name="provider-namespace-name"></a>提供者命名空間名稱  
 所有提供者都必須指定命名空間。 這個屬性會告知 Entity Framework 此提供者對特定建構 (例如型別和函式) 所使用的前置詞。 SqlClient 提供者資訊清單的命名空間是 `SqlServer`。 如需命名空間的詳細資訊，請參閱[命名空間](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)。  
  
## <a name="types"></a>類型  
 適用於 Entity Framework 的 SqlClient 提供者會提供概念模型類型和 SQL Server 型別之間的對應資訊。 如需詳細資訊，請參閱[適用於 Entity Framework 的 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)。  
  
## <a name="functions"></a>函式  
 Entity Framework 的 SqlClient 提供者會定義提供者所支援的函式清單。 如需支援的函式的清單，請參閱[適用於 Entity Framework 函式的 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)。  
  
## <a name="in-this-section"></a>本節內容  
 [適用於 Entity Framework 的 SqlClient 函式](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [適用於 Entity Framework 的 SqlClient 類型](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [適用於 Entity Framework 的 SqlClient 已知問題](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>另請參閱  
 [Entity SQL 語言](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [語言參考](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)  
 [Entity Framework 的 SqlClient 提供者中的已知問題](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
