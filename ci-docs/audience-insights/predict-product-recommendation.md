---
title: 產品建議預測
description: 預測一個客戶可能購買或互動的產品。
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: e46e31131a2dd5235af8221eafcd2e1d1394f3d4
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906754"
---
# <a name="product-recommendation-prediction-preview"></a><span data-ttu-id="948de-103">產品建議預測 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="948de-103">Product recommendation prediction (preview)</span></span>

<span data-ttu-id="948de-104">產品建議模型會建立一組預測的產品建議。</span><span class="sxs-lookup"><span data-stu-id="948de-104">The product recommendation model creates sets of predictive product recommendations.</span></span> <span data-ttu-id="948de-105">建議是基於先前的購買行為和具有類似購買模式的客戶而建立的。</span><span class="sxs-lookup"><span data-stu-id="948de-105">Recommendations are based on previous purchase behavior and customers with similar purchase patterns.</span></span> <span data-ttu-id="948de-106">您可以在 **智慧** > **預測** 頁面上建立新的產品建議預測。</span><span class="sxs-lookup"><span data-stu-id="948de-106">You can create new product recommendation predictions on the **Intelligence** > **Predictions** page.</span></span> <span data-ttu-id="948de-107">選取 **我的預測** 以查看您所建立的其他預測。</span><span class="sxs-lookup"><span data-stu-id="948de-107">Select **My predictions** to see other predictions that you've created.</span></span>

<span data-ttu-id="948de-108">產品建議可能受到當地法律、法規及客戶期望等限制，而模型並未特別納入考慮。</span><span class="sxs-lookup"><span data-stu-id="948de-108">Product recommendations may be subject to local laws and regulations and customer expectations, which the model is not built to specifically take into account.</span></span>  <span data-ttu-id="948de-109">使用者使用這種預測能力的時候，**必須先檢閱建議，再傳遞給您的客戶**，才能確保建議的內容符合任何適用的法律或規定以及客戶期望。</span><span class="sxs-lookup"><span data-stu-id="948de-109">As a user of this predictive capability, **you must review the recommendations prior to delivering them to your customers** to ensure you are complying with any applicable laws or regulations, and customer expectations for what you may recommend.</span></span> 

<span data-ttu-id="948de-110">此外，此模型的輸出將依據產品識別碼提供給您建議。</span><span class="sxs-lookup"><span data-stu-id="948de-110">Additionally, the output of this model will give you recommendations based on the product ID.</span></span> <span data-ttu-id="948de-111">您的傳遞機制必須將預測出的產品識別碼對應至適當的內容，讓您的客戶可以取得當地語系化、影像內容以及其他業務特定的內容或行為。</span><span class="sxs-lookup"><span data-stu-id="948de-111">Your delivery mechanism will need to map the predicted product IDs to appropriate content for your customers to account for localization, image content, and other business-specific content or behavior.</span></span>

## <a name="sample-guide"></a><span data-ttu-id="948de-112">範例指南</span><span class="sxs-lookup"><span data-stu-id="948de-112">Sample Guide</span></span>

<span data-ttu-id="948de-113">如果您想要試用此功能，但沒有能完成下面的需求的資料，您可以[建立範例實施](sample-guide-predict-product-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="948de-113">If you're interested in trying this feature but don't have data to complete the requirements below, you can [create a sample implementation](sample-guide-predict-product-recommendation.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="948de-114">先決條件</span><span class="sxs-lookup"><span data-stu-id="948de-114">Prerequisites</span></span>

- <span data-ttu-id="948de-115">至少有 Customer Insights 中的[參與者權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="948de-115">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="948de-116">商務知識，瞭解與您企業相關的各種類型產品，以及客戶如何與它們互動。</span><span class="sxs-lookup"><span data-stu-id="948de-116">Business knowledge to understand different types of products for your business and how your customers interact with them.</span></span> <span data-ttu-id="948de-117">我們的支援可建議您的客戶已購買過的產品或建議新的產品。</span><span class="sxs-lookup"><span data-stu-id="948de-117">We support recommending products that have been previously purchased by your customers or recommendations for new products.</span></span>

- <span data-ttu-id="948de-118">關於交易/購買及其歷史記錄的資料：</span><span class="sxs-lookup"><span data-stu-id="948de-118">Data about transactions, purchases, and their history:</span></span>
    - <span data-ttu-id="948de-119">區分購買或交易的交易識別碼。</span><span class="sxs-lookup"><span data-stu-id="948de-119">Transaction identifiers to distinguish purchases or transactions.</span></span>
    - <span data-ttu-id="948de-120">將客戶對應到交易的客戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="948de-120">Customer identifiers to map transactions to your customers.</span></span>
    - <span data-ttu-id="948de-121">交易事件日期指定交易發生的日期。</span><span class="sxs-lookup"><span data-stu-id="948de-121">Transaction event dates that specify dates the transaction occurred on.</span></span>
    - <span data-ttu-id="948de-122">交易記錄的產品識別碼資訊。</span><span class="sxs-lookup"><span data-stu-id="948de-122">Product ID information for the transaction.</span></span>
    - <span data-ttu-id="948de-123">(可選)用來篩選產品的產品類別目錄資料實體。</span><span class="sxs-lookup"><span data-stu-id="948de-123">(Optional) A product catalog data entity to use a product filter.</span></span>
    - <span data-ttu-id="948de-124">(可選) 交易是否為退貨。</span><span class="sxs-lookup"><span data-stu-id="948de-124">(Optional) If a transaction is a return or not.</span></span>
    - <span data-ttu-id="948de-125">語意資料結構描述需要下列資訊：</span><span class="sxs-lookup"><span data-stu-id="948de-125">The semantic data schema requires the following information:</span></span>
        - <span data-ttu-id="948de-126">**交易識別碼：** 購買或交易的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="948de-126">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="948de-127">**交易日期：** 購買或交易的日期。</span><span class="sxs-lookup"><span data-stu-id="948de-127">**Transaction date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="948de-128">**交易值**：購買或交易的數字值。</span><span class="sxs-lookup"><span data-stu-id="948de-128">**Value of the transaction:** The numerical value of the purchase or transaction.</span></span>
        - <span data-ttu-id="948de-129">**唯一的產品識別碼：** 產品識別碼，或者如果您的資料是明細項目層級，則為已購買服務的識別碼。</span><span class="sxs-lookup"><span data-stu-id="948de-129">**Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="948de-130">(可選)**購買或退貨：** 布林值欄位，其中值 *true* 表示交易是退貨。</span><span class="sxs-lookup"><span data-stu-id="948de-130">(Optional) **Purchase or return:** A boolean field where the value *true* identifies that a transaction was a return.</span></span> <span data-ttu-id="948de-131">如果未提供採購或退貨資料，然而 **交易記錄的值** 是負值，我們也會使用此資訊來推斷是退貨。</span><span class="sxs-lookup"><span data-stu-id="948de-131">If the Purchase or Return data is not provided the model and the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="948de-132">建議的資料特性：</span><span class="sxs-lookup"><span data-stu-id="948de-132">Suggested data characteristics:</span></span>
    - <span data-ttu-id="948de-133">足夠的歷史資料：至少一年的交易資料，要涵蓋一些季節性最好是 2 到 3 年。</span><span class="sxs-lookup"><span data-stu-id="948de-133">Sufficient historical data: At least one year of transactional data, preferably two to three years to include some seasonality.</span></span>
    - <span data-ttu-id="948de-134">每個客戶有多個購買：每個客戶識別碼有三個或更多交易記錄</span><span class="sxs-lookup"><span data-stu-id="948de-134">Multiple purchases per customer: Three or more transactions per Customer ID</span></span>
    - <span data-ttu-id="948de-135">客戶數量：至少 100 個客戶，最好超過 10,000 個客戶。</span><span class="sxs-lookup"><span data-stu-id="948de-135">Number of customers: At least 100 customers, preferably more than 10,000 customers.</span></span> <span data-ttu-id="948de-136">少於 100 個客戶模型會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="948de-136">The model will fail with fewer than 100 customers.</span></span>

> [!NOTE]
> - <span data-ttu-id="948de-137">模型需要客戶的交易歷史記錄。</span><span class="sxs-lookup"><span data-stu-id="948de-137">The model requires the transaction history of your customers.</span></span> <span data-ttu-id="948de-138">交易的定義非常靈活。</span><span class="sxs-lookup"><span data-stu-id="948de-138">The definition of a transaction is quite flexible.</span></span> <span data-ttu-id="948de-139">任何描述使用者-產品互動的資料都可以當作輸入。</span><span class="sxs-lookup"><span data-stu-id="948de-139">Any data that describes a user-product interaction can work as an input.</span></span> <span data-ttu-id="948de-140">例如，購買產品、上課或參加活動。</span><span class="sxs-lookup"><span data-stu-id="948de-140">For example, purchasing a product, taking a class, or attending an event.</span></span>
> - <span data-ttu-id="948de-141">目前只能設定一個交易記錄歷史記錄實體。</span><span class="sxs-lookup"><span data-stu-id="948de-141">Only one transaction history entity can be configured currently.</span></span> <span data-ttu-id="948de-142">如果有多個購買實體，請在資料內嵌之前，在 Power Query 將它們聯集。</span><span class="sxs-lookup"><span data-stu-id="948de-142">If there are multiple purchase entities, union them in Power Query before data ingestion.</span></span>
> - <span data-ttu-id="948de-143">如果訂單和訂單詳細資料是不同的實體，請於用在模型之前，先連結它們。</span><span class="sxs-lookup"><span data-stu-id="948de-143">If order and order details are different entities, join them before using in the model.</span></span> <span data-ttu-id="948de-144">在實體中只有訂單識別碼或收據識別碼時，模型無法運作。</span><span class="sxs-lookup"><span data-stu-id="948de-144">The model doesn't work with only an order ID or receipt ID in an entity.</span></span>


## <a name="create-a-product-recommendation-prediction"></a><span data-ttu-id="948de-145">建立產品建議預測</span><span class="sxs-lookup"><span data-stu-id="948de-145">Create a product recommendation prediction</span></span>

1. <span data-ttu-id="948de-146">在 Customer Insights 中，移至 **智慧** > **預測**。</span><span class="sxs-lookup"><span data-stu-id="948de-146">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="948de-147">選取 **產品建議模型 (預覽版)** 圖格和 **使用此模型**。</span><span class="sxs-lookup"><span data-stu-id="948de-147">Select the **Product recommendations model (preview)** tile and select **Use this model**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="948de-148">![使用此模型按鈕的產品建議模型圖格](media/product-recommendation-usethismodel.PNG "使用此模型按鈕的產品建議模型圖格")</span><span class="sxs-lookup"><span data-stu-id="948de-148">![Product Recommendation model tile with Use this model button](media/product-recommendation-usethismodel.PNG "Product Recommendation model tile with Use this model button")</span></span>

1. <span data-ttu-id="948de-149">查看有關模型需求的資訊。</span><span class="sxs-lookup"><span data-stu-id="948de-149">Review the information about the model requirements.</span></span> <span data-ttu-id="948de-150">如果您有必要的資料，請選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="948de-150">If you have the required data, select **Get started**.</span></span>

### <a name="name-model"></a><span data-ttu-id="948de-151">命名模型</span><span class="sxs-lookup"><span data-stu-id="948de-151">Name model</span></span>

1. <span data-ttu-id="948de-152">提供模型的名稱，以便與其他模型有所區分。</span><span class="sxs-lookup"><span data-stu-id="948de-152">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="948de-153">輸入輸出實體的名稱，名稱由字母和數位，而不需有任何空格。</span><span class="sxs-lookup"><span data-stu-id="948de-153">Enter a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="948de-154">這是模型實體將會使用的名稱。</span><span class="sxs-lookup"><span data-stu-id="948de-154">That's the name that the model entity will use.</span></span> <span data-ttu-id="948de-155">然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="948de-155">Then, select **Next**.</span></span>

### <a name="define-product-recommendation-configuration"></a><span data-ttu-id="948de-156">定義產品建議設定</span><span class="sxs-lookup"><span data-stu-id="948de-156">Define product recommendation configuration</span></span>

1. <span data-ttu-id="948de-157">設定想要向客戶建議的 **產品數目**。</span><span class="sxs-lookup"><span data-stu-id="948de-157">Set the **Number of products** you want to recommend to a customer.</span></span> <span data-ttu-id="948de-158">依照傳送方式此值填充資料。</span><span class="sxs-lookup"><span data-stu-id="948de-158">This value depends on how your delivery method fills data.</span></span> <span data-ttu-id="948de-159">如果您可以建議三種產品，請依此設定此值。</span><span class="sxs-lookup"><span data-stu-id="948de-159">If you can recommend three products, set this value accordingly.</span></span>
   
   >[!TIP]
   > <span data-ttu-id="948de-160">您隨時都可以選取 **儲存後關閉**，將預測儲存為草稿。</span><span class="sxs-lookup"><span data-stu-id="948de-160">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="948de-161">您可以在 **我的預測** 索引標籤中找到預測草稿。</span><span class="sxs-lookup"><span data-stu-id="948de-161">You'll find the draft prediction in the **My predictions** tab.</span></span>

1. <span data-ttu-id="948de-162">如果您想 **建議客戶最近購買過的產品**，請選擇。</span><span class="sxs-lookup"><span data-stu-id="948de-162">Choose if you want to **Suggest products customers have recently purchased**.</span></span>

1. <span data-ttu-id="948de-163">如果您已選取 *不要* 建議最近購買過的產品，請設定 **回顧視窗**。</span><span class="sxs-lookup"><span data-stu-id="948de-163">If you've selected to *not* recommend recently purchased products, set the **Look back window**.</span></span> <span data-ttu-id="948de-164">此設定指定模型向使用者再次推薦產品前，考量的時間範圍。</span><span class="sxs-lookup"><span data-stu-id="948de-164">This setting specifies the time frame the model considers before recommending the product to the user again.</span></span> <span data-ttu-id="948de-165">例如，指定客戶每兩年購買一台筆記本電腦。</span><span class="sxs-lookup"><span data-stu-id="948de-165">For example, indicate a customer purchases a laptop every two years.</span></span> <span data-ttu-id="948de-166">此視窗將查看過去兩年的購買歷史記錄，如果找到項目，則將該項目從建議中篩選掉。</span><span class="sxs-lookup"><span data-stu-id="948de-166">This window will look at the purchase history for the last two years, and if they find an item, the item will be filtered from the recommendations.</span></span>

1. <span data-ttu-id="948de-167">選取 **下一個**</span><span class="sxs-lookup"><span data-stu-id="948de-167">Select **Next**</span></span>

### <a name="add-required-data"></a><span data-ttu-id="948de-168">新增必要資料</span><span class="sxs-lookup"><span data-stu-id="948de-168">Add required data</span></span>

1. <span data-ttu-id="948de-169">對 **客戶交易歷史記錄** 選取 **新增資料** 接著選擇實體以提供[先決條件](#prerequisites) 中描述的交易/購買歷史記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="948de-169">Select **Add data** for **Customer transaction history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="948de-170">將語義欄位對應到您的購買歷史記錄實體中的屬性，並選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="948de-170">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="948de-171">如需欄位的描述，請查看[先決條件](#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="948de-171">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="948de-172">![定義實體關聯](media/product-recommendation-purchasehistorymapping.PNG "購買歷史記錄頁面，顯示的語意屬性可對應至選取的購買歷史記錄實體中欄位")</span><span class="sxs-lookup"><span data-stu-id="948de-172">![Define the entity relationship](media/product-recommendation-purchasehistorymapping.PNG "Purchase history page showing semantic attributes that are mapped to fields in the selected purchase history entity")</span></span>

1. <span data-ttu-id="948de-173">如果欄位未填寫，請設定購買歷史記錄實體到 *客戶* 實體的關聯。</span><span class="sxs-lookup"><span data-stu-id="948de-173">If the fields aren't filled in, configure the relationship from your purchase history entity to the *Customer* entity.</span></span>
    1. <span data-ttu-id="948de-174">請選取 **購買歷史記錄實體**。</span><span class="sxs-lookup"><span data-stu-id="948de-174">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="948de-175">請在購買歷史記錄實體中選取找出客戶的 **欄位**。</span><span class="sxs-lookup"><span data-stu-id="948de-175">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="948de-176">必須關聯到 *客戶* 實體的主要客戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="948de-176">It needs to relate to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="948de-177">選取與主要客戶實體相配的 **客戶實體**。</span><span class="sxs-lookup"><span data-stu-id="948de-177">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="948de-178">輸入描述此關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="948de-178">Enter a name that describes the relationship.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="948de-179">![購買歷史記錄頁面顯示建立對客戶的關聯](media/model-purchase-join.png "購買歷史記錄頁面顯示建立對客戶的關聯")</span><span class="sxs-lookup"><span data-stu-id="948de-179">![Purchase history page showing the creation of a relationship to customer](media/model-purchase-join.png "Purchase history page showing the creation of a relationship to customer")</span></span>

1. <span data-ttu-id="948de-180">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="948de-180">Select **Save**.</span></span>

1. <span data-ttu-id="948de-181">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="948de-181">Select **Next**.</span></span>

### <a name="configure-product-filters"></a><span data-ttu-id="948de-182">設定產品篩選</span><span class="sxs-lookup"><span data-stu-id="948de-182">Configure product filters</span></span>

<span data-ttu-id="948de-183">有些時候，您建立的預測類型只對特定產品有好處或只適用於特定產品。</span><span class="sxs-lookup"><span data-stu-id="948de-183">Sometimes, only certain products are beneficial or appropriate for the type of prediction you build.</span></span> <span data-ttu-id="948de-184">產品篩選可讓您找出有特定特徵的產品子集，來建議給客戶。</span><span class="sxs-lookup"><span data-stu-id="948de-184">Product filters let you identify a subset of products with specific characteristics to recommend to your customers.</span></span> <span data-ttu-id="948de-185">模型將使用所有可用的產品來學習模式，但只使用符合產品篩選輸出的產品。</span><span class="sxs-lookup"><span data-stu-id="948de-185">The model will use all the products available to learn patterns but only use the products matching the product filter in its output.</span></span>

1. <span data-ttu-id="948de-186">在 **新增產品資訊** 步驟中，將每一種產品的資訊新增至產品目錄。</span><span class="sxs-lookup"><span data-stu-id="948de-186">In the **Add product information** step, add your product catalog with information for each product.</span></span> <span data-ttu-id="948de-187">選取 **下一步** 對應必須的資訊。</span><span class="sxs-lookup"><span data-stu-id="948de-187">Map the information required in select **Next**.</span></span>

3. <span data-ttu-id="948de-188">在 **產品篩選** 步驟中，選擇下列選項。</span><span class="sxs-lookup"><span data-stu-id="948de-188">In the **Product filters** step, choose between the following options.</span></span>

   * <span data-ttu-id="948de-189">**無篩選**：使用產品建議預測中的全部產品。</span><span class="sxs-lookup"><span data-stu-id="948de-189">**No filters**: Use all products in the product recommendation prediction.</span></span>

   * <span data-ttu-id="948de-190">**定義特定的產品篩選**：使用產品建議預測中的特定產品。</span><span class="sxs-lookup"><span data-stu-id="948de-190">**Define specific product filters**: Use specific products in the product recommendation prediction.</span></span>

1. <span data-ttu-id="948de-191">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="948de-191">Select **Next**.</span></span>

1. <span data-ttu-id="948de-192">如果您選擇定義產品篩選，則需要立刻定義它。</span><span class="sxs-lookup"><span data-stu-id="948de-192">If you choose to define a product filter, you need to define it now.</span></span> <span data-ttu-id="948de-193">在 **產品類別目錄屬性** 窗格中，從 *產品類別目錄實體* 中選取要包含在篩選中的屬性。</span><span class="sxs-lookup"><span data-stu-id="948de-193">In the **Product catalog attributes** pane, select the attributes from your *Product Catalog entity* that you want include in the filter.</span></span>

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="側邊窗格顯示產品類別目錄實體中的屬性，可選取到產品篩選中。":::

1. <span data-ttu-id="948de-195">您可以選擇產品篩選是否要使用 **and** 或 **or** 連接子，以邏輯將選取的屬性與產品類別目錄合併。</span><span class="sxs-lookup"><span data-stu-id="948de-195">Choose if you want the product filter to use **and** or\*\* connectors to logically combine your selection of attributes from product catalog.</span></span>
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="產品篩選結合邏輯「AND」連接子的設定範例。":::

1. <span data-ttu-id="948de-197">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="948de-197">Select **Next**.</span></span>

### <a name="set-update-schedule-and-review-configuration"></a><span data-ttu-id="948de-198">設定更新排程並檢閱設定</span><span class="sxs-lookup"><span data-stu-id="948de-198">Set update schedule and review configuration</span></span>

1. <span data-ttu-id="948de-199">設定保留模型的頻率。</span><span class="sxs-lookup"><span data-stu-id="948de-199">Set a frequency to retrain your model.</span></span> <span data-ttu-id="948de-200">將新資料匯入至 Customer Insights 時，此設定對於更新預測準確度很重要。</span><span class="sxs-lookup"><span data-stu-id="948de-200">This setting is important to update the accuracy of predictions as new data is imported into Customer Insights.</span></span> <span data-ttu-id="948de-201">大部分企業都可以每月重新定型一次，讓他們的預測取得良好的準確度。</span><span class="sxs-lookup"><span data-stu-id="948de-201">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="948de-202">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="948de-202">Select **Next**.</span></span>

1. <span data-ttu-id="948de-203">檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="948de-203">Review the configuration.</span></span> <span data-ttu-id="948de-204">您可以選取顯示值底下的 **編輯**，返回預測設定的任何一部分。</span><span class="sxs-lookup"><span data-stu-id="948de-204">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="948de-205">或者，也可以從進度指示器中選取設定步驟。</span><span class="sxs-lookup"><span data-stu-id="948de-205">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="948de-206">如果所有的值都已正確設定，請選取 **儲存並執行** 以開始預測程序。</span><span class="sxs-lookup"><span data-stu-id="948de-206">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="948de-207">在 **我的預測** 索引標籤 中，您可以看到預測狀態。</span><span class="sxs-lookup"><span data-stu-id="948de-207">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="948de-208">視預測中使用的資料量而定，此程序可能需要數個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="948de-208">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="948de-209">檢閱預測狀態與結果</span><span class="sxs-lookup"><span data-stu-id="948de-209">Review a prediction status and results</span></span>

1. <span data-ttu-id="948de-210">移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="948de-210">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="948de-211">![我的預測頁面的檢視表](media/product-recommendation-mypredictions.PNG "我的預測頁面的檢視表")</span><span class="sxs-lookup"><span data-stu-id="948de-211">![View of the My Predictions page](media/product-recommendation-mypredictions.PNG "View of the My Predictions page")</span></span>

1. <span data-ttu-id="948de-212">選取您要檢閱的預測。</span><span class="sxs-lookup"><span data-stu-id="948de-212">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="948de-213">**預測名稱：** 建立預測時提供的預測名稱。</span><span class="sxs-lookup"><span data-stu-id="948de-213">**Prediction name:** The name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="948de-214">**預測類型：** 預測使用的模型類型</span><span class="sxs-lookup"><span data-stu-id="948de-214">**Prediction type:** The type of model used for the prediction</span></span>
   - <span data-ttu-id="948de-215">**輸出實體：** 用於儲存預測輸出之實體的名稱。</span><span class="sxs-lookup"><span data-stu-id="948de-215">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="948de-216">您可以在 **資料** > **實體** 中找到具有此名稱的實體。</span><span class="sxs-lookup"><span data-stu-id="948de-216">You can find an entity with this name on **Data** > **Entities**.</span></span>    
      <span data-ttu-id="948de-217">產出實體中的 *分數* 是此建議的量值。</span><span class="sxs-lookup"><span data-stu-id="948de-217">*Score* in the output entity is a quantitative measure of the recommendation.</span></span> <span data-ttu-id="948de-218">對比分數低的產品，此模型會建議分數較高的產品。</span><span class="sxs-lookup"><span data-stu-id="948de-218">The model recommends products with a higher score over products with a lower score.</span></span>
   - <span data-ttu-id="948de-219">**預測欄位：** 僅某些類型的預測需填入此欄位，並不用於產品建議預測。</span><span class="sxs-lookup"><span data-stu-id="948de-219">**Predicted field:** This field is populated only for some types of predictions, and isn't used in Product Recommendation prediction.</span></span>
   - <span data-ttu-id="948de-220">**狀態：** 預測的執行的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="948de-220">**Status:** The current status of the prediction's run.</span></span>
        - <span data-ttu-id="948de-221">**已排入佇列：** 預測目前正在等待其他要執行的程序。</span><span class="sxs-lookup"><span data-stu-id="948de-221">**Queued:** The prediction is currently waiting for other processes to run.</span></span>
        - <span data-ttu-id="948de-222">**重新整理：** 預測目前正在執行「分數」處理階段，以產生流入輸出實體的結果。</span><span class="sxs-lookup"><span data-stu-id="948de-222">**Refreshing:** The prediction is currently running the "score" stage of processing to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="948de-223">**失敗：** 預測失敗。</span><span class="sxs-lookup"><span data-stu-id="948de-223">**Failed:** the prediction has failed.</span></span> <span data-ttu-id="948de-224">選取 **記錄檔** 以取得更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="948de-224">Select **Logs** for more details.</span></span>
        - <span data-ttu-id="948de-225">**成功：** 預測已成功。</span><span class="sxs-lookup"><span data-stu-id="948de-225">**Succeeded:** the prediction has succeeded.</span></span> <span data-ttu-id="948de-226">選取垂直省略符號下方的 **檢視** 來檢閱預測</span><span class="sxs-lookup"><span data-stu-id="948de-226">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="948de-227">**已編輯：** 變更預測設定的日期。</span><span class="sxs-lookup"><span data-stu-id="948de-227">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="948de-228">**上次重新整理：** 預測重新整理輸出實體中結果的日期。</span><span class="sxs-lookup"><span data-stu-id="948de-228">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="948de-229">選取您要檢閱結果的預測旁邊的垂直省略符號，並選取 **檢視**。</span><span class="sxs-lookup"><span data-stu-id="948de-229">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="948de-230">![預測的垂直省略符號功能表的 [檢視] 選項包括編輯、重新整理、檢視、記錄和刪除](media/product-recommendation-verticalellipses.PNG "預測的垂直省略符號功能表的 [檢視] 選項包括編輯、重新整理、檢視、記錄和刪除")</span><span class="sxs-lookup"><span data-stu-id="948de-230">![View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete](media/product-recommendation-verticalellipses.PNG "View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete")</span></span>

1. <span data-ttu-id="948de-231">結果頁面中有五個主要資料區段：</span><span class="sxs-lookup"><span data-stu-id="948de-231">There are five primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="948de-232">**定型模型效能：** A、B 或 C 是可能的分數。</span><span class="sxs-lookup"><span data-stu-id="948de-232">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="948de-233">此分數表示預測的效能，可協助您做出決定以使用輸出實體中儲存的結果。</span><span class="sxs-lookup"><span data-stu-id="948de-233">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span>
        - <span data-ttu-id="948de-234">分數是根據下列規則所決定：</span><span class="sxs-lookup"><span data-stu-id="948de-234">Scores are determined based on the following rules:</span></span>
            - <span data-ttu-id="948de-235">**A** 如果 "Success @ K" 指標比基準模型至少高 10%，則該模型被視為品質 **A**。</span><span class="sxs-lookup"><span data-stu-id="948de-235">**A** The model will be considered **A** quality if the "Success @ K" metric is at least 10% more the baseline.</span></span> 
            - <span data-ttu-id="948de-236">**B** 如果 "Success @ K" 指標比基準高 0% 到 10%，則該模型被視為品質 **B**。</span><span class="sxs-lookup"><span data-stu-id="948de-236">**B** The model will be considered **B** quality if the "Success @ K" metric is 0% to 10% more than the baseline.</span></span>
            - <span data-ttu-id="948de-237">**C** 如果 "Success @ K" 指標比基準低，則該模型被視為品質 **C**。</span><span class="sxs-lookup"><span data-stu-id="948de-237">**C** The model will be considered **C** quality if the "Success @ K" metric is less than the baseline.</span></span>
               
               > [!div class="mx-imgBorder"]
               > <span data-ttu-id="948de-238">![模型效能結果的檢視](media/product-recommendation-modelperformance.PNG "模型效能結果的檢視")</span><span class="sxs-lookup"><span data-stu-id="948de-238">![View of the model performance result](media/product-recommendation-modelperformance.PNG "View of the model performance result")</span></span>
            - <span data-ttu-id="948de-239">**基準**：模型會透過所有客戶的購買總數來採用最常推薦的產品，並使用模型辨識出並習得的規則為客戶建立一組建議。</span><span class="sxs-lookup"><span data-stu-id="948de-239">**Baseline**: The model takes the top most recommended products by purchase count across all customers, and uses learned rules identified by the model to create a set of recommendations for the customers.</span></span> <span data-ttu-id="948de-240">然後，會將預測與前排名最高產品 (以購買該產品的客戶數目計算) 進行比較。</span><span class="sxs-lookup"><span data-stu-id="948de-240">The predictions are then compared to the top products, as calculated by the number of customers that had purchased the product.</span></span> <span data-ttu-id="948de-241">如果客戶的建議產品中至少有一個產品也能高購買量產品中看到，則會將他們視為基準的一部分。</span><span class="sxs-lookup"><span data-stu-id="948de-241">If a customer has at least one product in their recommended products that was also seen in the top purchased products, they're considered a part of the baseline.</span></span> <span data-ttu-id="948de-242">如果這樣的客戶每 100 位有 10 位曾購買建議的產品，則基準衡量為 10%。</span><span class="sxs-lookup"><span data-stu-id="948de-242">If there were 10 of these customers that had a recommended product purchased out of 100 total customers, the baseline would be 10%.</span></span>
            - <span data-ttu-id="948de-243">**Success @ K**：使用交易記錄時段的驗證集為所有客戶建立建議，並以此建議與交易的驗證集進行比較。</span><span class="sxs-lookup"><span data-stu-id="948de-243">**Success @ K**: Using a validation set of time period of transactions, recommendations are created for all customers and compared against the validation set of transactions.</span></span> <span data-ttu-id="948de-244">例如，在 12 個月的時段中，可能會將第 12 個月保留為資料的驗證集。</span><span class="sxs-lookup"><span data-stu-id="948de-244">For example, in a 12-month period, month 12 might be set aside as a validation set of data.</span></span> <span data-ttu-id="948de-245">如果此模型根據先前的 11 個月所學到的時間，可預測第 12 個月您所購買的至少一樣物品，則此客戶將會增加 "Success @ K" 的衡量標準。</span><span class="sxs-lookup"><span data-stu-id="948de-245">If the model predicts at least one thing you would purchase in month 12 based on what it learned from the previous 11 months, the customer would increase the "Success @ K" metric.</span></span>
    
    1. <span data-ttu-id="948de-246">**最建議的產品 (含計數)：** 為客戶預測的五種最佳的產品。</span><span class="sxs-lookup"><span data-stu-id="948de-246">**Most suggested products (with tally):** The top five products that were predicted for your customers.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="948de-247">![最建議的 5 個產品的圖表](media/product-recommendation-topproducts.PNG "最建議的 5 個產品的圖表")</span><span class="sxs-lookup"><span data-stu-id="948de-247">![Graph showing the top 5 most recommended products](media/product-recommendation-topproducts.PNG "Graph showing the top 5 most recommended products")</span></span>
    
    1. <span data-ttu-id="948de-248">**主要建議因素：** 模型會使用客戶的交易歷史記錄，來製作產品建議。</span><span class="sxs-lookup"><span data-stu-id="948de-248">**Key recommendation factors:** The model uses the customers' transaction history to make product recommendations.</span></span> <span data-ttu-id="948de-249">它會根據過去的購買內容學習模式，並尋找客戶與產品之間的相似處。</span><span class="sxs-lookup"><span data-stu-id="948de-249">It learns patterns based on past purchases and finds similarities between customers and products.</span></span> <span data-ttu-id="948de-250">然後使用這些相似處來生成產品建議。</span><span class="sxs-lookup"><span data-stu-id="948de-250">These similarities are then utilized to generate product recommendations.</span></span>
    <span data-ttu-id="948de-251">以下是可能會影響模型生成產品建議的因素。</span><span class="sxs-lookup"><span data-stu-id="948de-251">The following are the factors that could influence a product recommendation generated by the model.</span></span> 
        - <span data-ttu-id="948de-252">**過去交易**：過去的購買模式會被模型用來生成產品建議。</span><span class="sxs-lookup"><span data-stu-id="948de-252">**Past transactions**: Purchase patterns in the past were utilized by the model to generate product recommendations.</span></span> <span data-ttu-id="948de-253">例如，如果某個人最近購買了 _Surface Book 3_ 和 _Surface Pen_，則模型會建議 _Surface Arc 滑鼠_。</span><span class="sxs-lookup"><span data-stu-id="948de-253">For example, the model can recommend a _Surface Arc Mouse_ if someone recently purchased a _Surface Book 3_ and a _Surface Pen_.</span></span> <span data-ttu-id="948de-254">此模型瞭解到過去有許多客戶在購買 _Surface Book 3_ 和 _Surface Pen_ 後，就購買 _Surface Arc 滑鼠_。</span><span class="sxs-lookup"><span data-stu-id="948de-254">The model learned that historically, many customers had purchased a _Surface Arc Mouse_ after purchasing a _Surface Book 3_ and a _Surface Pen_.</span></span>
        - <span data-ttu-id="948de-255">**客戶相似性**：建議的產品在過去由表現出類似購買模式的其他客戶購買。</span><span class="sxs-lookup"><span data-stu-id="948de-255">**Customer similarity**: A recommended product was historically purchased by other customers who show similar purchase patterns.</span></span> <span data-ttu-id="948de-256">例如，因為 Jennifer 和 Brad 最近購買 _Surface 耳機 2_，John 被建議了 _Surface 耳機 2_。</span><span class="sxs-lookup"><span data-stu-id="948de-256">For example, John was recommended _Surface Headphones 2_ because Jennifer and Brad recently purchased _Surface Headphones 2_.</span></span> <span data-ttu-id="948de-257">因為他們過去都有類似的購買模式，模型相信 John 跟 Jennifer 與 Brad 相似。</span><span class="sxs-lookup"><span data-stu-id="948de-257">The model believes John is similar to Jennifer and Brad because they have historically had similar purchase patterns.</span></span>
        - <span data-ttu-id="948de-258">**產品相似性**：建議的產品與客戶先前購買的其他產品類似。</span><span class="sxs-lookup"><span data-stu-id="948de-258">**Product similarity**: A recommended product is similar to other products that the customer had previously purchased.</span></span> <span data-ttu-id="948de-259">如果產品過去會被同時購買或被類似的客戶購買，此模型會將兩種它們視為相似。</span><span class="sxs-lookup"><span data-stu-id="948de-259">The model considers two products to be similar if they were bought together or by similar customers.</span></span> <span data-ttu-id="948de-260">例如，有些人會取得 _USB 儲存裝置_ 建議，是因為他們先前購買了 _USB-C to USB 轉接器_，而且基於歷史購買模式，模型認為 _USB 儲存裝置_ 與 _USB-C to USB 轉接器_ 類似。</span><span class="sxs-lookup"><span data-stu-id="948de-260">For example, someone gets a recommendation for a _USB Storage Drive_ because they previously purchased a _USB-C to USB Adapter_ and the model believes that _USB Storage Drive_ is similar to _USB-C to USB Adapter_ based on historical purchase patterns.</span></span>

        <span data-ttu-id="948de-261">每個產品建議都會受到一個或多個因素的影響。</span><span class="sxs-lookup"><span data-stu-id="948de-261">Every product recommendation is influenced by one or more of these factors.</span></span> <span data-ttu-id="948de-262">在圖表中，會視覺化每個影響因素對建議造成影響的百分比。</span><span class="sxs-lookup"><span data-stu-id="948de-262">The percentage of recommendations where each influencing factor played a role is visualized in a chart.</span></span> <span data-ttu-id="948de-263">在下列範例中，100% 的建議受到過去交易的影響，60% 為客戶相似性，以及 22% 為產品相似性。</span><span class="sxs-lookup"><span data-stu-id="948de-263">In the following example, 100% of the recommendations were influenced by past transactions, 60% by customer similarity and 22% by product similarity.</span></span> <span data-ttu-id="948de-264">將滑鼠停留在圖表上的方塊，可查看影響因素所提供的確切百分比。</span><span class="sxs-lookup"><span data-stu-id="948de-264">Hover over the bars in the chart to see the exact percentage where the influencing factors contributed.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="948de-265">![關鍵建議因素](media/product-recommendation-keyrecommendationfactors.png "為生成產品建議，模型學習到的主要建議因素")</span><span class="sxs-lookup"><span data-stu-id="948de-265">![Key recommendation factors](media/product-recommendation-keyrecommendationfactors.png "Key recommendation factors learned by the model to generate product recommendations")</span></span>
       
     
   1. <span data-ttu-id="948de-266">**資料統計資料**：提供模型所考慮的交易、客戶及產品數量的概覽。</span><span class="sxs-lookup"><span data-stu-id="948de-266">**Data statistics**: Gives an overview of the number of transactions, customers, and products the model considered.</span></span> <span data-ttu-id="948de-267">這是根據用來學習模式和生成產品建議的輸入資料而定。</span><span class="sxs-lookup"><span data-stu-id="948de-267">It's based on the input data that was used to learn patterns and generate product recommendations.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="948de-268">![資料統計資料](media/product-recommendation-datastatistics.png "資料統計資訊關於模型使用來學習模式的 inout 資料")</span><span class="sxs-lookup"><span data-stu-id="948de-268">![Data statistics](media/product-recommendation-datastatistics.png "Data statistics around inout data used by the model to learn patterns")</span></span>

      <span data-ttu-id="948de-269">此區段顯示的統計資料是關於模型使用來學習模式並生成產品建議的資料點。</span><span class="sxs-lookup"><span data-stu-id="948de-269">This section shows stats around the data points that were used by the model to learn patterns and generate product recommendations.</span></span> <span data-ttu-id="948de-270">在模型設定中設定好的篩選，會套用在模型生成的輸出上。</span><span class="sxs-lookup"><span data-stu-id="948de-270">Filtering, as configured in the model configuration, will apply on the output generated by the model.</span></span> <span data-ttu-id="948de-271">但是，模型會使用所有可用的資料來學習模式。</span><span class="sxs-lookup"><span data-stu-id="948de-271">However, the model uses all available data to learn patterns.</span></span> <span data-ttu-id="948de-272">因此，如果您在模型設定中使用產品篩選，此區段會顯示模型分析來學習各種模式的產品總數量，這可能與符合篩選準則定義的產品數量不同。</span><span class="sxs-lookup"><span data-stu-id="948de-272">Therefore, if you use product filtering in the model configuration, this section will show the total number of products that the model analyzed to learn patterns, which might differ from the number of products that match the defined filtering criteria.</span></span>

   1. <span data-ttu-id="948de-273">**高信賴度的產品建議：** 提供給您的客戶建議範例，這些是模型認為客戶最有可能購買的。</span><span class="sxs-lookup"><span data-stu-id="948de-273">**High-confidence product recommendations:** A sample of recommendations provided to your customers that the model believes are likely to be purchased by the customer.</span></span>    
      <span data-ttu-id="948de-274">如果新增了產品類別目錄，則產品產品識別碼會被取代為產品名稱。</span><span class="sxs-lookup"><span data-stu-id="948de-274">If a product catalog is added, the product IDs get replaced with product names.</span></span> <span data-ttu-id="948de-275">產品名稱對預測提供更具備可操作性和最直觀的資訊。</span><span class="sxs-lookup"><span data-stu-id="948de-275">Product names provide a more actionable and intuitive information about the predictions.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="948de-276">![清單上是受選個別客戶組的高信賴度建議](media/product-recommendation-highconfidence.PNG "清單上是受選個別客戶組的高信賴度建議")</span><span class="sxs-lookup"><span data-stu-id="948de-276">![List showing high confidence suggestions for a select set of individual customers](media/product-recommendation-highconfidence.PNG "List showing high confidence suggestions for a select set of individual customers")</span></span>

## <a name="fix-a-failed-prediction"></a><span data-ttu-id="948de-277">修正失敗的預測</span><span class="sxs-lookup"><span data-stu-id="948de-277">Fix a failed prediction</span></span>

1. <span data-ttu-id="948de-278">移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="948de-278">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="948de-279">選取您要檢視其錯誤記錄檔的預測，並選取 **記錄檔**。</span><span class="sxs-lookup"><span data-stu-id="948de-279">Select the prediction you would like to view error logs for and select **Logs**.</span></span>

1. <span data-ttu-id="948de-280">檢閱所有錯誤。</span><span class="sxs-lookup"><span data-stu-id="948de-280">Review all the errors.</span></span> <span data-ttu-id="948de-281">可能發生的錯誤有數種類型，這些類型描述造成錯誤的狀況。</span><span class="sxs-lookup"><span data-stu-id="948de-281">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="948de-282">例如，錯誤訊息顯示沒有足夠的資料進行準確預測，通常是將更多資料載入到 Customer Insights 中來加以解析。</span><span class="sxs-lookup"><span data-stu-id="948de-282">For example, an error that there's not enough data to accurately predict is typically resolved by loading more data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="948de-283">重新整理預測</span><span class="sxs-lookup"><span data-stu-id="948de-283">Refresh a prediction</span></span>

<span data-ttu-id="948de-284">根據在設定中與[資料重新整理排程](system.md#schedule-tab)相同的設定，預測會自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="948de-284">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span>

1. <span data-ttu-id="948de-285">移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="948de-285">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="948de-286">選取您要重新整理之預測旁邊的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="948de-286">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="948de-287">選取 **重新整理**。</span><span class="sxs-lookup"><span data-stu-id="948de-287">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="948de-288">刪除預測</span><span class="sxs-lookup"><span data-stu-id="948de-288">Delete a prediction</span></span>

<span data-ttu-id="948de-289">刪除預測也會移除其輸出實體。</span><span class="sxs-lookup"><span data-stu-id="948de-289">Deleting a prediction will also remove its output entity.</span></span>

1. <span data-ttu-id="948de-290">移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="948de-290">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="948de-291">選取您要刪除之預測旁邊的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="948de-291">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="948de-292">選取 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="948de-292">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
