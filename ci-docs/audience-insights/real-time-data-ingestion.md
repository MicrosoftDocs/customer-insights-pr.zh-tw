---
title: 即時資料內嵌和限制
description: 關於對象見解中即時能力的一般資訊。
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598559"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="e7e47-103">即時資料擷取 (預覽)</span><span class="sxs-lookup"><span data-stu-id="e7e47-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="e7e47-104">接近即時的功能可讓您看到您的客戶已使用您的產品或服務所進行的最新互動。</span><span class="sxs-lookup"><span data-stu-id="e7e47-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="e7e47-105">[排程的重新整理](system.md#schedule-tab) 包括大量記錄和數次複雜作業。</span><span class="sxs-lookup"><span data-stu-id="e7e47-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="e7e47-106">首先，資料從資料來源拉出。</span><span class="sxs-lookup"><span data-stu-id="e7e47-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="e7e47-107">接下來，會統整資料，然後以額外資訊擴充。</span><span class="sxs-lookup"><span data-stu-id="e7e47-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="e7e47-108">每次執行此程序時，可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="e7e47-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="e7e47-109">即時功能立即提供資料方便使用，直到後續排程的重新整理將此資料從資料來源拉出為止。</span><span class="sxs-lookup"><span data-stu-id="e7e47-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="e7e47-110">即時更新有過期時間，超過此時間後，就不會再從資料來源中覆寫該值：</span><span class="sxs-lookup"><span data-stu-id="e7e47-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="e7e47-111">設定檔更新將保留 4 小時</span><span class="sxs-lookup"><span data-stu-id="e7e47-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="e7e47-112">活動將保留 30 天</span><span class="sxs-lookup"><span data-stu-id="e7e47-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="e7e47-113">這些值是您可以變更的 API 呼叫參數。</span><span class="sxs-lookup"><span data-stu-id="e7e47-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="e7e47-114">它們的目標是要確保您的來源資料仍然是事實資料的來源。</span><span class="sxs-lookup"><span data-stu-id="e7e47-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="e7e47-115">如果您想要拉長即時更新功能納入的時間，您必須將它們新增到資料來源，如此才能在下次排程重新整理期間拉出它們。</span><span class="sxs-lookup"><span data-stu-id="e7e47-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="e7e47-116">統整客戶設定檔欄位的即時更新</span><span class="sxs-lookup"><span data-stu-id="e7e47-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="e7e47-117">更新的設定檔將在數秒鐘內在客戶卡片視圖或其他任何視覺效果中顯示。</span><span class="sxs-lookup"><span data-stu-id="e7e47-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="e7e47-118">因為即時作業會在資料統整發生後進行，所以它們只適用於統整的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="e7e47-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="e7e47-119">因此，即時設定檔變更將不會更新量值、區段成員資格或擴充。</span><span class="sxs-lookup"><span data-stu-id="e7e47-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="e7e47-120">限制</span><span class="sxs-lookup"><span data-stu-id="e7e47-120">Limitations</span></span>

- <span data-ttu-id="e7e47-121">客戶設定檔可以更新，但無法建立或刪除。</span><span class="sxs-lookup"><span data-stu-id="e7e47-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="e7e47-122">目前不可能將即時更新匯出至外部系統（例如 Power BI）。</span><span class="sxs-lookup"><span data-stu-id="e7e47-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="e7e47-123">即時建立活動</span><span class="sxs-lookup"><span data-stu-id="e7e47-123">Real-time creation of activities</span></span>

<span data-ttu-id="e7e47-124">即時 API 讓您從來源系統 (個別來源記錄) 發佈新活動到統整的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="e7e47-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="e7e47-125">新的活動將在該統整客戶設定檔的時間間隔時間內以統整的活動提供。</span><span class="sxs-lookup"><span data-stu-id="e7e47-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="e7e47-126">您可以在客戶卡片視圖中或您組態其他任何的整合時間表中見到時間表。</span><span class="sxs-lookup"><span data-stu-id="e7e47-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="e7e47-127">活動是不可變的。</span><span class="sxs-lookup"><span data-stu-id="e7e47-127">Activities are immutable.</span></span> <span data-ttu-id="e7e47-128">它們一經建立就不會變更。</span><span class="sxs-lookup"><span data-stu-id="e7e47-128">They don't change once created.</span></span>
> - <span data-ttu-id="e7e47-129">目前，區段和量值不會根據新的活動而更新。</span><span class="sxs-lookup"><span data-stu-id="e7e47-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="e7e47-130">只有透過即時 API 所新增的活動不會納入匯出，也不會顯示在 PowerBI 中。</span><span class="sxs-lookup"><span data-stu-id="e7e47-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="e7e47-131">目前有兩種方式連接到即時 API：</span><span class="sxs-lookup"><span data-stu-id="e7e47-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="e7e47-132">[間接](#connect-via-the-dynamics-365-customer-insights-connector)，使用 [Dynamics 365 Customer Insights 連接器](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="e7e47-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="e7e47-133">[直接](#connect-directly-to-the-real-time-api)，使用程式碼</span><span class="sxs-lookup"><span data-stu-id="e7e47-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="e7e47-134">兩種方式都具有以下先決條件：</span><span class="sxs-lookup"><span data-stu-id="e7e47-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="e7e47-135">Customer Insights 環境</span><span class="sxs-lookup"><span data-stu-id="e7e47-135">A Customer Insights environment</span></span>
- <span data-ttu-id="e7e47-136">統整的客戶設定檔</span><span class="sxs-lookup"><span data-stu-id="e7e47-136">Unified customer profiles</span></span>
- <span data-ttu-id="e7e47-137">已設定並執行的活動</span><span class="sxs-lookup"><span data-stu-id="e7e47-137">Activities configured and run</span></span>
- <span data-ttu-id="e7e47-138">參與者或管理員權限以驗證您的帳戶</span><span class="sxs-lookup"><span data-stu-id="e7e47-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="e7e47-139">透過 Dynamics 365 Customer Insights 連接器連接</span><span class="sxs-lookup"><span data-stu-id="e7e47-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="e7e47-140">即時 API 可以從專用的 Power Platform 連接器（[Dynamics 365 Customer Insights 連接器](/connectors/customerinsights/)）擷取資料，而不需要撰寫和部署任何程式碼。</span><span class="sxs-lookup"><span data-stu-id="e7e47-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="e7e47-141">連接器可以執行與 API 相同的即時動作。</span><span class="sxs-lookup"><span data-stu-id="e7e47-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="e7e47-142">您需要進階連接器的有效授權。</span><span class="sxs-lookup"><span data-stu-id="e7e47-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="e7e47-143">如需詳細資訊，請參閱 [Power Apps 和 Power Automate 授權常見問題集](/power-platform/admin/powerapps-flow-licensing-faq)。</span><span class="sxs-lookup"><span data-stu-id="e7e47-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="e7e47-144">Power Platform [Power Apps 和/或 Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="e7e47-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="e7e47-145">Azure [Logic Apps](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="e7e47-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="e7e47-146">如需建立流程的詳細資料，請參閱 [Power Automate 文件](/power-automate/)。</span><span class="sxs-lookup"><span data-stu-id="e7e47-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="e7e47-147">直接連接至即時 API</span><span class="sxs-lookup"><span data-stu-id="e7e47-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="e7e47-148">您可以藉由組建自己的管道和直接連接到即時 API 方式使用即時能力。</span><span class="sxs-lookup"><span data-stu-id="e7e47-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="e7e47-149">您可以將活動張貼為來源系統的格式或 UnifiedActivity 格式。</span><span class="sxs-lookup"><span data-stu-id="e7e47-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="e7e47-150">對 /api/instances/{instanceId}/manage/entities/UnifiedActivity 進行 API 呼叫，取得格式。</span><span class="sxs-lookup"><span data-stu-id="e7e47-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="e7e47-151">此 API 詳細資料，包括參數和回應，均可參閱 [Customer Insights API 參考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) 的 **EntityData** 區。</span><span class="sxs-lookup"><span data-stu-id="e7e47-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="e7e47-152">如需更多資訊，請見 [搭配 Customer Insights API 處理](apis.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e47-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="e7e47-153">了解遙測的即時使用方式</span><span class="sxs-lookup"><span data-stu-id="e7e47-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="e7e47-154">取得即時 API 的要求量和系統可能遭遇的問題相關資訊總覽。</span><span class="sxs-lookup"><span data-stu-id="e7e47-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="e7e47-155">您可以[存取即時遙測](system.md#api-usage-tab)。</span><span class="sxs-lookup"><span data-stu-id="e7e47-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]