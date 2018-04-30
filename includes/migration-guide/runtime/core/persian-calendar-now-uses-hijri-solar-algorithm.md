### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a><span data-ttu-id="deea4-101">波斯曆現在會使用回教陽曆演算法</span><span class="sxs-lookup"><span data-stu-id="deea4-101">Persian calendar now uses the Hijri solar algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="deea4-102">詳細資料</span><span class="sxs-lookup"><span data-stu-id="deea4-102">Details</span></span>|<span data-ttu-id="deea4-103">從 .NET Framework 4.6 開始，<xref:System.Globalization.PersianCalendar?displayProperty=name> 類別會使用回教陽曆演算法。</span><span class="sxs-lookup"><span data-stu-id="deea4-103">Starting with the .NET Framework 4.6, the <xref:System.Globalization.PersianCalendar?displayProperty=name> class uses the Hijri solar algorithm.</span></span> <span data-ttu-id="deea4-104">從 .NET Framework 4.6 開始，針對 1800 年以前的日期或 2023 年以後的日期 (西曆)，在 <xref:System.Globalization.PersianCalendar?displayProperty=name> 與其他日曆之間轉換這些日期可能會產生稍微不同的結果。此外，<xref:System.Globalization.PersianCalendar.MinSupportedDateTime> 現在是 <code>March 22, 0622 instead of March 21, 0622</code>。</span><span class="sxs-lookup"><span data-stu-id="deea4-104">Converting dates between the <xref:System.Globalization.PersianCalendar?displayProperty=name> and other calendars may produce a slightly different result beginning with the .NET Framework 4.6 for dates earlier than 1800 or later than 2023 (Gregorian).Also, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime> is now <code>March 22, 0622 instead of March 21, 0622</code>.</span></span>|
|<span data-ttu-id="deea4-105">建議</span><span class="sxs-lookup"><span data-stu-id="deea4-105">Suggestion</span></span>|<span data-ttu-id="deea4-106">請注意，在 .NET 4.6 中使用 PersianCalendar 時，某些較早或較晚的日期可能會稍微不同。</span><span class="sxs-lookup"><span data-stu-id="deea4-106">Be aware that some early or late dates may be slightly different when using the PersianCalendar in .NET 4.6.</span></span> <span data-ttu-id="deea4-107">此外，在不同 .NET Framework 版本上執行的處理序之間序列化日期，不會將日期儲存為 PersianCalendar 日期字串 (因為這些值可能不同)。</span><span class="sxs-lookup"><span data-stu-id="deea4-107">Also, when serializing dates between processes which may run on different .NET Framework versions, do not store them as PersianCalendar date strings (since those values may be different).</span></span>|
|<span data-ttu-id="deea4-108">範圍</span><span class="sxs-lookup"><span data-stu-id="deea4-108">Scope</span></span>|<span data-ttu-id="deea4-109">次要</span><span class="sxs-lookup"><span data-stu-id="deea4-109">Minor</span></span>|
|<span data-ttu-id="deea4-110">版本</span><span class="sxs-lookup"><span data-stu-id="deea4-110">Version</span></span>|<span data-ttu-id="deea4-111">4.6</span><span class="sxs-lookup"><span data-stu-id="deea4-111">4.6</span></span>|
|<span data-ttu-id="deea4-112">類型</span><span class="sxs-lookup"><span data-stu-id="deea4-112">Type</span></span>|<span data-ttu-id="deea4-113">執行階段</span><span class="sxs-lookup"><span data-stu-id="deea4-113">Runtime</span></span>|
|<span data-ttu-id="deea4-114">受影響的 API</span><span class="sxs-lookup"><span data-stu-id="deea4-114">Affected APIs</span></span>|<ul><li><xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
