---
title: 將參與度見解的網頁數據和對象見解的整合
description: 將參與度見解中有關客戶的網站資訊匯入對象見解中。
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305008"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="2bc42-103">將參與度見解的網頁數據和對象見解的整合</span><span class="sxs-lookup"><span data-stu-id="2bc42-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="2bc42-104">客戶通常會使用網站來線上進行日常交易。</span><span class="sxs-lookup"><span data-stu-id="2bc42-104">Customers often do their day-to-day transactions online using web sites.</span></span> <span data-ttu-id="2bc42-105">Dynamics 365 Customer Insights 中的參與度見解 (預覽版) 功能是將 Web 資料整合為來源的便捷解決方案。</span><span class="sxs-lookup"><span data-stu-id="2bc42-105">The engagement insights (preview) capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="2bc42-106">除了交易、人口統計或行為資料之外，我們還可以在整合客戶設定檔中查看網頁上的活動。</span><span class="sxs-lookup"><span data-stu-id="2bc42-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="2bc42-107">我們可以使用這些個人資料來取得對象啟用的其他見解，例如分客戶細分、量值或預測。</span><span class="sxs-lookup"><span data-stu-id="2bc42-107">We can use these profiles to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="2bc42-108">本文說明將客戶網路活動資料從參與度見解移至現有對象見解環境的步驟。</span><span class="sxs-lookup"><span data-stu-id="2bc42-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="2bc42-109">在此範例中，我們假設有一個包含整合客戶設定檔的環境。</span><span class="sxs-lookup"><span data-stu-id="2bc42-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="2bc42-110">設定檔已經與調查、零售和票證系統的來源進行整合。</span><span class="sxs-lookup"><span data-stu-id="2bc42-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="2bc42-111">它也會顯示客戶的相關活動。</span><span class="sxs-lookup"><span data-stu-id="2bc42-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="2bc42-112">我們現在希望知道客戶是否拜訪我們的 web 資源並瞭解他們的活動。</span><span class="sxs-lookup"><span data-stu-id="2bc42-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="2bc42-113">活動包括如訪問網站或在電子郵件中從收到的連結查看的產品頁面。</span><span class="sxs-lookup"><span data-stu-id="2bc42-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2bc42-114">先決條件</span><span class="sxs-lookup"><span data-stu-id="2bc42-114">Prerequisites</span></span>

<span data-ttu-id="2bc42-115">若要整合參與度見解的資料，則需要符合幾個必要的先決條件：</span><span class="sxs-lookup"><span data-stu-id="2bc42-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="2bc42-116">整合參與度見解 SDK 與您的網站。</span><span class="sxs-lookup"><span data-stu-id="2bc42-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="2bc42-117">如需詳細資訊，請參閱[開發人員資源概觀](../engagement-insights/developer-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="2bc42-117">For more information, see [Developer resources overview](../engagement-insights/developer-resources.md).</span></span>
- <span data-ttu-id="2bc42-118">從參與度見解匯出 Web 事件需要存取 Azure Data Lake Storage 帳戶，該帳戶可以將 Web 事件資料擷取至對象見解。</span><span class="sxs-lookup"><span data-stu-id="2bc42-118">Exporting web events from engagement insights requires access to an Azure Data Lake Storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="2bc42-119">如需詳細資訊，請參閱 [匯出事件](../engagement-insights/export-events.md)。</span><span class="sxs-lookup"><span data-stu-id="2bc42-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="2bc42-120">在參與度見解中設定精簡事件</span><span class="sxs-lookup"><span data-stu-id="2bc42-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="2bc42-121">系統管理員使用參與度見解 SDK 檢測網站之後，當使用者查看網頁或按一下其中一個地方時，就會收集 *基準事件*。</span><span class="sxs-lookup"><span data-stu-id="2bc42-121">After an administrator instruments a website with the engagement insights SDK, *base events* are gathered when a user views a webpage or clicks somewhere.</span></span> <span data-ttu-id="2bc42-122">基本事件往往包含許多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2bc42-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="2bc42-123">根據您的使用案例，您只需要基本事件中的一部分資料。</span><span class="sxs-lookup"><span data-stu-id="2bc42-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="2bc42-124">參與度見解可讓您建立 *精簡事件*，其中僅包含選取的基準事件屬性。</span><span class="sxs-lookup"><span data-stu-id="2bc42-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="2bc42-125">如需詳細資訊，請參閱[建立和修改精簡事件](../engagement-insights/refined-events.md)。</span><span class="sxs-lookup"><span data-stu-id="2bc42-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="2bc42-126">建立精簡事件時的考量：</span><span class="sxs-lookup"><span data-stu-id="2bc42-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="2bc42-127">為精簡事件提供有意義的名稱。</span><span class="sxs-lookup"><span data-stu-id="2bc42-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="2bc42-128">在對象見解中，它會被用作活動名稱。</span><span class="sxs-lookup"><span data-stu-id="2bc42-128">It will be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="2bc42-129">至少選取下列屬性，建立對象見解中的活動：</span><span class="sxs-lookup"><span data-stu-id="2bc42-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="2bc42-130">Signal.Action.Name –表示活動詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2bc42-130">Signal.Action.Name – indicates the activity details.</span></span>
    - <span data-ttu-id="2bc42-131">Signal.User.Id – 用於對應客戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="2bc42-131">Signal.User.Id – used to map with the customer ID.</span></span>
    - <span data-ttu-id="2bc42-132">Signal.View.Uri – 當成網址使用，作為客戶細分或量值的基礎。</span><span class="sxs-lookup"><span data-stu-id="2bc42-132">Signal.View.Uri – used as a web address as a basis for segments or measures.</span></span>
    - <span data-ttu-id="2bc42-133">Signal.Export.Id – 當作事件的主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2bc42-133">Signal.Export.Id – used as a primary key for events.</span></span>
    - <span data-ttu-id="2bc42-134">Signal.Timestamp – 辨識活動的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="2bc42-134">Signal.Timestamp – determines the date and time for the activity.</span></span>

<span data-ttu-id="2bc42-135">選取篩選，專注在對使用案例重要的事件和頁面上。</span><span class="sxs-lookup"><span data-stu-id="2bc42-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="2bc42-136">在此範例中，我們將使用「電子郵件促銷」動作名稱。</span><span class="sxs-lookup"><span data-stu-id="2bc42-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="2bc42-137">匯出精簡 Web 事件</span><span class="sxs-lookup"><span data-stu-id="2bc42-137">Export the refined web events</span></span> 

<span data-ttu-id="2bc42-138">定義精簡事件之後，您必須設定將事件資料匯出至 Azure Data Lake Storage，並在對象見解中將其設定為資料來源進行擷取。</span><span class="sxs-lookup"><span data-stu-id="2bc42-138">After defining the refined event, you have to configure the export of the event data to Azure Data Lake Storage, which can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="2bc42-139">作為事件流程，來自 web 屬性的匯出持續發生。</span><span class="sxs-lookup"><span data-stu-id="2bc42-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="2bc42-140">如需詳細資訊，請參閱 [匯出事件](../engagement-insights/export-events.md)。</span><span class="sxs-lookup"><span data-stu-id="2bc42-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="2bc42-141">內嵌事件資料到觀眾見解中</span><span class="sxs-lookup"><span data-stu-id="2bc42-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="2bc42-142">現在您已定義好精簡事件並設定其匯出，我們開始內嵌資料到觀眾見解。</span><span class="sxs-lookup"><span data-stu-id="2bc42-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="2bc42-143">您需要依照 Common Data Model 資料夾建立新的資料來源。</span><span class="sxs-lookup"><span data-stu-id="2bc42-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="2bc42-144">輸入有關事件匯進的儲存體帳戶的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2bc42-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="2bc42-145">在 *default.cdm.json* 檔案中，選取要內嵌的精簡事件並在對象見解中建立實體。</span><span class="sxs-lookup"><span data-stu-id="2bc42-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="2bc42-146">如需詳細資訊，請參閱[使用 Azure Data Lake 帳戶連接至 Common Data Model 資料夾](connect-common-data-model.md)。</span><span class="sxs-lookup"><span data-stu-id="2bc42-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md).</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="2bc42-147">將精簡事件資料關聯成客戶設定檔的活動</span><span class="sxs-lookup"><span data-stu-id="2bc42-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="2bc42-148">完成實體內嵌之後，您可以為客戶設定檔設定活動。</span><span class="sxs-lookup"><span data-stu-id="2bc42-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="2bc42-149">如需詳細資訊，請參閱[客戶活動](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="2bc42-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="已展開編輯活動窗格並完成欄位填入的活動頁面。":::

<span data-ttu-id="2bc42-151">使用下列對應設定新活動：</span><span class="sxs-lookup"><span data-stu-id="2bc42-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="2bc42-152">**主索引鍵**：Signal.Export.Id，即參與度見解中每個事件記錄可用的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="2bc42-152">**Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="2bc42-153">此屬性是自動生成的。</span><span class="sxs-lookup"><span data-stu-id="2bc42-153">This property is automatically generated.</span></span>

- <span data-ttu-id="2bc42-154">**時間戳記**：事件屬性中的 Signal.Timestamp。</span><span class="sxs-lookup"><span data-stu-id="2bc42-154">**Timestamp**: Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="2bc42-155">**事件**：Signal.Name，您想要追蹤的事件名稱。</span><span class="sxs-lookup"><span data-stu-id="2bc42-155">**Event**: Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="2bc42-156">**網址**：Signal.View.Uri，參照建立事件的頁面的 URI。</span><span class="sxs-lookup"><span data-stu-id="2bc42-156">**Web address**: Signal.View.Uri referring to the URI of the page that created the event.</span></span>

- <span data-ttu-id="2bc42-157">**詳細資料**：Signal.Action.Name，顯示與事件有關的資訊。</span><span class="sxs-lookup"><span data-stu-id="2bc42-157">**Details**: Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="2bc42-158">在此案例中，選取的屬性標示這是電子郵件促銷的事件。</span><span class="sxs-lookup"><span data-stu-id="2bc42-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="2bc42-159">**活動類型**：在此範例中，我們選擇現有的活動類型 Weblog。</span><span class="sxs-lookup"><span data-stu-id="2bc42-159">**Activity type**: In this example, we choose the existing activity type WebLog.</span></span> <span data-ttu-id="2bc42-160">要依據此活動類型執行預測模型或建立客戶細分，這是一項非常實用的篩選選項。</span><span class="sxs-lookup"><span data-stu-id="2bc42-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="2bc42-161">**設定關聯**：這項重要設定會將活動與現有的客戶個人資料繫結。</span><span class="sxs-lookup"><span data-stu-id="2bc42-161">**Set up relationship**: This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="2bc42-162">**Signal.User.Id** 是在 SDK 中設定好用來收集的識別碼，且與對象見解中設定的其他資料來源其使用者識別碼相關。</span><span class="sxs-lookup"><span data-stu-id="2bc42-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="2bc42-163">在此範例中，我們會設定 Signal.User.Id 與 RetailCustomers:CustomerRetailId 之間的關聯，這是資料整合程序的對應步驟中識別的主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2bc42-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.</span></span>

<span data-ttu-id="2bc42-164">處理活動後，您可以查看客戶記錄並打開客戶卡，便能在時間表中查看參與度見解的活動。</span><span class="sxs-lookup"><span data-stu-id="2bc42-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="2bc42-165">若要尋找具有參與度見解活動的客戶識別碼，請移至 **實體**，並預覽 UnifiedActivity 實體的資料。</span><span class="sxs-lookup"><span data-stu-id="2bc42-165">To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="2bc42-166">ActivityTypeDisplay = WebLog 包含上述範例中設定的參與度見解活動。</span><span class="sxs-lookup"><span data-stu-id="2bc42-166">ActivityTypeDisplay = WebLog contains the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="2bc42-167">複製其中一個記錄客戶的識別碼並在 **客戶** 頁面上給出該識別碼。</span><span class="sxs-lookup"><span data-stu-id="2bc42-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2bc42-168">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2bc42-168">Next steps</span></span>

<span data-ttu-id="2bc42-169">您現在可以建立[客戶細分](segments.md)、[量值](measures.md)和 [預測](predictions.md)，讓與您的客戶有意義的連結。</span><span class="sxs-lookup"><span data-stu-id="2bc42-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
