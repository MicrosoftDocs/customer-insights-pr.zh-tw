---
title: 以活動為基礎的客戶細分建議。
description: 讓機器學習協助您根據客戶活動尋找新的且值得注意的客戶細分。
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034055"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="24b20-103">以活動資料為基礎的客戶細分建議 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="24b20-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="24b20-104">根據內嵌到 Customer Insights 的客戶活動資料，探索值得注意客戶細分。</span><span class="sxs-lookup"><span data-stu-id="24b20-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="24b20-105">活動資料的範例包括交易、支援通話長度、交易或退貨。</span><span class="sxs-lookup"><span data-stu-id="24b20-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="24b20-106">為了建議客戶細分，會針對新近程度、頻率和金額值 (或期間) 來分析活動資料。</span><span class="sxs-lookup"><span data-stu-id="24b20-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="24b20-107">或者，您也可以生成[建議的客戶細分來改善量值或更清楚地瞭解屬性影響](suggested-segments.md)。</span><span class="sxs-lookup"><span data-stu-id="24b20-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="建議的客戶細分索引標籤顯示的客戶細分建議是基於活動和基於屬性建立的。":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="24b20-109">依活動分類客戶</span><span class="sxs-lookup"><span data-stu-id="24b20-109">Categorize customers by activity</span></span>

<span data-ttu-id="24b20-110">透過 Customer Insights 中提供的[活動資料](activities.md)，我們可以生成建議來表現客戶群組：</span><span class="sxs-lookup"><span data-stu-id="24b20-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="24b20-111">最活躍的客戶</span><span class="sxs-lookup"><span data-stu-id="24b20-111">most active customers</span></span> 
- <span data-ttu-id="24b20-112">進行過最多購買的客戶</span><span class="sxs-lookup"><span data-stu-id="24b20-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="24b20-113">產生最多營收的客戶</span><span class="sxs-lookup"><span data-stu-id="24b20-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="24b20-114">最近沒有使用的客戶</span><span class="sxs-lookup"><span data-stu-id="24b20-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="24b20-115">經常與您的企業互動的客戶</span><span class="sxs-lookup"><span data-stu-id="24b20-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="24b20-116">如果您有零售業務，您可以找出哪些客戶產生最多的營收並使用優惠券回饋。</span><span class="sxs-lookup"><span data-stu-id="24b20-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="24b20-117">您也可以找出不定期客戶，並向他們提議加入獎勵計畫，讓他們更常造訪您的業務。</span><span class="sxs-lookup"><span data-stu-id="24b20-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="24b20-118">如果您是醫療保健商務的一份子，提供大眾醫療保健，而您的目標是把對個別患者的開銷降至最低。</span><span class="sxs-lookup"><span data-stu-id="24b20-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="24b20-119">若要這樣做，一種方式是在最少的訪視中，提供最好的服務，以減少定期訪視。</span><span class="sxs-lookup"><span data-stu-id="24b20-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="24b20-120">在此案例中，您的目標是保持較低的訪視頻率，並將患者的定期成本減至最小。</span><span class="sxs-lookup"><span data-stu-id="24b20-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="24b20-121">或者您也可以找出經預約和大量定期成本的患者客戶細分，並分析這些案例來改善個人的治療。</span><span class="sxs-lookup"><span data-stu-id="24b20-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="24b20-122">必要的資料</span><span class="sxs-lookup"><span data-stu-id="24b20-122">Required data</span></span>

<span data-ttu-id="24b20-123">建議會根據所選的輸入資料生成。</span><span class="sxs-lookup"><span data-stu-id="24b20-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="24b20-124">客戶個人資料：特定客戶細分的所有客戶或成員。</span><span class="sxs-lookup"><span data-stu-id="24b20-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="24b20-125">時段期間：上個月、去年或任何自訂時間範圍。</span><span class="sxs-lookup"><span data-stu-id="24b20-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="24b20-126">活動類型：購買、零售交易、線上交易、客戶支援案例、訂閱等等。</span><span class="sxs-lookup"><span data-stu-id="24b20-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="24b20-127">Customer Insights 中包含活動資料的實體：整合活動實體或特定活動的實體。</span><span class="sxs-lookup"><span data-stu-id="24b20-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="24b20-128">要包含的維度：新近度、頻率或金額維度，視您的業務需求而定。</span><span class="sxs-lookup"><span data-stu-id="24b20-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="24b20-129">生成建議的客戶細分</span><span class="sxs-lookup"><span data-stu-id="24b20-129">Generate suggested segments</span></span>

1. <span data-ttu-id="24b20-130">前往 **區段**。</span><span class="sxs-lookup"><span data-stu-id="24b20-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="24b20-131">選取 **建議 (預覽版)** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="24b20-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="24b20-132">選取 **尋找新建議**，然後選擇 **查看或預測客戶行為**。</span><span class="sxs-lookup"><span data-stu-id="24b20-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="24b20-133">選取 **開始** 執行引導式體驗。</span><span class="sxs-lookup"><span data-stu-id="24b20-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="根據活動建立建議的客戶細分的設定精靈，其第一個步驟。":::

1. <span data-ttu-id="24b20-135">提供必要的輸入資料，並選取 **下一步** 繼續。</span><span class="sxs-lookup"><span data-stu-id="24b20-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="24b20-136">選擇客戶：包括所有客戶或特定客戶細分。</span><span class="sxs-lookup"><span data-stu-id="24b20-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="24b20-137">選擇活動：選取活動類型以及說明該活動的實體。</span><span class="sxs-lookup"><span data-stu-id="24b20-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="24b20-138">喜好設定：設定要考量的時段期間、建議因素以及對應屬性。</span><span class="sxs-lookup"><span data-stu-id="24b20-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="24b20-139">檢閱您的輸入，並選取 **執行** 來執行模型生成建議。</span><span class="sxs-lookup"><span data-stu-id="24b20-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="24b20-140">視客戶個人資料數量和選取的活動數量而定，可能需要幾分鐘的時間完成。</span><span class="sxs-lookup"><span data-stu-id="24b20-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="24b20-141">生成建議之後，您可以依據您最感興趣的維度或值來篩選它們。</span><span class="sxs-lookup"><span data-stu-id="24b20-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="24b20-142">檢視建議的客戶細分詳細資料</span><span class="sxs-lookup"><span data-stu-id="24b20-142">View details of a suggested segment</span></span>

<span data-ttu-id="24b20-143">建議生成之後，可以在 **客戶細分** > **建議 (預覽版)** **基於活動建立的客戶細分建議** 區段中找到。</span><span class="sxs-lookup"><span data-stu-id="24b20-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="展開的側窗格，顯示建議客戶細分的詳細資料。":::

<span data-ttu-id="24b20-145">選取建議的客戶細分區段上的 **查看建議**，以查看該客戶細分的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="24b20-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="24b20-146">側面窗格提供如各維度範圍與目標群組比較的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="24b20-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="24b20-147">也會醒目提示客戶細分中潛在成員的數量，以及總客戶數量相應的百分比。</span><span class="sxs-lookup"><span data-stu-id="24b20-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="24b20-148">如果您要將建議保留為客戶細分，請選取 **建立客戶細分**。</span><span class="sxs-lookup"><span data-stu-id="24b20-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="24b20-149">將建議另存為客戶細分</span><span class="sxs-lookup"><span data-stu-id="24b20-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="24b20-150">移至 **客戶細分** > **建議 (預覽版)**。</span><span class="sxs-lookup"><span data-stu-id="24b20-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="24b20-151">選取您要儲存的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="24b20-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="24b20-152">在側面窗格中，選取 **建立客戶細分**。</span><span class="sxs-lookup"><span data-stu-id="24b20-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="24b20-153">儲存客戶細分之後，它便會顯示在所有 **客戶細分** 索引標籤的客戶細分清單中。現在[就像其他任何區段一樣可以重新整理或刪除](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="24b20-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="24b20-154">您不可以編輯客戶細分詳細資料。</span><span class="sxs-lookup"><span data-stu-id="24b20-154">You can't edit the segment details.</span></span> <span data-ttu-id="24b20-155">但是，您可以變更建議的輸入準則，並生成不同的建議。</span><span class="sxs-lookup"><span data-stu-id="24b20-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="24b20-156">重新整理或編輯一組建議</span><span class="sxs-lookup"><span data-stu-id="24b20-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="24b20-157">移至 **客戶細分** > **建議 (預覽版)**，並在 **基於活動的建議** 區段中尋找客戶細分。</span><span class="sxs-lookup"><span data-stu-id="24b20-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="24b20-158">選取 **重新整理建議**，以使用維持設定好的屬性，重新整理建議。</span><span class="sxs-lookup"><span data-stu-id="24b20-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="24b20-159">或選取 **編輯建議** 修改已設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="24b20-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="24b20-160">系統將會重新執行程序，並根據最新的資料生成客戶細分建議，並取代目前的建議。</span><span class="sxs-lookup"><span data-stu-id="24b20-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
