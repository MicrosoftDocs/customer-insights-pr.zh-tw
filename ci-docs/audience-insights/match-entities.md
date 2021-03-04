---
title: 比對資料統整的實體
description: 比對實體以建立統整的客戶設定檔。
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267468"
---
# <a name="match-entities"></a><span data-ttu-id="a702e-103">比對實體</span><span class="sxs-lookup"><span data-stu-id="a702e-103">Match entities</span></span>

<span data-ttu-id="a702e-104">完成比對階段之後，您就可以準備比對您的實體。</span><span class="sxs-lookup"><span data-stu-id="a702e-104">After completing the map phase, you're ready to match your entities.</span></span> <span data-ttu-id="a702e-105">比對階段指定如何將您的資料集結合至統整的客戶設定檔資料集。</span><span class="sxs-lookup"><span data-stu-id="a702e-105">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="a702e-106">比對階段需要至少[兩個已比對的實體](map-entities.md)。</span><span class="sxs-lookup"><span data-stu-id="a702e-106">The match phase requires at least [two mapped entities](map-entities.md).</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="a702e-107">指定比對順序</span><span class="sxs-lookup"><span data-stu-id="a702e-107">Specify the match order</span></span>

<span data-ttu-id="a702e-108">移至 **資料** > **統整** > **比對**，然後選取 **設定順序**，開始比對階段。</span><span class="sxs-lookup"><span data-stu-id="a702e-108">Go to **Data** > **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="a702e-109">每個比對都會將兩個或多個實體統整成單一實體，同時保留每個唯一的客戶記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-109">Each match unifies two or more entities into a single entity, while persisting each unique customer record.</span></span> <span data-ttu-id="a702e-110">在下列範例中，我們選取三個實體：**ContactCSV: TestData** 做為 **主要** 實體、**WebAccountCSV: TestData** 做為 **實體 2**，以及 **CallRecordSmall: TestData** 做為 **實體 3**。</span><span class="sxs-lookup"><span data-stu-id="a702e-110">In the following example, we selected three entities: **ContactCSV: TestData** as the **Primary** entity, **WebAccountCSV: TestData** as **Entity 2**, and **CallRecordSmall: TestData** as **Entity 3**.</span></span> <span data-ttu-id="a702e-111">選取項目上方的圖表將闡釋如何執行比對順序。</span><span class="sxs-lookup"><span data-stu-id="a702e-111">The diagram above the selections illustrates how the match order will be executed.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a702e-112">![編輯資料比對順序](media/configure-data-match-order-edit-page.png "編輯資料比對順序")</span><span class="sxs-lookup"><span data-stu-id="a702e-112">![Edit the data match order](media/configure-data-match-order-edit-page.png "Edit the data match order")</span></span>
  
<span data-ttu-id="a702e-113">**主要** 實體與 **實體 2** 進行比對。</span><span class="sxs-lookup"><span data-stu-id="a702e-113">The **Primary** entity is matched with **Entity 2**.</span></span> <span data-ttu-id="a702e-114">第一個比對所產生的資料集會與 **實體 3** 進行比對。</span><span class="sxs-lookup"><span data-stu-id="a702e-114">The dataset that results from the first match is matched with **Entity 3**.</span></span>
<span data-ttu-id="a702e-115">在此範例中，我們只選取兩個比對項目，但是系統可以支援更多的比對。</span><span class="sxs-lookup"><span data-stu-id="a702e-115">In this example, we only selected two matches, but the system can support more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a702e-116">您選擇做為 **主要** 實體的實體將用作您的統整主要資料集的基礎。</span><span class="sxs-lookup"><span data-stu-id="a702e-116">The entity that you choose as your **Primary** entity will serve as the basis for your unified master dataset.</span></span> <span data-ttu-id="a702e-117">在比對階段期間選取的其他實體將會新增至此實體中。</span><span class="sxs-lookup"><span data-stu-id="a702e-117">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="a702e-118">同時，這並不表示統整的實體將包括此實體中包含的 *所有* 資料。</span><span class="sxs-lookup"><span data-stu-id="a702e-118">At the same time, this doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="a702e-119">有兩個考慮可以協助您選擇實體的階層：</span><span class="sxs-lookup"><span data-stu-id="a702e-119">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="a702e-120">您要考慮哪一個實體，讓您的客戶有最完整和可靠的資料？</span><span class="sxs-lookup"><span data-stu-id="a702e-120">What entity do you consider having the most complete and reliable data about your customers?</span></span>
> - <span data-ttu-id="a702e-121">您剛剛識別的實體是否有其他實體共用的屬性（例如名稱、電話號碼或電子郵件地址）？</span><span class="sxs-lookup"><span data-stu-id="a702e-121">Does the entity that you just identified have attributes that are also shared by other entities (for example, name, phone number, or email address)?</span></span> <span data-ttu-id="a702e-122">如果沒有，請選擇第二個最可靠的實體。</span><span class="sxs-lookup"><span data-stu-id="a702e-122">If not, choose your second most reliable entity.</span></span>

<span data-ttu-id="a702e-123">選取 **完成** 來儲存您的比對順序。</span><span class="sxs-lookup"><span data-stu-id="a702e-123">Select **Done** to save your match order.</span></span>

## <a name="define-rules-for-your-first-match-pair"></a><span data-ttu-id="a702e-124">定義第一個比對配對的規則</span><span class="sxs-lookup"><span data-stu-id="a702e-124">Define rules for your first match pair</span></span>

<span data-ttu-id="a702e-125">指定比對順序之後，您會在 **比對** 頁面上看到已定義的比對。</span><span class="sxs-lookup"><span data-stu-id="a702e-125">After specifying the match order, you'll see the defined matches on the **Match** page.</span></span> <span data-ttu-id="a702e-126">在您執行比對順序之前，畫面頂端的圖標將會是空白。</span><span class="sxs-lookup"><span data-stu-id="a702e-126">The tiles at the top of the screen will be empty until you run your match order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a702e-127">![定義規則](media/configure-data-match-need-rules.png "定義規則")</span><span class="sxs-lookup"><span data-stu-id="a702e-127">![Define rules](media/configure-data-match-need-rules.png "Define rules")</span></span>

<span data-ttu-id="a702e-128">**需要規則** 警告表示未替比對配對定義比對規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-128">The **Needs Rules** warning suggests that no match rule is defined for a match pair.</span></span> <span data-ttu-id="a702e-129">比對規則指定將與特定實體配對進行比對的邏輯。</span><span class="sxs-lookup"><span data-stu-id="a702e-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

1. <span data-ttu-id="a702e-130">若要定義第一個規則，請在比對表格中選取對應的比對列 (1)，然後選取 **建立新規則** (2)，以開啟 **規則定義** 窗格。</span><span class="sxs-lookup"><span data-stu-id="a702e-130">To define your first rule, open the **Rule Definition** pane by selecting the corresponding match row in the matches table (1) and then selecting **Create new rule** (2).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a702e-131">![建立新規則](media/configure-data-match-new-rule2.png "建立新規則")</span><span class="sxs-lookup"><span data-stu-id="a702e-131">![Create new rule](media/configure-data-match-new-rule2.png "Create new rule")</span></span>

2. <span data-ttu-id="a702e-132">在 **編輯規則** 窗格中，設定該規則的條件。</span><span class="sxs-lookup"><span data-stu-id="a702e-132">In the **Edit Rule** pane, configure the conditions for that rule.</span></span> <span data-ttu-id="a702e-133">每個條件都是由兩列表示，其中包含必要選項。</span><span class="sxs-lookup"><span data-stu-id="a702e-133">Each condition is represented by two rows that include mandatory selections.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a702e-134">![新規則窗格](media/configure-data-match-new-rule-condition.png "新規則窗格")</span><span class="sxs-lookup"><span data-stu-id="a702e-134">![New rule pane](media/configure-data-match-new-rule-condition.png "New rule pane")</span></span>

   <span data-ttu-id="a702e-135">實體/欄位（第一個）- 將用於從第一個比對配對實體中進行比對的屬性。</span><span class="sxs-lookup"><span data-stu-id="a702e-135">Entity/Field (first) - An attribute that will be used for matching from the first match pair entity.</span></span> <span data-ttu-id="a702e-136">範例可以包括電話號碼或電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a702e-136">Examples could include a phone number or email address.</span></span> <span data-ttu-id="a702e-137">選擇可能對客戶有唯一性的屬性。</span><span class="sxs-lookup"><span data-stu-id="a702e-137">Choose an attribute that is likely to be unique to the customer.</span></span>

   > [!TIP]
   > <span data-ttu-id="a702e-138">避免根據活動類型屬性進行比對。</span><span class="sxs-lookup"><span data-stu-id="a702e-138">Avoid matching on the basis of activity-type attributes.</span></span> <span data-ttu-id="a702e-139">換言之，如果某個屬性看起來是活動，則它可能不是好的比對準則。</span><span class="sxs-lookup"><span data-stu-id="a702e-139">In other words, if an attribute seems to be an activity, then it might be a poor criteria to match by.</span></span>  

   <span data-ttu-id="a702e-140">實體/欄位（第二個）- 將用於從第二個比對配對實體中進行比對的屬性。</span><span class="sxs-lookup"><span data-stu-id="a702e-140">Entity/Field (Second) - An attribute that will be used for matching from the second match pair entity.</span></span>

   <span data-ttu-id="a702e-141">標準化 - **標準化方法**：您可以在選取的屬性上使用各種標準化選項。</span><span class="sxs-lookup"><span data-stu-id="a702e-141">Normalize - **Normalization method**: Various normalization options are available for the selected attributes.</span></span> <span data-ttu-id="a702e-142">例如，移除標點符號或移除空格</span><span class="sxs-lookup"><span data-stu-id="a702e-142">For example, removing punctuation or removing spaces</span></span>

   <span data-ttu-id="a702e-143">對於組織名稱標準化 (預覽)，您也可以選取 **類型 (電話、名稱、組織)**</span><span class="sxs-lookup"><span data-stu-id="a702e-143">For Organization name normalization (Preview), you can also select **Type (Phone, Name, Organization)**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a702e-144">![Normalization-B2B](media/match-normalization-b2b.png "Normalization-B2B")</span><span class="sxs-lookup"><span data-stu-id="a702e-144">![Normalization-B2B](media/match-normalization-b2b.png "Normalization-B2B")</span></span>

   <span data-ttu-id="a702e-145">精確度等級 - 用於此條件的精確度等級。</span><span class="sxs-lookup"><span data-stu-id="a702e-145">Precision level - The level of precision that will be used for this condition.</span></span> <span data-ttu-id="a702e-146">設定比對條件的精確度等級可以有兩種類型：**基本** 和 **自訂**。</span><span class="sxs-lookup"><span data-stu-id="a702e-146">Setting a precision level for a match condition can have two types: **Basic** and **Custom**.</span></span>  
   - <span data-ttu-id="a702e-147">基本：提供四個選項以供選取：[低]、[中]、[高] 和 [完全相符]。</span><span class="sxs-lookup"><span data-stu-id="a702e-147">Basic: Provides you with four options to select from: Low, Medium, High, and Exact.</span></span> <span data-ttu-id="a702e-148">選取 **完全相符** 以只比對符合 100% 的記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-148">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="a702e-149">選取其中一個其他等級，以比對不是 100% 相同的記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-149">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
   - <span data-ttu-id="a702e-150">自訂：使用滑桿來定義記錄需要比對的自訂百分比，或在 **自訂** 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="a702e-150">Custom: Use the slider to define the custom percentage that records need to match or enter a value in the **Custom** field.</span></span> <span data-ttu-id="a702e-151">系統只會將超過此閾值的記錄比對為合併的比對配對。</span><span class="sxs-lookup"><span data-stu-id="a702e-151">The system will only match records passing this threshold as conflated match pairs.</span></span> <span data-ttu-id="a702e-152">滑桿的值介於 0 與 1 之間。</span><span class="sxs-lookup"><span data-stu-id="a702e-152">Values on the slider are between 0 and 1.</span></span> <span data-ttu-id="a702e-153">因此 0.64 表示 64%。</span><span class="sxs-lookup"><span data-stu-id="a702e-153">So 0.64 represents 64 percent.</span></span>

3. <span data-ttu-id="a702e-154">選取 **完成** 以儲存規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-154">Select **Done** to save the rule.</span></span>

### <a name="add-multiple-conditions"></a><span data-ttu-id="a702e-155">新增多個條件</span><span class="sxs-lookup"><span data-stu-id="a702e-155">Add multiple conditions</span></span>

<span data-ttu-id="a702e-156">若只要在符合多個條件時比對實體，請新增透過 AND 運算子連結的更多條件。</span><span class="sxs-lookup"><span data-stu-id="a702e-156">To match your entities only if multiple conditions are met, add more conditions that are linked through an AND operator.</span></span>

1. <span data-ttu-id="a702e-157">在 **編輯規則** 窗格中，選取 **新增條件**。</span><span class="sxs-lookup"><span data-stu-id="a702e-157">In the **Edit rule** pane, select **Add condition**.</span></span> <span data-ttu-id="a702e-158">您也可以選取現有條件旁邊的 [移除] 按鈕來刪除條件。</span><span class="sxs-lookup"><span data-stu-id="a702e-158">You can also delete conditions by selecting the remove button next to an existing condition.</span></span>

2. <span data-ttu-id="a702e-159">選取 **完成** 以儲存規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-159">Select **Done** so save the rule.</span></span>

## <a name="add-multiple-rules"></a><span data-ttu-id="a702e-160">新增多個規則</span><span class="sxs-lookup"><span data-stu-id="a702e-160">Add multiple rules</span></span>

<span data-ttu-id="a702e-161">每個條件都會套用至單一屬性對，而規則則代表條件集。</span><span class="sxs-lookup"><span data-stu-id="a702e-161">Each condition applies to a single pair of attributes, while rules represent sets of conditions.</span></span> <span data-ttu-id="a702e-162">若要讓您的實體依照不同的屬性集進行比對，您可以新增其他規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-162">To have your entities matched by different sets of attributes, you can add more rules.</span></span>

1. <span data-ttu-id="a702e-163">請在對象見解中前往 **資料** > **統整** > **比對**。</span><span class="sxs-lookup"><span data-stu-id="a702e-163">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

2. <span data-ttu-id="a702e-164">選取您要更新的實體，然後選取 **新增規則**。</span><span class="sxs-lookup"><span data-stu-id="a702e-164">Select the entity you want to update and select **Add rules**.</span></span>

3. <span data-ttu-id="a702e-165">依照[定義第一個比對配對的規則](#define-rules-for-your-first-match-pair)中所述的程序進行。</span><span class="sxs-lookup"><span data-stu-id="a702e-165">Follow the procedure as outlined in [Define rules for your first match pair](#define-rules-for-your-first-match-pair).</span></span>

> [!NOTE]
> <span data-ttu-id="a702e-166">規則順序很重要。</span><span class="sxs-lookup"><span data-stu-id="a702e-166">The rule order matters.</span></span> <span data-ttu-id="a702e-167">比對演算法會嘗試根據您的第一個規則來進行比對，而且只有在第一個規則下未找到任何符合項目時，才會繼續進行第二個規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-167">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified under the first rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="a702e-168">請在比對實體上定義重複資料刪除</span><span class="sxs-lookup"><span data-stu-id="a702e-168">Define deduplication on a match entity</span></span>

<span data-ttu-id="a702e-169">您也可以同時指定上述各節概述的交叉實體比對規則和重複資料刪除規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-169">Along with specifying cross entity matching rules as outlined in the above sections, you can also specify deduplications rules.</span></span> <span data-ttu-id="a702e-170">*重複資料刪除* 是一道流程。</span><span class="sxs-lookup"><span data-stu-id="a702e-170">*Deduplication* is a process.</span></span> <span data-ttu-id="a702e-171">它找出重複記錄、將它們合併成一筆記錄，並將所有來源記錄連結到這筆與備用識別碼合併的記錄再連結到合併記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-171">It identifies duplicate records, merges them into one record, and links all the source records to this merged record with alternate IDs to the merged record.</span></span>

<span data-ttu-id="a702e-172">找出刪除重複的資料後，該筆記錄將用於跨實體比對流程。</span><span class="sxs-lookup"><span data-stu-id="a702e-172">After a deduplicated record is identified, that record will be used in the cross-entity matching process.</span></span> <span data-ttu-id="a702e-173">重複資料刪除在實體等級執行，可套用在比對流程中使用的每個實體。</span><span class="sxs-lookup"><span data-stu-id="a702e-173">Deduplication is implemented at the entity level and can be applied to every entity used in the Match process.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="a702e-174">新增重複資料刪除規則</span><span class="sxs-lookup"><span data-stu-id="a702e-174">Add deduplication rules</span></span>

1. <span data-ttu-id="a702e-175">請在對象見解中前往 **資料** > **統整** > **比對**。</span><span class="sxs-lookup"><span data-stu-id="a702e-175">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="a702e-176">請在 **合併的重複資料** 區段中選取 **設定實體**。</span><span class="sxs-lookup"><span data-stu-id="a702e-176">In the **Merged duplicates** section, select **Set entities**.</span></span>

1. <span data-ttu-id="a702e-177">請在 **合併偏好** 區段中選取您要套用重複資料刪除規則的實體。</span><span class="sxs-lookup"><span data-stu-id="a702e-177">In the **Merge preferences** section, select the entities you want to apply deduplication to.</span></span>

1. <span data-ttu-id="a702e-178">指定合併重複記錄的方式並選擇三種合併選項中其中一種：</span><span class="sxs-lookup"><span data-stu-id="a702e-178">Specify how to merge the duplicate records and choose one of three merge options:</span></span>
   - <span data-ttu-id="a702e-179">*填滿最多的*：找出填滿最多屬性的記錄並指定為贏家記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-179">*Most filled*: Identifies the record with most filled attributes as the winner record.</span></span> <span data-ttu-id="a702e-180">這是預設合併選項。</span><span class="sxs-lookup"><span data-stu-id="a702e-180">This is the default merge option.</span></span>
   - <span data-ttu-id="a702e-181">*最新*：根據最新情況找出贏家記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-181">*Most recent*: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="a702e-182">需要日期或數字欄位來定義最新。</span><span class="sxs-lookup"><span data-stu-id="a702e-182">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="a702e-183">*最近最少情況*：根據最近最少情況找出贏家記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-183">*Least recent*: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="a702e-184">需要日期或數字欄位來定義最新。</span><span class="sxs-lookup"><span data-stu-id="a702e-184">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a702e-185">![重複資料刪除規則步驟 1](media/match-selfconflation.png "重複資料刪除規則步驟 1")</span><span class="sxs-lookup"><span data-stu-id="a702e-185">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="a702e-186">一旦選取實體並設定其合併偏好後，請選取 **建立新規則**，以便在實體等級上定義重複資料刪除規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-186">Once the entities are selected and their merge preference is set, select **Create new rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="a702e-187">**選取欄位** 列出所有您要刪除重複資料來源資料實體的可用欄位。</span><span class="sxs-lookup"><span data-stu-id="a702e-187">**Select field** lists all the available fields from that entity you want to deduplicate source data on.</span></span>
   - <span data-ttu-id="a702e-188">以交叉實體比對流程中指定的類似方式指定正規化和精確度設定。</span><span class="sxs-lookup"><span data-stu-id="a702e-188">Specify the normalization and precision settings in similar way as specified in the cross entity matching.</span></span>
   - <span data-ttu-id="a702e-189">您可以選取 **新增條件** 來定義其他條件。</span><span class="sxs-lookup"><span data-stu-id="a702e-189">You can define additional conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a702e-190">![重複資料刪除規則步驟 2](media/match-selfconflation-rules.png "重複資料刪除規則步驟 2")</span><span class="sxs-lookup"><span data-stu-id="a702e-190">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="a702e-191">您可以為某實體建立多個重複資料刪除規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-191">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="a702e-192">現在執行比對流程會根據重複資料消除規則中定義的條件分組記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-192">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="a702e-193">記錄分組之後就會套用合併規則找出贏家記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-193">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="a702e-194">然後，此勝出記錄會傳遞至交叉實體比對，同時也會傳遞非勝出記錄 (例如，替代識別碼)，以改善比對品質。</span><span class="sxs-lookup"><span data-stu-id="a702e-194">This winner record is then passed on to the cross-entity matching, along with the non-winner records (for example, alternate IDs) to improve the matching quality.</span></span>

1. <span data-ttu-id="a702e-195">任何定義為永遠符合和從不符合的自訂比對規則都會否決重複資料刪除規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-195">Any custom match rules defined for always match and never match overrule deduplication rules.</span></span> <span data-ttu-id="a702e-196">若重複資料刪除規則找出比對記錄，且自訂比對規則設定為永不符合那些記錄，則這兩筆記錄將無法符合。</span><span class="sxs-lookup"><span data-stu-id="a702e-196">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="a702e-197">比對流程執行後，您將見到重複資料刪除統計數據。</span><span class="sxs-lookup"><span data-stu-id="a702e-197">After running the match process, you will see the deduplication stats.</span></span>
   
> [!NOTE]
> <span data-ttu-id="a702e-198">指定重複資料刪除規則並非必要動作。</span><span class="sxs-lookup"><span data-stu-id="a702e-198">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="a702e-199">如果未組態此類規則，會套用系統定義的規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-199">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="a702e-200">它們先將從主索引鍵分享同值組合 (完全符合) 的各筆記錄和比對規則中的各欄位摺疊收起為單筆記錄，再將實體資料傳遞到跨實體比對規則，強化效能和系統健全性。</span><span class="sxs-lookup"><span data-stu-id="a702e-200">They collapse all records that share the same value combination (exact match) from primary key and the fields in the matching rules into a single record before passing the entity data to cross-entity matching for enhanced performance and system sanity.</span></span>

## <a name="run-your-match-order"></a><span data-ttu-id="a702e-201">執行您的比對順序</span><span class="sxs-lookup"><span data-stu-id="a702e-201">Run your match order</span></span>

<span data-ttu-id="a702e-202">定義比對規則，包括跨實體比對和重複資料刪除規則後，您可以執行比對順序。</span><span class="sxs-lookup"><span data-stu-id="a702e-202">After defining the match rules, including cross-entity matching and deduplication rules, you can run the match order.</span></span> <span data-ttu-id="a702e-203">在 **比對** 頁面上，選取 **執行** 來開始處理。</span><span class="sxs-lookup"><span data-stu-id="a702e-203">On the **Match** page, select **Run** to start the process.</span></span> <span data-ttu-id="a702e-204">比對演算法可能需要一段時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="a702e-204">The matching algorithm might take some time to complete.</span></span> <span data-ttu-id="a702e-205">您無法在 **比對** 頁面上變更屬性，直到比對程序完成為止。</span><span class="sxs-lookup"><span data-stu-id="a702e-205">You can't change properties on the **Match** page until the match process completes.</span></span> <span data-ttu-id="a702e-206">您會在 **實體** 頁面上找到建立的統整客戶設定檔實體。</span><span class="sxs-lookup"><span data-stu-id="a702e-206">You'll find the unified customer profile entity that was created on the **Entities** page.</span></span> <span data-ttu-id="a702e-207">您的統整客戶實體稱為 **ConflationMatchPairs: CustomerInsights**。</span><span class="sxs-lookup"><span data-stu-id="a702e-207">Your unified customer entity is called **ConflationMatchPairs:CustomerInsights**.</span></span>

<span data-ttu-id="a702e-208">若要進行其他變更並重新執行步驟，您可以取消進行中的比對。</span><span class="sxs-lookup"><span data-stu-id="a702e-208">To make additional changes and rerun the step, you can cancel a match in progress.</span></span> <span data-ttu-id="a702e-209">選取 **重新整理中...** 文字，然後在出現的側面窗格底部選取 **取消工作**。</span><span class="sxs-lookup"><span data-stu-id="a702e-209">Select the **Refreshing ...** text and select **Cancel job** at the bottom of the side pane that appears.</span></span>

<span data-ttu-id="a702e-210">當比對程序完成時，**重新整理中...** 文字將會變更為 **成功**，您便可以再次使用頁面的所有功能。</span><span class="sxs-lookup"><span data-stu-id="a702e-210">When the match process is complete, the **Refreshing ...** text will change to **Successful** and you can use all functionality of the page again.</span></span>

<span data-ttu-id="a702e-211">第一個比對程序會建立統整的主要實體。</span><span class="sxs-lookup"><span data-stu-id="a702e-211">The first match process results in the creation of a unified master entity.</span></span> <span data-ttu-id="a702e-212">所有後續的比對執行都會造成該實體的延伸。</span><span class="sxs-lookup"><span data-stu-id="a702e-212">All subsequent match runs result in the expansion of that entity.</span></span>

> [!TIP]
> <span data-ttu-id="a702e-213">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="a702e-213">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a702e-214">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="a702e-214">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a702e-215">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a702e-215">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a702e-216">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="a702e-216">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="deduplication-output-as-an-entity"></a><span data-ttu-id="a702e-217">重複資料刪除輸出成實體</span><span class="sxs-lookup"><span data-stu-id="a702e-217">Deduplication output as an entity</span></span>
<span data-ttu-id="a702e-218">除了作為部分交叉實體比對而建立的整合主要實體之外，重複資料刪除程序也會為比對程序中的每個實體生成新的實體，以找出重複資料刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-218">In addition to the unified master entity created as part of the cross entity matching, the deduplication process also generates a new entity for every entity from the match order to identify the deduplicated records.</span></span> <span data-ttu-id="a702e-219">這些實體與 **ConflationMatchPairs:CustomerInsights** 都可以找到，位在 **實體** 頁面的 **系統** 區段中，名稱為 **Deduplication_Datasource_Entity**。</span><span class="sxs-lookup"><span data-stu-id="a702e-219">These entities can be found along with the **ConflationMatchPairs:CustomerInsights** in the **System** section in the **Entities** page, with the name **Deduplication_Datasource_Entity**.</span></span>

<span data-ttu-id="a702e-220">重複資料刪除輸出實體包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a702e-220">A deduplication output entity contains the following information:</span></span>
- <span data-ttu-id="a702e-221">識別碼/金鑰</span><span class="sxs-lookup"><span data-stu-id="a702e-221">IDs / Keys</span></span>
  - <span data-ttu-id="a702e-222">主索引鍵欄位及其替代識別碼欄位。</span><span class="sxs-lookup"><span data-stu-id="a702e-222">Primary key field and its alternate IDs field.</span></span> <span data-ttu-id="a702e-223">替代識別碼欄位是由被辨識為記錄的替代識別碼所組成。</span><span class="sxs-lookup"><span data-stu-id="a702e-223">Alternate IDs field consists of all the alternate IDs identified for a record.</span></span>
  - <span data-ttu-id="a702e-224">根據指定的重複資料刪除欄位，Deduplication_GroupId 欄位顯示實體中辨識出的群組或叢集，裡面都是類似記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-224">Deduplication_GroupId field shows the group or cluster identified within an entity that groups all the similar records based on the specified deduplication fields.</span></span> <span data-ttu-id="a702e-225">這是為了進行系統處理。</span><span class="sxs-lookup"><span data-stu-id="a702e-225">This is  used for system processing purposes.</span></span> <span data-ttu-id="a702e-226">如果未指定手動重複資料刪除規則，並套用系統定義的重複資料刪除規則，您就不會在重複資料刪除輸出實體中找到此欄位。</span><span class="sxs-lookup"><span data-stu-id="a702e-226">If there are no manual deduplication rules specified and system defined deduplication rules apply, you may not find this field in the deduplication output entity.</span></span>
  - <span data-ttu-id="a702e-227">Deduplication_WinnerId：此欄位包含的勝出識別碼來自於已辨識的群組或叢集。</span><span class="sxs-lookup"><span data-stu-id="a702e-227">Deduplication_WinnerId: This field contains the winner ID from the identified groups or clusters.</span></span> <span data-ttu-id="a702e-228">如果 Deduplication_WinnerId 與記錄的主索引鍵相同，則表示該記錄是勝出的記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-228">If the Deduplication_WinnerId is same as the Primary key value for a record, it means that the record is the winner record.</span></span>
- <span data-ttu-id="a702e-229">用來定義重複資料刪除規則的欄位。</span><span class="sxs-lookup"><span data-stu-id="a702e-229">Fields used to define the deduplication rules.</span></span>
- <span data-ttu-id="a702e-230">規則和分數欄位，表示所套用的重複資料刪除規則和比對演算法回傳的分數。</span><span class="sxs-lookup"><span data-stu-id="a702e-230">Rule and Score fields to denote which of the deduplication rules got applied and the score returned by the matching algorithm.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="a702e-231">檢閱和驗證您的比對</span><span class="sxs-lookup"><span data-stu-id="a702e-231">Review and validate your matches</span></span>

<span data-ttu-id="a702e-232">評估您的比對配對品質並對其進行微調：</span><span class="sxs-lookup"><span data-stu-id="a702e-232">Evaluate the quality of your match pairs and refine it:</span></span>

- <span data-ttu-id="a702e-233">在 **比對** 頁面上，您會找到兩個顯示您資料初始見解的圖標。</span><span class="sxs-lookup"><span data-stu-id="a702e-233">On the **Match** page, you'll find two tiles showing initial insights about your data.</span></span>

  - <span data-ttu-id="a702e-234">**唯一客戶**：顯示系統所識別的唯一設定檔數目。</span><span class="sxs-lookup"><span data-stu-id="a702e-234">**Unique customers**: shows the number of unique profiles that the system identified.</span></span>
  - <span data-ttu-id="a702e-235">**相符的記錄**：顯示所有比對配對中的相符項目數目。</span><span class="sxs-lookup"><span data-stu-id="a702e-235">**Matched records**: shows the number of matches across all of your match pairs.</span></span>

- <span data-ttu-id="a702e-236">在 **比對順序** 表格中，您可以比來自從這個比對配對實體中的記錄數與成功相符記錄數的百分比，來評估每個比對配對的結果。</span><span class="sxs-lookup"><span data-stu-id="a702e-236">In the **Match order** table, you can assess the results of each match pair by comparing the number of records that came from this match-pair entity against the percentage of successfully matched records.</span></span>

- <span data-ttu-id="a702e-237">在 **比對順序** 表格中實體的 **規則** 區段中，您可在規則等級找到成功相符記錄的百分比。</span><span class="sxs-lookup"><span data-stu-id="a702e-237">In the **Rules** section of an entity in the **Match order** table, you'll find the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="a702e-238">透過選取規則旁邊的表格符號，您就可以在規則等級查看所有這些記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-238">By selecting the table symbol next to a rule, you can view all these records on the rule level.</span></span> <span data-ttu-id="a702e-239">我們建議您檢閱部分記錄以驗證它們是否正確相符。</span><span class="sxs-lookup"><span data-stu-id="a702e-239">We recommend that you review a subset of the records to validate that they were matched correctly.</span></span>

- <span data-ttu-id="a702e-240">在您的條件中試驗不同的精確度閾值，以找出最佳的值。</span><span class="sxs-lookup"><span data-stu-id="a702e-240">Experiment with different precision thresholds around your conditions to identify the optimal value.</span></span>

  1. <span data-ttu-id="a702e-241">針對您要實驗的比對配對規則選取省略號 (...)，並選取 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="a702e-241">Select the ellipsis (...) for the match pair rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="a702e-242">選取您要實驗的條件。</span><span class="sxs-lookup"><span data-stu-id="a702e-242">Select the condition that you want to experiment with.</span></span> <span data-ttu-id="a702e-243">每個準則都在 **比對規則** 窗格中以一列表示。</span><span class="sxs-lookup"><span data-stu-id="a702e-243">Each criterion is represented by one row in the **Match rule** pane.</span></span>

  3. <span data-ttu-id="a702e-244">您可以在 **準則預覽** 頁面上看到的內容，取決於您所選取的條件精確度等級。</span><span class="sxs-lookup"><span data-stu-id="a702e-244">What you'll see on the **Criteria preview** page depends on the precision level you've selected for a condition.</span></span> <span data-ttu-id="a702e-245">尋找所選取條件的相符和不相符記錄數目。</span><span class="sxs-lookup"><span data-stu-id="a702e-245">Find the number of matched and unmatched records for the selected condition.</span></span>

     <span data-ttu-id="a702e-246">深入了解不同閾值等級的影響。</span><span class="sxs-lookup"><span data-stu-id="a702e-246">Get a rich understanding of the effects of different threshold levels.</span></span> <span data-ttu-id="a702e-247">您可以比較在每個閾值等級下方相符的記錄數，並查看每個選項下的記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-247">You can compare how many records will be matched under each of the threshold levels, and view the records under each option.</span></span> <span data-ttu-id="a702e-248">選取每個圖標，並查看表格區段中的資料。</span><span class="sxs-lookup"><span data-stu-id="a702e-248">Select each of the tiles and review the data in the table section.</span></span>

## <a name="optimize-your-matches"></a><span data-ttu-id="a702e-249">最佳化您的比對</span><span class="sxs-lookup"><span data-stu-id="a702e-249">Optimize your matches</span></span>

<span data-ttu-id="a702e-250">重新設定部分比對參數以改善品質：</span><span class="sxs-lookup"><span data-stu-id="a702e-250">Increase the quality by reconfiguring some of your match parameters:</span></span>

- <span data-ttu-id="a702e-251">**變更比對順序**：選取 **編輯** 並變更比對順序欄位。</span><span class="sxs-lookup"><span data-stu-id="a702e-251">**Change the match order** by selecting **Edit** and change the match order fields.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="a702e-252">![編輯資料比對順序](media/configure-data-match-order-edit.png "編輯資料比對順序")</span><span class="sxs-lookup"><span data-stu-id="a702e-252">![Edit data match order](media/configure-data-match-order-edit.png "Edit data match order")</span></span>

- <span data-ttu-id="a702e-253">**變更您的規則順序**：若您定義了多個規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-253">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="a702e-254">您可以在比對規則格線中選取 **上移** 和 **下移** 選項，重新排序比對規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-254">You can reorder the match rules by selecting the **Move Up** and **Move Down** options in the match rules grid.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="a702e-255">![變更規則順序](media/configure-data-change-rule-order.png "變更規則順序")</span><span class="sxs-lookup"><span data-stu-id="a702e-255">![Change rule order](media/configure-data-change-rule-order.png "Change rule order")</span></span>

- <span data-ttu-id="a702e-256">**複製您的規則**：如果您定義了比對規則，且想要透過修改來建立類似的規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-256">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications.</span></span> <span data-ttu-id="a702e-257">請選取 **複製** 來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a702e-257">Do so by selecting **Duplicate**.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="a702e-258">![複製規則](media/configure-data-duplicate-rule.png "複製規則")</span><span class="sxs-lookup"><span data-stu-id="a702e-258">![Duplicate a rule](media/configure-data-duplicate-rule.png "Duplicate a rule")</span></span>

- <span data-ttu-id="a702e-259">**停用規則**，從比對程序排除規則時，保留比對規則。</span><span class="sxs-lookup"><span data-stu-id="a702e-259">**Deactivate a rule** to retain a match rule while excluding it from the matching process.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="a702e-260">![停用規則](media/configure-data-deactivate-rule.png "停用規則")</span><span class="sxs-lookup"><span data-stu-id="a702e-260">![Deactivate a rule](media/configure-data-deactivate-rule.png "Deactivate a rule")</span></span>

- <span data-ttu-id="a702e-261">**編輯您的規則**：選取 **編輯** 符號。</span><span class="sxs-lookup"><span data-stu-id="a702e-261">**Edit your rules** by selecting the **Edit** symbol.</span></span> <span data-ttu-id="a702e-262">您可以套用下列變更：</span><span class="sxs-lookup"><span data-stu-id="a702e-262">You can apply the following changes:</span></span>

  - <span data-ttu-id="a702e-263">變更條件的屬性：在特定的條件列中選取新屬性。</span><span class="sxs-lookup"><span data-stu-id="a702e-263">Change attributes for a condition: Select new attributes within the specific condition row.</span></span>
  - <span data-ttu-id="a702e-264">變更條件的閾值：調整精確度滑桿。</span><span class="sxs-lookup"><span data-stu-id="a702e-264">Change the threshold for a condition: Adjust the precision slider.</span></span>
  - <span data-ttu-id="a702e-265">變更條件的標準化方法：更新標準化方法。</span><span class="sxs-lookup"><span data-stu-id="a702e-265">Change the normalization method for a condition: Update the normalization method.</span></span>

## <a name="specify-your-custom-match-records"></a><span data-ttu-id="a702e-266">指定自訂的比對記錄</span><span class="sxs-lookup"><span data-stu-id="a702e-266">Specify your custom match records</span></span>

<span data-ttu-id="a702e-267">您可以指定某些記錄應一律比對或絕不比對的條件。</span><span class="sxs-lookup"><span data-stu-id="a702e-267">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="a702e-268">這些規則可以大量上傳至比對程序。</span><span class="sxs-lookup"><span data-stu-id="a702e-268">These rules can be uploaded in bulk to the match process.</span></span>

1. <span data-ttu-id="a702e-269">在 **比對順序** 畫面上選取 **自訂比對** 選項。</span><span class="sxs-lookup"><span data-stu-id="a702e-269">Select the **Custom match** option on the **Match order** screen.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a702e-270">![建立自訂比對](media/custom-match-create.png "建立自訂比對")</span><span class="sxs-lookup"><span data-stu-id="a702e-270">![Create a custom match](media/custom-match-create.png "Create a custom match")</span></span>

2. <span data-ttu-id="a702e-271">如果您未上傳實體，則會看到新的 **自訂比對** 對話方塊，需要您填寫某些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a702e-271">If you have no uploaded entities, you'll see a new **Custom match** dialog box that requires you to fill in some details.</span></span> <span data-ttu-id="a702e-272">如果您先前已提供這些詳細資料，請跳至步驟 8。</span><span class="sxs-lookup"><span data-stu-id="a702e-272">If you've provided these details earlier, skip to step 8.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a702e-273">![新增自訂比對對話方塊](media/custom-match-new-dialog-box.png "新增自訂比對對話方塊")</span><span class="sxs-lookup"><span data-stu-id="a702e-273">![New custom match dialog box](media/custom-match-new-dialog-box.png "New custom match dialog box")</span></span>

3. <span data-ttu-id="a702e-274">選取 **填入範本** 以取得範本檔案，此範本檔案可以指定實體應一律比對或絕不比對的記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-274">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="a702e-275">您需要在兩個不同的檔案中，分別填入「一律比對」記錄和「絕不比對」記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-275">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

4. <span data-ttu-id="a702e-276">此範本包含欄位，指定實體以及要在自訂比對中使用的實體主索引鍵值。</span><span class="sxs-lookup"><span data-stu-id="a702e-276">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="a702e-277">例如，如果您想要來自銷售實體的主索引鍵 12345 一律比對來自連絡人實體中的主索引鍵 34567，您必須指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="a702e-277">For example, if you want primary key 12345 from Sales entity to always match with primary key 34567 from Contact entity, you'll need to specify as follows:</span></span>
    - <span data-ttu-id="a702e-278">Entity1：銷售</span><span class="sxs-lookup"><span data-stu-id="a702e-278">Entity1: Sales</span></span>
    - <span data-ttu-id="a702e-279">Entity1Key：12345</span><span class="sxs-lookup"><span data-stu-id="a702e-279">Entity1Key: 12345</span></span>
    - <span data-ttu-id="a702e-280">Entity2：連絡人</span><span class="sxs-lookup"><span data-stu-id="a702e-280">Entity2: Contact</span></span>
    - <span data-ttu-id="a702e-281">Entity2Key：34567</span><span class="sxs-lookup"><span data-stu-id="a702e-281">Entity2Key: 34567</span></span>

   <span data-ttu-id="a702e-282">相同的範本檔案可以指定來自多個實體的自訂比對記錄。</span><span class="sxs-lookup"><span data-stu-id="a702e-282">The same template file can specify custom match records from multiple entities.</span></span>
   
   <span data-ttu-id="a702e-283">如果您想要在實體上指定重複資料刪除的自訂比對，請提供相同的實體當作 Entity1 和 Entity2 ，並設定不同主索引鍵值。</span><span class="sxs-lookup"><span data-stu-id="a702e-283">If you want to specify custom matching for deduplication on an entity, provide the same entity as both Entity1 and Entity2 and set the different primary key values.</span></span>

5. <span data-ttu-id="a702e-284">在新增您要套用的所有覆寫之後，儲存範本檔案。</span><span class="sxs-lookup"><span data-stu-id="a702e-284">After adding all the overrides you want to apply, save the template file.</span></span>

6. <span data-ttu-id="a702e-285">前往 **資料** > **資料來源** 並將範本檔案內嵌為新實體。</span><span class="sxs-lookup"><span data-stu-id="a702e-285">Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="a702e-286">內嵌之後，您可以使用它們來指定比對設定。</span><span class="sxs-lookup"><span data-stu-id="a702e-286">Once ingested, you can use them to specify the Match configuration.</span></span>

7. <span data-ttu-id="a702e-287">在上傳檔案且實體可用之後，請再次選取 **自訂比對** 選項。</span><span class="sxs-lookup"><span data-stu-id="a702e-287">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="a702e-288">您會看到選項，以指定您想要加入的實體。</span><span class="sxs-lookup"><span data-stu-id="a702e-288">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="a702e-289">從下拉式功能表選取所需實體。</span><span class="sxs-lookup"><span data-stu-id="a702e-289">Select the required entities from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a702e-290">![自訂比對覆寫](media/custom-match-overrides.png "自訂比對覆寫")</span><span class="sxs-lookup"><span data-stu-id="a702e-290">![Custom match overrides](media/custom-match-overrides.png "Custom match overrides")</span></span>

8. <span data-ttu-id="a702e-291">選取您要用於 **一律比對** 和 **絕不比對** 的實體，選取 **完成**。</span><span class="sxs-lookup"><span data-stu-id="a702e-291">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

9. <span data-ttu-id="a702e-292">針對您剛剛設定的自訂比對設定，在 **比對** 頁面上選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="a702e-292">Select **Save** on the **Match** page for the custom match configuration you just set up.</span></span>

10. <span data-ttu-id="a702e-293">在 **比對** 頁面上選取 **執行** 以開始比對程序，而自訂的比對設定將生效。</span><span class="sxs-lookup"><span data-stu-id="a702e-293">Select **Run** on the **Match** page to start the matching process, and the custom match configuration will be taken into effect.</span></span> <span data-ttu-id="a702e-294">任何系統比對規則都會由設定集所取代。</span><span class="sxs-lookup"><span data-stu-id="a702e-294">Any system matched rules are overridden by the configuration set.</span></span>

11. <span data-ttu-id="a702e-295">完成比對後，您可以驗證 **ConflationMatchPair** 實體，確認在合併比對中套用了覆寫。</span><span class="sxs-lookup"><span data-stu-id="a702e-295">Once the matching is complete, you can verify the **ConflationMatchPair** entity to confirm that the overrides are applied in the conflation matches.</span></span>

## <a name="next-step"></a><span data-ttu-id="a702e-296">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a702e-296">Next step</span></span>

<span data-ttu-id="a702e-297">在完成至少一個比對配對的比對程序之後，您可以透過 [**合併**](merge-entities.md)主題來解決資料中可能的矛盾。</span><span class="sxs-lookup"><span data-stu-id="a702e-297">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]