---
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 5e157da25829a0741de988d1d6dde0318a93b109
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33475282"
---
# <a name="msmq"></a>MSMQ
在 MSMQ 應用程式中，沒有其他活動會從佇列通道傳輸至 MSMQ 或從 MSMQ 傳輸至佇列通道。  
  
 此外，系統也會追蹤 MSMQ 訊息識別碼和 SOAP 訊息識別碼 (若有活動識別碼，一樣會進行追蹤)，做為傳送作業中佇列通道追蹤的一部分。  
  
 系統會追蹤 MSMQ 訊息識別碼和 SOAP 訊息識別碼 (若有活動識別碼，一樣會進行追蹤)，做為接收作業中佇列通道追蹤的一部分。  
  
 接收作業上必要的傳輸動作，其執行方法類似其他傳輸 (接收位元組 -> 處理序訊息 -> 作業)。
