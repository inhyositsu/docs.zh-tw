---
title: 使用指數輪詢來實作重試
description: 容器化 .NET 應用程式的 .NET 微服務架構 | 使用指數輪詢來實作重試
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ee5dd711484ba7861eedbd9613fda1209736d5b6
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106914"
---
# <a name="implementing-retries-with-exponential-backoff"></a>使用指數輪詢來實作重試

[「使用指數輪詢重試」](https://docs.microsoft.com/azure/architecture/patterns/retry)是企圖重試某項作業，並呈指數增加等候時間，直到已達最大重試計數的技術 ([Exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff) (指數輪詢))。 這項技術體認到雲端資源可能會基於任何原因而斷斷續續無法使用超過好幾秒。 例如，協調器可能正在將某個容器移至叢集中的另一個節點進行負載平衡。 在這段期間，部分要求可能會失敗。 另一個範例可能是 SQL Azure 之類的資料庫，其中某個資料庫可能移至另一部伺服器進行負載平衡，而導致資料庫無法使用好幾秒。

使用指數輪詢來實作重試邏輯的方法有許多種。


>[!div class="step-by-step"]
[上一頁](partial-failure-strategies.md)
[下一頁](implement-resilient-entity-framework-core-sql-connections.md)
