---
title: '開始使用 Azure 資料表儲存體使用 F #'
description: 將結構化的資料儲存在雲端中使用 Azure 資料表儲存體或 Azure Cosmos DB。
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: ac81bc88db1436aa4d5f576da61a90839df04b99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575390"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a>開始使用 Azure 資料表儲存體和 Azure Cosmos DB 資料表 API 使用 F # # 

Azure 資料表儲存體是結構化的 NoSQL 資料存放在雲端服務。 資料表儲存體是 schemaless 設計的索引鍵/屬性存放區。 因為資料表儲存體是 schemaless，很容易就能為您的應用程式 evolve 的需求調整您的資料。 資料的存取權非常快速且符合成本效益的所有種類的應用程式。 資料表儲存體通常是遠低於成本中類似資料磁碟區的傳統 SQL。

您可以使用資料表儲存體來儲存彈性的資料集，例如 web 應用程式、 通訊錄，裝置資訊和任何其他類型的服務所需的中繼資料的使用者資料。 您可以將任意數目的實體儲存在資料表中，而且儲存體帳戶包含任何數量的資料表，儲存體帳戶的容量上限為止。

Azure Cosmos DB 會提供資料表 API 所撰寫，Azure 資料表儲存體，以及這類要求高階功能的應用程式：

- 周全的全域通訊。
- 專用的輸送量全球。
- 個 99th 百分位數毫秒延遲。
- 保證高可用性。
- 自動的次要索引。

Azure 資料表儲存體所撰寫的應用程式可以利用資料表 API 沒有變更程式碼移轉至 Azure Cosmos 資料庫，並利用高階功能。 資料表 API 有可用的用戶端 Sdk for.NET、 Java、 Python 和 Node.js。

如需詳細資訊，請參閱[Azure Cosmos DB 資料表 API 簡介](https://docs.microsoft.com/azure/cosmos-db/table-introduction)。

## <a name="about-this-tutorial"></a>關於本教學課程

本教學課程會示範如何撰寫 F # 程式碼來執行一些常見的工作，使用 Azure 資料表儲存體或 Azure Cosmos DB 資料表 API，包括建立和刪除資料表並插入、 更新、 刪除和查詢資料表的資料。

## <a name="prerequisites"></a>必要條件

若要使用本指南，您必須先[建立 Azure 儲存體帳戶](/azure/storage/storage-create-storage-account)或[Azure Cosmos DB 帳戶](https://azure.microsoft.com/try/cosmosdb/)。


## <a name="create-an-f-script-and-start-f-interactive"></a>建立 F # 指令碼，並開始 F # Interactive

這篇文章中的範例可以用於 F # 應用程式或 F # 指令碼。 若要建立 F # 指令碼，建立檔案之`.fsx`擴充功能，例如`tables.fsx`，F # 開發環境中。

接下來，使用[封裝管理員](package-management.md)例如[Paket](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)安裝`WindowsAzure.Storage`封裝和參考`WindowsAzure.Storage.dll`指令碼使用`#r`指示詞。 請勿重新`Microsoft.WindowsAzure.ConfigurationManager`才能取得 Microsoft.Azure 命名空間。

### <a name="add-namespace-declarations"></a>加入命名空間宣告

加入下列`open`上方的陳述式`tables.fsx`檔案：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a>取得您的 Azure 儲存體連接字串

如果您正在連接到 Azure 儲存體資料表服務，您必須連接字串在此教學課程。 您可以從 Azure 入口網站複製您的連接字串。 如需連接字串的詳細資訊，請參閱[設定儲存體連接字串](/azure/storage/storage-configure-connection-string)。

### <a name="get-your-azure-cosmos-db-connection-string"></a>取得您的 Azure Cosmos DB 連接字串

如果您正在連接到 Azure Cosmos DB，您必須連接字串在此教學課程。 您可以從 Azure 入口網站複製您的連接字串。 在 Azure 入口網站，Cosmos DB 帳戶中，移至**設定** > **連接字串**，然後按一下**複製** 按鈕複製主要的連線字串。 

教學課程中，輸入您的指令碼，如下列範例中的連接字串：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

不過，這是**不建議**用於真實的專案。 儲存體帳戶金鑰是類似於儲存體帳戶的根密碼。 一律為保護您的儲存體帳戶金鑰，請小心。 避免將其散發給其他使用者，硬式編碼，或將它儲存在其他人可以存取純文字檔案。 您可以重新產生您使用 Azure 入口網站，如果您認為可能已受到危害的金鑰。

用於真實的應用程式，以維護您的儲存體連接字串的最佳方式是在組態檔中。 若要從組態檔擷取連接字串，您可以：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

使用 Azure 組態管理員是選擇性的。 您也可以使用例如.NET Framework API`ConfigurationManager`型別。

### <a name="parse-the-connection-string"></a>剖析連接字串

若要剖析的連接字串，使用：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

這會傳回`CloudStorageAccount`。

### <a name="create-the-table-service-client"></a>建立表格服務用戶端

`CloudTableClient`類別可讓您擷取資料表和資料表儲存體中的實體。 以下是如何建立服務用戶端：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

現在您已準備好開始撰寫程式碼讀取資料，並將資料寫入資料表儲存體。

### <a name="create-a-table"></a>建立資料表

這個範例示範如何建立資料表，如果不存在：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a>將實體加入至資料表

實體必須要有型別繼承自`TableEntity`。 您可以擴充`TableEntity`任何方式，但您的型別*必須*具有無參數建構函式。 只有屬性同時具有`get`和`set`會儲存在 Azure 資料表。

實體的資料分割和資料列索引鍵唯一識別資料表中的實體。 具有相同的資料分割索引鍵的實體可以進行查詢速度比的不同資料分割索引鍵，但使用不同的資料分割索引鍵可讓平行作業的更佳的延展性。

以下是範例`Customer`使用`lastName`做為資料分割索引鍵和`firstName`做為資料列索引鍵。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

現在，加入`Customer`至資料表。 若要這樣做，請建立`TableOperation`資料表上執行。 在此情況下，您建立`Insert`作業。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a>插入實體批次

您可以將實體批次插入資料表中使用單一寫入作業。 批次作業可讓您將作業結合成單一的執行，但具有一些限制：

- 您可以執行更新、 刪除和插入相同的批次作業中。
- 批次作業可以包含多達 100 個項目。
- 批次作業中的所有實體必須都有相同的資料分割索引鍵。
- 雖然也可以在批次作業中執行查詢，但是它必須是批次中唯一的作業。

以下是一些結合成一個批次作業的兩個插入的程式碼：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a>擷取資料分割中的所有實體

若要查詢的資料表資料分割中的所有實體，請使用`TableQuery`物件。 在這裡，您篩選實體"Smith"所在的資料分割索引鍵。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

您現在會列印結果：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a>擷取某個範圍的資料分割中的實體

如果您不想要查詢資料分割中的所有實體，您可以指定範圍，藉由結合資料分割索引鍵篩選，資料列索引鍵的篩選。 在這裡，您使用兩個篩選器"Smith"的分割區中取得所有實體資料列索引鍵 （第一個名稱） 開始的位置以字母"M"中字母之前。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

您現在會列印結果：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a>擷取單一實體

您可以撰寫查詢以擷取單一的特定實體。 在此，您可以使用`TableOperation`來指定客戶"Ben Smith"。 而不是集合，您會回到`Customer`。 在查詢中指定資料分割索引鍵和資料列索引鍵是最快的方法來擷取與表格服務的單一實體。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

您現在會列印結果：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a>取代實體

若要更新實體，擷取與表格服務、 修改實體物件，以及將變更儲存至表格服務會使用`Replace`作業。 除非變更伺服器上的實體自擷取後，在此情況下作業失敗，這會導致在伺服器上，完全取代實體。 此失敗是為了防止您的應用程式不小心覆寫從其他來源的變更。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a>插入或取代實體

有時候，您不知道實體是否存在於資料表中。 而且，若是如此，不再需要儲存在它的目前值。 您可以使用`InsertOrReplace`建立實體，或取代它，如果存在的話，不論其狀態。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a>查詢實體屬性的子集

資料表查詢可以擷取只需要幾個屬性，而不是所有的這些實體。 這項技巧，呼叫投影，可以改善查詢效能，特別是大型的實體。 您在這裡，傳回僅電子郵件地址使用`DynamicTableEntity`和`EntityResolver`。 請注意，投影不支援在本機儲存體模擬器，以便在表格服務上使用的帳戶時，才執行此程式碼。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a>以非同步方式擷取頁面中的實體

如果您正在閱讀大量實體，而且您想要擷取，而非等待它們全部傳回，您可以使用分割的查詢時進行處理。 在這裡，您傳回的結果頁面中使用的非同步工作流程，因此正在等待將大量要傳回的結果時，不會封鎖執行。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

您現在執行這項計算以同步方式：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a>刪除實體

您可以在擷取之後，刪除實體。 與更新實體，此作業失敗之後，如果實體已變更您擷取它。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a>刪除資料表

您可以從儲存體帳戶刪除資料表。 已刪除的資料表將無法在重新建立此一段時間後刪除。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a>後續步驟

既然您已學到的資料表儲存體的基本概念，請遵循下列連結，以深入了解更複雜的儲存體工作以及 Azure Cosmos DB 資料表 API。

- [Azure Cosmos DB 資料表 API 簡介](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [儲存體用戶端程式庫.NET 參考](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [Azure 儲存體型別提供者](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [Azure 儲存體團隊部落格](http://blogs.msdn.com/b/windowsazurestorage/)
- [設定連接字串](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [在.NET 的 Azure 資料表儲存體使用者入門](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
