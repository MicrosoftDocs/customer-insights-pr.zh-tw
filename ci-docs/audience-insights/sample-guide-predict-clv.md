---
title: 客戶存留期值預測範例指南
description: 您可以依循此範例指南來嘗試客戶存留期值預測的模型。
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129935"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="c5920-103">客戶存留期值 (CLV) 預測範例指南</span><span class="sxs-lookup"><span data-stu-id="c5920-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="c5920-104">本指南以範例逐步說明如何在 Customer Insights 中使用範例資料預測使用者存留期值 (CLV)。</span><span class="sxs-lookup"><span data-stu-id="c5920-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="c5920-105">案例</span><span class="sxs-lookup"><span data-stu-id="c5920-105">Scenario</span></span>

<span data-ttu-id="c5920-106">Contoso 是一家生產高品質咖啡和咖啡機的公司。</span><span class="sxs-lookup"><span data-stu-id="c5920-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="c5920-107">他們透過 Contoso 咖啡網站銷售產品。</span><span class="sxs-lookup"><span data-stu-id="c5920-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="c5920-108">公司想要了解他們的客戶在未來 12 個月所能生成的價值 (營收)。</span><span class="sxs-lookup"><span data-stu-id="c5920-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="c5920-109">知道客戶在接下來的 12 個月中的預期價值，將可讓他們將行銷活動導向價值最高的客戶。</span><span class="sxs-lookup"><span data-stu-id="c5920-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c5920-110">先決條件</span><span class="sxs-lookup"><span data-stu-id="c5920-110">Prerequisites</span></span>

- <span data-ttu-id="c5920-111">在對象見解中至少是[投稿人參與者權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c5920-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="c5920-112">我們建議您 [在新環境中](manage-environments.md) 執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="c5920-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="c5920-113">任務 1 - 內嵌資料</span><span class="sxs-lookup"><span data-stu-id="c5920-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="c5920-114">請查看文章：[關於資料擷取](data-sources.md)和 [使用 Power Query 連接器匯入資料來源](connect-power-query.md)。</span><span class="sxs-lookup"><span data-stu-id="c5920-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="c5920-115">下列資訊假定您大體上已熟悉內嵌資料。</span><span class="sxs-lookup"><span data-stu-id="c5920-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="c5920-116">從電子商務平台內嵌客戶資料</span><span class="sxs-lookup"><span data-stu-id="c5920-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="c5920-117">建立名為 **電子商務** 的資料來源，選擇匯入選項並選取 **Text/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="c5920-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c5920-118">在電子商務連絡人輸入 URL [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts)。</span><span class="sxs-lookup"><span data-stu-id="c5920-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="c5920-119">編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="c5920-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c5920-120">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="c5920-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="c5920-121">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="c5920-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="c5920-122">**CreatedOn**：日期/時間/時區</span><span class="sxs-lookup"><span data-stu-id="c5920-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="將出生日期轉換為日期。":::

1. <span data-ttu-id="c5920-124">請在右側窗格的 '名稱' 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="c5920-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="c5920-125">**儲存** 資料來源。</span><span class="sxs-lookup"><span data-stu-id="c5920-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="c5920-126">內嵌線上購買資料</span><span class="sxs-lookup"><span data-stu-id="c5920-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="c5920-127">將另一個資料集新增到同一個 **電子商務** 資料來源。</span><span class="sxs-lookup"><span data-stu-id="c5920-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="c5920-128">再選擇一次 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="c5920-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="c5920-129">輸入 **線上購買** 資料 URL https://aka.ms/ciadclassonline。</span><span class="sxs-lookup"><span data-stu-id="c5920-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="c5920-130">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="c5920-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c5920-131">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="c5920-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="c5920-132">**PurchasedOn**：日期/時間</span><span class="sxs-lookup"><span data-stu-id="c5920-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="c5920-133">**TotalPrice**：貨幣</span><span class="sxs-lookup"><span data-stu-id="c5920-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="c5920-134">請在側邊窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommercePurchases**。</span><span class="sxs-lookup"><span data-stu-id="c5920-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="c5920-135">**儲存** 資料來源。</span><span class="sxs-lookup"><span data-stu-id="c5920-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="c5920-136">從忠實結構描述內嵌客戶資料</span><span class="sxs-lookup"><span data-stu-id="c5920-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="c5920-137">建立稱為 **LoyaltyScheme** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="c5920-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c5920-138">輸入電子商務連絡人 URL https://aka.ms/ciadclasscustomerloyalty。</span><span class="sxs-lookup"><span data-stu-id="c5920-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="c5920-139">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="c5920-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c5920-140">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="c5920-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="c5920-141">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="c5920-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c5920-142">**RewardsPoints**: 整數</span><span class="sxs-lookup"><span data-stu-id="c5920-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="c5920-143">**CreatedOn**：日期/時間</span><span class="sxs-lookup"><span data-stu-id="c5920-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="c5920-144">請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="c5920-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="c5920-145">**儲存** 資料來源。</span><span class="sxs-lookup"><span data-stu-id="c5920-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="c5920-146">從網站審查中內嵌客戶資料</span><span class="sxs-lookup"><span data-stu-id="c5920-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="c5920-147">建立稱為 **網站** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="c5920-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c5920-148">輸入電子商務連絡人 URL https://aka.ms/CI-ILT/WebReviews。</span><span class="sxs-lookup"><span data-stu-id="c5920-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="c5920-149">編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。</span><span class="sxs-lookup"><span data-stu-id="c5920-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c5920-150">更新下列欄位的資料類型：</span><span class="sxs-lookup"><span data-stu-id="c5920-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c5920-151">**ReviewRating**：十進位數字</span><span class="sxs-lookup"><span data-stu-id="c5920-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="c5920-152">**ReviewDate**：日期</span><span class="sxs-lookup"><span data-stu-id="c5920-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="c5920-153">在右窗格的'名稱'欄位中，將您的資料來源從 **查詢** 重新命名為 **檢閱**。</span><span class="sxs-lookup"><span data-stu-id="c5920-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="c5920-154">**儲存** 資料來源。</span><span class="sxs-lookup"><span data-stu-id="c5920-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="c5920-155">任務 2 - 資料統整</span><span class="sxs-lookup"><span data-stu-id="c5920-155">Task 2 - Data unification</span></span>

<span data-ttu-id="c5920-156">擷取資料之後，我們會開始進行資料整合處理，以建立整合的客戶個人資料。</span><span class="sxs-lookup"><span data-stu-id="c5920-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="c5920-157">如需更多資訊，請見 [資料統整](data-unification.md)。</span><span class="sxs-lookup"><span data-stu-id="c5920-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="c5920-158">對應</span><span class="sxs-lookup"><span data-stu-id="c5920-158">Map</span></span>

1. <span data-ttu-id="c5920-159">內嵌資料後，將電子商務的聯絡人與忠誠度資料對應到常用資料類型。</span><span class="sxs-lookup"><span data-stu-id="c5920-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="c5920-160">請前往 **資料** > **統整** > **對應**。</span><span class="sxs-lookup"><span data-stu-id="c5920-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="c5920-161">選取代表客戶設定檔的實體 – **eCommerceContacts** 和 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="c5920-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="c5920-162">然後，選取 **套用**。</span><span class="sxs-lookup"><span data-stu-id="c5920-162">Then, select **Apply**.</span></span>

   ![統整電子商務與忠誠度資料來源。](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="c5920-164">選取 **ContactId** 做為 **eCommerceContacts** 主鍵，而 **LoyaltyID** 做為 **loyCustomers** 主鍵。</span><span class="sxs-lookup"><span data-stu-id="c5920-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![統整 LoyaltyId 為主鍵。](media/unify-loyaltyid.png)

1. <span data-ttu-id="c5920-166">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="c5920-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="c5920-167">比對</span><span class="sxs-lookup"><span data-stu-id="c5920-167">Match</span></span>

1. <span data-ttu-id="c5920-168">請前往 **比對** 索引標籤並選取 **設定訂單**。</span><span class="sxs-lookup"><span data-stu-id="c5920-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="c5920-169">請在 **主要** 下拉式清單中選擇 **eCommerceContacts：電子商務** 為主要來源並包括所有記錄。</span><span class="sxs-lookup"><span data-stu-id="c5920-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="c5920-170">請在 **實體 2** 下拉式清單中選擇 **loyCustomers：LoyaltyScheme** 並包括所有記錄。</span><span class="sxs-lookup"><span data-stu-id="c5920-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![統整比對電子商務與忠誠度。](media/unify-match-order.png)

1. <span data-ttu-id="c5920-172">選取 **新增規則**</span><span class="sxs-lookup"><span data-stu-id="c5920-172">Select **Add rule**</span></span>

1. <span data-ttu-id="c5920-173">使用 FullName 新增您的第一個條件。</span><span class="sxs-lookup"><span data-stu-id="c5920-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="c5920-174">eCommerceContacts 方面，請在下拉式清單中選取 **FullName**。</span><span class="sxs-lookup"><span data-stu-id="c5920-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="c5920-175">loyCustomers 方面，請在下拉式清單中選取 **FullName**。</span><span class="sxs-lookup"><span data-stu-id="c5920-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="c5920-176">選取 **標準化** 下拉式清單並選擇 **類型 (電話、名稱、地址、...)**。</span><span class="sxs-lookup"><span data-stu-id="c5920-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="c5920-177">設定 **精密等級**：**基本** 與 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="c5920-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="c5920-178">輸入新規則名稱 **FullName、電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="c5920-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="c5920-179">選取 **新增條件** 來新增電子郵件地址的第二個條件</span><span class="sxs-lookup"><span data-stu-id="c5920-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="c5920-180">實體 eCommerceContacts 方面，請在下拉式清單中選擇 **電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="c5920-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="c5920-181">實體 loyCustomers 方面，請在下拉式清單中選擇 **電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="c5920-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="c5920-182">保留正規化空白。</span><span class="sxs-lookup"><span data-stu-id="c5920-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="c5920-183">設定 **精密等級**：**基本** 與 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="c5920-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![統整比對規則的名稱和電子郵件。](media/unify-match-rule.png)

1. <span data-ttu-id="c5920-185">選取 **完成**。</span><span class="sxs-lookup"><span data-stu-id="c5920-185">Select **Done**.</span></span>

1. <span data-ttu-id="c5920-186">選取 **儲存** 和 **執行**。</span><span class="sxs-lookup"><span data-stu-id="c5920-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="c5920-187">執行合併​​</span><span class="sxs-lookup"><span data-stu-id="c5920-187">Merge</span></span>

1. <span data-ttu-id="c5920-188">請前往 **合併** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c5920-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="c5920-189">在 **loyCustomers** 實體的 **ContactId** 上，將顯示名稱變更為 **ContactIdLOYALTY**，以便將它與其他內嵌的識別碼區分開來。</span><span class="sxs-lookup"><span data-stu-id="c5920-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![從忠誠度識別碼重新命名 contactid。](media/unify-merge-contactid.png)

1. <span data-ttu-id="c5920-191">選取 **儲存** 和 **執行合併與下游程序**。</span><span class="sxs-lookup"><span data-stu-id="c5920-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="c5920-192">工作 3 - 設定客戶存留期值預測</span><span class="sxs-lookup"><span data-stu-id="c5920-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="c5920-193">透過整合客戶個人資料，我們現在可以執行客戶存留期值預測。</span><span class="sxs-lookup"><span data-stu-id="c5920-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="c5920-194">如需詳細步驟，請參閱 [客戶存留期值預測 (預覽版)](predict-customer-lifetime-value.md)。</span><span class="sxs-lookup"><span data-stu-id="c5920-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="c5920-195">移至 **智慧**  > **預測**，然後選取 **客戶存留期值模型**。</span><span class="sxs-lookup"><span data-stu-id="c5920-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="c5920-196">瀏覽側邊窗格中的資訊，然後選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="c5920-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="c5920-197">將模型命名為 **OOB 電子商務 CLV 預測** 和輸出實體 **OOBeCommerceCLVPrediction**。</span><span class="sxs-lookup"><span data-stu-id="c5920-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="c5920-198">為 CLV 模型定義模型喜好設定：</span><span class="sxs-lookup"><span data-stu-id="c5920-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="c5920-199">**預測時間間隔**：**12 個月或 1 年**。</span><span class="sxs-lookup"><span data-stu-id="c5920-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="c5920-200">這個設定定義要預測客戶存留期值到未來多遠。</span><span class="sxs-lookup"><span data-stu-id="c5920-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="c5920-201">**活躍客戶**：指定業務活躍客戶的平均。</span><span class="sxs-lookup"><span data-stu-id="c5920-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="c5920-202">設定歷史時間範圍，其中客戶必須至少有一個交易被視為有效。</span><span class="sxs-lookup"><span data-stu-id="c5920-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="c5920-203">此模型只能預測活躍的客戶 CLV。</span><span class="sxs-lookup"><span data-stu-id="c5920-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="c5920-204">選擇讓模型根據歷史交易記錄資料計算時間間隔，或選擇提供指定的時間範圍。</span><span class="sxs-lookup"><span data-stu-id="c5920-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="c5920-205">在本範例指南中，我們 **讓模型計算採購間隔**，這是預設選項。</span><span class="sxs-lookup"><span data-stu-id="c5920-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="c5920-206">**高價值客戶**：定義高價值的客戶是前百分之幾的付費客戶。</span><span class="sxs-lookup"><span data-stu-id="c5920-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="c5920-207">模型使用此輸入，以您商務定義上的高價值客戶提供結果。</span><span class="sxs-lookup"><span data-stu-id="c5920-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="c5920-208">您可以選擇讓模型定義高價值客戶。</span><span class="sxs-lookup"><span data-stu-id="c5920-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="c5920-209">它使用能產生百分位數的啟發性規則。</span><span class="sxs-lookup"><span data-stu-id="c5920-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="c5920-210">您可以定義定義高價值的客戶是前百分之幾的未來付費客戶。</span><span class="sxs-lookup"><span data-stu-id="c5920-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="c5920-211">在本範例指南中，我們手動將高價值的客戶定義為 **前 30% 的活躍付費客戶**，並選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="c5920-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV 模型的引導式體驗中的喜好設定步驟。":::

1. <span data-ttu-id="c5920-213">在 **必要的資料** 步驟，選取 **新增資料** 以提供交易歷史資料。</span><span class="sxs-lookup"><span data-stu-id="c5920-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="c5920-214">新增 **eCommercePurchases : eCommerce** 實體，並對應模型所需的屬性：</span><span class="sxs-lookup"><span data-stu-id="c5920-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="c5920-215">交易識別碼：eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="c5920-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="c5920-216">交易日期：eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="c5920-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="c5920-217">交易金額：eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="c5920-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="c5920-218">產品識別碼：eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="c5920-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="c5920-219">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="c5920-219">Select **Next**.</span></span>

1. <span data-ttu-id="c5920-220">設定 **eCommercePurchases : eCommerce** 實體和 **eCommerceContacts : eCommerce** 之間的關聯。</span><span class="sxs-lookup"><span data-stu-id="c5920-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="c5920-221">**其他資料 (可選)** 步驟可讓您新增更多的客戶活動資料。</span><span class="sxs-lookup"><span data-stu-id="c5920-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="c5920-222">這項資料可協助您深入解析客戶與您的業務間的互動，這可能會對 CLV 有貢獻。</span><span class="sxs-lookup"><span data-stu-id="c5920-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="c5920-223">新增關鍵的客戶互動 (例如 web 日誌、客戶服務記錄或獎勵計劃歷史記錄) 可以改善預測的準確性。</span><span class="sxs-lookup"><span data-stu-id="c5920-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="c5920-224">選取 **新增資料** 以包括更多客戶活動資料。</span><span class="sxs-lookup"><span data-stu-id="c5920-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="c5920-225">新增客戶活動實體，並將其欄位名稱對應至模型所需的對應欄位：</span><span class="sxs-lookup"><span data-stu-id="c5920-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="c5920-226">客戶活動實體：Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="c5920-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="c5920-227">主索引鍵：Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="c5920-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="c5920-228">時間戳記：Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="c5920-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="c5920-229">事件 (活動名稱)：Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="c5920-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="c5920-230">詳細資料 (金額或值)：Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="c5920-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="c5920-231">選取 **下一步**，然後設定交易資料與客戶資料間的活動與關聯：</span><span class="sxs-lookup"><span data-stu-id="c5920-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="c5920-232">活動類型：選擇現有</span><span class="sxs-lookup"><span data-stu-id="c5920-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="c5920-233">活動標籤：檢閱</span><span class="sxs-lookup"><span data-stu-id="c5920-233">Activity label: Review</span></span>
   - <span data-ttu-id="c5920-234">對應的標籤：Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="c5920-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="c5920-235">客戶實體：eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="c5920-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="c5920-236">關聯：WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="c5920-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="c5920-237">選取 **下一步** 以設定模型排程。</span><span class="sxs-lookup"><span data-stu-id="c5920-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="c5920-238">模型需要定期進行定型，在擷取到新的資料時，學習新的模式。</span><span class="sxs-lookup"><span data-stu-id="c5920-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="c5920-239">在這個範例中，請選擇 **每月**。</span><span class="sxs-lookup"><span data-stu-id="c5920-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="c5920-240">檢閱所有詳細資料後，請選取 **儲存和執行**。</span><span class="sxs-lookup"><span data-stu-id="c5920-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="c5920-241">任務 4 - 評論模型結果和解釋</span><span class="sxs-lookup"><span data-stu-id="c5920-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="c5920-242">讓模型完成資料的定型與計分。</span><span class="sxs-lookup"><span data-stu-id="c5920-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="c5920-243">接下來，您可以檢閱 CLV 模型結果和解釋。</span><span class="sxs-lookup"><span data-stu-id="c5920-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="c5920-244">如需更多資訊，請見 [評論預測狀態和結果](predict-customer-lifetime-value.md#review-prediction-status-and-results)。</span><span class="sxs-lookup"><span data-stu-id="c5920-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="c5920-245">工作 5 - 建立高價值客戶的客戶細分</span><span class="sxs-lookup"><span data-stu-id="c5920-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="c5920-246">執行模型會建立新的實體，列在 **資料** > **實體** 中。</span><span class="sxs-lookup"><span data-stu-id="c5920-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="c5920-247">您可以依據模型所建立的實體來建立新的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="c5920-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="c5920-248">前往 **區段**。</span><span class="sxs-lookup"><span data-stu-id="c5920-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="c5920-249">選取 **新增** 並選擇 **從...建立** > **智慧**。</span><span class="sxs-lookup"><span data-stu-id="c5920-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![使用模型輸出建立區段。](media/segment-intelligence.png)

1. <span data-ttu-id="c5920-251">選取 **OOBeCommerceCLVPrediction** 實體並定義客戶細分：</span><span class="sxs-lookup"><span data-stu-id="c5920-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="c5920-252">欄位：CLVScore</span><span class="sxs-lookup"><span data-stu-id="c5920-252">Field: CLVScore</span></span>
  - <span data-ttu-id="c5920-253">運算子：大於</span><span class="sxs-lookup"><span data-stu-id="c5920-253">Operator: greater than</span></span>
  - <span data-ttu-id="c5920-254">值：1500</span><span class="sxs-lookup"><span data-stu-id="c5920-254">Value: 1500</span></span>

1. <span data-ttu-id="c5920-255">選取 **檢閱** 並 **儲存** 客戶細分。</span><span class="sxs-lookup"><span data-stu-id="c5920-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="c5920-256">您現在有一個客戶細分，能識別出接下來的 12 個月中，預計生成超過 $1500 營收的客戶。</span><span class="sxs-lookup"><span data-stu-id="c5920-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="c5920-257">若擷取更多的資料，則會動態更新此分段。</span><span class="sxs-lookup"><span data-stu-id="c5920-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="c5920-258">如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="c5920-258">For more information, see [Create and manage segments](segments.md).</span></span>
