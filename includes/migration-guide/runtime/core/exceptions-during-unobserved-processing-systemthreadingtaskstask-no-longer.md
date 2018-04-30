### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a><span data-ttu-id="a9092-101">在 System.Threading.Tasks.Task 中未觀察到的處理期間發生的例外狀況，將不再於完成項執行緒上傳播</span><span class="sxs-lookup"><span data-stu-id="a9092-101">Exceptions during unobserved processing in System.Threading.Tasks.Task no longer propagate on finalizer thread</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a9092-102">詳細資料</span><span class="sxs-lookup"><span data-stu-id="a9092-102">Details</span></span>|<span data-ttu-id="a9092-103">由於 <xref:System.Threading.Tasks.Task?displayProperty=name> 類別代表非同步作業，因此它會攔截非同步處理期間發生的所有非嚴重的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="a9092-103">Because the <xref:System.Threading.Tasks.Task?displayProperty=name> class represents an asynchronous operation, it catches all non-severe exceptions that occur during asynchronous processing.</span></span> <span data-ttu-id="a9092-104">在 .NET Framework 4.5 中，如果未觀察到某個例外狀況，而您的程式碼絕不會等候這項工作，則該例外狀況將不再於完成項執行緒上傳播，並且會在記憶體回收期間損毀處理序。</span><span class="sxs-lookup"><span data-stu-id="a9092-104">In the .NET Framework 4.5, if an exception is not observed and your code never waits on the task, the exception will no longer propagate on the finalizer thread and crash the process during garbage collection.</span></span> <span data-ttu-id="a9092-105">這項變更可以增強使用 Task 類別執行未觀察到的非同步處理之應用程式的可靠性。</span><span class="sxs-lookup"><span data-stu-id="a9092-105">This change enhances the reliability of applications that use the Task class to perform unobserved asynchronous processing.</span></span>|
|<span data-ttu-id="a9092-106">建議</span><span class="sxs-lookup"><span data-stu-id="a9092-106">Suggestion</span></span>|<span data-ttu-id="a9092-107">如果應用程式必須將未觀察到的非同步例外狀況傳播至完成項執行緒，可以藉由提供適當的處理常式給 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> 事件，或藉由設定[執行階段組態項目](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)，來還原舊版行為。</span><span class="sxs-lookup"><span data-stu-id="a9092-107">If an app depends on unobserved asynchronous exceptions propagating to the finalizer thread, the previous behavior can be restored by providing an appropriate handler for the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event, or by setting a [runtime configuration element](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).</span></span>|
|<span data-ttu-id="a9092-108">範圍</span><span class="sxs-lookup"><span data-stu-id="a9092-108">Scope</span></span>|<span data-ttu-id="a9092-109">Edge</span><span class="sxs-lookup"><span data-stu-id="a9092-109">Edge</span></span>|
|<span data-ttu-id="a9092-110">版本</span><span class="sxs-lookup"><span data-stu-id="a9092-110">Version</span></span>|<span data-ttu-id="a9092-111">4.5</span><span class="sxs-lookup"><span data-stu-id="a9092-111">4.5</span></span>|
|<span data-ttu-id="a9092-112">類型</span><span class="sxs-lookup"><span data-stu-id="a9092-112">Type</span></span>|<span data-ttu-id="a9092-113">執行階段</span><span class="sxs-lookup"><span data-stu-id="a9092-113">Runtime</span></span>|
|<span data-ttu-id="a9092-114">受影響的 API</span><span class="sxs-lookup"><span data-stu-id="a9092-114">Affected APIs</span></span>|<ul><li><xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType></li></ul>|
