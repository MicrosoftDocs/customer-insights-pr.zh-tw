---
title: Dynamics 365 Customer Insights 中的服務限制
description: 瞭解限制和約束。
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641752"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights 的服務限制

本文描述 Customer Insights 服務的內建限制，其專門設計確保服務的信賴度和穩定度。 任何變更要求都可以透過[想法論壇](https://go.microsoft.com/fwlink/?linkid=2074172)提出。 

## <a name="customer-insights"></a>Customer Insights

| 面積圖  | 限制  | 注意事項 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 客戶細分、量值以及預測 | 300  | [客戶細分](segments.md)、[量值](measures.md)和[預測](predictions.md)總數不能超過 300。  |
| 關係 | 實體路徑中關聯的 20 層深度。 | 當使用建立器介面建立[客戶細分](segments.md)或[量值](measures.md)時，開始實體與目標實體之間的實體路徑最多可以有 20 個關聯躍點。  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
