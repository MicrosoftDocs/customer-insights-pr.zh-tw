---
title: 產品建議預測
description: 預測一個客戶可能購買或互動的產品。
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270475"
---
# <a name="product-recommendation-prediction-preview"></a><span data-ttu-id="a420b-103">產品建議預測 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="a420b-103">Product recommendation prediction (preview)</span></span>

<span data-ttu-id="a420b-104">產品建議模型會建立一組預測的產品建議。</span><span class="sxs-lookup"><span data-stu-id="a420b-104">The product recommendation model creates sets of predictive product recommendations.</span></span> <span data-ttu-id="a420b-105">建議是基於先前的購買行為和具有類似購買模式的客戶而建立的。</span><span class="sxs-lookup"><span data-stu-id="a420b-105">Recommendations are based on previous purchase behavior and customers with similar purchase patterns.</span></span> <span data-ttu-id="a420b-106">您可以在 **智慧** > **預測** 頁面上建立新的產品建議預測。</span><span class="sxs-lookup"><span data-stu-id="a420b-106">You can create new product recommendation predictions on the **Intelligence** > **Predictions** page.</span></span> <span data-ttu-id="a420b-107">選取 **我的預測** 以查看您所建立的其他預測。</span><span class="sxs-lookup"><span data-stu-id="a420b-107">Select **My predictions** to see other predictions that you've created.</span></span>

<span data-ttu-id="a420b-108">產品建議應取決於當地法律和法規以及客戶的期望，但此模型不是組建來專門考量這些項目。</span><span class="sxs-lookup"><span data-stu-id="a420b-108">Product recommendations may be subject to local laws and regulations as well as customer expectations, which the model is not built to specifically take into account.</span></span>  <span data-ttu-id="a420b-109">作為此預測能力的使用者，**您必須先審查建議，再傳送給您的客戶**，以確保您有遵守所有適用的法律或法規，以及客戶對建議的期待。</span><span class="sxs-lookup"><span data-stu-id="a420b-109">As a user of this predictive capability, **you must review the recommendations prior to delivering them to your customers** to ensure you are complying with any applicable laws or regulations, as well as customer expectations for what you may recommend.</span></span> 

<span data-ttu-id="a420b-110">此外，此模型的輸出將依據產品識別碼提供給您建議。</span><span class="sxs-lookup"><span data-stu-id="a420b-110">Additionally, the output of this model will give you recommendations based on the product ID.</span></span> <span data-ttu-id="a420b-111">您的傳送機制將需要取得預測的產品識別碼，並將它們對應至提供客戶的適當內容，來說明當地語系化、影像內容以及其他特定業務的內容或行為。</span><span class="sxs-lookup"><span data-stu-id="a420b-111">Your delivery mechanism will need to take predicted product IDs and map them to appropriate content for your customers to account for localization, image content, and other business specific content or behavior.</span></span>

## <a name="sample-guide"></a><span data-ttu-id="a420b-112">範例指南</span><span class="sxs-lookup"><span data-stu-id="a420b-112">Sample Guide</span></span>

<span data-ttu-id="a420b-113">如果您想要試用此功能，但沒有能完成下面的需求的資料，您可以[建立範例實施](sample-guide-predict-product-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="a420b-113">If you're interested in trying this feature but don't have data to complete the requirements below, you can [create a sample implementation](sample-guide-predict-product-recommendation.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a420b-114">先決條件</span><span class="sxs-lookup"><span data-stu-id="a420b-114">Prerequisites</span></span>

- <span data-ttu-id="a420b-115">至少有 Customer Insights 中的[參與者權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="a420b-115">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="a420b-116">商務知識，瞭解與您企業相關的各種類型產品，以及客戶如何與它們互動。</span><span class="sxs-lookup"><span data-stu-id="a420b-116">Business knowledge to understand different types of products for your business and how your customers interact with them.</span></span> <span data-ttu-id="a420b-117">我們的支援可建議您的客戶已購買過的產品或建議新的產品。</span><span class="sxs-lookup"><span data-stu-id="a420b-117">We support recommending products that have been previously purchased by your customers or recommendations for new products.</span></span>
- <span data-ttu-id="a420b-118">關於交易/購買及其歷史記錄的資料：</span><span class="sxs-lookup"><span data-stu-id="a420b-118">Data about transactions, purchases, and their history:</span></span>
    - <span data-ttu-id="a420b-119">區分購買或交易的交易識別碼。</span><span class="sxs-lookup"><span data-stu-id="a420b-119">Transaction identifiers to distinguish purchases or transactions.</span></span>
    - <span data-ttu-id="a420b-120">將客戶對應到交易的客戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="a420b-120">Customer identifiers to map transactions to your customers.</span></span>
    - <span data-ttu-id="a420b-121">交易事件日期指定交易發生的日期。</span><span class="sxs-lookup"><span data-stu-id="a420b-121">Transaction event dates that specify dates the transaction occurred on.</span></span>
    - <span data-ttu-id="a420b-122">(可選) 交易的產品識別碼資訊。</span><span class="sxs-lookup"><span data-stu-id="a420b-122">(Optional) Product ID information for the transaction.</span></span>
    - <span data-ttu-id="a420b-123">(可選) 交易是否為退貨。</span><span class="sxs-lookup"><span data-stu-id="a420b-123">(Optional) If a transaction is a return or not.</span></span>
    - <span data-ttu-id="a420b-124">語意資料結構描述需要下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a420b-124">The semantic data schema requires the following information:</span></span>
        - <span data-ttu-id="a420b-125">**交易識別碼：** 購買或交易的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a420b-125">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="a420b-126">**交易日期**：購買或交易的日期。</span><span class="sxs-lookup"><span data-stu-id="a420b-126">**Transaction date:** The date the of the purchase or transaction.</span></span>
        - <span data-ttu-id="a420b-127">**交易值**：購買或交易的數字值。</span><span class="sxs-lookup"><span data-stu-id="a420b-127">**Value of the transaction:** The numerical value of the purchase or transaction.</span></span>
        - <span data-ttu-id="a420b-128">**唯一的產品識別碼：** 產品識別碼，或者如果您的資料是明細項目層級，則為已購買服務的識別碼。</span><span class="sxs-lookup"><span data-stu-id="a420b-128">**Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="a420b-129">(可選) **購買或退貨：** 標識交易是否為退貨的是/否欄位。</span><span class="sxs-lookup"><span data-stu-id="a420b-129">(Optional) **Purchase or return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="a420b-130">如果 **交易值** 是負值，我們也會使用此項資訊推論是否退還。</span><span class="sxs-lookup"><span data-stu-id="a420b-130">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>


## <a name="create-a-product-recommendation-prediction"></a><span data-ttu-id="a420b-131">建立產品建議預測</span><span class="sxs-lookup"><span data-stu-id="a420b-131">Create a product recommendation prediction</span></span>

1. <span data-ttu-id="a420b-132">在 Customer Insights 中，移至 **智慧** > **預測**。</span><span class="sxs-lookup"><span data-stu-id="a420b-132">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="a420b-133">選取 **產品建議模型 (預覽版)** 圖格和 **使用此模型**。</span><span class="sxs-lookup"><span data-stu-id="a420b-133">Select the **Product recommendations model (preview)** tile and select **Use this model**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a420b-134">![使用此模型按鈕的產品建議模型圖格](media/product-recommendation-usethismodel.PNG "使用此模型按鈕的產品建議模型圖格")</span><span class="sxs-lookup"><span data-stu-id="a420b-134">![Product Recommendation model tile with Use this model button](media/product-recommendation-usethismodel.PNG "Product Recommendation model tile with Use this model button")</span></span>

1. <span data-ttu-id="a420b-135">查看有關模型需求的資訊。</span><span class="sxs-lookup"><span data-stu-id="a420b-135">Review the information about the model requirements.</span></span> <span data-ttu-id="a420b-136">如果您有必要的資料，請選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="a420b-136">If you have the required data, select **Get started**.</span></span>

### <a name="name-model"></a><span data-ttu-id="a420b-137">命名模型</span><span class="sxs-lookup"><span data-stu-id="a420b-137">Name model</span></span>

1. <span data-ttu-id="a420b-138">提供模型的名稱，以便與其他模型有所區分。</span><span class="sxs-lookup"><span data-stu-id="a420b-138">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="a420b-139">輸入輸出實體的名稱，名稱由字母和數位，而不需有任何空格。</span><span class="sxs-lookup"><span data-stu-id="a420b-139">Enter a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="a420b-140">這是模型實體將會使用的名稱。</span><span class="sxs-lookup"><span data-stu-id="a420b-140">That's the name that the model entity will use.</span></span> <span data-ttu-id="a420b-141">然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="a420b-141">Then, select **Next**.</span></span>

### <a name="define-product-recommendation-configuration"></a><span data-ttu-id="a420b-142">定義產品建議設定</span><span class="sxs-lookup"><span data-stu-id="a420b-142">Define product recommendation configuration</span></span>

1. <span data-ttu-id="a420b-143">設定想要向客戶建議的 **產品數目**。</span><span class="sxs-lookup"><span data-stu-id="a420b-143">Set the **Number of products** you want to recommend to a customer.</span></span> <span data-ttu-id="a420b-144">依照傳送方式此值填充資料。</span><span class="sxs-lookup"><span data-stu-id="a420b-144">This value depends on how your delivery method fills data.</span></span> <span data-ttu-id="a420b-145">如果您可以建議三種產品，請依此設定此值。</span><span class="sxs-lookup"><span data-stu-id="a420b-145">If you can recommend three products, set this value accordingly.</span></span>
   
   >[!TIP]
   > <span data-ttu-id="a420b-146">您隨時都可以選取 **儲存後關閉**，將預測儲存為草稿。</span><span class="sxs-lookup"><span data-stu-id="a420b-146">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="a420b-147">您可以在 **我的預測** 索引標籤中找到預測草稿。</span><span class="sxs-lookup"><span data-stu-id="a420b-147">You'll find the draft prediction in the **My predictions** tab.</span></span>

1. <span data-ttu-id="a420b-148">如果您想 **建議客戶最近購買過的產品**，請選擇。</span><span class="sxs-lookup"><span data-stu-id="a420b-148">Choose if you want to **Suggest products customers have recently purchased**.</span></span>

1. <span data-ttu-id="a420b-149">如果您已選取 *不要* 建議最近購買過的產品，請設定 **回顧視窗**。</span><span class="sxs-lookup"><span data-stu-id="a420b-149">If you've selected to *not* recommend recently purchased products, set the **Look back window**.</span></span> <span data-ttu-id="a420b-150">此設定指定模型向使用者再次推薦產品前，考量的時間範圍。</span><span class="sxs-lookup"><span data-stu-id="a420b-150">This setting specifies the time frame the model considers before recommending the product to the user again.</span></span> <span data-ttu-id="a420b-151">例如，標示客戶每 2 年就會購買筆記本電腦。</span><span class="sxs-lookup"><span data-stu-id="a420b-151">For example, indicate a customer purchases a laptop every 2 years.</span></span> <span data-ttu-id="a420b-152">此視窗將查看過去 2 年的購買歷史記錄，如果他們找到項目，則會將該項目從建議篩選掉。</span><span class="sxs-lookup"><span data-stu-id="a420b-152">This window will look at the purchase history for the last 2 years, and if they find an item, the item will be filtered from the recommendations.</span></span>

1. <span data-ttu-id="a420b-153">選取 **下一個**</span><span class="sxs-lookup"><span data-stu-id="a420b-153">Select **Next**</span></span>

### <a name="add-required-data"></a><span data-ttu-id="a420b-154">新增必要資料</span><span class="sxs-lookup"><span data-stu-id="a420b-154">Add required data</span></span>

1. <span data-ttu-id="a420b-155">對 **客戶交易歷史記錄** 選取 **新增資料** 接著選擇實體以提供[先決條件](#prerequisites) 中描述的交易/購買歷史記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="a420b-155">Select **Add data** for **Customer transaction history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="a420b-156">將語義欄位對應到您的購買歷史記錄實體中的屬性，並選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="a420b-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="a420b-157">如需欄位的描述，請查看[先決條件](#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="a420b-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a420b-158">![定義實體關聯](media/product-recommendation-purchasehistorymapping.PNG "購買歷史記錄頁面，顯示的語意屬性可對應至選取的購買歷史記錄實體中欄位")</span><span class="sxs-lookup"><span data-stu-id="a420b-158">![Define the entity relationship](media/product-recommendation-purchasehistorymapping.PNG "Purchase history page showing semantic attributes that are mapped to fields in the selected purchase history entity")</span></span>

1. <span data-ttu-id="a420b-159">如果欄位未填寫，請設定購買歷史記錄實體到 *客戶* 實體的關聯。</span><span class="sxs-lookup"><span data-stu-id="a420b-159">If the fields aren't filled in, configure the relationship from your purchase history entity to the *Customer* entity.</span></span>
    1. <span data-ttu-id="a420b-160">請選取 **購買歷史記錄實體**。</span><span class="sxs-lookup"><span data-stu-id="a420b-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="a420b-161">請在購買歷史記錄實體中選取找出客戶的 **欄位**。</span><span class="sxs-lookup"><span data-stu-id="a420b-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="a420b-162">必須關聯到 *客戶* 實體的主要客戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="a420b-162">It needs to relate to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="a420b-163">選取與主要客戶實體相配的 **客戶實體**。</span><span class="sxs-lookup"><span data-stu-id="a420b-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="a420b-164">輸入描述此關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="a420b-164">Enter a name that describes the relationship.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="a420b-165">![購買歷史記錄頁面顯示建立對客戶的關聯](media/model-purchase-join.png "購買歷史記錄頁面顯示建立對客戶的關聯")</span><span class="sxs-lookup"><span data-stu-id="a420b-165">![Purchase history page showing the creation of a relationship to customer](media/model-purchase-join.png "Purchase history page showing the creation of a relationship to customer")</span></span>

1. <span data-ttu-id="a420b-166">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="a420b-166">Select **Save**.</span></span>

1. <span data-ttu-id="a420b-167">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="a420b-167">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="a420b-168">設定排程並檢閱設定</span><span class="sxs-lookup"><span data-stu-id="a420b-168">Set schedule and review configuration</span></span>

1. <span data-ttu-id="a420b-169">設定保留模型的頻率。</span><span class="sxs-lookup"><span data-stu-id="a420b-169">Set a frequency to retrain your model.</span></span> <span data-ttu-id="a420b-170">將新資料匯入至 Customer Insights 時，此設定對於更新預測準確度很重要。</span><span class="sxs-lookup"><span data-stu-id="a420b-170">This setting is important to update the accuracy of predictions as new data is imported into Customer Insights.</span></span> <span data-ttu-id="a420b-171">大部分企業都可以每月重新定型一次，讓他們的預測取得良好的準確度。</span><span class="sxs-lookup"><span data-stu-id="a420b-171">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="a420b-172">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="a420b-172">Select **Next**.</span></span>

1. <span data-ttu-id="a420b-173">檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="a420b-173">Review the configuration.</span></span> <span data-ttu-id="a420b-174">您可以選取顯示值底下的 **編輯**，返回預測設定的任何一部分。</span><span class="sxs-lookup"><span data-stu-id="a420b-174">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="a420b-175">或者，也可以從進度指示器中選取設定步驟。</span><span class="sxs-lookup"><span data-stu-id="a420b-175">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="a420b-176">如果所有的值都已正確設定，請選取 **儲存並執行** 以開始預測程序。</span><span class="sxs-lookup"><span data-stu-id="a420b-176">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="a420b-177">在 **我的預測** 索引標籤 中，您可以看到預測狀態。</span><span class="sxs-lookup"><span data-stu-id="a420b-177">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="a420b-178">視預測中使用的資料量而定，此程序可能需要數個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="a420b-178">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="a420b-179">檢閱預測狀態與結果</span><span class="sxs-lookup"><span data-stu-id="a420b-179">Review a prediction status and results</span></span>

1. <span data-ttu-id="a420b-180">移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a420b-180">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a420b-181">![我的預測頁面的檢視表](media/product-recommendation-mypredictions.PNG "我的預測頁面的檢視表")</span><span class="sxs-lookup"><span data-stu-id="a420b-181">![View of the My Predictions page](media/product-recommendation-mypredictions.PNG "View of the My Predictions page")</span></span>

1. <span data-ttu-id="a420b-182">選取您要檢閱的預測。</span><span class="sxs-lookup"><span data-stu-id="a420b-182">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="a420b-183">**預測名稱：** 建立預測時提供的預測名稱。</span><span class="sxs-lookup"><span data-stu-id="a420b-183">**Prediction name:** The name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="a420b-184">**預測類型：** 預測使用的模型類型</span><span class="sxs-lookup"><span data-stu-id="a420b-184">**Prediction type:** The type of model used for the prediction</span></span>
   - <span data-ttu-id="a420b-185">**輸出實體：** 用於儲存預測輸出之實體的名稱。</span><span class="sxs-lookup"><span data-stu-id="a420b-185">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="a420b-186">您可以在 **資料** > **實體** 中找到具有此名稱的實體。</span><span class="sxs-lookup"><span data-stu-id="a420b-186">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="a420b-187">**預測欄位：** 此欄位只填入某些類型的預測，並不用在流失預測中。</span><span class="sxs-lookup"><span data-stu-id="a420b-187">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="a420b-188">**狀態：** 預測的執行的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="a420b-188">**Status:** The current status of the prediction's run.</span></span>
        - <span data-ttu-id="a420b-189">**已排入佇列：** 預測目前正在等待其他要執行的程序。</span><span class="sxs-lookup"><span data-stu-id="a420b-189">**Queued:** The prediction is currently waiting for other processes to run.</span></span>
        - <span data-ttu-id="a420b-190">**重新整理：** 預測目前正在執行「分數」處理階段，以產生流入輸出實體的結果。</span><span class="sxs-lookup"><span data-stu-id="a420b-190">**Refreshing:** The prediction is currently running the "score" stage of processing to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="a420b-191">**失敗：** 預測失敗。</span><span class="sxs-lookup"><span data-stu-id="a420b-191">**Failed:** the prediction has failed.</span></span> <span data-ttu-id="a420b-192">選取 **記錄檔** 以取得更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a420b-192">Select **Logs** for more details.</span></span>
        - <span data-ttu-id="a420b-193">**成功：** 預測已成功。</span><span class="sxs-lookup"><span data-stu-id="a420b-193">**Succeeded:** the prediction has succeeded.</span></span> <span data-ttu-id="a420b-194">選取垂直省略符號下方的 **檢視** 來檢閱預測</span><span class="sxs-lookup"><span data-stu-id="a420b-194">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="a420b-195">**已編輯：** 變更預測設定的日期。</span><span class="sxs-lookup"><span data-stu-id="a420b-195">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="a420b-196">**上次重新整理：** 預測重新整理輸出實體中結果的日期。</span><span class="sxs-lookup"><span data-stu-id="a420b-196">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="a420b-197">選取您要檢閱結果的預測旁邊的垂直省略符號，並選取 **檢視**。</span><span class="sxs-lookup"><span data-stu-id="a420b-197">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a420b-198">![預測的垂直省略符號功能表的 [檢視] 選項包括編輯、重新整理、檢視、記錄和刪除](media/product-recommendation-verticalellipses.PNG "預測的垂直省略符號功能表的 [檢視] 選項包括編輯、重新整理、檢視、記錄和刪除")</span><span class="sxs-lookup"><span data-stu-id="a420b-198">![View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete](media/product-recommendation-verticalellipses.PNG "View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete")</span></span>

1. <span data-ttu-id="a420b-199">結果頁面中有三個主要的資料區段：</span><span class="sxs-lookup"><span data-stu-id="a420b-199">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="a420b-200">**定型模型效能：** A、B 或 C 是可能的分數。</span><span class="sxs-lookup"><span data-stu-id="a420b-200">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="a420b-201">此分數表示預測的效能，可協助您做出決定以使用輸出實體中儲存的結果。</span><span class="sxs-lookup"><span data-stu-id="a420b-201">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span>
        - <span data-ttu-id="a420b-202">分數是根據下列規則所決定：</span><span class="sxs-lookup"><span data-stu-id="a420b-202">Scores are determined based on the following rules:</span></span>
            - <span data-ttu-id="a420b-203">**A** 如果 "Success @ K" 指標比基準模型至少高 10%，則該模型被視為品質 **A**。</span><span class="sxs-lookup"><span data-stu-id="a420b-203">**A** The model will be considered **A** quality if the "Success @ K" metric is at least 10% more the baseline.</span></span> 
            - <span data-ttu-id="a420b-204">**B** 如果 "Success @ K" 指標比基準模型高 0 到 10%，則該模型被視為品質 **B**。</span><span class="sxs-lookup"><span data-stu-id="a420b-204">**B** The model will be considered **B** quality if the "Success @ K" metric is 0 to 10% more than the baseline.</span></span>
            - <span data-ttu-id="a420b-205">**C** 如果 "Success @ K" 指標比基準模型低，則該模型被視為品質 **C**。</span><span class="sxs-lookup"><span data-stu-id="a420b-205">**C** The model will be considered **C** quality if the "Success @ K" metric is less than than the baseline.</span></span>
               
               > [!div class="mx-imgBorder"]
               > <span data-ttu-id="a420b-206">![模型效能結果的檢視](media/product-recommendation-modelperformance.PNG "模型效能結果的檢視")</span><span class="sxs-lookup"><span data-stu-id="a420b-206">![View of the model performance result](media/product-recommendation-modelperformance.PNG "View of the model performance result")</span></span>
            - <span data-ttu-id="a420b-207">**基準**：模型會透過所有客戶的購買總數來採用最常推薦的產品，並使用模型辨識出並習得的規則為客戶建立一組建議。</span><span class="sxs-lookup"><span data-stu-id="a420b-207">**Baseline**: The model takes the top most recommended products by purchase count across all customers, and uses learned rules identified by the model to create a set of recommendations for the customers.</span></span> <span data-ttu-id="a420b-208">然後，會將預測與前排名最高產品 (以購買該產品的客戶數目計算) 進行比較。</span><span class="sxs-lookup"><span data-stu-id="a420b-208">The predictions are then compared to the top products, as calculated by the number of customers that had purchased the product.</span></span> <span data-ttu-id="a420b-209">如果客戶的建議產品中至少有一個產品也能高購買量產品中看到，則會將他們視為基準的一部分。</span><span class="sxs-lookup"><span data-stu-id="a420b-209">If a customer has at least one product in their recommended products that was also seen in the top purchased products, they're considered a part of the baseline.</span></span> <span data-ttu-id="a420b-210">如果這樣的客戶每 100 位有 10 位曾購買建議的產品，則基準衡量為 10%。</span><span class="sxs-lookup"><span data-stu-id="a420b-210">If there were 10 of these customers that had a recommended product purchased out of 100 total customers, the baseline would be 10%.</span></span>
            - <span data-ttu-id="a420b-211">**Success @ K**：使用交易記錄時段的驗證集為所有客戶建立建議，並以此建議與交易的驗證集進行比較。</span><span class="sxs-lookup"><span data-stu-id="a420b-211">**Success @ K**: Using a validation set of time period of transactions, recommendations are created for all customers and compared against the validation set of transactions.</span></span> <span data-ttu-id="a420b-212">例如，在 12 個月的時段中，可能會將第 12 個月保留為資料的驗證集。</span><span class="sxs-lookup"><span data-stu-id="a420b-212">For example, in a 12 month period, month 12 might be set aside as a validation set of data.</span></span> <span data-ttu-id="a420b-213">如果此模型根據先前的 11 個月所學到的時間，可預測第 12 個月您所購買的至少一樣物品，則此客戶將會增加 "Success @ K" 的衡量標準。</span><span class="sxs-lookup"><span data-stu-id="a420b-213">If the model predicts at least one thing you would purchase in month 12 based on what it learned from the previous 11 months, the customer would increase the "Success @ K" metric.</span></span>
    
    1. <span data-ttu-id="a420b-214">**最建議的產品 (含計數)：** 為客戶預測的前 5 種產品。</span><span class="sxs-lookup"><span data-stu-id="a420b-214">**Most suggested products (with tally):** The top 5 products that were predicted for your customers.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="a420b-215">![最建議的 5 個產品的圖表](media/product-recommendation-topproducts.PNG "最建議的 5 個產品的圖表")</span><span class="sxs-lookup"><span data-stu-id="a420b-215">![Graph showing the top 5 most recommended products](media/product-recommendation-topproducts.PNG "Graph showing the top 5 most recommended products")</span></span>
    
    1. <span data-ttu-id="a420b-216">**高信賴度的產品建議：** 提供給您的客戶建議範例，這些是模型認為客戶最有可能購買的。</span><span class="sxs-lookup"><span data-stu-id="a420b-216">**High-confidence product recommendations:** A sample of recommendations provided to your customers that the model believes are likely to be purchased by the customer.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="a420b-217">![清單上是受選個別客戶組的高信賴度建議](media/product-recommendation-highconfidence.PNG "清單上是受選個別客戶組的高信賴度建議")</span><span class="sxs-lookup"><span data-stu-id="a420b-217">![List showing high confidence suggestions for a select set of individual customers](media/product-recommendation-highconfidence.PNG "List showing high confidence suggestions for a select set of individual customers")</span></span>

## <a name="fix-a-failed-prediction"></a><span data-ttu-id="a420b-218">修正失敗的預測</span><span class="sxs-lookup"><span data-stu-id="a420b-218">Fix a failed prediction</span></span>

1. <span data-ttu-id="a420b-219">移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a420b-219">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="a420b-220">選取您要檢視其錯誤記錄檔的預測，並選取 **記錄檔**。</span><span class="sxs-lookup"><span data-stu-id="a420b-220">Select the prediction you would like to view error logs for and select **Logs**.</span></span>

1. <span data-ttu-id="a420b-221">檢閱所有錯誤。</span><span class="sxs-lookup"><span data-stu-id="a420b-221">Review all the errors.</span></span> <span data-ttu-id="a420b-222">可能發生的錯誤有數種類型，這些類型描述造成錯誤的狀況。</span><span class="sxs-lookup"><span data-stu-id="a420b-222">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="a420b-223">例如，沒有足夠資料而無法準確預測的錯誤，通常是透過載入額外資料到 Customer Insights 中來解決。</span><span class="sxs-lookup"><span data-stu-id="a420b-223">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="a420b-224">重新整理預測</span><span class="sxs-lookup"><span data-stu-id="a420b-224">Refresh a prediction</span></span>

<span data-ttu-id="a420b-225">根據在設定中與[資料重新整理排程](system.md#schedule-tab)相同的設定，預測會自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="a420b-225">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span>

1. <span data-ttu-id="a420b-226">移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a420b-226">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="a420b-227">選取您要重新整理之預測旁邊的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="a420b-227">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="a420b-228">選取 **重新整理**。</span><span class="sxs-lookup"><span data-stu-id="a420b-228">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="a420b-229">刪除預測</span><span class="sxs-lookup"><span data-stu-id="a420b-229">Delete a prediction</span></span>

<span data-ttu-id="a420b-230">刪除預測也會移除其輸出實體。</span><span class="sxs-lookup"><span data-stu-id="a420b-230">Deleting a prediction will also remove its output entity.</span></span>

1. <span data-ttu-id="a420b-231">移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a420b-231">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="a420b-232">選取您要刪除之預測旁邊的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="a420b-232">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="a420b-233">選取 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="a420b-233">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]