---
title: Dynamics 365 Customer Insights 中的服務限制
description: 瞭解限制和約束。
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791972"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights 功能的服務限制

本文描述 Customer Insights 服務的內建限制，其專門設計確保服務的信賴度和穩定度。 任何變更要求都可以透過[想法論壇](https://go.microsoft.com/fwlink/?linkid=2074172)提出。 

## <a name="audience-insights"></a>對象見解

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights 對象見解能力的服務限制

| 面積圖  | 限制  | 注意事項 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 客戶細分、量值以及預測 | 300  | [客戶細分](audience-insights/segments.md)、[量值](audience-insights/measures.md)和[預測](audience-insights/predictions.md)總數不能超過 300。  |
| 關係 | 實體路徑中關聯的 20 層深度。 | 當使用建立器介面建立[客戶細分](audience-insights/segments.md)或[量值](audience-insights/measures.md)時，開始實體與目標實體之間的實體路徑最多可以有 20 個關聯躍點。  |


## <a name="engagement-insights"></a>參與見解

### <a name="workspace-and-event-quotas"></a>工作區與事件配額

業務開發見解是一個可高度擴充的應用程式，每秒可支援數百萬個事件。 在公用預覽版中，事件有數量閥值。 組織中的工作區數目也有限制。

### <a name="engagement-insights-limits"></a>業務開發見解限制

- 每個工作區的最大事件數量 = 100 個事件/秒

- 每個組織的最大工作區數目 = 100

當事件數量超過閾值時，會造成根據這些事件建立之報表上的資料遺失。 您可以[聯繫支援部門](https://go.microsoft.com/fwlink/?linkid=2145734)，要求在超過限制前增加容量。 我們將與您合作，判斷您是否需要增加數量並支援您的請求。


[!INCLUDE[footer-include](includes/footer-banner.md)]
