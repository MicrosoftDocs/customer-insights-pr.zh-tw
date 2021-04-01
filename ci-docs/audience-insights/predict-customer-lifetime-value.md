---
title: 客戶生命週期價值預測
description: 預測活躍客戶的未來營收潛力。
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 835a9f3371a8c1b1a10d5c6901c03e1df5379d3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595788"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a><span data-ttu-id="90ea5-103">客戶生命週期價值 (CLV) 預測 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="90ea5-103">Customer lifetime value (CLV) prediction (Preview)</span></span>

<span data-ttu-id="90ea5-104">預測在一段定義好的未來時間中，個別活躍客戶將帶來的業務潛在價值 (營收)。</span><span class="sxs-lookup"><span data-stu-id="90ea5-104">Predict potential value (revenue) that individual active customers will bring in to your business through a defined future time period.</span></span> <span data-ttu-id="90ea5-105">此功能可協助您實現許多目標：</span><span class="sxs-lookup"><span data-stu-id="90ea5-105">This feature can help you achieve various goals:</span></span> 
- <span data-ttu-id="90ea5-106">找出高價值的客戶並處理這種見解</span><span class="sxs-lookup"><span data-stu-id="90ea5-106">Identify high-value customers and process this insight</span></span>
- <span data-ttu-id="90ea5-107">根據潛在價值建立策略性的客戶細分，便能在目標銷售、行銷及支援工作執行個人化行銷活動</span><span class="sxs-lookup"><span data-stu-id="90ea5-107">Create strategical customer segments based on their potential value to run personalized campaigns with targeted sales, marketing, and support efforts</span></span>
- <span data-ttu-id="90ea5-108">引導產品開發，專注能增加客戶價值的功能</span><span class="sxs-lookup"><span data-stu-id="90ea5-108">Guide product development by focusing on features tht increase customer value</span></span>
- <span data-ttu-id="90ea5-109">透過優化銷售、行銷策略、更準確地分配預算等方式來進行客戶拓展</span><span class="sxs-lookup"><span data-stu-id="90ea5-109">Optimize sales or marketing strategy and allocate budget more accurately for customer outreach</span></span>
- <span data-ttu-id="90ea5-110">透過忠誠度或獎勵計畫，識別和獎勵高價值客戶</span><span class="sxs-lookup"><span data-stu-id="90ea5-110">Recognize and reward high-value customers through loyalty or rewards programs</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="90ea5-111">先決條件</span><span class="sxs-lookup"><span data-stu-id="90ea5-111">Prerequisites</span></span>

<span data-ttu-id="90ea5-112">在開始使用之前，請思考 CLV 對企業的意義。</span><span class="sxs-lookup"><span data-stu-id="90ea5-112">Before getting started, reflect what CLV means for your business.</span></span> <span data-ttu-id="90ea5-113">目前，我們支援以交易為基礎的 CLV 預測。</span><span class="sxs-lookup"><span data-stu-id="90ea5-113">Currently, we support transaction-based CLV prediction.</span></span> <span data-ttu-id="90ea5-114">客戶的預測價值是依據商務交易的歷史記錄產生。</span><span class="sxs-lookup"><span data-stu-id="90ea5-114">The predicted value of a customer is based on history of business transactions.</span></span> <span data-ttu-id="90ea5-115">若要建立預測，您至少需要[參與者](permissions.md)權限。</span><span class="sxs-lookup"><span data-stu-id="90ea5-115">To create the prediction, you need at least [Contributor](permissions.md) permissions.</span></span>

<span data-ttu-id="90ea5-116">因為設定與執行 CLV 模型所需的時間不長，請考慮以不同輸入喜好設定建立多個模型，並比較模型結果，查看哪種模型方案最符合您的業務需求。</span><span class="sxs-lookup"><span data-stu-id="90ea5-116">Since configuring and running a CLV model doesn't take much time, consider creating several models with varying input preferences and compare model results to see which model scenario best fits your business needs.</span></span>

###  <a name="data-requirements"></a><span data-ttu-id="90ea5-117">資料需求</span><span class="sxs-lookup"><span data-stu-id="90ea5-117">Data requirements</span></span>

<span data-ttu-id="90ea5-118">下列是需要的資料，而標示為選擇性的地方，建議使用以增加模型效能。</span><span class="sxs-lookup"><span data-stu-id="90ea5-118">The following data is required, and where marked optional, recommended for increased model performance.</span></span> <span data-ttu-id="90ea5-119">模型處理的資料越多，預測就越準確。</span><span class="sxs-lookup"><span data-stu-id="90ea5-119">The more data the model can process, the more accurate the prediction will be.</span></span> <span data-ttu-id="90ea5-120">因此，我們鼓勵您盡可能內嵌更多的客戶活動資料。</span><span class="sxs-lookup"><span data-stu-id="90ea5-120">Therefore, we encourage you to ingest more customer activity data, if available.</span></span>

- <span data-ttu-id="90ea5-121">客戶識別碼：將交易記錄匹配至單一客戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="90ea5-121">Customer Identifier: Unique identifier to match transactions to an individual customer</span></span>

- <span data-ttu-id="90ea5-122">交易記錄：歷史交易記錄與下方的語意資料架構</span><span class="sxs-lookup"><span data-stu-id="90ea5-122">Transaction History: Historical transactions log with below semantic data schema</span></span>
    - <span data-ttu-id="90ea5-123">交易識別碼：交易的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="90ea5-123">Transaction ID: Unique identifier of each transaction</span></span>
    - <span data-ttu-id="90ea5-124">交易日期：日期，最好是每個交易記錄的時間戳記</span><span class="sxs-lookup"><span data-stu-id="90ea5-124">Transaction date: Date, preferably a time stamp of each transaction</span></span>
    - <span data-ttu-id="90ea5-125">交易總額：每個交易記錄的金錢價值 (例如，營收或獲利率)</span><span class="sxs-lookup"><span data-stu-id="90ea5-125">Transaction amount: Monetary value (for example, revenue or profit margin) of each transaction</span></span>
    - <span data-ttu-id="90ea5-126">指派給退貨的標籤 (選用)：布林值，表示交易是否為退貨</span><span class="sxs-lookup"><span data-stu-id="90ea5-126">Label assigned to returns (optional): Boolean value signifying whether the transaction is a return</span></span> 
    - <span data-ttu-id="90ea5-127">產品識別碼 (選用)：此交易記錄內的產品其產品識別碼</span><span class="sxs-lookup"><span data-stu-id="90ea5-127">Product ID (optional): Product ID of product involved in the transaction</span></span>

- <span data-ttu-id="90ea5-128">其他資料 (選用)，例如</span><span class="sxs-lookup"><span data-stu-id="90ea5-128">Additional data (optional), for example</span></span>
    - <span data-ttu-id="90ea5-129">網頁活動：網站訪問歷史記錄、電子郵件歷史記錄</span><span class="sxs-lookup"><span data-stu-id="90ea5-129">Web activities: website visit history, email history</span></span>
    - <span data-ttu-id="90ea5-130">忠誠度活動：忠誠度獎勵積分應計和兌換歷史記錄</span><span class="sxs-lookup"><span data-stu-id="90ea5-130">Loyalty activities: loyalty reward points accrual and redemption history</span></span>
    - <span data-ttu-id="90ea5-131">客戶服務記錄、服務電話、投訴或退貨歷史記錄</span><span class="sxs-lookup"><span data-stu-id="90ea5-131">Customer service log, service call, complaint, or return history</span></span>
- <span data-ttu-id="90ea5-132">關於客戶活動的資料 (可選)：</span><span class="sxs-lookup"><span data-stu-id="90ea5-132">Data about customer activities (optional):</span></span>
    - <span data-ttu-id="90ea5-133">活動識別碼，用於區分相同類型的活動</span><span class="sxs-lookup"><span data-stu-id="90ea5-133">Activity identifiers to distinguish activities of the same type</span></span>
    - <span data-ttu-id="90ea5-134">客戶識別碼，可將活動對應至客戶</span><span class="sxs-lookup"><span data-stu-id="90ea5-134">Customer identifiers to map activities to your customers</span></span>
    - <span data-ttu-id="90ea5-135">活動資訊，包含活動的名稱和日期</span><span class="sxs-lookup"><span data-stu-id="90ea5-135">Activity information containing the name and date of the activity</span></span>
    - <span data-ttu-id="90ea5-136">活動的語意資料結構描述包含：</span><span class="sxs-lookup"><span data-stu-id="90ea5-136">The semantic data schema for activities includes:</span></span> 
        - <span data-ttu-id="90ea5-137">主索引鍵：活動的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="90ea5-137">Primary key: A unique identifier for an activity</span></span>
        - <span data-ttu-id="90ea5-138">時間戳記：由主索引鍵辨識事件的日期和時間</span><span class="sxs-lookup"><span data-stu-id="90ea5-138">Timestamp: The date and time of the event identified by the primary key</span></span>
        - <span data-ttu-id="90ea5-139">事件 (活動名稱)：您要使用的事件名稱</span><span class="sxs-lookup"><span data-stu-id="90ea5-139">Event (activity name):  The name of event you want to use</span></span>
        - <span data-ttu-id="90ea5-140">詳細資料 (總量或價值)：有關客戶活動的詳細資料</span><span class="sxs-lookup"><span data-stu-id="90ea5-140">Details (amount or value): Details about the customer activity</span></span>

## <a name="create-a-customer-lifetime-value-prediction"></a><span data-ttu-id="90ea5-141">建立客戶生命週期價值預測</span><span class="sxs-lookup"><span data-stu-id="90ea5-141">Create a Customer Lifetime Value prediction</span></span>

1. <span data-ttu-id="90ea5-142">請在對象見解中前往 **智慧**　 > **預測**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-142">In audience insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="90ea5-143">選取 **客戶生命週期價值** 圖格，然後選取 **使用模型**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-143">Select the **Customer lifetime value** tile and select **Use model**.</span></span> 

1. <span data-ttu-id="90ea5-144">在 **客戶生命週期價值 (預覽版)** 窗格中，選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-144">In the **Customer lifetime value (preview)** pane, select **Get started**.</span></span>

1. <span data-ttu-id="90ea5-145">**命名此模型** 及 **輸出實體名稱**，將它們與其他模型或實體區分開來。</span><span class="sxs-lookup"><span data-stu-id="90ea5-145">**Name this model** and the **Output entity name** to distinguish them from other models or entities.</span></span>

1. <span data-ttu-id="90ea5-146">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-146">Select **Next**.</span></span>

### <a name="define-model-preferences"></a><span data-ttu-id="90ea5-147">定義模型喜好設定</span><span class="sxs-lookup"><span data-stu-id="90ea5-147">Define model preferences</span></span>

1. <span data-ttu-id="90ea5-148">設定 **預測時間區段**，定義未來您要預測多遠以後的 CLV。</span><span class="sxs-lookup"><span data-stu-id="90ea5-148">Set a **Prediction time period** to define how far into the future you want to predict the CLV.</span></span>    
   <span data-ttu-id="90ea5-149">根據預設，單位會設定為月。</span><span class="sxs-lookup"><span data-stu-id="90ea5-149">By default, the unit is set as months.</span></span> <span data-ttu-id="90ea5-150">您可以將它變更年，研究更遠的未來。</span><span class="sxs-lookup"><span data-stu-id="90ea5-150">You can change it to years to look further in the future.</span></span>

   > [!TIP]
   > <span data-ttu-id="90ea5-151">若要在您設定的時段精確預測 CLV，您需要有可比較時段的歷史資料。</span><span class="sxs-lookup"><span data-stu-id="90ea5-151">To accurately predict CLV for the time period you set, you need a comparable period of historical data.</span></span> <span data-ttu-id="90ea5-152">例如，如果您想要預測接下來的 12 個月，擁有至少 18 – 24 個月的歷史資料會比較好。</span><span class="sxs-lookup"><span data-stu-id="90ea5-152">For example, if you want to predict for the next 12 months, it is recommended that you have at least 18 – 24 months of historical data.</span></span>

1. <span data-ttu-id="90ea5-153">指定 **活動客戶** 在您企業中的意義。</span><span class="sxs-lookup"><span data-stu-id="90ea5-153">Specify what **Active customers** mean for your business.</span></span> <span data-ttu-id="90ea5-154">設定時間範圍，客戶在此範圍內必須至少有一個交易才能被視為活躍。</span><span class="sxs-lookup"><span data-stu-id="90ea5-154">Set the time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="90ea5-155">此模型只能預測活躍的客戶 CLV。</span><span class="sxs-lookup"><span data-stu-id="90ea5-155">The model will only predict CLV for active customers.</span></span> 
   - <span data-ttu-id="90ea5-156">**讓模型計算購買間隔 (建議使用)**：模型會分析您的資料，並根據歷史採購判斷時間長度。</span><span class="sxs-lookup"><span data-stu-id="90ea5-156">**Let model calculate purchase interval (recommended)**: The model analyzes your data and determines a time period based on historical purchases.</span></span>
   - <span data-ttu-id="90ea5-157">**手動設定間隔**：如果您擁有活躍客戶的特定業務定義，請選擇此選項，並相應地設定時間長度。</span><span class="sxs-lookup"><span data-stu-id="90ea5-157">**Set interval manually**: If you have a specific business definition of an active customer, choose this option and set the time period accordingly.</span></span>

1. <span data-ttu-id="90ea5-158">定義 **高價值客戶** 的百分位數，讓模型能提供符合您業務定義的結果。</span><span class="sxs-lookup"><span data-stu-id="90ea5-158">Define percentile of **High-value customer** to enable the model to provide results that fit your business definition.</span></span>
    - <span data-ttu-id="90ea5-159">**模型計算 (建議)**：模型會分析您的資料，並根據您的客戶交易歷史資料，判斷業務中的高價值客戶為何。</span><span class="sxs-lookup"><span data-stu-id="90ea5-159">**Model calculation (recommended)**: The model analyzes your data and determines what a high value customer might be for your business based on your customers’ transaction history.</span></span> <span data-ttu-id="90ea5-160">模型使用啟發型規則 (受 80/20 規則或柏拉圖法則而出現的) 尋找高價值客戶的比例。</span><span class="sxs-lookup"><span data-stu-id="90ea5-160">The model uses a heuristic rule (inspired by the 80/20 rule or pareto principle) to find the proportion of high-value customers.</span></span> <span data-ttu-id="90ea5-161">在歷史記錄期間內，對業務累積營收貢獻 80% 的前百分之幾的客戶被視為高價值客戶。</span><span class="sxs-lookup"><span data-stu-id="90ea5-161">The percentage of customers that contributed to 80% cumulative revenue for your business in the historical period are considered high-value customers.</span></span> <span data-ttu-id="90ea5-162">通常，80% 的累計營收是由少於 30-40% 的客戶貢獻的。</span><span class="sxs-lookup"><span data-stu-id="90ea5-162">Typically, less than 30-40% customers contribute to 80% cumulative revenue.</span></span> <span data-ttu-id="90ea5-163">但是，不同的企業和產業，這個數字可能會不同。</span><span class="sxs-lookup"><span data-stu-id="90ea5-163">However, this number might vary depending on your business and industry.</span></span>    
    - <span data-ttu-id="90ea5-164">**最活躍的客戶數百分比**：將企業的高價值客戶定義成排名前百分比之幾的活躍付費客戶。</span><span class="sxs-lookup"><span data-stu-id="90ea5-164">**Percent of top active customers**: Define high-value customers for your business as a percentile of top active paying customers.</span></span> <span data-ttu-id="90ea5-165">例如，您可以使用此選項，定義高價值的客戶為未來前 20% 的付費客戶。</span><span class="sxs-lookup"><span data-stu-id="90ea5-165">For example, you can use this option to define high-value customers as top 20% of future paying customers.</span></span>

    <span data-ttu-id="90ea5-166">如果您的企業以不同的方式定義高價值的客戶，[請跟我們說，我們樂意傾聽您的意見](https://go.microsoft.com/fwlink/?linkid=2074172)。</span><span class="sxs-lookup"><span data-stu-id="90ea5-166">If your business defines high value customers in a different way, [let us know as we would love to hear](https://go.microsoft.com/fwlink/?linkid=2074172).</span></span>

1. <span data-ttu-id="90ea5-167">選取 **下一步** 繼續進行下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="90ea5-167">Select **Next** to proceed to the next step.</span></span>

### <a name="add-required-data"></a><span data-ttu-id="90ea5-168">新增必要資料</span><span class="sxs-lookup"><span data-stu-id="90ea5-168">Add required data</span></span>

1. <span data-ttu-id="90ea5-169">在 **必要資料** 的步驟，選取 **購買歷史記錄** 的 **新增資料** 接著選擇實體來提供[先決條件](#prerequisites)中說明的交易/購買歷史記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="90ea5-169">In the **Required data** step, select **Add data** for **Customer transaction history** and choose the entity that provides the transaction history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="90ea5-170">將語義欄位對應到您的購買歷史記錄實體中的屬性，並選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-170">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span>

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="圖片上對應資料屬性給必要資料的設定步驟。":::
 
1. <span data-ttu-id="90ea5-172">如果未填寫下方欄位，設定將您的購買歷史記錄實體關聯到 *客戶* 實體並 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-172">If the fields below aren't populated, configure the relationship from your purchase history entity to the *Customer* entity and select **Save**.</span></span>
    1. <span data-ttu-id="90ea5-173">請選取交易歷史記錄實體。</span><span class="sxs-lookup"><span data-stu-id="90ea5-173">Select the transaction history entity.</span></span>
    1. <span data-ttu-id="90ea5-174">請在購買歷史記錄實體中選取辨識客戶的欄位。</span><span class="sxs-lookup"><span data-stu-id="90ea5-174">Select the field that identifies a customer in the purchase history entity.</span></span> <span data-ttu-id="90ea5-175">這必須與您的客戶實體的主要客戶識別碼相關。</span><span class="sxs-lookup"><span data-stu-id="90ea5-175">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="90ea5-176">選取符合您的主要客戶實體的實體。</span><span class="sxs-lookup"><span data-stu-id="90ea5-176">Select the entity that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="90ea5-177">輸入描述此關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="90ea5-177">Enter a name that describes the relationship.</span></span>

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="圖片上為定義客戶實體關聯的定義步驟。":::

1. <span data-ttu-id="90ea5-179">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-179">Select **Next**.</span></span>

### <a name="add-optional-data"></a><span data-ttu-id="90ea5-180">新增選擇性資料</span><span class="sxs-lookup"><span data-stu-id="90ea5-180">Add optional data</span></span>

<span data-ttu-id="90ea5-181">資料表現出關鍵客戶互動 (例如 web、客戶服務及事件記錄)，會將背景新增至交易記錄。</span><span class="sxs-lookup"><span data-stu-id="90ea5-181">Data reflecting key customer interactions (like web, customer service, and event logs) adds context to transaction records.</span></span> <span data-ttu-id="90ea5-182">在您的客戶活動資料中找到更多的模式，可以增進預測的準確性。</span><span class="sxs-lookup"><span data-stu-id="90ea5-182">More patterns found in your customer activity data can improve the accuracy of the predictions.</span></span> 

1. <span data-ttu-id="90ea5-183">在 **其他資料 (選擇性)** 步驟中，選取 **新增資料**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-183">In the **Additional data (optional)** step, select **Add data**.</span></span> <span data-ttu-id="90ea5-184">選擇客戶活動實體提供[先決條件](#prerequisites)說明的客戶活動資訊。</span><span class="sxs-lookup"><span data-stu-id="90ea5-184">Choose the customer activity entity that provides the customer activity information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="90ea5-185">將語義欄位對應到您的客戶活動實體中的屬性，並選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-185">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span>

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="圖片為對應欄位提供其他資料的設定步驟。":::

1. <span data-ttu-id="90ea5-187">為您正在新增的客戶活動，選取符合其類型的活動類型。</span><span class="sxs-lookup"><span data-stu-id="90ea5-187">Select an activity type that matches the type of customer activity you're adding.</span></span> <span data-ttu-id="90ea5-188">從現有的活動類型中選擇或新增活動類型。</span><span class="sxs-lookup"><span data-stu-id="90ea5-188">Choose from existing activity types or add a new activity type.</span></span>

1. <span data-ttu-id="90ea5-189">設定客戶活動實體到 *客戶* 實體的關聯。</span><span class="sxs-lookup"><span data-stu-id="90ea5-189">Configure the relationship from your customer activity entity to the *Customer* entity.</span></span>
    
    1. <span data-ttu-id="90ea5-190">請在客戶活動表格中選取找出客戶的欄位。</span><span class="sxs-lookup"><span data-stu-id="90ea5-190">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="90ea5-191">這可以直接關聯到 *客戶* 實體的主要客戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="90ea5-191">It can be directly related to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="90ea5-192">選取與主要 *客戶* 實體相符的 *客戶* 實體。</span><span class="sxs-lookup"><span data-stu-id="90ea5-192">Select the *Customer* entity that matches your primary *Customer* entity.</span></span>
    1. <span data-ttu-id="90ea5-193">輸入描述此關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="90ea5-193">Enter a name that describes the relationship.</span></span>

   :::image type="content" source="media/clv-additional-data.png" alt-text="圖片上是設定流程中的步驟，此步驟將新增其他資料並用已填入的範例設定活動。":::

1. <span data-ttu-id="90ea5-195">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-195">Select **Save**.</span></span>    
    <span data-ttu-id="90ea5-196">如果有其他想要放入的客戶活動，請新增更多資料。</span><span class="sxs-lookup"><span data-stu-id="90ea5-196">Add more data if there are other customer activities you want to include.</span></span>

1. <span data-ttu-id="90ea5-197">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-197">Select **Next**.</span></span>

### <a name="set-update-schedule"></a><span data-ttu-id="90ea5-198">設定更新排程</span><span class="sxs-lookup"><span data-stu-id="90ea5-198">Set update schedule</span></span>

1. <span data-ttu-id="90ea5-199">在 **資料更新排程** 步驟中，選擇根據最新資料重新定型模型的頻率。</span><span class="sxs-lookup"><span data-stu-id="90ea5-199">In the **Data update schedule** step, choose the frequency to retrain your model based on the latest data.</span></span> <span data-ttu-id="90ea5-200">此設定對更新預測準確度很重要，因為新資料會內嵌到對象見解中。</span><span class="sxs-lookup"><span data-stu-id="90ea5-200">This setting is important to update the accuracy of predictions as new data is ingested in audience insights.</span></span> <span data-ttu-id="90ea5-201">大部分企業都可以每月重新定型一次，讓他們的預測取得良好的準確度。</span><span class="sxs-lookup"><span data-stu-id="90ea5-201">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="90ea5-202">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-202">Select **Next**.</span></span>


### <a name="review-and-run-the-model-configuration"></a><span data-ttu-id="90ea5-203">審查並執行模型設定</span><span class="sxs-lookup"><span data-stu-id="90ea5-203">Review and run the model configuration</span></span>

1. <span data-ttu-id="90ea5-204">在 **審查模型詳細資料** 步驟中，驗證預測的設定。</span><span class="sxs-lookup"><span data-stu-id="90ea5-204">In the **Review your model details** step, validate the configuration of the prediction.</span></span> <span data-ttu-id="90ea5-205">您可以選取顯示值底下的 **編輯**，返回預測設定的任何一部分。</span><span class="sxs-lookup"><span data-stu-id="90ea5-205">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="90ea5-206">您也可以從進度列指示器中選取設定步驟。</span><span class="sxs-lookup"><span data-stu-id="90ea5-206">You can also select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="90ea5-207">如果所有值都已正確設定，請選取 **儲存並執行** 開始執行模型。</span><span class="sxs-lookup"><span data-stu-id="90ea5-207">If all values are configured correctly, select **Save and run** to start running the model.</span></span> <span data-ttu-id="90ea5-208">在 **我的預測** 索引標籤中，您可以看到預測程序的狀態。</span><span class="sxs-lookup"><span data-stu-id="90ea5-208">On the **My predictions** tab, you can see the status of the prediction process.</span></span> <span data-ttu-id="90ea5-209">視預測中使用的資料量而定，此程序可能需要數個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="90ea5-209">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-prediction-status-and-results"></a><span data-ttu-id="90ea5-210">審查預測狀態與結果</span><span class="sxs-lookup"><span data-stu-id="90ea5-210">Review prediction status and results</span></span>

### <a name="review-prediction-status"></a><span data-ttu-id="90ea5-211">審查預測狀態</span><span class="sxs-lookup"><span data-stu-id="90ea5-211">Review prediction status</span></span>

1.  <span data-ttu-id="90ea5-212">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="90ea5-212">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2.  <span data-ttu-id="90ea5-213">選取您要檢閱的預測。</span><span class="sxs-lookup"><span data-stu-id="90ea5-213">Select the prediction you want to review.</span></span>

- <span data-ttu-id="90ea5-214">**預測名稱**：建立預測時提供的名稱。</span><span class="sxs-lookup"><span data-stu-id="90ea5-214">**Prediction name**: Name of the prediction provided when creating it.</span></span>
- <span data-ttu-id="90ea5-215">**預測類型**：用於預測的模型類型</span><span class="sxs-lookup"><span data-stu-id="90ea5-215">**Prediction type**: Type of model used for the prediction</span></span>
- <span data-ttu-id="90ea5-216">**輸出實體**：儲存預測輸出實體的名稱。</span><span class="sxs-lookup"><span data-stu-id="90ea5-216">**Output entity**: Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="90ea5-217">移至 **資料** > **實體** 尋找此名稱的實體。</span><span class="sxs-lookup"><span data-stu-id="90ea5-217">Go to **Data** > **Entities** to find the entity with this name.</span></span>
- <span data-ttu-id="90ea5-218">**預測欄位**：此欄位只填入某些類型的預測，並不用在客戶生命週期價值預測中。</span><span class="sxs-lookup"><span data-stu-id="90ea5-218">**Predicted field**: This field is populated only for some types of predictions, and isn't used in customer lifetime value prediction.</span></span>
- <span data-ttu-id="90ea5-219">**狀態**：預測執行狀態。</span><span class="sxs-lookup"><span data-stu-id="90ea5-219">**Status**: Status of the prediction run.</span></span>
    - <span data-ttu-id="90ea5-220">**已排入佇列**：預測正等待其他程序完成。</span><span class="sxs-lookup"><span data-stu-id="90ea5-220">**Queued**: Prediction is waiting for other processes to complete.</span></span>
    - <span data-ttu-id="90ea5-221">**重新整理**：預測目前正在建立將進入輸出實體的結果。</span><span class="sxs-lookup"><span data-stu-id="90ea5-221">**Refreshing**: Prediction is currently running to create results that will flow into the output entity.</span></span>
    - <span data-ttu-id="90ea5-222">**失敗**：預測執行失敗。</span><span class="sxs-lookup"><span data-stu-id="90ea5-222">**Failed**: Prediction run has failed.</span></span> <span data-ttu-id="90ea5-223">如需更多細節，[請回顧記錄](#troubleshoot-a-failed-prediction)。</span><span class="sxs-lookup"><span data-stu-id="90ea5-223">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
    - <span data-ttu-id="90ea5-224">**已成功**：預測已成功。</span><span class="sxs-lookup"><span data-stu-id="90ea5-224">**Succeeded**: Prediction has succeeded.</span></span> <span data-ttu-id="90ea5-225">在垂直省略符號下方選取 **檢視表**，以檢閱預測結果。</span><span class="sxs-lookup"><span data-stu-id="90ea5-225">Select **View** under the vertical ellipses to review the prediction results.</span></span>
- <span data-ttu-id="90ea5-226">**已編輯**：預測設定變更的日期。</span><span class="sxs-lookup"><span data-stu-id="90ea5-226">**Edited**: The date the configuration for the prediction was changed.</span></span>
- <span data-ttu-id="90ea5-227">**上次重新整理**：在此日期預測重新整理輸出實體中的結果。</span><span class="sxs-lookup"><span data-stu-id="90ea5-227">**Last refreshed**: The date the prediction refreshed results in the output entity.</span></span>


### <a name="review-prediction-results"></a><span data-ttu-id="90ea5-228">檢閱預測結果</span><span class="sxs-lookup"><span data-stu-id="90ea5-228">Review prediction results</span></span>

1. <span data-ttu-id="90ea5-229">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="90ea5-229">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="90ea5-230">選取您要檢閱其結果的預測。</span><span class="sxs-lookup"><span data-stu-id="90ea5-230">Select the prediction you want to review results for.</span></span>

<span data-ttu-id="90ea5-231">結果頁面中有三個主要的資料區段。</span><span class="sxs-lookup"><span data-stu-id="90ea5-231">There are three primary sections of data within the results page.</span></span>

- <span data-ttu-id="90ea5-232">**訓練模型效能**：A、B 或 C 為可能的評分。</span><span class="sxs-lookup"><span data-stu-id="90ea5-232">**Training model performance**: A, B, or C are possible grades.</span></span> <span data-ttu-id="90ea5-233">此分數表示預測的效能，並可協助您決定是否使用輸出實體中儲存的結果。</span><span class="sxs-lookup"><span data-stu-id="90ea5-233">This grade indicates the performance of the prediction and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="90ea5-234">選取 **瞭解此分數**，深入瞭解基礎模型效能指標和此最終模型效能評分是如何獲得的。</span><span class="sxs-lookup"><span data-stu-id="90ea5-234">Select **Learn about this score** to better understand the underlying model performance metrics and how the final model performance grade was derived.</span></span>
  
  :::image type="content" source="media/clv-model-score.png" alt-text="圖片上為評分為 A 的模型分數資訊方塊。":::

  <span data-ttu-id="90ea5-236">根據設定預測時提供的高價值客戶定義，系統會評估與基準模型相比， AI 模型在預測高價值客戶時表現如何。</span><span class="sxs-lookup"><span data-stu-id="90ea5-236">Using the definition of high value customers provided while configuring the prediction, the system assess how the AI model performed in predicting the high value customers as compared to a baseline model.</span></span>    

  <span data-ttu-id="90ea5-237">評分是根據下列規則而定：</span><span class="sxs-lookup"><span data-stu-id="90ea5-237">Grades are determined based on the following rules:</span></span>
  - <span data-ttu-id="90ea5-238">A 是與基準模型相比，模型準確預測至少多 5% 的高價值客戶。</span><span class="sxs-lookup"><span data-stu-id="90ea5-238">A when the model accurately predicted at least 5% more high-value customers as compared to the baseline model.</span></span>
  - <span data-ttu-id="90ea5-239">B 是與基準模型相比，模型準確預測多 0-5% 的高價值客戶。</span><span class="sxs-lookup"><span data-stu-id="90ea5-239">B when the model accurately predicted between 0-5% more high-value customers as compared to the baseline model.</span></span>
  - <span data-ttu-id="90ea5-240">C 是與基準模型相比，模型準確預測的高價值客戶更少。</span><span class="sxs-lookup"><span data-stu-id="90ea5-240">C when the model accurately predicted fewer high-value customers as compared to the baseline model.</span></span>

  <span data-ttu-id="90ea5-241">**模型評等** 窗格會顯示關於 AI 模型效能和基準模型的更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="90ea5-241">The **Model rating** pane shows further details about the AI model performance and the baseline model.</span></span> <span data-ttu-id="90ea5-242">基準模型主要根據客戶完成的歷史購買記錄，使用非 AI 方法計算客戶生命週期價值。</span><span class="sxs-lookup"><span data-stu-id="90ea5-242">The baseline model uses a non-AI based approach to calculate customer lifetime value based primarily on historical purchases made by customers.</span></span>     
  <span data-ttu-id="90ea5-243">基準模型用來計算 CLV 的標準公式：</span><span class="sxs-lookup"><span data-stu-id="90ea5-243">The standard formula used to calculate CLV by the baseline model:</span></span>    

  <span data-ttu-id="90ea5-244">*每個客戶的 CLV = 由活躍客戶視窗中的客戶完成的平均每月購買量 \* CLV 預測期間中的月數 \* 所有客戶的整體留存率*</span><span class="sxs-lookup"><span data-stu-id="90ea5-244">*CLV for each customer = Average monthly purchase made by the customer in the active customer window \* Number of months in the CLV prediction period \* Overall retention rate of all customers*</span></span>

  <span data-ttu-id="90ea5-245">AI 模型將根據兩種模型效能指標與基準模型進行比較。</span><span class="sxs-lookup"><span data-stu-id="90ea5-245">The AI model is compared to the baseline model based on two model performance metrics.</span></span>
  
  - <span data-ttu-id="90ea5-246">**預測高價值客戶的成功率**</span><span class="sxs-lookup"><span data-stu-id="90ea5-246">**Success rate in predicting high-value customers**</span></span>

    <span data-ttu-id="90ea5-247">請查看預測高價值客戶時，使用 AI 模型與基準模型相比的差異。</span><span class="sxs-lookup"><span data-stu-id="90ea5-247">See the difference in predicting high-value customers using the AI model compared to the baseline model.</span></span> <span data-ttu-id="90ea5-248">例如，84% 成功率表示訓練資料中的所有高價值客戶，AI 模型可以準確地預測 84%。</span><span class="sxs-lookup"><span data-stu-id="90ea5-248">For example, 84% success rate means that out of all the high-value customers in the training data, the AI model was able to accurately capture 84%.</span></span> <span data-ttu-id="90ea5-249">接著，我們會將此成功率與基線模型的成功率進行比較，以報告相對變化。</span><span class="sxs-lookup"><span data-stu-id="90ea5-249">We then compare this success rate with the success rate of the baseline model to report the relative change.</span></span> <span data-ttu-id="90ea5-250">這個值會用來指派模型的評分。</span><span class="sxs-lookup"><span data-stu-id="90ea5-250">This value is used to assign a grade to the model.</span></span>

  - <span data-ttu-id="90ea5-251">**錯誤指標**</span><span class="sxs-lookup"><span data-stu-id="90ea5-251">**Error metrics**</span></span>
    
    <span data-ttu-id="90ea5-252">另一個指標可讓您從預測未來值中的錯誤來檢閱模型的整體效能。</span><span class="sxs-lookup"><span data-stu-id="90ea5-252">Another metric lets you review the overall performance of the model in terms of error in predicting future values.</span></span> <span data-ttu-id="90ea5-253">我們使用整體均方根誤差 (RMSE) 指標來評估此錯誤。</span><span class="sxs-lookup"><span data-stu-id="90ea5-253">We use the overall Root Mean Squared Error (RMSE) metric to assess this error.</span></span> <span data-ttu-id="90ea5-254">RMSE 是一種標準方式，可以在預測量化資料時測量模型的錯誤。</span><span class="sxs-lookup"><span data-stu-id="90ea5-254">RMSE is a standard way to measure the error of a model in predicting quantitative data.</span></span> <span data-ttu-id="90ea5-255">將 AI 模型的 RMSE 與基準模型的 RMSE 比較，並會報告相對差異。</span><span class="sxs-lookup"><span data-stu-id="90ea5-255">The AI model’s RMSE is compared to the RMSE of the baseline model and the relative difference is reported.</span></span>

  <span data-ttu-id="90ea5-256">AI 模型會根據其對業務的價值排出客戶準確的等級。</span><span class="sxs-lookup"><span data-stu-id="90ea5-256">The AI model prioritizes the accurate ranking of customers according to the value they bring to your business.</span></span> <span data-ttu-id="90ea5-257">因此，只有預測高價值客戶的成功比率，才用來取得最終的模型評等。</span><span class="sxs-lookup"><span data-stu-id="90ea5-257">So only the success rate of predicting high-value customers is used to derive the final model grade.</span></span> <span data-ttu-id="90ea5-258">RMSE 指標對極端值敏感。</span><span class="sxs-lookup"><span data-stu-id="90ea5-258">The RMSE metric is sensitive to outliers.</span></span> <span data-ttu-id="90ea5-259">當案例中低比例的客戶擁有超高購買價值時，整體 RMSE 指標可能無法給予模型效能的全貌。</span><span class="sxs-lookup"><span data-stu-id="90ea5-259">In scenarios where you have a small percentage of customers with extraordinarily high purchase values, the overall RMSE metric might not give the full picture of the model performance.</span></span>   

- <span data-ttu-id="90ea5-260">**依百分比區分客戶價值**：使用您的高價值客戶定義，會根據其 CLV 預測將客戶分組成低價值和高價值，並顯示在圖表中，。</span><span class="sxs-lookup"><span data-stu-id="90ea5-260">**Value of customers by percentile**: Using your definition of high-value customers, customers are grouped into low-value and high-value, based on their CLV predictions, and shown in a chart.</span></span> <span data-ttu-id="90ea5-261">透過暫留在直方圖中的長方形，您就可以看到每個群組的客戶數，以及該群組的平均 CLV。</span><span class="sxs-lookup"><span data-stu-id="90ea5-261">By hovering over the bars in the histogram, you can see the number of customers in each group and the average CLV of that group.</span></span> <span data-ttu-id="90ea5-262">若您想根據 CLV 預測 [建立客戶的區段](segments.md)，此資料有所幫助。</span><span class="sxs-lookup"><span data-stu-id="90ea5-262">This data can help if you want to [create segments of customers](segments.md) based on their CLV predictions.</span></span>

- <span data-ttu-id="90ea5-263">**最具影響力的因素**：根據提供給 AI 模型的輸入資料，建立 CLV 預測時，會考慮各種因素。</span><span class="sxs-lookup"><span data-stu-id="90ea5-263">**Most influential factors**: Various factors are considered when creating your CLV prediction based on the input data provided to the AI model.</span></span> <span data-ttu-id="90ea5-264">每個因素都有其針對模型所建立彙總預測而計算的重要性。</span><span class="sxs-lookup"><span data-stu-id="90ea5-264">Each of the factors has their importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="90ea5-265">您可以使用這些因素來協助驗證預測結果。</span><span class="sxs-lookup"><span data-stu-id="90ea5-265">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="90ea5-266">對預測 CLV 所有客戶的最具影響力因素，這些因素也提供更多深入解析。</span><span class="sxs-lookup"><span data-stu-id="90ea5-266">These factors also provide more insight about the most influential factors that contributed towards predicting CLV across all your customers.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="90ea5-267">重新整理預測</span><span class="sxs-lookup"><span data-stu-id="90ea5-267">Refresh a prediction</span></span>

<span data-ttu-id="90ea5-268">根據在設定中與[資料重新整理排程](system.md#schedule-tab)相同的設定，預測會自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="90ea5-268">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="90ea5-269">您也可以手動重新整理它們。</span><span class="sxs-lookup"><span data-stu-id="90ea5-269">You can refresh them manually too.</span></span>

1. <span data-ttu-id="90ea5-270">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="90ea5-270">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="90ea5-271">選取您要重新整理之預測旁邊的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="90ea5-271">Select the vertical ellipses next to the prediction you want to refresh.</span></span>
3. <span data-ttu-id="90ea5-272">選取 **重新整理**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-272">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="90ea5-273">刪除預測</span><span class="sxs-lookup"><span data-stu-id="90ea5-273">Delete a prediction</span></span>

<span data-ttu-id="90ea5-274">刪除預測也會同時移除其輸出實體。</span><span class="sxs-lookup"><span data-stu-id="90ea5-274">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="90ea5-275">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="90ea5-275">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="90ea5-276">選取您要刪除之預測旁邊的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="90ea5-276">Select the vertical ellipses next to the prediction you want to delete.</span></span>
3. <span data-ttu-id="90ea5-277">選取 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-277">Select **Delete**.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="90ea5-278">疑難排解失敗的預測</span><span class="sxs-lookup"><span data-stu-id="90ea5-278">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="90ea5-279">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="90ea5-279">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="90ea5-280">選取您要檢視錯誤記錄的預測旁的垂直刪節號。</span><span class="sxs-lookup"><span data-stu-id="90ea5-280">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>
3. <span data-ttu-id="90ea5-281">選取 **記錄**。</span><span class="sxs-lookup"><span data-stu-id="90ea5-281">Select **Logs**.</span></span>
4. <span data-ttu-id="90ea5-282">檢閱所有錯誤。</span><span class="sxs-lookup"><span data-stu-id="90ea5-282">Review all the errors.</span></span> <span data-ttu-id="90ea5-283">可能發生的錯誤有數種類型，這些類型描述造成錯誤的狀況。</span><span class="sxs-lookup"><span data-stu-id="90ea5-283">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="90ea5-284">例如準確預測所需資料不足的錯誤，一般是以載入更多資料到對象見解中解決。</span><span class="sxs-lookup"><span data-stu-id="90ea5-284">For example, an error that there's not enough data to accurately predict is typically resolved by loading more data into audience insights.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]