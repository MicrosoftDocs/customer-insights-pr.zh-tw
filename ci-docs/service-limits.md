---
title: Customer Insights 的服務限制
description: 瞭解 Customer Insights SaaS 服務中的限制。
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940658"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights 的服務限制

本文描述 Customer Insights 服務的內建限制，其專門設計確保服務的信賴度和穩定度。 任何變更要求都可以透過[想法論壇](https://go.microsoft.com/fwlink/?linkid=2074172)提出。

## <a name="customer-insights"></a>Customer Insights

| 面積圖  | 限制  | 注意事項 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 客戶細分、量值以及預測 | 300  | [客戶細分](segments.md)、[量值](measures.md)和[預測](predictions.md)總數不能超過 300。  |
| 關係 | 實體路徑中關聯的 20 層深度。 | 當使用建立器介面建立[客戶細分](segments.md)或[量值](measures.md)時，開始實體與目標實體之間的實體路徑最多可以有 20 個關聯躍點。  |

## <a name="fair-scheduling-of-jobs"></a>工作的公平排程

Customer Insights 是 SaaS 服務且使用共用的 Azure 資源。 客戶的工作負荷往往是多元的強度和不同排程。 為了確保基礎資源存取是公平的，我們會確定系統程序會以公平順序執行。 系統程序的範例包括那些涉及資料整合、客戶細分更新或量值計算的工作。 如果出現工作要求的峰值，公平排程就會防止您進入資源的佇列中。 同時，Customer Insights 並不能保證所有排入佇列的工作都會並行處理。

[!INCLUDE [footer-include](includes/footer-banner.md)]
