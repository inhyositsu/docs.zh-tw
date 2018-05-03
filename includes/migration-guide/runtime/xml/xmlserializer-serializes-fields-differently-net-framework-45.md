### <a name="xmlserializer-serializes-fields-differently-in-net-framework-45"></a><span data-ttu-id="5195f-101">XmlSerializer 會在 .NET Framework 4.5 中以不同的方式序列化欄位</span><span class="sxs-lookup"><span data-stu-id="5195f-101">XmlSerializer serializes fields differently in .NET Framework 4.5</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5195f-102">詳細資料</span><span class="sxs-lookup"><span data-stu-id="5195f-102">Details</span></span>|<span data-ttu-id="5195f-103">.NET Framework 4.5 中的 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> 變更會在序列化的 XML 中以不同的方式格式化欄位。</span><span class="sxs-lookup"><span data-stu-id="5195f-103">Changes in the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> in .NET Framework 4.5 caused fields to be formatted differently in the serialized XML.</span></span>|
|<span data-ttu-id="5195f-104">建議</span><span class="sxs-lookup"><span data-stu-id="5195f-104">Suggestion</span></span>|<span data-ttu-id="5195f-105">此行為已在 .NET Framework 4.5 的服務更新中進行更正。</span><span class="sxs-lookup"><span data-stu-id="5195f-105">This behavior was corrected in a servicing update of .NET Framework 4.5.</span></span> <span data-ttu-id="5195f-106">請更新 .NET Framework 4.5，或是升級至 .NET Framework 4.5.1 或更新版本，以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="5195f-106">Please update the .NET Framework 4.5, or upgrade to .NET Framework 4.5.1 or later, to fix this issue.</span></span> <span data-ttu-id="5195f-107">或者，下列組態設定會還原為 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> 行為：</span><span class="sxs-lookup"><span data-stu-id="5195f-107">Alternatively, the following config setting will revert to 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> behavior:</span></span><pre><code>&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="5195f-108">範圍</span><span class="sxs-lookup"><span data-stu-id="5195f-108">Scope</span></span>|<span data-ttu-id="5195f-109">主要</span><span class="sxs-lookup"><span data-stu-id="5195f-109">Major</span></span>|
|<span data-ttu-id="5195f-110">版本</span><span class="sxs-lookup"><span data-stu-id="5195f-110">Version</span></span>|<span data-ttu-id="5195f-111">4.5</span><span class="sxs-lookup"><span data-stu-id="5195f-111">4.5</span></span>|
|<span data-ttu-id="5195f-112">類型</span><span class="sxs-lookup"><span data-stu-id="5195f-112">Type</span></span>|<span data-ttu-id="5195f-113">執行階段</span><span class="sxs-lookup"><span data-stu-id="5195f-113">Runtime</span></span>|
|<span data-ttu-id="5195f-114">受影響的 API</span><span class="sxs-lookup"><span data-stu-id="5195f-114">Affected APIs</span></span>|<ul><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream%2CSystem.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter%2CSystem.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object%2CSystem.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces%2CSystem.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces%2CSystem.String%2CSystem.String)?displayProperty=nameWithType></li></ul>|
