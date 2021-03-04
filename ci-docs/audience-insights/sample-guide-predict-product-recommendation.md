---
title: 產品建議預測範例指南
description: 使用此範例指南嘗試立即可用的產品建議預測模型。
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270474"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="beef4-103">產品建議預測 (預覽版) 範例指南</span><span class="sxs-lookup"><span data-stu-id="beef4-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="beef4-104">我們將使用的下方範例資料，逐步介紹完整的產品建議預測範例。</span><span class="sxs-lookup"><span data-stu-id="beef4-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="beef4-105">案例</span><span class="sxs-lookup"><span data-stu-id="beef4-105">Scenario</span></span>

<span data-ttu-id="beef4-106">Contoso 是一家公司，生產高品質咖啡和咖啡機，透過 Contoso 咖啡網站銷售。</span><span class="sxs-lookup"><span data-stu-id="beef4-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="beef4-107">他們的目標是瞭解他們應該建議哪些產品給他們的重複客戶。</span><span class="sxs-lookup"><span data-stu-id="beef4-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="beef4-108">知道客戶 **很可能購買** 哪些產品，可協助他們專注在特定項目並精簡行銷工作。</span><span class="sxs-lookup"><span data-stu-id="beef4-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="beef4-109">先決條件</span><span class="sxs-lookup"><span data-stu-id="beef4-109">Prerequisites</span></span>

- <span data-ttu-id="beef4-110">至少有 Customer Insights 中的[參與者權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="beef4-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="beef4-111">我們建議您 [在新環境中](manage-environments.md) 執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="beef4-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="beef4-112">任務 1 - 內嵌資料</span><span class="sxs-lookup"><span data-stu-id="beef4-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="beef4-113">具體回顧這些文章 [關於資料內嵌](data-sources.md) 和 [使用 Power Query 連接器匯入資料來源](connect-power-query.md)。</span><span class="sxs-lookup"><span data-stu-id="beef4-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="beef4-114">下列資訊假定您大體上已熟悉內嵌資料。</span><span class="sxs-lookup"><span data-stu-id="beef4-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="beef4-115">從電子商務平台內嵌客戶資料</span><span class="sxs-lookup"><span data-stu-id="beef4-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="beef4-116">建立稱為 **電子商務** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="beef4-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="beef4-117">輸入電子商務連絡人 URL https://aka.ms/ciadclasscontacts。</span><span class="sxs-lookup"><span data-stu-id="beef4-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="beef4-118">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="beef4-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="beef4-119">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="beef4-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="beef4-120">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="beef4-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="beef4-121">**CreatedOn**：日期/時間/時區</span><span class="sxs-lookup"><span data-stu-id="beef4-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="將出生日期轉換為日期。":::

5. <span data-ttu-id="beef4-123">請在右側窗格的 '名稱' 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="beef4-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="beef4-124">**儲存** 資料來源。</span><span class="sxs-lookup"><span data-stu-id="beef4-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="beef4-125">內嵌線上購買資料</span><span class="sxs-lookup"><span data-stu-id="beef4-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="beef4-126">將另一個資料集新增到同一個 **電子商務** 資料來源。</span><span class="sxs-lookup"><span data-stu-id="beef4-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="beef4-127">再選擇一次 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="beef4-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="beef4-128">輸入 **線上購買** 資料 URL https://aka.ms/ciadclassonline。</span><span class="sxs-lookup"><span data-stu-id="beef4-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="beef4-129">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="beef4-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="beef4-130">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="beef4-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="beef4-131">**PurchasedOn**：日期/時間</span><span class="sxs-lookup"><span data-stu-id="beef4-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="beef4-132">**TotalPrice**：貨幣</span><span class="sxs-lookup"><span data-stu-id="beef4-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="beef4-133">請在側邊窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommercePurchases**。</span><span class="sxs-lookup"><span data-stu-id="beef4-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="beef4-134">儲存資料來源。</span><span class="sxs-lookup"><span data-stu-id="beef4-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="beef4-135">從忠實結構描述內嵌客戶資料</span><span class="sxs-lookup"><span data-stu-id="beef4-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="beef4-136">建立稱為 **LoyaltyScheme** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="beef4-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="beef4-137">輸入電子商務連絡人 URL https://aka.ms/ciadclasscustomerloyalty。</span><span class="sxs-lookup"><span data-stu-id="beef4-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="beef4-138">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="beef4-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="beef4-139">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="beef4-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="beef4-140">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="beef4-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="beef4-141">**RewardsPoints**: 整數</span><span class="sxs-lookup"><span data-stu-id="beef4-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="beef4-142">**CreatedOn**：日期/時間</span><span class="sxs-lookup"><span data-stu-id="beef4-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="beef4-143">請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="beef4-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="beef4-144">儲存資料來源。</span><span class="sxs-lookup"><span data-stu-id="beef4-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="beef4-145">任務 2 - 資料統整</span><span class="sxs-lookup"><span data-stu-id="beef4-145">Task 2 - Data unification</span></span>

<span data-ttu-id="beef4-146">內嵌資料後，我們現在就會開始 **對應、比對、合併** 流程，以建立統整的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="beef4-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="beef4-147">如需更多資訊，請見 [資料統整](data-unification.md)。</span><span class="sxs-lookup"><span data-stu-id="beef4-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="beef4-148">對應</span><span class="sxs-lookup"><span data-stu-id="beef4-148">Map</span></span>

1. <span data-ttu-id="beef4-149">內嵌資料後，將電子商務的聯絡人與忠誠度資料對應到常用資料類型。</span><span class="sxs-lookup"><span data-stu-id="beef4-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="beef4-150">請前往 **資料** > **統整** > **對應**。</span><span class="sxs-lookup"><span data-stu-id="beef4-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="beef4-151">選取代表客戶設定檔的實體 – **eCommerceContacts** 和 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="beef4-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![統整電子商務與忠誠度資料來源。](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="beef4-153">選取 **ContactId** 做為 **eCommerceContacts** 主鍵，而 **LoyaltyID** 做為 **loyCustomers** 主鍵。</span><span class="sxs-lookup"><span data-stu-id="beef4-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![統整 LoyaltyId 為主鍵。](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="beef4-155">相符項目</span><span class="sxs-lookup"><span data-stu-id="beef4-155">Match</span></span>

1. <span data-ttu-id="beef4-156">請前往 **比對** 索引標籤並選取 **設定訂單**。</span><span class="sxs-lookup"><span data-stu-id="beef4-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="beef4-157">請在 **主要** 下拉式清單中選擇 **eCommerceContacts：電子商務** 為主要來源並包括所有記錄。</span><span class="sxs-lookup"><span data-stu-id="beef4-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="beef4-158">請在 **實體 2** 下拉式清單中選擇 **loyCustomers：LoyaltyScheme** 並包括所有記錄。</span><span class="sxs-lookup"><span data-stu-id="beef4-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![統整比對電子商務與忠誠度。](media/unify-match-order.png)

4. <span data-ttu-id="beef4-160">選取 **建立新規則**</span><span class="sxs-lookup"><span data-stu-id="beef4-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="beef4-161">使用 FullName 新增您的第一個條件。</span><span class="sxs-lookup"><span data-stu-id="beef4-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="beef4-162">eCommerceContacts 方面，請在下拉式清單中選取 **FullName**。</span><span class="sxs-lookup"><span data-stu-id="beef4-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="beef4-163">loyCustomers 方面，請在下拉式清單中選取 **FullName**。</span><span class="sxs-lookup"><span data-stu-id="beef4-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="beef4-164">選取 **正規化** 下拉式清單並選擇 **類型 (電話、名稱、地址、...)**。</span><span class="sxs-lookup"><span data-stu-id="beef4-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="beef4-165">設定 **精密等級**：**基本** 與 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="beef4-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="beef4-166">輸入新規則名稱 **FullName、電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="beef4-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="beef4-167">選取 **新增條件** 來新增電子郵件地址的第二個條件</span><span class="sxs-lookup"><span data-stu-id="beef4-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="beef4-168">實體 eCommerceContacts 方面，請在下拉式清單中選擇 **電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="beef4-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="beef4-169">實體 loyCustomers 方面，請在下拉式清單中選擇 **電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="beef4-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="beef4-170">保留正規化空白。</span><span class="sxs-lookup"><span data-stu-id="beef4-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="beef4-171">設定 **精密等級**：**基本** 與 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="beef4-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![統整比對規則的名稱和電子郵件。](media/unify-match-rule.png)

7. <span data-ttu-id="beef4-173">選取 **儲存** 和 **執行**。</span><span class="sxs-lookup"><span data-stu-id="beef4-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="beef4-174">執行合併​​</span><span class="sxs-lookup"><span data-stu-id="beef4-174">Merge</span></span>

1. <span data-ttu-id="beef4-175">請前往 **合併** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="beef4-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="beef4-176">在 **loyCustomers** 實體的 **ContactId** 上，將顯示名稱變更為 **ContactIdLOYALTY**，以便將它與其他內嵌的識別碼區分開來。</span><span class="sxs-lookup"><span data-stu-id="beef4-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![從忠誠度識別碼重新命名 contactid。](media/unify-merge-contactid.png)

1. <span data-ttu-id="beef4-178">選取 **儲存** 並 **執行** 以便開始合併流程。</span><span class="sxs-lookup"><span data-stu-id="beef4-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="beef4-179">工作 3 - 設定產品建議預測</span><span class="sxs-lookup"><span data-stu-id="beef4-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="beef4-180">現在我們可以使用統整的客戶設定檔執行訂閱流失預測。</span><span class="sxs-lookup"><span data-stu-id="beef4-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="beef4-181">移至 **智慧** > **預測** 選擇 **產品建議**。</span><span class="sxs-lookup"><span data-stu-id="beef4-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="beef4-182">請然後選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="beef4-182">Select **Get started**.</span></span>

1. <span data-ttu-id="beef4-183">模型命名為 **OOB 產品建議模型預測** 並將輸出實體命名為 **OOBProductRecommendationModelPrediction**。</span><span class="sxs-lookup"><span data-stu-id="beef4-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="beef4-184">為模型定義三個條件：</span><span class="sxs-lookup"><span data-stu-id="beef4-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="beef4-185">**產品數目**：將此值設定為 **5**。</span><span class="sxs-lookup"><span data-stu-id="beef4-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="beef4-186">這個設定為定義您想要向客戶建議多少產品。</span><span class="sxs-lookup"><span data-stu-id="beef4-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="beef4-187">**建議客戶最近購買過的產品？**：選取 **是** 表示您想要建議裡加入客戶之前先購買的產品。</span><span class="sxs-lookup"><span data-stu-id="beef4-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="beef4-188">**回顧視窗：** 至少要選取 **365 天**。</span><span class="sxs-lookup"><span data-stu-id="beef4-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="beef4-189">此設定是定義模型要回顧客戶活動的天數，用來作為其建議的輸入值。</span><span class="sxs-lookup"><span data-stu-id="beef4-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="產品建議模型的模型喜好設定。":::

1. <span data-ttu-id="beef4-191">選取購買歷史資料的 **必要資料** 和 **新增資料**。</span><span class="sxs-lookup"><span data-stu-id="beef4-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="beef4-192">新增 **eCommercePurchases：電子商務** 實體並將電子商務欄位對應到模型所需的對應欄位。</span><span class="sxs-lookup"><span data-stu-id="beef4-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="beef4-193">加入 **eCommercePurchases：電子商務** 實體和 **eCommerceContacts：電子商務**。</span><span class="sxs-lookup"><span data-stu-id="beef4-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![加入電子商務實體。](media/model-purchase-join.png)

1. <span data-ttu-id="beef4-195">選取 **下一步** 以設定模型排程。</span><span class="sxs-lookup"><span data-stu-id="beef4-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="beef4-196">當內嵌新資料時，模型必須定期定型以便瞭解新樣式。</span><span class="sxs-lookup"><span data-stu-id="beef4-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="beef4-197">本範例中，請選取 **按月**。</span><span class="sxs-lookup"><span data-stu-id="beef4-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="beef4-198">評論所有詳細資料後，請選取 **儲存和執行**。</span><span class="sxs-lookup"><span data-stu-id="beef4-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="beef4-199">任務 4 - 評論模型結果和解釋</span><span class="sxs-lookup"><span data-stu-id="beef4-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="beef4-200">讓模型完成資料的定型與計分。</span><span class="sxs-lookup"><span data-stu-id="beef4-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="beef4-201">您現在可以審閱產品建議模型說明。</span><span class="sxs-lookup"><span data-stu-id="beef4-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="beef4-202">如需更多資訊，請見 [評論預測狀態和結果](predict-subscription-churn.md#review-a-prediction-status-and-results)。</span><span class="sxs-lookup"><span data-stu-id="beef4-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="beef4-203">工作 5 - 建立高購買量產品區段</span><span class="sxs-lookup"><span data-stu-id="beef4-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="beef4-204">執行生產模型會一併建立您可以在 **資料** > **實體** 中看見的新實體。</span><span class="sxs-lookup"><span data-stu-id="beef4-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="beef4-205">您可以根據模型建立的實體基礎建立新區段。</span><span class="sxs-lookup"><span data-stu-id="beef4-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="beef4-206">前往 **區段**。</span><span class="sxs-lookup"><span data-stu-id="beef4-206">Go to **Segments**.</span></span> <span data-ttu-id="beef4-207">選取 **新增** 並選擇 **從** > **智慧** 建立。</span><span class="sxs-lookup"><span data-stu-id="beef4-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![使用模型輸出建立區段。](media/segment-intelligence.png)

1. <span data-ttu-id="beef4-209">選取 **OOBProductRecommendationModelPrediction** 端點並定義區段：</span><span class="sxs-lookup"><span data-stu-id="beef4-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="beef4-210">欄位：ProductID</span><span class="sxs-lookup"><span data-stu-id="beef4-210">Field: ProductID</span></span>
   - <span data-ttu-id="beef4-211">運算子：值</span><span class="sxs-lookup"><span data-stu-id="beef4-211">Operator: Value</span></span>
   - <span data-ttu-id="beef4-212">值：選取前三個產品識別碼</span><span class="sxs-lookup"><span data-stu-id="beef4-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="從模型結果建立區段。":::

<span data-ttu-id="beef4-214">您現在有一個動態更新的區段，能找出最可能購買三種最建議產品的客戶</span><span class="sxs-lookup"><span data-stu-id="beef4-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="beef4-215">如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="beef4-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]