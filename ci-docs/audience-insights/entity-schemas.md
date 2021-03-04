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
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269274"
---
# <a name="entity-schemas-in-common-data-model"></a><span data-ttu-id="bb207-103">Common Data Model 中的實體結構描述</span><span class="sxs-lookup"><span data-stu-id="bb207-103">Entity schemas in Common Data Model</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bb207-104">[Common Data Model](https://docs.microsoft.com/common-data-model/) 是宣告式規格，以及標準實體的定義，這些實體代表各種不同商務應用程式與生產力應用程式上常用的概念和活動。</span><span class="sxs-lookup"><span data-stu-id="bb207-104">[Common Data Model](https://docs.microsoft.com/common-data-model/) is a declarative specification, and a definition of standard entities that represent commonly used concepts and activities across business and productivity applications.</span></span> <span data-ttu-id="bb207-105">此模型也正在向觀測及分析資料延伸。</span><span class="sxs-lookup"><span data-stu-id="bb207-105">This model is being extended to observational and analytical data as well.</span></span> <span data-ttu-id="bb207-106">Common Data Model 提供定義完善、模組化且可擴充的商務實體 (例如帳戶、業務單位、案例、連絡人、潛在客戶、商機和產品)，以及與廠商、員工和客戶之間的互動 (例如活動和服務等級協定)。</span><span class="sxs-lookup"><span data-stu-id="bb207-106">Common Data Model provides well-defined, modular, and extensible business entities—such as Account, Business Unit, Case, Contact, Lead, Opportunity, and Product—as well as interactions with vendors, workers, and customers—such as activities and service level agreements.</span></span> <span data-ttu-id="bb207-107">任何人都可以在 Common Data Model 定義的基礎上進行建置和延伸，以捕捉其他業務特定創意。</span><span class="sxs-lookup"><span data-stu-id="bb207-107">Anyone can build on and extend Common Data Model definitions to capture additional business-specific ideas.</span></span>

<span data-ttu-id="bb207-108">這是一種共用資料模型，可讓應用程式與資料整合者提供統一的資料定義，更加輕鬆地進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="bb207-108">This shared data model allows applications and data integrators to collaborate more easily by providing a unified definition of data.</span></span> <span data-ttu-id="bb207-109">Common Data Model 包含具有標準實體、關聯、階層、特性等項目的豐富中繼資料系統。</span><span class="sxs-lookup"><span data-stu-id="bb207-109">Common Data Model includes a rich metadata system with standard entities, relationships, hierarchies, traits, and more.</span></span> <span data-ttu-id="bb207-110">其源自 Dynamics 365 應用程式，並且在 GitHub 以開放原始碼形式提供超過 260 個標準實體。</span><span class="sxs-lookup"><span data-stu-id="bb207-110">It originated from Dynamics 365 apps and is open-sourced on GitHub with over 260 standard entities.</span></span> <span data-ttu-id="bb207-111">有龐大的內部及外部合作夥伴系統會根據 Common Data Model 發表業界特有的概念。</span><span class="sxs-lookup"><span data-stu-id="bb207-111">A large system of internal and external partners contributes industry-specific concepts to Common Data Model.</span></span>

<span data-ttu-id="bb207-112">現今有多個系統和平台實作 Common Data Model，包括 Power BI 資料流程和 Azure 資料服務。</span><span class="sxs-lookup"><span data-stu-id="bb207-112">Multiple systems and platforms implement Common Data Model today, including Power BI dataflows and Azure Data Services.</span></span> <span data-ttu-id="bb207-113">這已經在 Common Data Service、Dynamics 365、Power Apps、Power BI 以及即將推出的 Azure 資料服務中受到支援，直接彰顯出 [Open Data Initiative](https://www.microsoft.com/open-data-initiative) 的價值。</span><span class="sxs-lookup"><span data-stu-id="bb207-113">It's already supported in the Common Data Service, Dynamics 365, Power Apps, Power BI, and upcoming Azure data services, directly accruing value towards the [Open Data Initiative](https://www.microsoft.com/open-data-initiative).</span></span>

## <a name="customer-insights-entity-schemas"></a><span data-ttu-id="bb207-114">Customer Insights 實體結構描述</span><span class="sxs-lookup"><span data-stu-id="bb207-114">Customer Insights entity schemas</span></span>

<span data-ttu-id="bb207-115">為了建立了解客戶的 360 度全方位觀點，並讓 Customer Insights 模型可在 Common Data Model 中用來取得擴充性，我們發佈了下列實體中繼資料：</span><span class="sxs-lookup"><span data-stu-id="bb207-115">To establish a 360-degree view of the customer and make Customer Insights models available in Common Data Model for extensibility, we've published the following entity schemas:</span></span>

| <span data-ttu-id="bb207-116">實體</span><span class="sxs-lookup"><span data-stu-id="bb207-116">Entity</span></span> | <span data-ttu-id="bb207-117">描述</span><span class="sxs-lookup"><span data-stu-id="bb207-117">Description</span></span> |
|---------|---------|
|[<span data-ttu-id="bb207-118">CustomerActivity</span><span class="sxs-lookup"><span data-stu-id="bb207-118">CustomerActivity</span></span>](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | <span data-ttu-id="bb207-119">有業務觀測值的使用者所執行的活動。</span><span class="sxs-lookup"><span data-stu-id="bb207-119">An activity performed by a user that has observational value to the business.</span></span> |
|[<span data-ttu-id="bb207-120">CustomerProfile</span><span class="sxs-lookup"><span data-stu-id="bb207-120">CustomerProfile</span></span>](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | <span data-ttu-id="bb207-121">已執行或有能力參與商務活動的人員或組織。</span><span class="sxs-lookup"><span data-stu-id="bb207-121">A person or organization that either performed, or has the potential to engage in, business activities.</span></span> |
|[<span data-ttu-id="bb207-122">MeasureDefinition</span><span class="sxs-lookup"><span data-stu-id="bb207-122">MeasureDefinition</span></span>](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | <span data-ttu-id="bb207-123">以零維度或更多維度分割的 KPI 定義 (例如每月使用中使用者、客戶的總支出、平均客戶取得成本)</span><span class="sxs-lookup"><span data-stu-id="bb207-123">Definition of KPIs partitioned by zero or more dimensions (such as Monthly Active Users, Total Spend By Customer, Average Customer Acquisition Cost)</span></span> |
|[<span data-ttu-id="bb207-124">區段</span><span class="sxs-lookup"><span data-stu-id="bb207-124">Segment</span></span>](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | <span data-ttu-id="bb207-125">定義具有共同特性的成員群組。</span><span class="sxs-lookup"><span data-stu-id="bb207-125">Defines a group of members with common traits.</span></span> |
|[<span data-ttu-id="bb207-126">SegmentMembership</span><span class="sxs-lookup"><span data-stu-id="bb207-126">SegmentMembership</span></span>](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | <span data-ttu-id="bb207-127">參與特定區段的成員。</span><span class="sxs-lookup"><span data-stu-id="bb207-127">Members participating in a given segment.</span></span> |

<span data-ttu-id="bb207-128">如需詳細資訊，請參閱有關 [Common Data Model 中的 Customer Insights 實體結構描述](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview)的文件。</span><span class="sxs-lookup"><span data-stu-id="bb207-128">For more information, see the documentation about the [Customer Insights entity schemas in Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).</span></span>

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a><span data-ttu-id="bb207-129">使用 Common Data Model 實體導覽器來檢視實體</span><span class="sxs-lookup"><span data-stu-id="bb207-129">View entities using the Common Data Model Entity Navigator</span></span>

<span data-ttu-id="bb207-130">您可以在 [Common Data Model 實體導航器中](https://microsoft.github.io/CDM/) 檢視實體。</span><span class="sxs-lookup"><span data-stu-id="bb207-130">You can view entities in the [Common Data Model Entity Navigator](https://microsoft.github.io/CDM/).</span></span> <span data-ttu-id="bb207-131">選取 **從 GitHub 載入！**</span><span class="sxs-lookup"><span data-stu-id="bb207-131">Select the **Load from GitHub!**</span></span> <span data-ttu-id="bb207-132">按鈕，然後瀏覽至 **foundationCommon** > **crmCommon** > **解決方案** > **customerInsights**，您會在其中找到 Customer Insights 實體及其定義的清單。</span><span class="sxs-lookup"><span data-stu-id="bb207-132">button and navigate to **foundationCommon** > **crmCommon** > **solutions** > **customerInsights** where you'll find the list of Customer Insights entities and their definitions.</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="bb207-133">![顯示 CustomerActivity 實體的 CDM 實體導覽器](media/CDM-entity-navigator.png "顯示 CustomerActivity 實體的 CDM 實體導覽器")</span><span class="sxs-lookup"><span data-stu-id="bb207-133">![CDM Entity Navigator showing CustomerActivity entity](media/CDM-entity-navigator.png "CDM Entity Navigator showing CustomerActivity entity")</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]