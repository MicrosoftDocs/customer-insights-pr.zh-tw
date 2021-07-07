---
title: 交易性流失預測範例指南
description: 使用此範例指南試用交易性流失創意預測模型。
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306110"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="a0af7-103">交易性流失預測 (預覽版) 範例指南</span><span class="sxs-lookup"><span data-stu-id="a0af7-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="a0af7-104">本指南將以 Customer Insights 在交易性流失預測範例使用的下方資料從頭到尾向您說明。</span><span class="sxs-lookup"><span data-stu-id="a0af7-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="a0af7-105">本指南中使用的所有資料都不是真實客戶數據，是在 Customer Insights 訂閱中 *示範* 環境中的 Contoso 資料集的一部分。</span><span class="sxs-lookup"><span data-stu-id="a0af7-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="a0af7-106">案例</span><span class="sxs-lookup"><span data-stu-id="a0af7-106">Scenario</span></span>

<span data-ttu-id="a0af7-107">Contoso 是生產高品質咖啡和咖啡機的一家公司，並透過其 Contoso 咖啡網站進行銷售。</span><span class="sxs-lookup"><span data-stu-id="a0af7-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="a0af7-108">他們的目標是了解典型上定期購買他們產品的客戶在未來 60 天將不再是有效客戶。</span><span class="sxs-lookup"><span data-stu-id="a0af7-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="a0af7-109">知道哪一位客戶 **很有可能流失** 可協助他們持續聚焦行銷力量。</span><span class="sxs-lookup"><span data-stu-id="a0af7-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a0af7-110">先決條件</span><span class="sxs-lookup"><span data-stu-id="a0af7-110">Prerequisites</span></span>

- <span data-ttu-id="a0af7-111">至少有 Customer Insights 中的[參與者權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="a0af7-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="a0af7-112">我們建議您 [在新環境中](manage-environments.md) 執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="a0af7-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="a0af7-113">任務 1 - 內嵌資料</span><span class="sxs-lookup"><span data-stu-id="a0af7-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="a0af7-114">具體回顧這些文章 [關於資料內嵌](data-sources.md) 和 [使用 Power Query 連接器匯入資料來源](connect-power-query.md)。</span><span class="sxs-lookup"><span data-stu-id="a0af7-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="a0af7-115">下列資訊假定您大體上已熟悉內嵌資料。</span><span class="sxs-lookup"><span data-stu-id="a0af7-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="a0af7-116">從電子商務平台內嵌客戶資料</span><span class="sxs-lookup"><span data-stu-id="a0af7-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="a0af7-117">建立稱為 **電子商務** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="a0af7-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a0af7-118">輸入電子商務連絡人 URL https://aka.ms/ciadclasscontacts。</span><span class="sxs-lookup"><span data-stu-id="a0af7-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="a0af7-119">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a0af7-120">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="a0af7-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="a0af7-121">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="a0af7-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a0af7-122">**CreatedOn**：日期/時間/時區</span><span class="sxs-lookup"><span data-stu-id="a0af7-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="a0af7-123">![轉換出生日期到日期](media/ecommerce-dob-date.PNG "將出生日期轉換為日期")</span><span class="sxs-lookup"><span data-stu-id="a0af7-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="a0af7-124">請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="a0af7-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="a0af7-125">儲存資料來源。</span><span class="sxs-lookup"><span data-stu-id="a0af7-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="a0af7-126">內嵌線上購買資料</span><span class="sxs-lookup"><span data-stu-id="a0af7-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="a0af7-127">將另一個資料集新增到同一個 **電子商務** 資料來源。</span><span class="sxs-lookup"><span data-stu-id="a0af7-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="a0af7-128">再選擇一次 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="a0af7-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="a0af7-129">輸入 **線上購買** 資料 URL https://aka.ms/ciadclassonline。</span><span class="sxs-lookup"><span data-stu-id="a0af7-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="a0af7-130">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a0af7-131">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="a0af7-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="a0af7-132">**PurchasedOn**：日期/時間</span><span class="sxs-lookup"><span data-stu-id="a0af7-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="a0af7-133">**TotalPrice**：貨幣</span><span class="sxs-lookup"><span data-stu-id="a0af7-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="a0af7-134">請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommercePurchases**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="a0af7-135">儲存資料來源。</span><span class="sxs-lookup"><span data-stu-id="a0af7-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="a0af7-136">從忠實結構描述內嵌客戶資料</span><span class="sxs-lookup"><span data-stu-id="a0af7-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="a0af7-137">建立稱為 **LoyaltyScheme** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="a0af7-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a0af7-138">輸入電子商務連絡人 URL https://aka.ms/ciadclasscustomerloyalty。</span><span class="sxs-lookup"><span data-stu-id="a0af7-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="a0af7-139">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a0af7-140">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="a0af7-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="a0af7-141">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="a0af7-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a0af7-142">**RewardsPoints**: 整數</span><span class="sxs-lookup"><span data-stu-id="a0af7-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="a0af7-143">**CreatedOn**：日期/時間</span><span class="sxs-lookup"><span data-stu-id="a0af7-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="a0af7-144">請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="a0af7-145">儲存資料來源。</span><span class="sxs-lookup"><span data-stu-id="a0af7-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="a0af7-146">任務 2 - 資料統整</span><span class="sxs-lookup"><span data-stu-id="a0af7-146">Task 2 - Data unification</span></span>

<span data-ttu-id="a0af7-147">內嵌資料後，我們現在就會開始 **對應、比對、合併** 流程，以建立統整的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="a0af7-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="a0af7-148">如需更多資訊，請見 [資料統整](data-unification.md)。</span><span class="sxs-lookup"><span data-stu-id="a0af7-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="a0af7-149">對應</span><span class="sxs-lookup"><span data-stu-id="a0af7-149">Map</span></span>

1. <span data-ttu-id="a0af7-150">內嵌資料後，將電子商務的聯絡人與忠誠度資料對應到常用資料類型。</span><span class="sxs-lookup"><span data-stu-id="a0af7-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="a0af7-151">請前往 **資料** > **統整** > **對應**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="a0af7-152">選取代表客戶設定檔的實體 – **eCommerceContacts** 和 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="統整電子商務與忠誠度資料來源。":::

1. <span data-ttu-id="a0af7-154">選取 **ContactId** 做為 **eCommerceContacts** 主鍵，而 **LoyaltyID** 做為 **loyCustomers** 主鍵。</span><span class="sxs-lookup"><span data-stu-id="a0af7-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="統整 LoyaltyId 為主鍵。":::

### <a name="match"></a><span data-ttu-id="a0af7-156">比對</span><span class="sxs-lookup"><span data-stu-id="a0af7-156">Match</span></span>

1. <span data-ttu-id="a0af7-157">請前往 **比對** 索引標籤並選取 **設定訂單**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="a0af7-158">在 **主要** 下拉式清單中，選擇 **eCommerceContacts : eCommerce** 作為主要來源，並包含所有記錄。</span><span class="sxs-lookup"><span data-stu-id="a0af7-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="a0af7-159">在 **實體 2** 下拉清單中，選擇 **loyCustomers : LoyaltyScheme** 並包含所有記錄。</span><span class="sxs-lookup"><span data-stu-id="a0af7-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="統整比對電子商務與忠誠度。":::

1. <span data-ttu-id="a0af7-161">選取 **建立新規則**</span><span class="sxs-lookup"><span data-stu-id="a0af7-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="a0af7-162">使用 FullName 新增您的第一個條件。</span><span class="sxs-lookup"><span data-stu-id="a0af7-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="a0af7-163">在 eCommerceContacts ，請在下拉式清單中選擇 **全名**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="a0af7-164">在 loyCustomers，請在下拉式清單中選擇 **全名**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="a0af7-165">選取 **正規化** 下拉式清單並選擇 **類型 (電話、名稱、地址、...)**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="a0af7-166">設定 **精密等級**：**基本** 與 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="a0af7-167">輸入新規則名稱 **FullName、電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="a0af7-168">選取 **新增條件** 來新增電子郵件地址的第二個條件</span><span class="sxs-lookup"><span data-stu-id="a0af7-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="a0af7-169">在 eCommerceContacts 實體，請在下拉式清單中選擇 **電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="a0af7-170">在loyCustomers 實體，請在下拉式清單中選擇 **電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="a0af7-171">保留正規化空白。</span><span class="sxs-lookup"><span data-stu-id="a0af7-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="a0af7-172">設定 **精密等級**：**基本** 與 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="統整比對規則的名稱和電子郵件。":::

7. <span data-ttu-id="a0af7-174">選取 **儲存** 和 **執行**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="a0af7-175">執行合併​​</span><span class="sxs-lookup"><span data-stu-id="a0af7-175">Merge</span></span>

1. <span data-ttu-id="a0af7-176">請前往 **合併** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a0af7-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="a0af7-177">在 **loyCustomers** 實體的 **ContactId** 上，將顯示名稱變更為 **ContactIdLOYALTY**，以便將它與其他內嵌的識別碼區分開來。</span><span class="sxs-lookup"><span data-stu-id="a0af7-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="從忠誠度識別碼重新命名 contactid。":::

1. <span data-ttu-id="a0af7-179">選取 **儲存** 並 **執行** 以便開始合併流程。</span><span class="sxs-lookup"><span data-stu-id="a0af7-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="a0af7-180">任務 3 - 組態交易流失預測</span><span class="sxs-lookup"><span data-stu-id="a0af7-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="a0af7-181">現在我們可以使用統整的客戶設定檔執行訂閱流失預測。</span><span class="sxs-lookup"><span data-stu-id="a0af7-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="a0af7-182">如需詳細步驟，請見 [訂閱流失預測 (預覽版)](predict-subscription-churn.md) 文章。</span><span class="sxs-lookup"><span data-stu-id="a0af7-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="a0af7-183">前往 **智慧** > **發現** 並選取使用 **客戶流失模型**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="a0af7-184">選取 **交易性** 選項並選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="a0af7-185">將模型 **OOB 電子商務交易流失預測** 和輸出實體命名為 **OOBeCommerceChurnPrediction**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="a0af7-186">定義流失模型的兩個條件：</span><span class="sxs-lookup"><span data-stu-id="a0af7-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="a0af7-187">**預測視窗**：**至少 60** 天。</span><span class="sxs-lookup"><span data-stu-id="a0af7-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="a0af7-188">此設定定義我們未來要預測客戶流失的時間長度。</span><span class="sxs-lookup"><span data-stu-id="a0af7-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="a0af7-189">**流失定義**：**至少 60** 天。</span><span class="sxs-lookup"><span data-stu-id="a0af7-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="a0af7-190">無購買期間過後，客戶即視同已流失。</span><span class="sxs-lookup"><span data-stu-id="a0af7-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="選取模型槓桿預測視窗和流失定義。":::

1. <span data-ttu-id="a0af7-192">選取 **購買歷史記錄 (必要項目)** 和 **新增** 購買歷史資料。</span><span class="sxs-lookup"><span data-stu-id="a0af7-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="a0af7-193">新增 **eCommercePurchases：電子商務** 實體並將電子商務欄位對應到模型所需的對應欄位。</span><span class="sxs-lookup"><span data-stu-id="a0af7-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="a0af7-194">加入 **eCommercePurchases：電子商務** 實體和 **eCommerceContacts：電子商務**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="加入電子商務實體。":::

1. <span data-ttu-id="a0af7-196">選取 **下一步** 以設定模型排程。</span><span class="sxs-lookup"><span data-stu-id="a0af7-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="a0af7-197">當內嵌新資料時，模型必須定期定型以便瞭解新樣式。</span><span class="sxs-lookup"><span data-stu-id="a0af7-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="a0af7-198">本範例中，請選取 **按月**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="a0af7-199">評論所有詳細資料後，請選取 **儲存和執行**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="a0af7-200">任務 4 - 評論模型結果和解釋</span><span class="sxs-lookup"><span data-stu-id="a0af7-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="a0af7-201">讓模型完成資料的定型與計分。</span><span class="sxs-lookup"><span data-stu-id="a0af7-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="a0af7-202">您現在可以評論訂閱流失模型解釋。</span><span class="sxs-lookup"><span data-stu-id="a0af7-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="a0af7-203">如需更多資訊，請見 [評論預測狀態和結果](predict-subscription-churn.md#review-a-prediction-status-and-results)。</span><span class="sxs-lookup"><span data-stu-id="a0af7-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="a0af7-204">任務 5 - 建立高流失風險客戶的區段</span><span class="sxs-lookup"><span data-stu-id="a0af7-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="a0af7-205">執行生產模型會一併建立您可以在 **資料** > **實體** 中看見的新實體。</span><span class="sxs-lookup"><span data-stu-id="a0af7-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="a0af7-206">您可以根據模型建立的實體基礎建立新區段。</span><span class="sxs-lookup"><span data-stu-id="a0af7-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="a0af7-207">前往 **區段**。</span><span class="sxs-lookup"><span data-stu-id="a0af7-207">Go to **Segments**.</span></span> <span data-ttu-id="a0af7-208">選取 **新增** 並選擇 **從** > **智慧** 建立。</span><span class="sxs-lookup"><span data-stu-id="a0af7-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="使用模型輸出建立區段。":::

1. <span data-ttu-id="a0af7-210">選取 **OOBSubscriptionChurnPrediction** 端點並定義區段：</span><span class="sxs-lookup"><span data-stu-id="a0af7-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="a0af7-211">欄位：ChurnScore</span><span class="sxs-lookup"><span data-stu-id="a0af7-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="a0af7-212">運算子：大於</span><span class="sxs-lookup"><span data-stu-id="a0af7-212">Operator: greater than</span></span>
   - <span data-ttu-id="a0af7-213">值：0.6</span><span class="sxs-lookup"><span data-stu-id="a0af7-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="設定訂閱流失區段。":::

<span data-ttu-id="a0af7-215">您現在有動態更新的區段，其找出對此訂閱業務而言屬於高流失風險的客戶。</span><span class="sxs-lookup"><span data-stu-id="a0af7-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="a0af7-216">如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="a0af7-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]