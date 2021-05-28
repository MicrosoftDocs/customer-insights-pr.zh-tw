---
title: 建立和管理區段
description: 建立客戶的區段，以依據各種屬性來群組。
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064927"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="60882-103">建立和管理區段</span><span class="sxs-lookup"><span data-stu-id="60882-103">Create and manage segments</span></span>

<span data-ttu-id="60882-104">對整合客戶實體周圍及相關實體，定義複雜篩選。</span><span class="sxs-lookup"><span data-stu-id="60882-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="60882-105">每個區段會在處理後建立一組可匯出和採取相應動作的客戶記錄。</span><span class="sxs-lookup"><span data-stu-id="60882-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="60882-106">區段會在 **區段** 頁面上加以管理。</span><span class="sxs-lookup"><span data-stu-id="60882-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="60882-107">下列範例說明區隔能力。</span><span class="sxs-lookup"><span data-stu-id="60882-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="60882-108">我們為在過去 90 天中至少訂購了 $500 貨物的客戶，*以及* 參與了已上呈之客戶服務通話的客戶，定義了區段。</span><span class="sxs-lookup"><span data-stu-id="60882-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="螢幕擷取畫面，圖上客戶細分產生器 UI ，並有兩個群組指定客戶客戶細分。":::

## <a name="create-a-new-segment"></a><span data-ttu-id="60882-110">建立新區段</span><span class="sxs-lookup"><span data-stu-id="60882-110">Create a new segment</span></span>

<span data-ttu-id="60882-111">有很多方式可以建立新的客戶細分：</span><span class="sxs-lookup"><span data-stu-id="60882-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="60882-112">本節說明如何從頭開始建立 *空白客戶細分*。</span><span class="sxs-lookup"><span data-stu-id="60882-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="60882-113">您也可以依據現有的實體建立 *快速客戶細分*，或使用機器學習模型來取得 *建議的客戶細分*。</span><span class="sxs-lookup"><span data-stu-id="60882-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="60882-114">其他資訊：[客戶細分概觀](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="60882-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="60882-115">建立客戶細分時，您可以儲存草稿。</span><span class="sxs-lookup"><span data-stu-id="60882-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="60882-116">它會儲存為非使用中的客戶細分，而且無法啟用，完成有效的設定為止。</span><span class="sxs-lookup"><span data-stu-id="60882-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="60882-117">移至 **區段** 頁。</span><span class="sxs-lookup"><span data-stu-id="60882-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="60882-118">選取 **新增** > **空白區段**。</span><span class="sxs-lookup"><span data-stu-id="60882-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="60882-119">在 **新增客戶細分** 窗格中，選取客戶細分類型：</span><span class="sxs-lookup"><span data-stu-id="60882-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="60882-120">**動態客戶細分** 會定期[重新整理](segments.md#refresh-segments)。</span><span class="sxs-lookup"><span data-stu-id="60882-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="60882-121">**靜態客戶細分** 僅在您建立時執行一次。</span><span class="sxs-lookup"><span data-stu-id="60882-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="60882-122">提供客戶細分的 **輸出實體名稱**。</span><span class="sxs-lookup"><span data-stu-id="60882-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="60882-123">您也可以提供顯示名稱以及有助於識別區段的描述。</span><span class="sxs-lookup"><span data-stu-id="60882-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="60882-124">選取 **下一步** 以進入 **區段建立器** 頁面，您可以在其中定義群組。</span><span class="sxs-lookup"><span data-stu-id="60882-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="60882-125">群組是一組客戶。</span><span class="sxs-lookup"><span data-stu-id="60882-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="60882-126">選擇包含您要據以建立區段之屬性的實體。</span><span class="sxs-lookup"><span data-stu-id="60882-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="60882-127">選擇要據以建立區段的屬性。</span><span class="sxs-lookup"><span data-stu-id="60882-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="60882-128">此屬性可以有四個數值類型之一：數值、字串、日期或布林值。</span><span class="sxs-lookup"><span data-stu-id="60882-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="60882-129">為選取的屬性選擇運算子與值。</span><span class="sxs-lookup"><span data-stu-id="60882-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="60882-130">![自訂群組篩選](media/customer-group-numbers.png "客戶群組篩選")</span><span class="sxs-lookup"><span data-stu-id="60882-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="60882-131">號碼</span><span class="sxs-lookup"><span data-stu-id="60882-131">Number</span></span> |<span data-ttu-id="60882-132">定義</span><span class="sxs-lookup"><span data-stu-id="60882-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="60882-133">1</span><span class="sxs-lookup"><span data-stu-id="60882-133">1</span></span>     |<span data-ttu-id="60882-134">Entity</span><span class="sxs-lookup"><span data-stu-id="60882-134">Entity</span></span>          |
   |<span data-ttu-id="60882-135">2</span><span class="sxs-lookup"><span data-stu-id="60882-135">2</span></span>     |<span data-ttu-id="60882-136">屬性</span><span class="sxs-lookup"><span data-stu-id="60882-136">Attribute</span></span>          |
   |<span data-ttu-id="60882-137">3</span><span class="sxs-lookup"><span data-stu-id="60882-137">3</span></span>    |<span data-ttu-id="60882-138">運算子</span><span class="sxs-lookup"><span data-stu-id="60882-138">Operator</span></span>         |
   |<span data-ttu-id="60882-139">4</span><span class="sxs-lookup"><span data-stu-id="60882-139">4</span></span>    |<span data-ttu-id="60882-140">值</span><span class="sxs-lookup"><span data-stu-id="60882-140">Value</span></span>         |

   1. <span data-ttu-id="60882-141">若要將更多條件新增至群組，您可以使用兩個邏輯運算子：</span><span class="sxs-lookup"><span data-stu-id="60882-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="60882-142">**AND** 運算子：在區段程序中兩個條件都必須符合。</span><span class="sxs-lookup"><span data-stu-id="60882-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="60882-143">當您跨不同實體定義條件時，此選項非常有用。</span><span class="sxs-lookup"><span data-stu-id="60882-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="60882-144">**OR** 運算子：在區段程序中，需要符合其中一項條件。</span><span class="sxs-lookup"><span data-stu-id="60882-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="60882-145">當您為相同實體定義多個條件時，此選項非常有用。</span><span class="sxs-lookup"><span data-stu-id="60882-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="60882-146">![需要符合任一條件的 OR 運算子](media/segmentation-either-condition.png "需要符合任一條件的 OR 運算子")</span><span class="sxs-lookup"><span data-stu-id="60882-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="60882-147">目前可以將 **OR** 運算子內嵌在 **AND** 運算子之下，但相反過來不行。</span><span class="sxs-lookup"><span data-stu-id="60882-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="60882-148">每個群組比對一組客戶。</span><span class="sxs-lookup"><span data-stu-id="60882-148">Each group matches set of customers.</span></span> <span data-ttu-id="60882-149">您可以結合群組以包括商務案例中必要的客戶。</span><span class="sxs-lookup"><span data-stu-id="60882-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="60882-150">選取 **新增群組**。</span><span class="sxs-lookup"><span data-stu-id="60882-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="60882-151">![客戶群組新增群組](media/customer-group-add-group.png "客戶群組新增群組")</span><span class="sxs-lookup"><span data-stu-id="60882-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="60882-152">選取集合運算子中的一個：**Union**、**Intersect** 或 **Except**。</span><span class="sxs-lookup"><span data-stu-id="60882-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="60882-153">![客戶群組新增聯集](media/customer-group-union.png "客戶群組新增聯集")</span><span class="sxs-lookup"><span data-stu-id="60882-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="60882-154">**聯集** 會聯合兩個群組。</span><span class="sxs-lookup"><span data-stu-id="60882-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="60882-155">**交集** 會重疊兩個群組。</span><span class="sxs-lookup"><span data-stu-id="60882-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="60882-156">唯有兩個群組 *共有* 的資料才會在統整群組中保留。</span><span class="sxs-lookup"><span data-stu-id="60882-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="60882-157">**差集** 會結合兩個群組。</span><span class="sxs-lookup"><span data-stu-id="60882-157">**Except** combines the two groups.</span></span> <span data-ttu-id="60882-158">唯有 *不與 B 組資料共有* 的 A 組資料才會保留。</span><span class="sxs-lookup"><span data-stu-id="60882-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="60882-159">如果實體是透過[關聯](relationships.md)連接至統整的客戶實體，則需要定義關聯路徑來建立有效的區段。</span><span class="sxs-lookup"><span data-stu-id="60882-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="60882-160">從關聯路徑新增實體，直到您可以從下拉清單中選取 **客戶：CustomerInsights** 實體。</span><span class="sxs-lookup"><span data-stu-id="60882-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="60882-161">然後，在各個步驟中選擇 **所有記錄**。</span><span class="sxs-lookup"><span data-stu-id="60882-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="60882-162">![建立區段期間的關聯路徑](media/segments-multiple-relationships.png "建立段落期間的關聯路徑")</span><span class="sxs-lookup"><span data-stu-id="60882-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="60882-163">根據預設，客戶細分會生成一個輸出實體，其中包含所有符合已定義篩選準則的客戶個人資料屬性。</span><span class="sxs-lookup"><span data-stu-id="60882-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="60882-164">如果客戶細分依據其他實體而非 *客戶* 實體，您可以將這些實體中的多個屬性新增至輸出實體。</span><span class="sxs-lookup"><span data-stu-id="60882-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="60882-165">選取 **專案屬性**，以選擇附加至輸出實體的屬性。</span><span class="sxs-lookup"><span data-stu-id="60882-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="60882-166">範例：有一份客戶細分是根據包含與 *客戶* 實體相關的客戶活動資料實體建立的。</span><span class="sxs-lookup"><span data-stu-id="60882-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="60882-167">此客戶細分會尋找過去 60 天中電話連絡技術服務人員的所有客戶。</span><span class="sxs-lookup"><span data-stu-id="60882-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="60882-168">您可以選擇將通話長度和通話次數附加至輸出實體中所有相符的客戶記錄。</span><span class="sxs-lookup"><span data-stu-id="60882-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="60882-169">若傳送電子郵件並附上線上說明文章連結和常見問題集給經常電話連絡的客戶，此資訊可能會非常實用。</span><span class="sxs-lookup"><span data-stu-id="60882-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="60882-170">映射屬性只適用在與客戶實體有一對多關聯性的實體。</span><span class="sxs-lookup"><span data-stu-id="60882-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="60882-171">例如，一個客戶可以有多個訂閱。</span><span class="sxs-lookup"><span data-stu-id="60882-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="60882-172">只能從正在組建中的每個客戶細分查詢群組內使用到的實體中映射屬性。</span><span class="sxs-lookup"><span data-stu-id="60882-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="60882-173">使用集合運算子時，映射屬性會被計入。</span><span class="sxs-lookup"><span data-stu-id="60882-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="60882-174">選取 **儲存** 以儲存區段。</span><span class="sxs-lookup"><span data-stu-id="60882-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="60882-175">如果所有需求均已驗證，就會儲存和處理您的區段。</span><span class="sxs-lookup"><span data-stu-id="60882-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="60882-176">否則，它會儲存為草稿。</span><span class="sxs-lookup"><span data-stu-id="60882-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="60882-177">選取 **返回區段** 以返回 **區段** 頁面。</span><span class="sxs-lookup"><span data-stu-id="60882-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="60882-178">快速區段</span><span class="sxs-lookup"><span data-stu-id="60882-178">Quick segments</span></span>

<span data-ttu-id="60882-179">使用快速客戶細分，您可以快速組建具有單一運算子的簡單客戶細分，更快取得見解。</span><span class="sxs-lookup"><span data-stu-id="60882-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="60882-180">在 **細分** 頁面上，選取 **新增** > **從...建立**。</span><span class="sxs-lookup"><span data-stu-id="60882-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="60882-181">選取 **個人資料** 選項，組建基於 *統整客戶實體* 的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="60882-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="60882-182">選取 **量值** 選項，在您先前組建的量值周圍建立客戶細分。</span><span class="sxs-lookup"><span data-stu-id="60882-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="60882-183">選取 **智慧** 選項，以使用 **預測** 或 **自訂模型** 功能產生的其中一個輸出實體建立區段。</span><span class="sxs-lookup"><span data-stu-id="60882-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="60882-184">在 **新增快速區段** 對話方塊中，從 **欄位** 下拉式功能表中選取屬性。</span><span class="sxs-lookup"><span data-stu-id="60882-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="60882-185">系統將提供一些其他見解，可協助您建立更佳的客戶區段。</span><span class="sxs-lookup"><span data-stu-id="60882-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="60882-186">對於類別欄位，我們會顯示 10 個最高的客戶計數。</span><span class="sxs-lookup"><span data-stu-id="60882-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="60882-187">選擇 **值** 並選取 **檢閱**。</span><span class="sxs-lookup"><span data-stu-id="60882-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="60882-188">在數值屬性中，系統會顯示落在每個客戶百分位下的屬性值。</span><span class="sxs-lookup"><span data-stu-id="60882-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="60882-189">選擇 **運算子** 和 **值**，然後選取 **檢閱**。</span><span class="sxs-lookup"><span data-stu-id="60882-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="60882-190">系統將為您提供 **估計的區段大小**。</span><span class="sxs-lookup"><span data-stu-id="60882-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="60882-191">您可以選擇是否要產生您定義的區段，或先重新檢視它以取得不同的區段大小。</span><span class="sxs-lookup"><span data-stu-id="60882-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="60882-192">![快速區段的名稱與估計](media/quick-segment-name.png "快速區段的名稱與估計")</span><span class="sxs-lookup"><span data-stu-id="60882-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="60882-193">提供區段的 **名稱**。</span><span class="sxs-lookup"><span data-stu-id="60882-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="60882-194">或者，提供 **顯示名稱**。</span><span class="sxs-lookup"><span data-stu-id="60882-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="60882-195">選取 **儲存** 以建立您的區段。</span><span class="sxs-lookup"><span data-stu-id="60882-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="60882-196">區段完成處理之後，您可以像您所建立的其他段落一樣來查看它。</span><span class="sxs-lookup"><span data-stu-id="60882-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="60882-197">後續步驟</span><span class="sxs-lookup"><span data-stu-id="60882-197">Next steps</span></span>

<span data-ttu-id="60882-198">[匯出區段](export-destinations.md)並探索[客戶卡片](customer-card-add-in.md)和[連接器](export-power-bi.md)，以取得客戶等級的見解。</span><span class="sxs-lookup"><span data-stu-id="60882-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
