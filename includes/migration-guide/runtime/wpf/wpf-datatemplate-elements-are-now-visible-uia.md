### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a><span data-ttu-id="a5a26-101">UIA 現在看得到 WPF DataTemplate 項目</span><span class="sxs-lookup"><span data-stu-id="a5a26-101">WPF DataTemplate elements are now visible to UIA</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a5a26-102">詳細資料</span><span class="sxs-lookup"><span data-stu-id="a5a26-102">Details</span></span>|<span data-ttu-id="a5a26-103">之前，UI 自動化看不到 <xref:System.Windows.DataTemplate?displayProperty=name> 項目。</span><span class="sxs-lookup"><span data-stu-id="a5a26-103">Previously, <xref:System.Windows.DataTemplate?displayProperty=name> elements were invisible to UI Automation.</span></span> <span data-ttu-id="a5a26-104">從 4.5 開始，使用者介面自動化將會偵測這些項目。</span><span class="sxs-lookup"><span data-stu-id="a5a26-104">Beginning in 4.5, UI Automation will detect these elements.</span></span> <span data-ttu-id="a5a26-105">這在許多情況下很有用，但可能會中斷相依於不含 <xref:System.Windows.DataTemplate?displayProperty=name> 項目之 UIA 樹狀目錄的測試。</span><span class="sxs-lookup"><span data-stu-id="a5a26-105">This is useful in many cases, but can break tests that depend on UIA trees not containing <xref:System.Windows.DataTemplate?displayProperty=name> elements.</span></span>|
|<span data-ttu-id="a5a26-106">建議</span><span class="sxs-lookup"><span data-stu-id="a5a26-106">Suggestion</span></span>|<span data-ttu-id="a5a26-107">您可能需要更新此應用程式的 UI 自動化測試，UIA 樹狀目錄現在才能包含先前不可見的 <xref:System.Windows.DataTemplate?displayProperty=name> 項目。</span><span class="sxs-lookup"><span data-stu-id="a5a26-107">UI Automation tests for this app may need updated to account for the UIA tree now including previously invisible <xref:System.Windows.DataTemplate?displayProperty=name> elements.</span></span> <span data-ttu-id="a5a26-108">例如，預期某些項目彼此相鄰的測試，現在可能需要預期這些項目之間會出現先前不可見的 UIA 項目。</span><span class="sxs-lookup"><span data-stu-id="a5a26-108">For example, tests that expect some elements to be next to each other may now need to expect previously invisible UIA elements in between.</span></span> <span data-ttu-id="a5a26-109">或者，依賴幾個 UIA 項目或其索引的測試，可能需要以新值更新。</span><span class="sxs-lookup"><span data-stu-id="a5a26-109">Or tests that rely on certain counts or indexes for UIA elements may need updated with new values.</span></span>|
|<span data-ttu-id="a5a26-110">範圍</span><span class="sxs-lookup"><span data-stu-id="a5a26-110">Scope</span></span>|<span data-ttu-id="a5a26-111">Edge</span><span class="sxs-lookup"><span data-stu-id="a5a26-111">Edge</span></span>|
|<span data-ttu-id="a5a26-112">版本</span><span class="sxs-lookup"><span data-stu-id="a5a26-112">Version</span></span>|<span data-ttu-id="a5a26-113">4.5</span><span class="sxs-lookup"><span data-stu-id="a5a26-113">4.5</span></span>|
|<span data-ttu-id="a5a26-114">類型</span><span class="sxs-lookup"><span data-stu-id="a5a26-114">Type</span></span>|<span data-ttu-id="a5a26-115">執行階段</span><span class="sxs-lookup"><span data-stu-id="a5a26-115">Runtime</span></span>|
|<span data-ttu-id="a5a26-116">受影響的 API</span><span class="sxs-lookup"><span data-stu-id="a5a26-116">Affected APIs</span></span>|<ul><li><xref:System.Windows.DataTemplate.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)?displayProperty=nameWithType></li></ul>|
