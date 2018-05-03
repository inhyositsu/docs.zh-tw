---
title: -deterministic (C# 編譯器選項)
ms.date: 04/12/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6dd597f726b5bbc40feb4cc6f5b03acabd92f4a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2018
---
# <a name="-deterministic"></a><span data-ttu-id="eeb33-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="eeb33-102">-deterministic</span></span>

<span data-ttu-id="eeb33-103">可讓編譯器產生相同輸入之編譯間的逐一位元組輸出相同的組件。</span><span class="sxs-lookup"><span data-stu-id="eeb33-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="eeb33-104">語法</span><span class="sxs-lookup"><span data-stu-id="eeb33-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="eeb33-105">備註</span><span class="sxs-lookup"><span data-stu-id="eeb33-105">Remarks</span></span>

<span data-ttu-id="eeb33-106">根據預設，一組指定輸入的編譯器輸出是唯一的，因為編譯器會新增時間戳記以及透過亂數所產生的 GUID。</span><span class="sxs-lookup"><span data-stu-id="eeb33-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="eeb33-107">您可以使用 `-deterministic` 選項來產生「確定性組件」，這是只要輸入維持不變，其二進位內容在編譯之間就相同的組件。</span><span class="sxs-lookup"><span data-stu-id="eeb33-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="eeb33-108">編譯器會基於確定性而考慮下列輸入：</span><span class="sxs-lookup"><span data-stu-id="eeb33-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="eeb33-109">命令列參數序列。</span><span class="sxs-lookup"><span data-stu-id="eeb33-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="eeb33-110">編譯器之 .rsp 回應檔的內容。</span><span class="sxs-lookup"><span data-stu-id="eeb33-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="eeb33-111">使用的編譯器精確版本和其參考的組件。</span><span class="sxs-lookup"><span data-stu-id="eeb33-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="eeb33-112">目前的目錄路徑。</span><span class="sxs-lookup"><span data-stu-id="eeb33-112">The current directory path.</span></span>
- <span data-ttu-id="eeb33-113">以直接或間接方式明確地傳遞給編譯器之所有檔案的二進位內容，包含：</span><span class="sxs-lookup"><span data-stu-id="eeb33-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
    - <span data-ttu-id="eeb33-114">原始程式檔</span><span class="sxs-lookup"><span data-stu-id="eeb33-114">Source files</span></span>
    - <span data-ttu-id="eeb33-115">參考的組件</span><span class="sxs-lookup"><span data-stu-id="eeb33-115">Referenced assemblies</span></span>
    - <span data-ttu-id="eeb33-116">參考的模組</span><span class="sxs-lookup"><span data-stu-id="eeb33-116">Referenced modules</span></span>
    - <span data-ttu-id="eeb33-117">資源</span><span class="sxs-lookup"><span data-stu-id="eeb33-117">Resources</span></span>
    - <span data-ttu-id="eeb33-118">強式名稱金鑰檔</span><span class="sxs-lookup"><span data-stu-id="eeb33-118">The strong name key file</span></span>
    - <span data-ttu-id="eeb33-119">@ 回應檔</span><span class="sxs-lookup"><span data-stu-id="eeb33-119">@ response files</span></span>
    - <span data-ttu-id="eeb33-120">分析器</span><span class="sxs-lookup"><span data-stu-id="eeb33-120">Analyzers</span></span>
    - <span data-ttu-id="eeb33-121">規則集</span><span class="sxs-lookup"><span data-stu-id="eeb33-121">Rulesets</span></span>
    - <span data-ttu-id="eeb33-122">分析器可能使用的其他檔案</span><span class="sxs-lookup"><span data-stu-id="eeb33-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="eeb33-123">目前文化特性 (Culture) (適用於用來產生診斷和例外狀況訊息的語言)。</span><span class="sxs-lookup"><span data-stu-id="eeb33-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="eeb33-124">如果未指定編碼，則為預設編碼 (或目前字碼頁)。</span><span class="sxs-lookup"><span data-stu-id="eeb33-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="eeb33-125">存在、不存在，以及編譯器搜尋路徑 (例如，透過 `/lib` 或 `/recurse` 指定) 上檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="eeb33-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="eeb33-126">在其上執行編譯器的 CLR 平台。</span><span class="sxs-lookup"><span data-stu-id="eeb33-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="eeb33-127">`%LIBPATH%` 的值，可能會影響分析器相依性載入。</span><span class="sxs-lookup"><span data-stu-id="eeb33-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="eeb33-128">來源公開可用時，確定性編譯可以用於建立是否從信任的來源編譯二進位檔。</span><span class="sxs-lookup"><span data-stu-id="eeb33-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="eeb33-129">它也可以用於持續建置系統，確定是否需要執行與二進位檔變更相依的建置步驟。</span><span class="sxs-lookup"><span data-stu-id="eeb33-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="eeb33-130">請參閱</span><span class="sxs-lookup"><span data-stu-id="eeb33-130">See Also</span></span>  
 [<span data-ttu-id="eeb33-131">C# 編譯器選項</span><span class="sxs-lookup"><span data-stu-id="eeb33-131">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="eeb33-132">管理專案和方案屬性</span><span class="sxs-lookup"><span data-stu-id="eeb33-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)