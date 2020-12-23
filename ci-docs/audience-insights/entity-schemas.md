---
title: Common Data Model 中的 Customer Insights 實體結構描述
description: 搭配 Common Data Model 中的實體處理。
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2cf01029ef6b64fe566022d09ce65bca3603189c
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643898"
---
# <a name="entity-schemas-in-common-data-model"></a>Common Data Model 中的實體結構描述

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) 是宣告式規格，以及標準實體的定義，這些實體代表各種不同商務應用程式與生產力應用程式上常用的概念和活動。 此模型也正在向觀測及分析資料延伸。 Common Data Model 提供定義完善、模組化且可擴充的商務實體 (例如帳戶、業務單位、案例、連絡人、潛在客戶、商機和產品)，以及與廠商、員工和客戶之間的互動 (例如活動和服務等級協定)。 任何人都可以在 Common Data Model 定義的基礎上進行建置和延伸，以捕捉其他業務特定創意。

這是一種共用資料模型，可讓應用程式與資料整合者提供統一的資料定義，更加輕鬆地進行共同作業。 Common Data Model 包含具有標準實體、關聯、階層、特性等項目的豐富中繼資料系統。 其源自 Dynamics 365 應用程式，並且在 GitHub 以開放原始碼形式提供超過 260 個標準實體。 有龐大的內部及外部合作夥伴系統會根據 Common Data Model 發表業界特有的概念。

現今有多個系統和平台實作 Common Data Model，包括 Power BI 資料流程和 Azure 資料服務。 這已經在 Common Data Service、Dynamics 365、Power Apps、Power BI 以及即將推出的 Azure 資料服務中受到支援，直接彰顯出 [Open Data Initiative](https://www.microsoft.com/open-data-initiative) 的價值。

## <a name="customer-insights-entity-schemas"></a>Customer Insights 實體結構描述

為了建立了解客戶的 360 度全方位觀點，並讓 Customer Insights 模型可在 Common Data Model 中用來取得擴充性，我們發佈了下列實體中繼資料：

| 實體 | 描述 |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | 有業務觀測值的使用者所執行的活動。 |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | 已執行或有能力參與商務活動的人員或組織。 |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | 以零維度或更多維度分割的 KPI 定義 (例如每月使用中使用者、客戶的總支出、平均客戶取得成本) |
|[區段](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | 定義具有共同特性的成員群組。 |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | 參與特定區段的成員。 |

如需詳細資訊，請參閱有關 [Common Data Model 中的 Customer Insights 實體結構描述](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview)的文件。

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>使用 Common Data Model 實體導覽器來檢視實體

您可以在 [Common Data Model 實體導航器中](https://microsoft.github.io/CDM/) 檢視實體。 選取 **從 GitHub 載入！** 按鈕，然後瀏覽至 **foundationCommon** > **crmCommon** > **解決方案** > **customerInsights**，您會在其中找到 Customer Insights 實體及其定義的清單。
> [!div class="mx-imgBorder"]
> ![顯示 CustomerActivity 實體的 CDM 實體導覽器](media/CDM-entity-navigator.png "顯示 CustomerActivity 實體的 CDM 實體導覽器")
