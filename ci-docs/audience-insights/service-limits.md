---
title: 服務限制
description: 瞭解限制和約束。
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604359"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights 對象見解能力的服務限制

本文描述 Customer Insights 服務的內建限制，其專門設計確保服務的信賴度和穩定度。 任何變更要求都可以透過[想法論壇](https://go.microsoft.com/fwlink/?linkid=2074172)提出。 
 
| 面積圖  | 限制  | 備註 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 客戶細分與量值 | 100 個區段或量值。 | 有效 [區段](segments.md) 和 [量值](measures.md) 結合後的總數不能超過 100。  |
| 關係 | 實體路徑中關聯的 20 層深度。 | 當使用建立器介面建立[客戶細分](segments.md)或[量值](measures.md)時，開始實體與目標實體之間的實體路徑最多可以有 20 個關聯躍點。  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]