---
title: 訂閱流失預測範例指南
description: 使用此範例指南試用訂閱流失創意預測模型。
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269826"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="8c737-103">訂閱流失預測 (預覽版) 範例指南</span><span class="sxs-lookup"><span data-stu-id="8c737-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="8c737-104">我們將以訂閱流失預測範例使用的下方範例資料從頭到尾向您說明。</span><span class="sxs-lookup"><span data-stu-id="8c737-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="8c737-105">案例</span><span class="sxs-lookup"><span data-stu-id="8c737-105">Scenario</span></span>

<span data-ttu-id="8c737-106">Contoso 是一家公司，生產高品質咖啡和咖啡機，透過 Contoso 咖啡網站銷售。</span><span class="sxs-lookup"><span data-stu-id="8c737-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="8c737-107">他們最近開始客戶的訂閱業務，讓客戶定期取用咖啡。</span><span class="sxs-lookup"><span data-stu-id="8c737-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="8c737-108">他們的目標是瞭解哪些已訂閱的客戶可能在接下來的幾個月取消訂閱。</span><span class="sxs-lookup"><span data-stu-id="8c737-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="8c737-109">知道哪一位客戶 **很有可能流失** 可協助他們持續聚焦行銷力量。</span><span class="sxs-lookup"><span data-stu-id="8c737-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c737-110">先決條件</span><span class="sxs-lookup"><span data-stu-id="8c737-110">Prerequisites</span></span>

- <span data-ttu-id="8c737-111">至少有 Customer Insights 中的[參與者權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8c737-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="8c737-112">我們建議您 [在新環境中](manage-environments.md) 執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="8c737-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="8c737-113">任務 1 - 內嵌資料</span><span class="sxs-lookup"><span data-stu-id="8c737-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="8c737-114">具體回顧這些文章 [關於資料內嵌](data-sources.md) 和 [使用 Power Query 連接器匯入資料來源](connect-power-query.md)。</span><span class="sxs-lookup"><span data-stu-id="8c737-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="8c737-115">下列資訊假定您大體上已熟悉內嵌資料。</span><span class="sxs-lookup"><span data-stu-id="8c737-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="8c737-116">從電子商務平台內嵌客戶資料</span><span class="sxs-lookup"><span data-stu-id="8c737-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="8c737-117">建立稱為 **電子商務** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="8c737-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8c737-118">輸入電子商務連絡人 URL https://aka.ms/ciadclasscontacts。</span><span class="sxs-lookup"><span data-stu-id="8c737-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="8c737-119">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="8c737-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8c737-120">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="8c737-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="8c737-121">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="8c737-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="8c737-122">**CreatedOn**：日期/時間/時區</span><span class="sxs-lookup"><span data-stu-id="8c737-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="將出生日期轉換為日期。":::

1. <span data-ttu-id="8c737-124">請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="8c737-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="8c737-125">儲存資料來源。</span><span class="sxs-lookup"><span data-stu-id="8c737-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="8c737-126">從忠實結構描述內嵌客戶資料</span><span class="sxs-lookup"><span data-stu-id="8c737-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="8c737-127">建立稱為 **LoyaltyScheme** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="8c737-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8c737-128">輸入電子商務連絡人 URL https://aka.ms/ciadclasscustomerloyalty。</span><span class="sxs-lookup"><span data-stu-id="8c737-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="8c737-129">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="8c737-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8c737-130">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="8c737-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="8c737-131">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="8c737-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="8c737-132">**RewardsPoints**: 整數</span><span class="sxs-lookup"><span data-stu-id="8c737-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="8c737-133">**CreatedOn**：日期/時間</span><span class="sxs-lookup"><span data-stu-id="8c737-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="8c737-134">請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="8c737-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="8c737-135">儲存資料來源。</span><span class="sxs-lookup"><span data-stu-id="8c737-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="8c737-136">內嵌訂閱資訊</span><span class="sxs-lookup"><span data-stu-id="8c737-136">Ingest subscription information</span></span>

1. <span data-ttu-id="8c737-137">建立稱為 **SubscriptionHistory** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="8c737-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8c737-138">輸入電子商務連絡人 URL https://aka.ms/ciadchurnsubscriptionhistory。</span><span class="sxs-lookup"><span data-stu-id="8c737-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="8c737-139">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="8c737-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8c737-140">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="8c737-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="8c737-141">**SubscriptioID**: 整數</span><span class="sxs-lookup"><span data-stu-id="8c737-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="8c737-142">**SubscriptionAmount**：貨幣</span><span class="sxs-lookup"><span data-stu-id="8c737-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="8c737-143">**SubscriptionEndDate**：日期/時間</span><span class="sxs-lookup"><span data-stu-id="8c737-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="8c737-144">**SubscriptionStartDate**：日期/時間</span><span class="sxs-lookup"><span data-stu-id="8c737-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="8c737-145">**TransactionDate**：日期/時間</span><span class="sxs-lookup"><span data-stu-id="8c737-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="8c737-146">**IsRecurring**：真/偽</span><span class="sxs-lookup"><span data-stu-id="8c737-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="8c737-147">**Is_auto_renew**：真/偽</span><span class="sxs-lookup"><span data-stu-id="8c737-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="8c737-148">**RecurringFrequencyInMonths**：整數</span><span class="sxs-lookup"><span data-stu-id="8c737-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="8c737-149">請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **SubscriptionHistory**。</span><span class="sxs-lookup"><span data-stu-id="8c737-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="8c737-150">儲存資料來源。</span><span class="sxs-lookup"><span data-stu-id="8c737-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="8c737-151">從網站審查中內嵌客戶資料</span><span class="sxs-lookup"><span data-stu-id="8c737-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="8c737-152">建立稱為 **網站** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="8c737-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8c737-153">輸入電子商務連絡人 URL https://aka.ms/ciadclasswebsite。</span><span class="sxs-lookup"><span data-stu-id="8c737-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="8c737-154">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="8c737-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8c737-155">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="8c737-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="8c737-156">**ReviewRating**：整數</span><span class="sxs-lookup"><span data-stu-id="8c737-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="8c737-157">**ReviewDate**：日期</span><span class="sxs-lookup"><span data-stu-id="8c737-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="8c737-158">請在右側窗格的 '名稱' 欄位中將您的資料來源從 **查詢** 重新命名為 **webReviews**。</span><span class="sxs-lookup"><span data-stu-id="8c737-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="8c737-159">任務 2 - 資料統整</span><span class="sxs-lookup"><span data-stu-id="8c737-159">Task 2 - Data unification</span></span>

<span data-ttu-id="8c737-160">內嵌資料後，我們現在就會開始 **對應、比對、合併** 流程，以建立統整的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="8c737-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="8c737-161">如需更多資訊，請見 [資料統整](data-unification.md)。</span><span class="sxs-lookup"><span data-stu-id="8c737-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="8c737-162">對應</span><span class="sxs-lookup"><span data-stu-id="8c737-162">Map</span></span>

1. <span data-ttu-id="8c737-163">內嵌資料後，將電子商務的聯絡人與忠誠度資料對應到常用資料類型。</span><span class="sxs-lookup"><span data-stu-id="8c737-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="8c737-164">請前往 **資料** > **統整** > **對應**。</span><span class="sxs-lookup"><span data-stu-id="8c737-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="8c737-165">選取代表客戶設定檔的實體 – **eCommerceContacts** 和 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="8c737-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="統整電子商務與忠誠度資料來源。":::

1. <span data-ttu-id="8c737-167">選取 **ContactId** 做為 **eCommerceContacts** 主鍵，而 **LoyaltyID** 做為 **loyCustomers** 主鍵。</span><span class="sxs-lookup"><span data-stu-id="8c737-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="統整 LoyaltyId 為主鍵。":::

### <a name="match"></a><span data-ttu-id="8c737-169">相符項目</span><span class="sxs-lookup"><span data-stu-id="8c737-169">Match</span></span>

1. <span data-ttu-id="8c737-170">請前往 **比對** 索引標籤並選取 **設定訂單**。</span><span class="sxs-lookup"><span data-stu-id="8c737-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="8c737-171">請在 **主要** 下拉式清單中選擇 **eCommerceContacts：電子商務** 為主要來源並包括所有記錄。</span><span class="sxs-lookup"><span data-stu-id="8c737-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="8c737-172">請在 **實體 2** 下拉式清單中選擇 **loyCustomers：LoyaltyScheme** 並包括所有記錄。</span><span class="sxs-lookup"><span data-stu-id="8c737-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="統整比對電子商務與忠誠度。":::

1. <span data-ttu-id="8c737-174">選取 **建立新規則**</span><span class="sxs-lookup"><span data-stu-id="8c737-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="8c737-175">使用 FullName 新增您的第一個條件。</span><span class="sxs-lookup"><span data-stu-id="8c737-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="8c737-176">eCommerceContacts 方面，請在下拉式清單中選取 **FullName**。</span><span class="sxs-lookup"><span data-stu-id="8c737-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="8c737-177">loyCustomers 方面，請在下拉式清單中選取 **FullName**。</span><span class="sxs-lookup"><span data-stu-id="8c737-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="8c737-178">選取 **正規化** 下拉式清單並選擇 **類型 (電話、名稱、地址、...)**。</span><span class="sxs-lookup"><span data-stu-id="8c737-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="8c737-179">設定 **精密等級**：**基本** 與 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="8c737-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="8c737-180">輸入新規則名稱 **FullName、電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="8c737-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="8c737-181">選取 **新增條件** 來新增電子郵件地址的第二個條件</span><span class="sxs-lookup"><span data-stu-id="8c737-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="8c737-182">實體 eCommerceContacts 方面，請在下拉式清單中選擇 **電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="8c737-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="8c737-183">實體 loyCustomers 方面，請在下拉式清單中選擇 **電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="8c737-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="8c737-184">保留正規化空白。</span><span class="sxs-lookup"><span data-stu-id="8c737-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="8c737-185">設定 **精密等級**：**基本** 與 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="8c737-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="統整比對規則的名稱和電子郵件。":::

7. <span data-ttu-id="8c737-187">選取 **儲存** 和 **執行**。</span><span class="sxs-lookup"><span data-stu-id="8c737-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="8c737-188">執行合併​​</span><span class="sxs-lookup"><span data-stu-id="8c737-188">Merge</span></span>

1. <span data-ttu-id="8c737-189">請前往 **合併** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8c737-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="8c737-190">在 **loyCustomers** 實體的 **ContactId** 上，將顯示名稱變更為 **ContactIdLOYALTY**，以便將它與其他內嵌的識別碼區分開來。</span><span class="sxs-lookup"><span data-stu-id="8c737-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="從忠誠度識別碼重新命名 contactid。":::

1. <span data-ttu-id="8c737-192">選取 **儲存** 並 **執行** 以便開始合併流程。</span><span class="sxs-lookup"><span data-stu-id="8c737-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="8c737-193">任務 3 - 組態訂閱流失預測</span><span class="sxs-lookup"><span data-stu-id="8c737-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="8c737-194">現在我們可以使用統整的客戶設定檔執行訂閱流失預測。</span><span class="sxs-lookup"><span data-stu-id="8c737-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="8c737-195">如需詳細步驟，請見 [訂閱流失預測 (預覽版)](predict-subscription-churn.md) 文章。</span><span class="sxs-lookup"><span data-stu-id="8c737-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="8c737-196">前往 **智慧** > **發現** 並選取使用 **客戶流失模型**。</span><span class="sxs-lookup"><span data-stu-id="8c737-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="8c737-197">選取 **訂閱** 選項和 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="8c737-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="8c737-198">將模型 **OOB 訂閱流失預測** 和輸出實體命名為 **OOBSubscriptionChurnPrediction**。</span><span class="sxs-lookup"><span data-stu-id="8c737-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="8c737-199">定義流失模型的兩個條件：</span><span class="sxs-lookup"><span data-stu-id="8c737-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="8c737-200">**訂閱結束後的天數**：**至少 60** 天。</span><span class="sxs-lookup"><span data-stu-id="8c737-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="8c737-201">如果客戶在訂閱結束後這段期間未續訂訂閱動作，則視同已流失。</span><span class="sxs-lookup"><span data-stu-id="8c737-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="8c737-202">**流失定義**：**至少 93** 天。</span><span class="sxs-lookup"><span data-stu-id="8c737-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="8c737-203">模型預測可能流失客戶的持續時間。</span><span class="sxs-lookup"><span data-stu-id="8c737-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="8c737-204">未來您看的愈仔細，結果就愈不精確。</span><span class="sxs-lookup"><span data-stu-id="8c737-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="選取模型槓桿預測視窗和流失定義。":::

1. <span data-ttu-id="8c737-206">選取訂閱歷史資料的 **新增必要資料** 和 **新增資料**。</span><span class="sxs-lookup"><span data-stu-id="8c737-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="8c737-207">新增 **訂閱：SubscriptionHistory** 實體並將電子商務欄位對應到模型所需的對應欄位。</span><span class="sxs-lookup"><span data-stu-id="8c737-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="8c737-208">加入 **訂閱：SubscriptionHistory** 實體和 **eCommerceContacts：電子商務**，命名 **eCommerceSubscription** 關係。</span><span class="sxs-lookup"><span data-stu-id="8c737-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="加入電子商務實體。":::

1. <span data-ttu-id="8c737-210">請在客戶活動下方新增 **webReviews：網站** 實體並將 webReviews 欄位對應到模型所需的對應欄位。</span><span class="sxs-lookup"><span data-stu-id="8c737-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="8c737-211">主索引鍵：ReviewId</span><span class="sxs-lookup"><span data-stu-id="8c737-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="8c737-212">時間戳記：ReviewDate</span><span class="sxs-lookup"><span data-stu-id="8c737-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="8c737-213">事件：ReviewRating</span><span class="sxs-lookup"><span data-stu-id="8c737-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="8c737-214">組態用於網站評論的活動。</span><span class="sxs-lookup"><span data-stu-id="8c737-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="8c737-215">選取活動 **評論**，並加入 **webReviews：網站** 實體和 **eCommerceContacts：電子商務**。</span><span class="sxs-lookup"><span data-stu-id="8c737-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="8c737-216">選取 **下一步** 以設定模型排程。</span><span class="sxs-lookup"><span data-stu-id="8c737-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="8c737-217">當內嵌新資料時，模型必須定期定型以便瞭解新樣式。</span><span class="sxs-lookup"><span data-stu-id="8c737-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="8c737-218">本範例中，請選取 **按月**。</span><span class="sxs-lookup"><span data-stu-id="8c737-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="8c737-219">評論所有詳細資料後，請選取 **儲存和執行**。</span><span class="sxs-lookup"><span data-stu-id="8c737-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="8c737-220">任務 4 - 評論模型結果和解釋</span><span class="sxs-lookup"><span data-stu-id="8c737-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="8c737-221">讓模型完成資料的定型與計分。</span><span class="sxs-lookup"><span data-stu-id="8c737-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="8c737-222">您現在可以評論訂閱流失模型解釋。</span><span class="sxs-lookup"><span data-stu-id="8c737-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="8c737-223">如需更多資訊，請見 [評論預測狀態和結果](predict-subscription-churn.md#review-a-prediction-status-and-results)。</span><span class="sxs-lookup"><span data-stu-id="8c737-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="8c737-224">任務 5 - 建立高流失風險客戶的區段</span><span class="sxs-lookup"><span data-stu-id="8c737-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="8c737-225">執行生產模型會一併建立您可以在 **資料** > **實體** 中看見的新實體。</span><span class="sxs-lookup"><span data-stu-id="8c737-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="8c737-226">您可以根據模型建立的實體基礎建立新區段。</span><span class="sxs-lookup"><span data-stu-id="8c737-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="8c737-227">前往 **區段**。</span><span class="sxs-lookup"><span data-stu-id="8c737-227">Go to **Segments**.</span></span> <span data-ttu-id="8c737-228">選取 **新增** 並選擇 **從** > **智慧** 建立。</span><span class="sxs-lookup"><span data-stu-id="8c737-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="使用模型輸出建立區段。":::

1. <span data-ttu-id="8c737-230">選取 **OOBSubscriptionChurnPrediction** 端點並定義區段：</span><span class="sxs-lookup"><span data-stu-id="8c737-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="8c737-231">欄位：ChurnScore</span><span class="sxs-lookup"><span data-stu-id="8c737-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="8c737-232">運算子：大於</span><span class="sxs-lookup"><span data-stu-id="8c737-232">Operator: greater than</span></span>
   - <span data-ttu-id="8c737-233">值：0.6</span><span class="sxs-lookup"><span data-stu-id="8c737-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="設定訂閱流失區段。":::

<span data-ttu-id="8c737-235">您現在有動態更新的區段，其找出對此訂閱業務而言屬於高流失風險的客戶。</span><span class="sxs-lookup"><span data-stu-id="8c737-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="8c737-236">如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="8c737-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]