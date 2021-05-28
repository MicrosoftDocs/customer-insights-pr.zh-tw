---
title: 新功能以及近期即將推出的功能
description: 關於新功能、改善和 BUG 修正的資訊。
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988910"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a><span data-ttu-id="ce760-103">Dynamics 365 Customer Insights 的觀象見解能力有什麼新發表的功能</span><span class="sxs-lookup"><span data-stu-id="ce760-103">What's new in the audience insights capability of Dynamics 365 Customer Insights</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ce760-104">我們很高興宣布我們最新的更新！</span><span class="sxs-lookup"><span data-stu-id="ce760-104">We're excited to announce our newest updates!</span></span> <span data-ttu-id="ce760-105">本文摘要說明公開預覽功能、正式發行增強功能以及功能更新。</span><span class="sxs-lookup"><span data-stu-id="ce760-105">This article summarizes public preview features, general availability enhancements, and feature updates.</span></span> <span data-ttu-id="ce760-106">若要查看長期功能計劃，請參閱 [Dynamics 365 和 Power Platform 發行計劃](/dynamics365/release-plans/)。</span><span class="sxs-lookup"><span data-stu-id="ce760-106">To see the long-term feature plans, take a look at the [Dynamics 365 and Power Platform release plans](/dynamics365/release-plans/).</span></span>

<span data-ttu-id="ce760-107">我們會逐一在各地區推出更新。</span><span class="sxs-lookup"><span data-stu-id="ce760-107">We roll out updates on a region-by-region basis.</span></span> <span data-ttu-id="ce760-108">因此可能會在特定地區提前看到其他地區尚未推出的功能。</span><span class="sxs-lookup"><span data-stu-id="ce760-108">So certain regions might see features before others.</span></span> <span data-ttu-id="ce760-109">除非另有指示，您不需要採取任何動作，我們會在不停機的情況下自動更新應用程式。</span><span class="sxs-lookup"><span data-stu-id="ce760-109">Unless specified differently, you don't need to take any action and we'll update the app automatically with no downtime.</span></span>

> [!TIP]
> <span data-ttu-id="ce760-110">若要送出和票選功能要求和產品建議，請前往 [Dynamics 365 應用程式想法入口網站](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)。</span><span class="sxs-lookup"><span data-stu-id="ce760-110">To submit and vote on feature requests and product suggestions, go to the [Dynamics 365 Application Ideas portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span></span>

## <a name="april-2021-updates"></a><span data-ttu-id="ce760-111">2021 年 4 月更新</span><span class="sxs-lookup"><span data-stu-id="ce760-111">April 2021 updates</span></span>

<span data-ttu-id="ce760-112">2021 年 4 月的更新包括幾種功能、效能升級和 bug 修正。</span><span class="sxs-lookup"><span data-stu-id="ce760-112">The updates in April 2021 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="data-unification"></a><span data-ttu-id="ce760-113">資料統整</span><span class="sxs-lookup"><span data-stu-id="ce760-113">Data unification</span></span>
 
- <span data-ttu-id="ce760-114">**增強了資料整合的合併體驗**</span><span class="sxs-lookup"><span data-stu-id="ce760-114">**Enhanced merge experience for data unification**</span></span>    
  
   <span data-ttu-id="ce760-115">現在，在資料整合程序的合併設定中，我們有了更好的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="ce760-115">We now have an enhanced user experience in the merge configuration of the data unification process.</span></span> <span data-ttu-id="ce760-116">變更包括合併欄位的直覺排序功能，以及結合和單一欄位的詳細統計資料。</span><span class="sxs-lookup"><span data-stu-id="ce760-116">The changes include intuitive ordering of the merged fields and detailed statistics on combined and singleton fields.</span></span>

- <span data-ttu-id="ce760-117">**實體重新排序，並把所有來源記錄設定到客戶實體**</span><span class="sxs-lookup"><span data-stu-id="ce760-117">**Entity reordering and configure all source records into the Customer entity**</span></span>  
      
   <span data-ttu-id="ce760-118">您現在可以在資料整合處理程序中，從現有的合併方案中重新排序和移除實體。</span><span class="sxs-lookup"><span data-stu-id="ce760-118">You can now reorder and remove entities from an existing conflation plan in the data unification process.</span></span> <span data-ttu-id="ce760-119">根據業務需求，它可讓您在比對程序中更靈活地重新排序實體。</span><span class="sxs-lookup"><span data-stu-id="ce760-119">It gives flexibility to reorder the entities in the match process according to business needs.</span></span> <span data-ttu-id="ce760-120">此外，我們啟用了在最終的 *客戶* 實體中包含所有未比對的紀錄，讓他們定義其客戶個人資料的資料集定義。</span><span class="sxs-lookup"><span data-stu-id="ce760-120">Additionally, we enable include all non-matched records into the final *Customer* entity, which lets them define their customer profile dataset definition.</span></span>

### <a name="enrichments"></a><span data-ttu-id="ce760-121">擴充</span><span class="sxs-lookup"><span data-stu-id="ce760-121">Enrichments</span></span>

 - <span data-ttu-id="ce760-122">**新擴充：增強地址**</span><span class="sxs-lookup"><span data-stu-id="ce760-122">**New enrichment: Enhanced addresses**</span></span>    
  
   <span data-ttu-id="ce760-123">我們很高興引進新的擴充來增強客戶資料中的地址。</span><span class="sxs-lookup"><span data-stu-id="ce760-123">We're excited to introduce a new enrichment to enhance addresses in your customer data.</span></span> <span data-ttu-id="ce760-124">資料中的地址可能未結構化、不完整或不正確。</span><span class="sxs-lookup"><span data-stu-id="ce760-124">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="ce760-125">此功能使用 Microsoft 的模型，將您的地址標準化並擴充為 Common Data Model 格式，以獲得更良好的準確性和洞察力。</span><span class="sxs-lookup"><span data-stu-id="ce760-125">This feature uses Microsoft's models to normalize and enrich your addresses into the Common Data Model format for better accuracy and insights.</span></span>
 
   <span data-ttu-id="ce760-126">如需詳細資訊，請參閱[以增強地址擴充客戶個人資料](enrichment-enhanced-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-126">For more information, see [Enrichment of customer profiles with enhanced addresses](enrichment-enhanced-addresses.md).</span></span>

- <span data-ttu-id="ce760-127">**擴充的引導式設定體驗**</span><span class="sxs-lookup"><span data-stu-id="ce760-127">**Guided configuration experience for enrichments**</span></span>    
  
   <span data-ttu-id="ce760-128">我們以簡單的引導式體驗重新設計了擴充的設定體驗。</span><span class="sxs-lookup"><span data-stu-id="ce760-128">We revisited the configuration experience for enrichments with a simple, guided experience.</span></span> <span data-ttu-id="ce760-129">現在有一個清楚的逐步程序，來建立和編輯擴充。</span><span class="sxs-lookup"><span data-stu-id="ce760-129">You now have a clear step-by-step process for creating and editing enrichments.</span></span>
 
   <span data-ttu-id="ce760-130">此外，我們分離了協力廠商擴充的連接設定，啟用以相同連接多個擴充。</span><span class="sxs-lookup"><span data-stu-id="ce760-130">Additionally, we separated the configuration of connections for third-party enrichments to enable the same connection to be used by multiple enrichments.</span></span> <span data-ttu-id="ce760-131">只有系統管理員才可以設定新的連接，但其建立的連接可供系統管理員和參與者使用。</span><span class="sxs-lookup"><span data-stu-id="ce760-131">Only administrators can configure new connections, but the created connections are available to both administrators and contributors.</span></span>    

   <span data-ttu-id="ce760-132">如需詳細資訊，請參閱[連接概觀](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-132">For more information, see [Connections overview](connections.md).</span></span>

- <span data-ttu-id="ce760-133">**多個相同類型的擴充**</span><span class="sxs-lookup"><span data-stu-id="ce760-133">**Multiple enrichments of the same type**</span></span>    
  
   <span data-ttu-id="ce760-134">現在，我們允許使用者建立和管理相同擴充類型中的多個擴充。</span><span class="sxs-lookup"><span data-stu-id="ce760-134">We now allow users to create and manage multiple enrichments of the same enrichment type.</span></span> <span data-ttu-id="ce760-135">例如，您現在可以建立兩個獨立的地址擴充，以擴充兩個不同的客戶區段。</span><span class="sxs-lookup"><span data-stu-id="ce760-135">For example, you can now create two separate address enrichments to enrich two different customer segments.</span></span> <span data-ttu-id="ce760-136">會限制相同類型擴充可以建立多少個，此限制因為類型不同而有所不同。</span><span class="sxs-lookup"><span data-stu-id="ce760-136">Limits apply on how many enrichments of the same type can be created and vary depending on the enrichment type.</span></span>
  
   <span data-ttu-id="ce760-137">如需詳細資訊，請參閱[客戶設定檔的擴充](enrichment-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-137">For more information, see [Enrichment for customer profiles](enrichment-hub.md).</span></span>

## <a name="march-2021-updates"></a><span data-ttu-id="ce760-138">2021 年 3 月的更新</span><span class="sxs-lookup"><span data-stu-id="ce760-138">March 2021 updates</span></span>

<span data-ttu-id="ce760-139">2021 年 3 月的更新包括幾種功能、效能升級和 bug 修正。</span><span class="sxs-lookup"><span data-stu-id="ce760-139">The updates in March 2021 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="activities"></a><span data-ttu-id="ce760-140">活動</span><span class="sxs-lookup"><span data-stu-id="ce760-140">Activities</span></span>

- <span data-ttu-id="ce760-141">**活動精靈和語義類型**</span><span class="sxs-lookup"><span data-stu-id="ce760-141">**Activity wizard and semantic types**</span></span>

   <span data-ttu-id="ce760-142">我們已改善並更新了活動對應體驗，以引導並簡化活動對應的建立。</span><span class="sxs-lookup"><span data-stu-id="ce760-142">We have improved and updated our activity mapping experience to guide and simplify the creation of activity mapping.</span></span> <span data-ttu-id="ce760-143">在此新體驗中，使用者會取得引導式體驗，協助完成每個程式步驟。</span><span class="sxs-lookup"><span data-stu-id="ce760-143">In this new experience, users get a guided experience to help completing of each step of the process.</span></span> <span data-ttu-id="ce760-144">在活動對應步驟中，除了選擇許多活動類型之外，使用者還可以選擇以語意方式將 *訂閱* 和/或 *SalesOrderLine* 的資料對應至可在下游運用的產業標準結構描述。</span><span class="sxs-lookup"><span data-stu-id="ce760-144">At the activity mapping step, in addition to choosing from many activity types, the user can choose to semantically map data for *Subscription* and/or *SalesOrderLine* to industry standard schemas, which can be used for downstream consumption.</span></span>   

   <span data-ttu-id="ce760-145">如需詳細資訊，請參閱[客戶活動](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-145">For more information, see [Customer activities](activities.md).</span></span>

### <a name="data-ingestion"></a><span data-ttu-id="ce760-146">資料擷取</span><span class="sxs-lookup"><span data-stu-id="ce760-146">Data ingestion</span></span>

- <span data-ttu-id="ce760-147">**使用 Power Platform 資料流程和閘道來連接至內部部署資料來源** 我們非常高興地公開預覽版：Power Platform 資料流程及在 Customer Insights 中與關聯 Power Platform 或 Dataverse 的環境使用閘道的內部部署連線。</span><span class="sxs-lookup"><span data-stu-id="ce760-147">**Connect to on-premises data sources using Power Platform dataflows and gateways** We are pleased to announce the preview of Power Platform dataflows and on-premises connectivity using gateways in Customer Insights with an associated Power Platform or Dataverse environment.</span></span> <span data-ttu-id="ce760-148">在連接至 Dataverse 環境的 Customer Insights 環境中建立任何新的資料來源，都會預設為 Power Platform 資料流程，會導入內部部署資料連線以及一組豐富的連接器和轉換功能。</span><span class="sxs-lookup"><span data-stu-id="ce760-148">Any new data sources created in a Customer Insights environment with a linked Dataverse environment will default to Power Platform dataflows bringing in the on-premises data connectivity and a rich set of connectors and transformation capabilities.</span></span>

### <a name="extensibility"></a><span data-ttu-id="ce760-149">擴充性</span><span class="sxs-lookup"><span data-stu-id="ce760-149">Extensibility</span></span>

- <span data-ttu-id="ce760-150">**匯出彙整到「連接」和「匯出」中** ，我們已將 **匯出目的地** 頁面的名稱變更為 **連接**，並為 **匯出** 新增一個獨立的頁面。</span><span class="sxs-lookup"><span data-stu-id="ce760-150">**Exports organized in connections and exports** We have changed the name of the **Export destinations** page to **Connections** and added a separate page for **Exports**.</span></span> <span data-ttu-id="ce760-151">在此更新中，我們將現有的匯出轉換為成對的連接以及使用該連接的匯出。</span><span class="sxs-lookup"><span data-stu-id="ce760-151">As part of this update, we'll transition existing exports into pairs of a connection and an export using that connection.</span></span> <span data-ttu-id="ce760-152">系統管理員現在對 **連接** 頁面上即將送出的資料更加清楚。</span><span class="sxs-lookup"><span data-stu-id="ce760-152">Administrators now have more clarity over outgoing data on the **Connections** page.</span></span> <span data-ttu-id="ce760-153">所有使用者角色都具備 **匯出** 頁面的存取權，但是只有系統管理員可以選擇參與者來編輯已共用連接的特定匯出。</span><span class="sxs-lookup"><span data-stu-id="ce760-153">All user roles have access to the **Exports** page, but only administrators can choose to allow contributors to edit specific exports with shared connections.</span></span>     
  <span data-ttu-id="ce760-154">如需詳細資訊，請參閱[連接概述](connections.md)和[匯出概述](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-154">For more information, see [Connections overview](connections.md) and [Exports overview](export-destinations.md).</span></span>

- <span data-ttu-id="ce760-155">**將客戶細分匯出至 Campaign Monitor** 我們已擴展了匯出目的地，現在包括 Campaign Monitor。</span><span class="sxs-lookup"><span data-stu-id="ce760-155">**Export segments to Campaign Monitor** We have extended our export destinations to include Campaign Monitor.</span></span> <span data-ttu-id="ce760-156">您現在可以從 Customer Insights 將客戶細分匯出至 Campaign Monitor 清單，並用來當作行銷廣告活動的基準。</span><span class="sxs-lookup"><span data-stu-id="ce760-156">You can now export segments from Customer Insights to Campaign Monitor lists and use them as the baseline for your marketing campaigns.</span></span>    
   <span data-ttu-id="ce760-157">如需詳細資訊，請參閱[匯出資料至 Campaign Monitor](export-campaign-monitor.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-157">For more information, see [Export to Campaign Monitor](export-campaign-monitor.md).</span></span>

- <span data-ttu-id="ce760-158">**將客戶細分匯出至 Constant Contact** 我們已擴展了匯出目的地，現在包括 Constant Contact。</span><span class="sxs-lookup"><span data-stu-id="ce760-158">**Export segments to Constant Contact** We have extended our export destinations to include Constant Contact.</span></span> <span data-ttu-id="ce760-159">您現在可以從 Customer Insights 將客戶細分匯出至 Constant Contact 清單，並用來當作行銷廣告活動的基準。</span><span class="sxs-lookup"><span data-stu-id="ce760-159">You can now export segments from Customer Insights to Constant Contact lists and use them as the baseline for your marketing campaigns.</span></span>   
   <span data-ttu-id="ce760-160">如需詳細資訊，請參閱[匯出資料至 Constant Contact](export-constant-contact.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-160">For more information, see [Export to Constant Contact](export-constant-contact.md).</span></span>

- <span data-ttu-id="ce760-161">**將客戶細分匯出至 RollWorks** 我們已擴展了匯出目的地，現在包括 RollWorks。</span><span class="sxs-lookup"><span data-stu-id="ce760-161">**Export segments to RollWorks** We have extended our export destinations to include RollWorks.</span></span> <span data-ttu-id="ce760-162">您現在可以從 Customer Insights 將客戶細分匯出至 RollWorks 對象，並用來當作 B2B 廣告的基準。</span><span class="sxs-lookup"><span data-stu-id="ce760-162">You can now export segments from Customer Insights to RollWorks audiences and use them as the baseline for your B2B advertising.</span></span>    
   <span data-ttu-id="ce760-163">如需詳細資訊，請參閱[匯出資料至 RollWorks](export-rollworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-163">For more information, see [Export to RollWorks ](export-rollworks.md).</span></span>

- <span data-ttu-id="ce760-164">**將客戶細分匯出至 Snapchat** 我們已擴展了匯出目的地，現在包括 Snapchat。</span><span class="sxs-lookup"><span data-stu-id="ce760-164">**Export segments to Snapchat** We have extended our export destinations to include Snapchat.</span></span> <span data-ttu-id="ce760-165">您現在可以從 Customer Insights 將客戶細分匯出至 Snapchat 對象，並用來當作廣告的基準。</span><span class="sxs-lookup"><span data-stu-id="ce760-165">You can now export segments from Customer Insights to Snapchat audiences and use them as the baseline for your advertising.</span></span>     
   <span data-ttu-id="ce760-166">如需詳細資訊，請參閱[匯出資料至 Snapchat](export-snapchat.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-166">For more information, see [Export to Snapchat](export-snapchat.md).</span></span>

### <a name="predictions"></a><span data-ttu-id="ce760-167">預測</span><span class="sxs-lookup"><span data-stu-id="ce760-167">Predictions</span></span>

- <span data-ttu-id="ce760-168">**在預測產品建議中使用產品篩選** 我們在產品建議模型中新增了產品篩選的能力。</span><span class="sxs-lookup"><span data-stu-id="ce760-168">**Use product filters in predictive product recommendations** We have added the capability to use product filters in our product recommendation model.</span></span> <span data-ttu-id="ce760-169">您現在可以只使用一部分產品建立預測。</span><span class="sxs-lookup"><span data-stu-id="ce760-169">You can now create a prediction that uses only a subset of your products.</span></span>    
   <span data-ttu-id="ce760-170">如需詳細資訊，請參閱[設定產品篩選](predict-product-recommendation.md#configure-product-filters)。</span><span class="sxs-lookup"><span data-stu-id="ce760-170">For more information, see [Configure product filters](predict-product-recommendation.md#configure-product-filters).</span></span>

- <span data-ttu-id="ce760-171">**從模型預測建立客戶細分** 我們新增了使用預測模型結果來建立客戶細分的快速方式。</span><span class="sxs-lookup"><span data-stu-id="ce760-171">**Create segments from model predictions** We have added a quick way to create segments using the results of a prediction model.</span></span> <span data-ttu-id="ce760-172">從模型結果頁面中，您可以選取 **新的建立客戶細分** 選項，輕易地建立新的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="ce760-172">From the model results page, you can easily create a new segment by selecting the new **Create segment** option.</span></span>    
  <span data-ttu-id="ce760-173">如需詳細資訊，請參閱[根據預測模型建立客戶細分](prediction-based-segment.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-173">For more information, see [Create a segment based on a prediction model](prediction-based-segment.md).</span></span>

- <span data-ttu-id="ce760-174">**產品建議的解釋** 我們新增了一些資訊，解釋了生成產品建議時 AI 模型學習到的主要因素，以及這些因素對產品建議的影響程度。</span><span class="sxs-lookup"><span data-stu-id="ce760-174">**Explanations for product recommendations** We have added information explaining the key factors learned by the AI model to generate product recommendations and the degree to which those factors contribute towards the product recommendations.</span></span> <span data-ttu-id="ce760-175">此資訊會新增到模型結果畫面。</span><span class="sxs-lookup"><span data-stu-id="ce760-175">This information is added to the model results screen.</span></span>    
   <span data-ttu-id="ce760-176">如需更多資訊，請見 [評論預測狀態和結果](predict-product-recommendation.md#review-a-prediction-status-and-results)。</span><span class="sxs-lookup"><span data-stu-id="ce760-176">For more information, see [Review a prediction status and results](predict-product-recommendation.md#review-a-prediction-status-and-results).</span></span>

## <a name="february-2021-updates"></a><span data-ttu-id="ce760-177">2021 年 2 月更新</span><span class="sxs-lookup"><span data-stu-id="ce760-177">February 2021 updates</span></span>

<span data-ttu-id="ce760-178">2021 年 2 月更新包含數個功能、效能升級和 BUG 修正。</span><span class="sxs-lookup"><span data-stu-id="ce760-178">The updates in February 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="ce760-179">擴充性</span><span class="sxs-lookup"><span data-stu-id="ce760-179">Extensibility</span></span>

- <span data-ttu-id="ce760-180">**將客戶細分匯出至 AdRoll**</span><span class="sxs-lookup"><span data-stu-id="ce760-180">**Export segments to AdRoll**</span></span>

  <span data-ttu-id="ce760-181">我們的匯出目的地成功擴展，包括 AdRoll 了。</span><span class="sxs-lookup"><span data-stu-id="ce760-181">We have extended our export destinations to include AdRoll.</span></span> <span data-ttu-id="ce760-182">您現在可以從 Customer Insights 匯出客戶細分到 AdRoll 對象，並把它當成廣告的基準。</span><span class="sxs-lookup"><span data-stu-id="ce760-182">You can now export segments from Customer Insights to AdRoll audiences and use them as the baseline for your advertising.</span></span> <span data-ttu-id="ce760-183">如需更多資訊，請見 [AdRoll 連接器](export-adroll.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-183">For more information, see [Connector for AdRoll](export-adroll.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="ce760-184">客戶細分</span><span class="sxs-lookup"><span data-stu-id="ce760-184">Segments</span></span>
 
- <span data-ttu-id="ce760-185">**複製客戶細分**</span><span class="sxs-lookup"><span data-stu-id="ce760-185">**Duplicate a segment**</span></span>
  
  <span data-ttu-id="ce760-186">要基於現有客戶細分建立新的客戶細分，您現在可以複製一個客戶細分並透過編輯複製完成的客戶細分進一步優化它。</span><span class="sxs-lookup"><span data-stu-id="ce760-186">To create a new segment based on an existing one, you can now duplicate a segment and edit the duplicated segment to refine it further.</span></span> 

- <span data-ttu-id="ce760-187">**新增其他屬性到客戶細分**</span><span class="sxs-lookup"><span data-stu-id="ce760-187">**Add additional attributes to a segment**</span></span>

  <span data-ttu-id="ce760-188">您現在可以把屬性包含進客戶細分輸出中，即使這些屬性不是客戶個人資料的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce760-188">You can now include attributes in your segment output, even if these attributes are not part of the customer profile.</span></span> <span data-ttu-id="ce760-189">例如，將訂閱識別碼包括在一個客戶細分中，即使它是訂閱實體的一部分，而該實體與客戶實體有 M:1 關係。</span><span class="sxs-lookup"><span data-stu-id="ce760-189">For example, include subscription IDs in a segment even though it is part of the subscription entity that has a M:1 relation with the customer entity.</span></span> <span data-ttu-id="ce760-190">只要屬性屬於與客戶實體相關的實體，您現在就可以把這些屬性包含進去。</span><span class="sxs-lookup"><span data-stu-id="ce760-190">As long as the attribute belongs to an entity related to the customer entity you can now include these attributes.</span></span>  

#### <a name="predictions"></a><span data-ttu-id="ce760-191">預測</span><span class="sxs-lookup"><span data-stu-id="ce760-191">Predictions</span></span>

- <span data-ttu-id="ce760-192">**建立預測的產品建議**</span><span class="sxs-lookup"><span data-stu-id="ce760-192">**Create predictive product recommendations**</span></span>

  <span data-ttu-id="ce760-193">以個人化和業務開發提高公司收入和建立客戶忠誠度，了解客戶有興趣購買什麼是必須的最初步驟之一。</span><span class="sxs-lookup"><span data-stu-id="ce760-193">Understanding what customers are interested in purchasing is one of the first steps needed to improve business revenue and build customer loyalty through personalization and engagement.</span></span> <span data-ttu-id="ce760-194">提供的產品建議不符合客戶興趣可能會在客戶與公司之間產生隔閡感，並最終限制客戶的整體潛在收入和體驗。</span><span class="sxs-lookup"><span data-stu-id="ce760-194">Providing recommendations for products that aren’t aligned to your customer’s interests can create a sense of disconnect between the customer and your business, and ultimately limit the overall potential revenue and experience for a customer.</span></span> 

  <span data-ttu-id="ce760-195">使用您自己的數據，您現在可以對客戶未來可能購買的產品建立預測。</span><span class="sxs-lookup"><span data-stu-id="ce760-195">Using your own data, you can now create predictions for what products your customers are likely to purchase in the future.</span></span> <span data-ttu-id="ce760-196">想瞭解更多資訊，請參閱[產品建議預測](predict-product-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-196">For more information, see [Product recommendation prediction](predict-product-recommendation.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="ce760-197">系統管理</span><span class="sxs-lookup"><span data-stu-id="ce760-197">System administration</span></span>

- <span data-ttu-id="ce760-198">**複製環境支援更多類型的資料來源**</span><span class="sxs-lookup"><span data-stu-id="ce760-198">**Copy environment support more types of data sources**</span></span>

  <span data-ttu-id="ce760-199">系統管理員可以將環境組態複製到在同一組織中的新環境中。</span><span class="sxs-lookup"><span data-stu-id="ce760-199">Admins can copy environment configurations to a new environment in the same organization.</span></span> <span data-ttu-id="ce760-200">一些案例使用到的資料來源基於 Common Data Service data lake 或 Common Data Model 資料夾，為這些案例此這項功能擴展了複製環境功能。</span><span class="sxs-lookup"><span data-stu-id="ce760-200">This feature extends the copy environment functionality for cases in which data sources based on a Common Data Service data lake or a Common Data Model folder are used.</span></span>

## <a name="january-2021-updates"></a><span data-ttu-id="ce760-201">2021 年 1 月更新</span><span class="sxs-lookup"><span data-stu-id="ce760-201">January 2021 updates</span></span>

<span data-ttu-id="ce760-202">2021 年 1 月更新包含數個功能、效能升級和 BUG 修正。</span><span class="sxs-lookup"><span data-stu-id="ce760-202">The updates in January 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="ce760-203">擴充性</span><span class="sxs-lookup"><span data-stu-id="ce760-203">Extensibility</span></span>

- <span data-ttu-id="ce760-204">**SFTP 匯出的擴充功能和增強效能** 您現在可以將 Customer Insights 的所有輸出實體匯出至 SFTP 主機。</span><span class="sxs-lookup"><span data-stu-id="ce760-204">**Extended functionality and enhanced performance for SFTP export** You can now export all output entities from Customer Insights to an SFTP host.</span></span> <span data-ttu-id="ce760-205">先前，匯出會限制在客戶細分實體。</span><span class="sxs-lookup"><span data-stu-id="ce760-205">Previously, export was limited to segment entities.</span></span> <span data-ttu-id="ce760-206">此外，SFTP 匯出的效能可讓您以較少的時間完成更多的資料量，視您的 SFTP 主機效能而定。</span><span class="sxs-lookup"><span data-stu-id="ce760-206">Additionally, the performance of the SFTP export allows more data volume in less time, depending on the performance of your SFTP host.</span></span>    
  <span data-ttu-id="ce760-207">如需更多資訊，請見 [ SFTP 的連接器 (預覽版)](export-sftp.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-207">For more information, see [Connector for SFTP (preview)](export-sftp.md).</span></span>  

#### <a name="segments"></a><span data-ttu-id="ce760-208">客戶細分</span><span class="sxs-lookup"><span data-stu-id="ce760-208">Segments</span></span>

- <span data-ttu-id="ce760-209">**用機器學習支援建議的客戶細分以改善指標** 一種新的方式來探索並建立客戶細分。</span><span class="sxs-lookup"><span data-stu-id="ce760-209">**Machine learning powered suggested segments to improve metrics** There's a new way do discover and create segments.</span></span> <span data-ttu-id="ce760-210">系統會使用 AI 模型來建議客戶細分，這有助於改善正在追蹤的 KPI (量值)。</span><span class="sxs-lookup"><span data-stu-id="ce760-210">The system uses an AI model to suggest segments that can help improve a KPI (measure) you are already tracking.</span></span> <span data-ttu-id="ce760-211">我們會顯示您選取的屬性在量值或另一個主要屬性上的影響程度。</span><span class="sxs-lookup"><span data-stu-id="ce760-211">We show the extent of influence of attributes that you select on a measure or another primary attribute.</span></span> <span data-ttu-id="ce760-212">此資訊可協助尋找存在商機的潛在客戶細分。</span><span class="sxs-lookup"><span data-stu-id="ce760-212">This information helps finding potential segments that present opportunities.</span></span>    
  <span data-ttu-id="ce760-213">如需更多資訊，請見[建議的客戶細分 (預覽版)](suggested-segments.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-213">For more information, see [Suggested segments (preview)](suggested-segments.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="ce760-214">資料統整</span><span class="sxs-lookup"><span data-stu-id="ce760-214">Data unification</span></span>

- <span data-ttu-id="ce760-215">**增強的比對體驗** 在資料整合區域中，已更新比對體驗。</span><span class="sxs-lookup"><span data-stu-id="ce760-215">**Enhanced match experience** In the data unification area, the match experience was updated.</span></span> <span data-ttu-id="ce760-216">它可讓您設定並查看比對規則，包括能進一步說明比對運作方式的統計詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ce760-216">It lets you configure and view the match rules, including detailed stats to further explain how matching works.</span></span> <span data-ttu-id="ce760-217">有一些選項可停用比對規則，所以在保留設定、拖放比對規則或更多作業時，它已不再可以使用。</span><span class="sxs-lookup"><span data-stu-id="ce760-217">There are options to disable a match rule so it's no longer active while retaining the configuration, drag and drop match rules, and more.</span></span>
  <span data-ttu-id="ce760-218">如需詳細資訊，請參閱[比對實體](match-entities.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-218">For more information, see [Match entities](match-entities.md).</span></span>

- <span data-ttu-id="ce760-219">**來自比對程序中的重複資料刪除輸出可作為實體使用** 來自比對程序中的重複資料刪除輸出現在會寫入另一個實體中，提供進一步分析使用。</span><span class="sxs-lookup"><span data-stu-id="ce760-219">**Deduplication output from the match process is available as an entity** Deduplication process output from the match process is now written into a separate entity for further analysis.</span></span> <span data-ttu-id="ce760-220">這個實體包含在重複資料刪除程序中使用的欄位，以及勝出記錄，以及與勝出記錄合併的對應替代記錄。</span><span class="sxs-lookup"><span data-stu-id="ce760-220">This entity consists of the fields used in the deduplication process and the winner record and the corresponding alternate records that get merged with the winner record.</span></span>
  <span data-ttu-id="ce760-221">如需更多資訊，請見[重複資料刪除輸出實體](match-entities.md#deduplication-output-as-an-entity)。</span><span class="sxs-lookup"><span data-stu-id="ce760-221">For more information, see [Deduplication output as an entity](match-entities.md#deduplication-output-as-an-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="ce760-222">系統管理</span><span class="sxs-lookup"><span data-stu-id="ce760-222">System administration</span></span>

- <span data-ttu-id="ce760-223">**將資料無縫共用給 Microsoft Dataverse** 您現在可以使用 Microsoft Dataverse Managed Data Lake 共用 Customer Insights 輸出給 Microsoft Dataverse 應用程式。</span><span class="sxs-lookup"><span data-stu-id="ce760-223">**Seamlessly share data to Microsoft Dataverse** You can now share Customer Insights output with Microsoft Dataverse applications using the Microsoft Dataverse Managed Data Lake.</span></span> <span data-ttu-id="ce760-224">在您將 Dataverse 環境與 Customer Insights 關聯之後，便有啟用資料共用的選項。</span><span class="sxs-lookup"><span data-stu-id="ce760-224">Once you associate a Dataverse environment with Customer Insights, you get the option to enable data sharing.</span></span>
  <span data-ttu-id="ce760-225">如需詳細資訊，請參閱[管理環境](manage-environments.md)。</span><span class="sxs-lookup"><span data-stu-id="ce760-225">For more information, see [Manage environments](manage-environments.md).</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]