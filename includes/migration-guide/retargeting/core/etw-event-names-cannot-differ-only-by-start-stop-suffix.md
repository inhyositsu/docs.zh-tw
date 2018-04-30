### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="a2691-101">ETW 事件名稱不能只有 "Start" 或 "Stop" 尾碼不同</span><span class="sxs-lookup"><span data-stu-id="a2691-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a2691-102">詳細資料</span><span class="sxs-lookup"><span data-stu-id="a2691-102">Details</span></span>|<span data-ttu-id="a2691-103">在 .NET Framework 4.6 和 4.6.1 中，當兩個 Windows 事件追蹤 (ETW) 事件名稱的差異只在 &quot;Start&quot; 或 &quot;Stop&quot; 尾碼時 (例如當一個事件的名稱為 <code>LogUser</code> 而另一個事件的名稱為 <code>LogUserStart</code> 時)，執行階段會擲回 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="a2691-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix (as when one event is named <code>LogUser</code> and another is named <code>LogUserStart</code>).</span></span> <span data-ttu-id="a2691-104">在此情況下，執行階段無法建構事件來源，因此無法發出任何記錄。</span><span class="sxs-lookup"><span data-stu-id="a2691-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>|
|<span data-ttu-id="a2691-105">建議</span><span class="sxs-lookup"><span data-stu-id="a2691-105">Suggestion</span></span>|<span data-ttu-id="a2691-106">若要避免這個例外狀況，請確定沒有兩個事件的名稱差異只在 &quot;Start&quot; 或 &quot;Stop&quot; 尾碼。從 .NET Framework 4.6.2 開始已移除這項需求；執行階段可以釐清差異只在於 &quot;Start&quot; 和 &quot;Stop&quot; 尾碼的事件名稱。</span><span class="sxs-lookup"><span data-stu-id="a2691-106">To prevent the exception, ensure that no two event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the &quot;Start&quot; and &quot;Stop&quot; suffix.</span></span>|
|<span data-ttu-id="a2691-107">範圍</span><span class="sxs-lookup"><span data-stu-id="a2691-107">Scope</span></span>|<span data-ttu-id="a2691-108">Edge</span><span class="sxs-lookup"><span data-stu-id="a2691-108">Edge</span></span>|
|<span data-ttu-id="a2691-109">版本</span><span class="sxs-lookup"><span data-stu-id="a2691-109">Version</span></span>|<span data-ttu-id="a2691-110">4.6</span><span class="sxs-lookup"><span data-stu-id="a2691-110">4.6</span></span>|
|<span data-ttu-id="a2691-111">類型</span><span class="sxs-lookup"><span data-stu-id="a2691-111">Type</span></span>|<span data-ttu-id="a2691-112">正在重定目標</span><span class="sxs-lookup"><span data-stu-id="a2691-112">Retargeting</span></span>|
