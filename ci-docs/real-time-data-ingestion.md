---
title: 即時資料擷取 (預覽)
description: Customer Insights 中即時功能的一般資訊。
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 403cc9dbd3bddcf67f59b5cb0be936af4d268fc2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195648"
---
# <a name="real-time-data-ingestion-preview"></a>即時資料擷取 (預覽)

接近即時的功能可讓您看到您的客戶已使用您的產品或服務所進行的最新互動。

[排程的重新整理](system.md#schedule-tab) 包括大量記錄和數次複雜作業。 首先，資料從資料來源拉出。 接下來，會統整資料，然後以額外資訊擴充。 每次執行此程序時，可能需要幾分鐘的時間。

即時功能立即提供資料方便使用，直到後續排程的重新整理將此資料從資料來源拉出為止。

即時更新有過期時間，超過此時間後，就不會再從資料來源中覆寫該值：

- 設定檔更新將保留四小時
- 活動將保留 30 天

這些值是您可以變更的 API 呼叫參數。 它們的目標是要確保您的來源資料仍然是事實資料的來源。 如果您想要拉長即時更新功能納入的時間，您必須將它們新增到資料來源，如此才能在下次排程重新整理期間拉出它們。

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>統整客戶設定檔欄位的即時更新

更新的設定檔將在數秒鐘內在客戶卡片視圖或其他任何視覺效果中顯示。

因為即時作業會在資料統整發生後進行，所以它們只適用於統整的客戶設定檔。 因此，即時設定檔變更將不會更新量值、區段成員資格或擴充。

### <a name="limitations"></a>限制

- 客戶設定檔可以更新，但無法建立或刪除。
- 目前不可能將即時更新匯出至外部系統（例如 Power BI）。

## <a name="real-time-creation-of-activities"></a>即時建立活動

即時 API 讓您從來源系統 (個別來源記錄) 發佈新活動到統整的客戶設定檔。 新的活動將在該統整客戶設定檔的時間間隔時間內以統整的活動提供。 您可以在客戶卡片視圖中或您組態其他任何的整合時間表中見到時間表。

> [!NOTE]
>
> - 活動是不可變的。 它們一經建立就不會變更。
> - 目前，區段和量值不會根據新的活動而更新。
> - 只有透過即時 API 所新增的活動不會納入匯出，也不會顯示在 PowerBI 中。

目前有兩種方式連接到即時 API：

- [間接](#connect-via-the-dynamics-365-customer-insights-connector)，使用 [Dynamics 365 Customer Insights 連接器](/connectors/customerinsights/)
- [直接](#connect-directly-to-the-real-time-api)，使用程式碼

兩種方式都具有以下先決條件：

- Customer Insights 環境
- 統整的客戶設定檔
- 已設定並執行的活動
- 參與者或管理員權限以驗證您的帳戶

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>透過 Dynamics 365 Customer Insights 連接器連接

即時 API 可以從專用的 Power Platform 連接器（[Dynamics 365 Customer Insights 連接器](/connectors/customerinsights/)）擷取資料，而不需要撰寫和部署任何程式碼。    
連接器可以執行與 API 相同的即時動作。 您需要進階連接器的有效授權。 如需詳細資訊，請參閱 [Power Apps 和 Power Automate 授權常見問題集](/power-platform/admin/powerapps-flow-licensing-faq)。

- Power Platform [Power Apps 和/或 Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

如需建立流程的詳細資料，請參閱 [Power Automate 文件](/power-automate/)。

## <a name="connect-directly-to-the-real-time-api"></a>直接連接至即時 API

您可以藉由組建自己的管道和直接連接到即時 API 方式使用即時能力。    
您可以將活動張貼為來源系統的格式或 UnifiedActivity 格式。 對 /api/instances/{instanceId}/manage/entities/UnifiedActivity 進行 API 呼叫，取得格式。

此 API 詳細資料，包括參數和回應，均可參閱 [Customer Insights API 參考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) 的 **EntityData** 區。 如需更多資訊，請見 [搭配 Customer Insights API 處理](apis.md)。

## <a name="understand-your-real-time-usage-with-telemetry"></a>了解遙測的即時使用方式

取得即時 API 的要求量和系統可能遭遇的問題相關資訊總覽。 您可以[存取即時遙測](system.md#api-usage-tab)。 


[!INCLUDE [footer-include](includes/footer-banner.md)]
