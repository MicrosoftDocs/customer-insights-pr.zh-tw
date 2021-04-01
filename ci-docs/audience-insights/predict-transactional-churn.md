---
title: 交易性流失預測
description: 預測客戶是否面臨不再購買您的產品或服務的風險。
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f120e9e3cf8d40d913c7fa6a81fbf9facd045e3c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597179"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="827de-103">交易性流失預測 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="827de-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="827de-104">交易性流失預測有助於預測客戶是否會在預訂的時間視窗中不再購買您的產品或服務。</span><span class="sxs-lookup"><span data-stu-id="827de-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="827de-105">您可以在 **智慧** > **預測** 上建立新流失預測。</span><span class="sxs-lookup"><span data-stu-id="827de-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="827de-106">選取 **我的預測** 以查看您所建立的其他預測。</span><span class="sxs-lookup"><span data-stu-id="827de-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="827de-107">試用以範例資料組成的交易性流失預測教學課程：[交易性流失預測 (預覽版) 範例指南](sample-guide-predict-transactional-churn.md)。</span><span class="sxs-lookup"><span data-stu-id="827de-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="827de-108">先決條件</span><span class="sxs-lookup"><span data-stu-id="827de-108">Prerequisites</span></span>

- <span data-ttu-id="827de-109">至少有 Customer Insights 中的[參與者權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="827de-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="827de-110">可了解流失率對您的業務所具意義的商務知識。</span><span class="sxs-lookup"><span data-stu-id="827de-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="827de-111">我們支援以時間較主的流失定義，意謂在無購買期間後，客戶視同已流失。</span><span class="sxs-lookup"><span data-stu-id="827de-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="827de-112">關於您的交易/購買及其歷史記錄的資料：</span><span class="sxs-lookup"><span data-stu-id="827de-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="827de-113">區分購買/交易的交易識別碼。</span><span class="sxs-lookup"><span data-stu-id="827de-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="827de-114">比對您的客戶交易的客戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="827de-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="827de-115">交易事件日期定義發生交易的日期。</span><span class="sxs-lookup"><span data-stu-id="827de-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="827de-116">購買/交易的語義資料結構描述需要下列資訊：</span><span class="sxs-lookup"><span data-stu-id="827de-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="827de-117">**交易識別碼：** 購買或交易的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="827de-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="827de-118">**交易日期：** 購買或交易的日期。</span><span class="sxs-lookup"><span data-stu-id="827de-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="827de-119">**交易值：** 交易/品項的貨幣/數字價值金額。</span><span class="sxs-lookup"><span data-stu-id="827de-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="827de-120">(非必要) **唯一的產品識別碼：** 如果您的資料是細列項目等級，則為已購買產品或服務的識別碼。</span><span class="sxs-lookup"><span data-stu-id="827de-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="827de-121">(非必要) **是否要退還此筆交易：** 標識交易是否退還與否的真/偽欄位。</span><span class="sxs-lookup"><span data-stu-id="827de-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="827de-122">如果 **交易值** 是負值，我們也會使用此項資訊推論是否退還。</span><span class="sxs-lookup"><span data-stu-id="827de-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="827de-123">(非必要) 關於客戶活動的資料：</span><span class="sxs-lookup"><span data-stu-id="827de-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="827de-124">活動識別碼，用於區分相同類型的活動。</span><span class="sxs-lookup"><span data-stu-id="827de-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="827de-125">客戶識別碼，用於將活動對應至客戶。</span><span class="sxs-lookup"><span data-stu-id="827de-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="827de-126">活動資訊，包含活動的名稱和日期。</span><span class="sxs-lookup"><span data-stu-id="827de-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="827de-127">客戶活動的語意資料結構描述包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="827de-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="827de-128">**主索引鍵：** 活動的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="827de-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="827de-129">例如顯示客戶試用您產品樣本的網站造訪或使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="827de-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="827de-130">**時間戳記：** 由主索引鍵所識別之事件的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="827de-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="827de-131">**事件：** 您要使用的事件的名稱。</span><span class="sxs-lookup"><span data-stu-id="827de-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="827de-132">例如雜貨店內稱為 "UserAction" 的欄位可能是客戶的優惠券用途。</span><span class="sxs-lookup"><span data-stu-id="827de-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="827de-133">**詳細資料：** 關於事件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="827de-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="827de-134">例如雜貨店內稱為 "CouponValue" 的欄位可能是優惠券的貨幣值。</span><span class="sxs-lookup"><span data-stu-id="827de-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="827de-135">建立交易性流失預測</span><span class="sxs-lookup"><span data-stu-id="827de-135">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="827de-136">在 Customer Insights 中，移至 **智慧** > **預測**。</span><span class="sxs-lookup"><span data-stu-id="827de-136">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="827de-137">選取 **客戶流失模型 (預覽版)** 圖格和 **使用此模型**。</span><span class="sxs-lookup"><span data-stu-id="827de-137">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="827de-138">請在 **客戶流失模型** 窗格中選擇 **交易性** 並選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="827de-138">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="內含客戶流失模型窗格中選取的交易性選項的螢幕擷取畫面。":::

### <a name="name-model"></a><span data-ttu-id="827de-140">命名模型</span><span class="sxs-lookup"><span data-stu-id="827de-140">Name model</span></span>

1. <span data-ttu-id="827de-141">提供模型的名稱，以便與其他模型有所區分。</span><span class="sxs-lookup"><span data-stu-id="827de-141">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="827de-142">使用數字和字母提供輸出實體的名稱，不含任何空格。</span><span class="sxs-lookup"><span data-stu-id="827de-142">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="827de-143">這是模型實體將會使用的名稱。</span><span class="sxs-lookup"><span data-stu-id="827de-143">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="827de-144">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="827de-144">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="827de-145">定義客戶流失</span><span class="sxs-lookup"><span data-stu-id="827de-145">Define customer churn</span></span>

1. <span data-ttu-id="827de-146">設定天數視窗以便預測 **找出下一個可能流失的客戶** 欄位中的流失情況。</span><span class="sxs-lookup"><span data-stu-id="827de-146">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="827de-147">例如預測您的客戶在未來 90 天流失的風險，以便符合您的行銷留客心血。</span><span class="sxs-lookup"><span data-stu-id="827de-147">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="827de-148">預測較長或較短期間的風險會更難解決您的流失風險設定檔中的因素，但得視您的特定業務需求而定。</span><span class="sxs-lookup"><span data-stu-id="827de-148">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="827de-149">您隨時都可以選取 **儲存後關閉**，將預測儲存為草稿。</span><span class="sxs-lookup"><span data-stu-id="827de-149">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="827de-150">您可在 **我的預測** 索引標籤中找到草稿預測來繼續。</span><span class="sxs-lookup"><span data-stu-id="827de-150">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="827de-151">在 **客戶未於下列期間購買，視同已流失：** 欄位中輸入天數以便定義流失情況。</span><span class="sxs-lookup"><span data-stu-id="827de-151">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="827de-152">例如倘若客戶在過去 30 天內未曾購買，則可能視同您已流失他們的生意。</span><span class="sxs-lookup"><span data-stu-id="827de-152">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="827de-153">選取 **下一步** 以繼續</span><span class="sxs-lookup"><span data-stu-id="827de-153">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="827de-154">新增必要資料</span><span class="sxs-lookup"><span data-stu-id="827de-154">Add required data</span></span>

1. <span data-ttu-id="827de-155">選取 **購買歷史記錄** 的 **新增資料** 並選擇提供 [先決條件](#prerequisites) 中描述的交易/購買歷史記錄資訊的實體。</span><span class="sxs-lookup"><span data-stu-id="827de-155">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="827de-156">將語義欄位對應到您的購買歷史記錄實體中的屬性，並選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="827de-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="827de-157">如需欄位的描述，請查看[先決條件](#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="827de-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="對應採購實體的語義欄位。":::

1. <span data-ttu-id="827de-159">如果未填寫下方欄位，請將您的購買歷史記錄實體關係組態為客戶實體。</span><span class="sxs-lookup"><span data-stu-id="827de-159">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="827de-160">請選取 **購買歷史記錄實體**。</span><span class="sxs-lookup"><span data-stu-id="827de-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="827de-161">請在購買歷史記錄實體中選取找出客戶的 **欄位**。</span><span class="sxs-lookup"><span data-stu-id="827de-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="827de-162">這必須與您的客戶實體的主要客戶識別碼相關。</span><span class="sxs-lookup"><span data-stu-id="827de-162">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="827de-163">選取與主要客戶實體相配的 **客戶實體**。</span><span class="sxs-lookup"><span data-stu-id="827de-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="827de-164">輸入描述此關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="827de-164">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="購買歷史記錄頁面顯示對客戶關係的建立。":::
   
1. <span data-ttu-id="827de-166">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="827de-166">Select **Next**.</span></span>

1. <span data-ttu-id="827de-167">或者選取 **新增** **客戶活動資料**。</span><span class="sxs-lookup"><span data-stu-id="827de-167">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="827de-168">選擇提供先決條件中描述客戶活動資訊的實體。</span><span class="sxs-lookup"><span data-stu-id="827de-168">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="827de-169">將語義欄位對應到您的客戶活動實體中的屬性，並選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="827de-169">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="827de-170">如需欄位的描述，請查看[先決條件](#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="827de-170">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="為交易資料對應至客戶欄位。":::

1. <span data-ttu-id="827de-172">選取與您要設定之客戶活動類型相配的活動類型。</span><span class="sxs-lookup"><span data-stu-id="827de-172">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="827de-173">請選取 **新建** 並選擇可用的活動類型或建立新類型。</span><span class="sxs-lookup"><span data-stu-id="827de-173">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="827de-174">您必須設定從客戶活動實體到客戶實體的關聯。</span><span class="sxs-lookup"><span data-stu-id="827de-174">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="827de-175">請在客戶活動表格中選取找出客戶的欄位。</span><span class="sxs-lookup"><span data-stu-id="827de-175">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="827de-176">它可以直接攸關您的客戶實體的主要客戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="827de-176">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="827de-177">選取與主要客戶實體相配的客戶實體</span><span class="sxs-lookup"><span data-stu-id="827de-177">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="827de-178">輸入描述此關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="827de-178">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="827de-179">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="827de-179">Select **Save**.</span></span>

1. <span data-ttu-id="827de-180">如果您有任何其他想要納入的客戶活動，請重覆上述步驟。</span><span class="sxs-lookup"><span data-stu-id="827de-180">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="827de-181">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="827de-181">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="827de-182">設定排程並檢閱設定</span><span class="sxs-lookup"><span data-stu-id="827de-182">Set schedule and review configuration</span></span>

1. <span data-ttu-id="827de-183">設定保留模型的頻率。</span><span class="sxs-lookup"><span data-stu-id="827de-183">Set a frequency to retrain your model.</span></span> <span data-ttu-id="827de-184">此設定對更新預測準確度很重要，因為新資料已經內嵌。</span><span class="sxs-lookup"><span data-stu-id="827de-184">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="827de-185">大部分企業都可以每月重新定型一次，讓他們的預測取得良好的準確度。</span><span class="sxs-lookup"><span data-stu-id="827de-185">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="827de-186">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="827de-186">Select **Next**.</span></span>

1. <span data-ttu-id="827de-187">評論預測的組態。</span><span class="sxs-lookup"><span data-stu-id="827de-187">Review the configuration of the prediction.</span></span> <span data-ttu-id="827de-188">您可以藉由選取顯示值下方的 **編輯** 返回先前步驟。</span><span class="sxs-lookup"><span data-stu-id="827de-188">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="827de-189">或者，也可以從進度指示器中選取設定步驟。</span><span class="sxs-lookup"><span data-stu-id="827de-189">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="827de-190">如果所有的值都已正確設定，請選取 **儲存並執行** 以開始預測程序。</span><span class="sxs-lookup"><span data-stu-id="827de-190">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="827de-191">在 **我的預測** 索引標籤 中，您可以看到預測狀態。</span><span class="sxs-lookup"><span data-stu-id="827de-191">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="827de-192">視預測中使用的資料量而定，此程序可能需要數個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="827de-192">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="827de-193">檢閱預測狀態與結果</span><span class="sxs-lookup"><span data-stu-id="827de-193">Review a prediction status and results</span></span>

1. <span data-ttu-id="827de-194">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="827de-194">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="827de-195">選取您要檢閱的預測。</span><span class="sxs-lookup"><span data-stu-id="827de-195">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="827de-196">**預測名稱：** 建立時提供的預測名稱。</span><span class="sxs-lookup"><span data-stu-id="827de-196">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="827de-197">**預測類型：** 用於預測的模型類型</span><span class="sxs-lookup"><span data-stu-id="827de-197">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="827de-198">**輸出實體：** 用於儲存預測輸出之實體的名稱。</span><span class="sxs-lookup"><span data-stu-id="827de-198">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="827de-199">您可以在 **資料** > **實體** 中找到具有此名稱的實體。</span><span class="sxs-lookup"><span data-stu-id="827de-199">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="827de-200">**預測欄位：** 此欄位只填入某些類型的預測，並不用在流失預測中。</span><span class="sxs-lookup"><span data-stu-id="827de-200">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="827de-201">**狀態：** 預測執行狀態。</span><span class="sxs-lookup"><span data-stu-id="827de-201">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="827de-202">**已排入佇列：** 預測正等待其他流程執行。</span><span class="sxs-lookup"><span data-stu-id="827de-202">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="827de-203">**重新整理：** 預測目前正在產生將流入輸出實體的結果。</span><span class="sxs-lookup"><span data-stu-id="827de-203">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="827de-204">**失敗：** 預測執行已失敗。</span><span class="sxs-lookup"><span data-stu-id="827de-204">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="827de-205">如需更多細節，[請回顧記錄](#troubleshoot-a-failed-prediction)。</span><span class="sxs-lookup"><span data-stu-id="827de-205">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="827de-206">**已成功：** 預測已成功。</span><span class="sxs-lookup"><span data-stu-id="827de-206">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="827de-207">選取垂直省略符號下方的 **檢視** 來檢閱預測</span><span class="sxs-lookup"><span data-stu-id="827de-207">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="827de-208">**已編輯：** 變更預測設定的日期。</span><span class="sxs-lookup"><span data-stu-id="827de-208">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="827de-209">**上次重新整理：** 預測重新整理輸出實體中結果的日期。</span><span class="sxs-lookup"><span data-stu-id="827de-209">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="827de-210">選取您要檢閱結果的預測旁邊的垂直省略符號，並選取 **檢視**。</span><span class="sxs-lookup"><span data-stu-id="827de-210">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="檢視控制項以便查看預測的結果。":::   

1. <span data-ttu-id="827de-212">結果頁面中有三個主要的資料區段：</span><span class="sxs-lookup"><span data-stu-id="827de-212">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="827de-213">**定型模型效能：** A、B 或 C 是可能的分數。</span><span class="sxs-lookup"><span data-stu-id="827de-213">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="827de-214">此分數表示預測的效能，可協助您做出決定以使用輸出實體中儲存的結果。</span><span class="sxs-lookup"><span data-stu-id="827de-214">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="827de-215">分數是根據下列規則所決定：</span><span class="sxs-lookup"><span data-stu-id="827de-215">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="827de-216">**A** 當模型準確預測到至少佔總預測數 50% 時，並且當已流失客戶的準確預測百分比大於基準率至少 10% 時。</span><span class="sxs-lookup"><span data-stu-id="827de-216">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="827de-217">**B** 當模型準確預測到至少佔總預測數 50% 時，並且當已流失客戶的準確預測百分比大於基準率達到 10% 時。</span><span class="sxs-lookup"><span data-stu-id="827de-217">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="827de-218">**C** 當模型準確預測到佔總預測數 50% 以下時，或者當已流失客戶的準確預測百分比少於基準率時。</span><span class="sxs-lookup"><span data-stu-id="827de-218">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="827de-219">**基準** 採用模型的預測時間視窗輸入 (例如一年)，而模型會一分為二建立不同時段直到它達到一個月或更短期間。</span><span class="sxs-lookup"><span data-stu-id="827de-219">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="827de-220">它使用這些時段建立這個時間框架中並未購買的客戶商業規則。</span><span class="sxs-lookup"><span data-stu-id="827de-220">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="827de-221">這些客戶視同已流失。</span><span class="sxs-lookup"><span data-stu-id="827de-221">These customers are considered as churned.</span></span> <span data-ttu-id="827de-222">預測極可能流失能力最高的時段型商業規則已選為基準模型。</span><span class="sxs-lookup"><span data-stu-id="827de-222">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="827de-223">**流失可能性 (客戶數目)：** 根據預測的流失風險分組的客戶群組。</span><span class="sxs-lookup"><span data-stu-id="827de-223">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="827de-224">稍後如果您想要建立有高度流失風險的客戶細分時，此資料可以協助您。</span><span class="sxs-lookup"><span data-stu-id="827de-224">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="827de-225">這類客戶細分有助於了解客戶細分成員分界所在的位置。</span><span class="sxs-lookup"><span data-stu-id="827de-225">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="827de-226">**最具影響力的因素：** 建立預測時，有許多納入考慮的因素。</span><span class="sxs-lookup"><span data-stu-id="827de-226">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="827de-227">每個因素都會根據模型建立的彙總預測來計算其重要性。</span><span class="sxs-lookup"><span data-stu-id="827de-227">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="827de-228">您可以使用這些因素來協助驗證預測結果。</span><span class="sxs-lookup"><span data-stu-id="827de-228">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="827de-229">您也可以稍後再使用此資訊來[建立客戶細分](segments.md)，這可能有助於影響客戶的流失風險。</span><span class="sxs-lookup"><span data-stu-id="827de-229">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="827de-230">疑難排解失敗的預測</span><span class="sxs-lookup"><span data-stu-id="827de-230">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="827de-231">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="827de-231">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="827de-232">選取您要檢視錯誤記錄的預測旁的垂直刪節號。</span><span class="sxs-lookup"><span data-stu-id="827de-232">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="827de-233">選取 **記錄**。</span><span class="sxs-lookup"><span data-stu-id="827de-233">Select **Logs**.</span></span>

1. <span data-ttu-id="827de-234">檢閱所有錯誤。</span><span class="sxs-lookup"><span data-stu-id="827de-234">Review all the errors.</span></span> <span data-ttu-id="827de-235">可能發生的錯誤有數種類型，這些類型描述造成錯誤的狀況。</span><span class="sxs-lookup"><span data-stu-id="827de-235">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="827de-236">例如，沒有足夠資料而無法準確預測的錯誤，通常是透過載入額外資料到 Customer Insights 中來解決。</span><span class="sxs-lookup"><span data-stu-id="827de-236">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="827de-237">重新整理預測</span><span class="sxs-lookup"><span data-stu-id="827de-237">Refresh a prediction</span></span>

<span data-ttu-id="827de-238">測試會依照設定中所設定的同樣[資料重新整理排程](system.md#schedule-tab)自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="827de-238">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="827de-239">您也可以手動重新整理它們。</span><span class="sxs-lookup"><span data-stu-id="827de-239">You can refresh them manually too.</span></span>

1. <span data-ttu-id="827de-240">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="827de-240">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="827de-241">選取您要重新整理之預測旁邊的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="827de-241">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="827de-242">選取 **重新整理**。</span><span class="sxs-lookup"><span data-stu-id="827de-242">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="827de-243">刪除預測</span><span class="sxs-lookup"><span data-stu-id="827de-243">Delete a prediction</span></span>

<span data-ttu-id="827de-244">刪除預測也會同時移除其輸出實體。</span><span class="sxs-lookup"><span data-stu-id="827de-244">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="827de-245">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="827de-245">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="827de-246">選取您要刪除之預測旁邊的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="827de-246">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="827de-247">選取 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="827de-247">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]