# [LINQ to SQL](index.md)
## [快速入門](getting-started.md)
### [您可以執行 Linq to SQL](what-you-can-do-with-linq-to-sql.md)
### [使用 LINQ to SQL 的一般步驟](typical-steps-for-using-linq-to-sql.md)
### [下載範例資料庫](downloading-sample-databases.md)
### [依逐步解說學習](learning-by-walkthroughs.md)
#### [逐步解說： 簡單的物件模型和查詢 (Visual Basic)](walkthrough-simple-object-model-and-query-visual-basic.md)
#### [逐步解說： 跨關聯性 (Visual Basic) 查詢](walkthrough-querying-across-relationships-visual-basic.md)
#### [逐步解說： 操作資料 (Visual Basic)](walkthrough-manipulating-data-visual-basic.md)
#### [逐步解說： 僅使用預存程序 (Visual Basic)](walkthrough-using-only-stored-procedures-visual-basic.md)
#### [逐步解說： 簡單的物件模型和查詢 (C#)](walkthrough-simple-object-model-and-query-csharp.md)
#### [逐步解說： 跨關聯性 (C#) 查詢](walkthrough-querying-across-relationships-csharp.md)
#### [逐步解說： 操作資料 (C#)](walkthrough-manipulating-data-csharp.md)
#### [逐步解說： 僅使用預存程序 (C#)](walkthrough-using-only-stored-procedures-csharp.md)
## [程式設計手冊](programming-guide.md)
### [建立物件模型](creating-the-object-model.md)
#### [如何： 在 Visual Basic 或 C# 中產生物件模型](how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
#### [如何： 產生物件模型做為外部檔案](how-to-generate-the-object-model-as-an-external-file.md)
#### [如何： 藉由修改 DBML 檔案產生自訂的程式碼](how-to-generate-customized-code-by-modifying-a-dbml-file.md)
#### [如何： 驗證 DBML 和外部對應檔案](how-to-validate-dbml-and-external-mapping-files.md)
#### [如何： 讓實體可序列化](how-to-make-entities-serializable.md)
#### [如何： 使用程式碼編輯器自訂實體類別](how-to-customize-entity-classes-by-using-the-code-editor.md)
##### [如何： 指定資料庫名稱](how-to-specify-database-names.md)
##### [如何： 資料表表示為類別](how-to-represent-tables-as-classes.md)
##### [如何： 表示為類別成員的資料行](how-to-represent-columns-as-class-members.md)
##### [如何： 表示主索引鍵](how-to-represent-primary-keys.md)
##### [如何： 對應資料庫關聯性](how-to-map-database-relationships.md)
##### [如何： 表示為資料庫產生資料行](how-to-represent-columns-as-database-generated.md)
##### [如何： 資料行表示為時間戳記或版本資料行](how-to-represent-columns-as-timestamp-or-version-columns.md)
##### [如何： 指定資料庫資料類型](how-to-specify-database-data-types.md)
##### [如何： 表示計算資料行](how-to-represent-computed-columns.md)
##### [如何： 指定私用儲存欄位](how-to-specify-private-storage-fields.md)
##### [如何： 為允許 Null 值表示資料行](how-to-represent-columns-as-allowing-null-values.md)
##### [如何： 對應繼承階層架構](how-to-map-inheritance-hierarchies.md)
##### [如何： 指定並行衝突檢查](how-to-specify-concurrency-conflict-checking.md)
### [與資料庫通訊](communicating-with-the-database.md)
#### [如何： 連接到資料庫](how-to-connect-to-a-database.md)
#### [如何： 直接執行 SQL 命令](how-to-directly-execute-sql-commands.md)
#### [如何： 重複使用 ADO.NET 命令和 DataContext 之間的連接](how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
### [查詢資料庫](querying-the-database.md)
#### [如何： 查詢資訊](how-to-query-for-information.md)
#### [如何： 擷取資訊以唯讀狀態](how-to-retrieve-information-as-read-only.md)
#### [如何： 控制要擷取的相關的資料多寡](how-to-control-how-much-related-data-is-retrieved.md)
#### [如何： 篩選相關的資料](how-to-filter-related-data.md)
#### [如何： 關閉延後載入](how-to-turn-off-deferred-loading.md)
#### [如何： 直接執行 SQL 查詢](how-to-directly-execute-sql-queries.md)
#### [如何： 儲存和重複使用查詢](how-to-store-and-reuse-queries.md)
#### [如何： 處理查詢中的複合索引鍵](how-to-handle-composite-keys-in-queries.md)
#### [如何： 一次擷取多個物件](how-to-retrieve-many-objects-at-once.md)
#### [如何： 在 DataContext 層級篩選](how-to-filter-at-the-datacontext-level.md)
#### [查詢範例](query-examples.md)
##### [彙總查詢](aggregate-queries.md)
###### [傳回數值序列的平均值](return-the-average-value-from-a-numeric-sequence.md)
###### [計算序列中的項目數](count-the-number-of-elements-in-a-sequence.md)
###### [尋找數值序列中的最大值](find-the-maximum-value-in-a-numeric-sequence.md)
###### [尋找數值序列中的最小值](find-the-minimum-value-in-a-numeric-sequence.md)
###### [計算數值序列中值的總和](compute-the-sum-of-values-in-a-numeric-sequence.md)
##### [傳回序列中的第一個項目](return-the-first-element-in-a-sequence.md)
##### [傳回或略過序列中的項目](return-or-skip-elements-in-a-sequence.md)
##### [排序順序中的項目](sort-elements-in-a-sequence.md)
##### [序列中的群組項目](group-elements-in-a-sequence.md)
##### [排除重複的項目，從序列](eliminate-duplicate-elements-from-a-sequence.md)
##### [決定是否序列中的任何或所有項目滿足條件](determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)
##### [串連兩個序列](concatenate-two-sequences.md)
##### [傳回兩個序列之間的差異](return-the-set-difference-between-two-sequences.md)
##### [傳回兩個序列的集合交集](return-the-set-intersection-of-two-sequences.md)
##### [傳回兩個序列的聯集](return-the-set-union-of-two-sequences.md)
##### [將序列轉換為陣列](convert-a-sequence-to-an-array.md)
##### [將序列轉換為一般清單](convert-a-sequence-to-a-generic-list.md)
##### [將類型轉換成泛型 IEnumerable](convert-a-type-to-a-generic-ienumerable.md)
##### [制定聯結和交叉乘積查詢](formulate-joins-and-cross-product-queries.md)
##### [制定投影](formulate-projections.md)
### [建立和提交資料變更](making-and-submitting-data-changes.md)
#### [如何： 將資料列插入資料庫](how-to-insert-rows-into-the-database.md)
#### [如何： 更新資料庫中的資料列](how-to-update-rows-in-the-database.md)
#### [如何： 從資料庫刪除資料列](how-to-delete-rows-from-the-database.md)
#### [如何： 將變更提交至資料庫](how-to-submit-changes-to-the-database.md)
#### [如何： 使用異動括資料提交](how-to-bracket-data-submissions-by-using-transactions.md)
#### [如何： 動態建立資料庫](how-to-dynamically-create-a-database.md)
#### [如何： 管理變更衝突](how-to-manage-change-conflicts.md)
##### [如何： 偵測及解決衝突的提交](how-to-detect-and-resolve-conflicting-submissions.md)
##### [如何： 指定並行例外狀況會擲回](how-to-specify-when-concurrency-exceptions-are-thrown.md)
##### [如何： 指定的成員會用於測試並行衝突](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
##### [如何： 擷取實體衝突資訊](how-to-retrieve-entity-conflict-information.md)
##### [如何： 擷取成員衝突資訊](how-to-retrieve-member-conflict-information.md)
##### [如何： 解決衝突，藉由保留資料庫值](how-to-resolve-conflicts-by-retaining-database-values.md)
##### [如何： 覆寫資料庫值來解決衝突](how-to-resolve-conflicts-by-overwriting-database-values.md)
##### [如何： 藉由合併資料庫值來解決衝突](how-to-resolve-conflicts-by-merging-with-database-values.md)
### [偵錯支援](debugging-support.md)
#### [如何： 顯示產生的 SQL](how-to-display-generated-sql.md)
#### [如何： 顯示變更集](how-to-display-a-changeset.md)
#### [如何： 顯示 LINQ to SQL 命令](how-to-display-linq-to-sql-commands.md)
#### [疑難排解](troubleshooting.md)
### [背景資訊](background-information.md)
#### [ADO.NET 和 LINQ to SQL](ado-net-and-linq-to-sql.md)
#### [分析 LINQ to SQL 原始程式碼](analyzing-linq-to-sql-source-code.md)
#### [自訂插入、 更新和刪除作業](customizing-insert-update-and-delete-operations.md)
##### [自訂作業： 概觀](customizing-operations-overview.md)
##### [插入、 更新和刪除作業](insert-update-and-delete-operations.md)
##### [開發人員覆寫預設行為的責任](responsibilities-of-the-developer-in-overriding-default-behavior.md)
##### [使用部分方法加入商務邏輯](adding-business-logic-by-using-partial-methods.md)
#### [資料繫結](data-binding.md)
#### [繼承支援](inheritance-support.md)
#### [區域方法呼叫](local-method-calls.md)
#### [多層式架構和遠端的應用程式使用 LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
##### [LINQ to SQL 多層式架構與 ASP.NET](linq-to-sql-n-tier-with-aspnet.md)
##### [LINQ to SQL 多層式架構與 Web 服務](linq-to-sql-n-tier-with-web-services.md)
##### [LINQ to SQL 搭配緊密結合的用戶端-伺服器應用程式](linq-to-sql-with-tightly-coupled-client-server-applications.md)
##### [實作多層式架構商務邏輯](implementing-business-logic-linq-to-sql.md)
##### [資料擷取和 CUD 作業，在多層式架構應用程式 (LINQ to SQL)](data-retrieval-and-cud-operations-in-n-tier-applications.md)
#### [物件識別](object-identity.md)
#### [LINQ to SQL 物件模型](the-linq-to-sql-object-model.md)
#### [物件狀態和變更追蹤](object-states-and-change-tracking.md)
#### [開放式並行存取： 概觀](optimistic-concurrency-overview.md)
#### [查詢概念](query-concepts.md)
##### [LINQ to SQL 查詢](linq-to-sql-queries.md)
##### [跨關聯性查詢](querying-across-relationships.md)
##### [遠端與本機執行](remote-vs-local-execution.md)
##### [延後執行與立即載入](deferred-versus-immediate-loading.md)
#### [從識別快取擷取物件](retrieving-objects-from-the-identity-cache.md)
#### [LINQ to SQL 中的安全性](security-in-linq-to-sql.md)
#### [序列化](serialization.md)
#### [預存程序](stored-procedures.md)
##### [如何： 傳回資料列集](how-to-return-rowsets.md)
##### [如何： 使用參數的預存程序](how-to-use-stored-procedures-that-take-parameters.md)
##### [如何： 使用對應的多個結果圖案的預存程序](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)
##### [如何： 使用循序結果型式對應的預存程序](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)
##### [使用預存程序來自訂作業](customizing-operations-by-using-stored-procedures.md)
##### [以獨佔方式使用自訂作業預存程序](customizing-operations-by-using-stored-procedures-exclusively.md)
#### [異動支援](transaction-support.md)
#### [SQL CLR 類型不符](sql-clr-type-mismatches.md)
#### [SQL-CLR 自訂類型對應](sql-clr-custom-type-mappings.md)
#### [使用者定義函式](user-defined-functions.md)
##### [如何： 使用純量值使用者定義函式](how-to-use-scalar-valued-user-defined-functions.md)
##### [如何： 使用資料表值使用者定義函式](how-to-use-table-valued-user-defined-functions.md)
##### [如何： 呼叫內嵌使用者定義函式](how-to-call-user-defined-functions-inline.md)
## [參考](reference.md)
### [資料型別和函式](data-types-and-functions.md)
#### [SQL CLR 型別對應](sql-clr-type-mapping.md)
#### [基本資料型別](basic-data-types.md)
#### [布林資料類型](boolean-data-types.md)
#### [Null 語意](null-semantics.md)
#### [數字和比較運算子](numeric-and-comparison-operators.md)
#### [序列運算子](sequence-operators.md)
#### [System.Convert 方法](system-convert-methods.md)
#### [System.DateTime 方法](system-datetime-methods.md)
#### [System.Math 方法](system-math-methods.md)
#### [System.Object 方法](system-object-methods.md)
#### [System.String 方法](system-string-methods.md)
#### [System.TimeSpan 方法](system-timespan-methods.md)
#### [不支援的功能](unsupported-functionality.md)
#### [System.DateTimeOffset 方法](system-datetimeoffset-methods.md)
### [屬性為基礎的對應](attribute-based-mapping.md)
### [LINQ to SQL 中的程式碼產生](code-generation-in-linq-to-sql.md)
### [外部對應](external-mapping.md)
### [常見問題集](frequently-asked-questions.md)
### [SQL Server Compact 和 LINQ to SQL](sql-server-compact-and-linq-to-sql.md)
### [標準查詢運算子轉譯](standard-query-operator-translation.md)
## [範例](samples.md)