---
title: 比對資料統整的實體
description: 比對實體以建立統整的客戶設定檔。
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2155042d86cda0cffee1588760a06d6c7eb7077e
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085612"
---
# <a name="match-entities"></a><span data-ttu-id="46ef1-103">比對實體</span><span class="sxs-lookup"><span data-stu-id="46ef1-103">Match entities</span></span>

<span data-ttu-id="46ef1-104">比對階段指定如何將您的資料集結合至統整的客戶設定檔資料集。</span><span class="sxs-lookup"><span data-stu-id="46ef1-104">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="46ef1-105">在完成資料整合過程中的[對應](map-entities.md)步驟後，已準備好進行比對實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-105">After completing the [map step](map-entities.md) in the data unification process, you're ready to match your entities.</span></span> <span data-ttu-id="46ef1-106">比對階段需要至少兩個已比對的實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-106">The match phase requires at least two mapped entities.</span></span>

<span data-ttu-id="46ef1-107">比對頁面由三個部分組成：</span><span class="sxs-lookup"><span data-stu-id="46ef1-107">The match page consists of three sections:</span></span> 
- <span data-ttu-id="46ef1-108">摘要比對記錄數量的關鍵計量</span><span class="sxs-lookup"><span data-stu-id="46ef1-108">Key metrics that summarize the number of matched records</span></span>
- <span data-ttu-id="46ef1-109">跨實體比對的比對順序和規則</span><span class="sxs-lookup"><span data-stu-id="46ef1-109">Match order and rules for cross-entity matching</span></span>
- <span data-ttu-id="46ef1-110">比對實體的重複資料刪除規則</span><span class="sxs-lookup"><span data-stu-id="46ef1-110">Rules for deduplication of match entities</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="46ef1-111">指定比對順序</span><span class="sxs-lookup"><span data-stu-id="46ef1-111">Specify the match order</span></span>

<span data-ttu-id="46ef1-112">移至 **資料** > **統整** > **比對**，然後選取 **設定順序**，開始比對階段。</span><span class="sxs-lookup"><span data-stu-id="46ef1-112">Go to **Data** > **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="46ef1-113">每次比對將兩個或多個實體整合為一個合併實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-113">Each match unifies two or more entities into a single, consolidated entity.</span></span> <span data-ttu-id="46ef1-114">同時，它會保留唯一的客戶記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-114">At the same time, it keeps the unique customer records.</span></span> <span data-ttu-id="46ef1-115">例如，我們選擇了兩個實體：**eCommerce:eCommerceContacts** 作為主要實體，**LoyaltyScheme:loyCustomers** 作為第二實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-115">For example, we selected two entities: **eCommerce:eCommerceContacts** as the primary entity and **LoyaltyScheme:loyCustomers** as second entity.</span></span> <span data-ttu-id="46ef1-116">實體順序表示系統嘗試比對記錄的順序。</span><span class="sxs-lookup"><span data-stu-id="46ef1-116">The order of the entities specifies in which order the system will try to match the records.</span></span>

:::image type="content" source="media/match-page.png" alt-text="比對頁面的資料整合過程中統一區域的螢幕擷取畫面。":::
  
<span data-ttu-id="46ef1-118">主要實體 *eCommerce:eCommerceContacts* 與下一個實體 *LoyaltyScheme:loyCustomers* 相符。</span><span class="sxs-lookup"><span data-stu-id="46ef1-118">The primary entity *eCommerce:eCommerceContacts* is matched with the next entity *LoyaltyScheme:loyCustomers*.</span></span> <span data-ttu-id="46ef1-119">如果您有兩個以上實體，則從第一個比對步驟中產生的資料集將與接下來的實體進行比對。</span><span class="sxs-lookup"><span data-stu-id="46ef1-119">The dataset that results from the first match step is matched with the following entity if you have more than two entities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46ef1-120">您選擇作為主要實體的實體將用作整合個人資料資料集的基礎。</span><span class="sxs-lookup"><span data-stu-id="46ef1-120">The entity that you choose as your primary entity will serve as the basis for your unified profiles dataset.</span></span> <span data-ttu-id="46ef1-121">在比對階段期間選取的其他實體將會新增至此實體中。</span><span class="sxs-lookup"><span data-stu-id="46ef1-121">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="46ef1-122">這並不代表著整合實體將包含此實體中包含的 *所有* 資料。</span><span class="sxs-lookup"><span data-stu-id="46ef1-122">This doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="46ef1-123">有兩個考慮可以協助您選擇實體的階層：</span><span class="sxs-lookup"><span data-stu-id="46ef1-123">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="46ef1-124">請選擇擁有客戶最完整、最可靠的個人資料的實體來作為主要實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-124">Choose the entity with the most complete and reliable profile data about your customers as primary entity.</span></span>
> - <span data-ttu-id="46ef1-125">選擇與其他實體有多個共同屬性 (例如姓名、電話號碼或電子郵寄地址) 的實體作為主要實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-125">Choose the entity that hast several attributes in common with other entities (for example, name, phone number, or email address) as primary entity.</span></span>

<span data-ttu-id="46ef1-126">在指定比對順序後，您將在 **資料** > **整合** > **比對** 的 **比對記錄詳細資訊** 區段看到定義好的比對組。</span><span class="sxs-lookup"><span data-stu-id="46ef1-126">After specifying the match order, you'll see the defined match pairs in the **Matched records details** section on **Data** > **Unify** > **Match**.</span></span> <span data-ttu-id="46ef1-127">到比對過程完成前，關鍵計量將維持空白。</span><span class="sxs-lookup"><span data-stu-id="46ef1-127">The key metrics will be empty until the match process completes.</span></span>

## <a name="define-rules-for-match-pairs"></a><span data-ttu-id="46ef1-128">定義比對組的規則</span><span class="sxs-lookup"><span data-stu-id="46ef1-128">Define rules for match pairs</span></span>

<span data-ttu-id="46ef1-129">比對規則指定將與特定實體配對進行比對的邏輯。</span><span class="sxs-lookup"><span data-stu-id="46ef1-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

<span data-ttu-id="46ef1-130">實體名稱旁邊的 **需要規則** 警告表示對比對組沒有定義比對規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-130">The **Needs rules** warning next to an entity name suggests that no match rule is defined for a match pair.</span></span> 

:::image type="content" source="media/match-rule-add.png" alt-text="比對記錄詳細資訊區段的螢幕擷取畫面，畫面上有醒目提示新增規則的控制項。":::

1. <span data-ttu-id="46ef1-132">在 **比對記錄詳細資訊** 區段的實體下選擇 **新增規則**，定義比對規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-132">Select **Add rules** under an entity in the **Matched records details** section to define match rules.</span></span>

1. <span data-ttu-id="46ef1-133">在 **建立規則** 的窗格中，設定規則的條件。</span><span class="sxs-lookup"><span data-stu-id="46ef1-133">In the **Create rule** pane, configure the conditions for the rule.</span></span>

   :::image type="content" source="media/match-rule-conditions.png" alt-text="已新增條件，比對規則開啟的螢幕擷取畫面。":::

   - <span data-ttu-id="46ef1-135">**實體/欄位 (第一列)**：選擇相關實體和屬性以指定有可能唯一的客戶記錄屬性。</span><span class="sxs-lookup"><span data-stu-id="46ef1-135">**Entity/Field (first row)**: Choose a related entity and an attribute to specify a record property that is likely unique to a customer.</span></span> <span data-ttu-id="46ef1-136">例如，電話號碼或電子郵寄地址。</span><span class="sxs-lookup"><span data-stu-id="46ef1-136">For example, a phone number or email address.</span></span> <span data-ttu-id="46ef1-137">避免以活動類型屬性進行比對。</span><span class="sxs-lookup"><span data-stu-id="46ef1-137">Avoid matching by activity-type attributes.</span></span> <span data-ttu-id="46ef1-138">例如，購買識別碼可能會在其他記錄類型中找不到符合項目。</span><span class="sxs-lookup"><span data-stu-id="46ef1-138">For example, a purchase ID will likely find no match in other record types.</span></span>

   - <span data-ttu-id="46ef1-139">**實體/欄位 (第二列)**：選擇與第一列中指定的實體屬性相關的屬性。</span><span class="sxs-lookup"><span data-stu-id="46ef1-139">**Entity/Field (second row)**: Choose an attribute that relates to the attribute of the entity specified in the first row.</span></span>

   - <span data-ttu-id="46ef1-140">**正規化**：為選取的屬性從以下正規化選項中進行選擇。</span><span class="sxs-lookup"><span data-stu-id="46ef1-140">**Normalize**: Select from following normalization options for the selected attributes.</span></span> 
     - <span data-ttu-id="46ef1-141">空格：刪除所有空白。</span><span class="sxs-lookup"><span data-stu-id="46ef1-141">Whitespace: Removes all spaces.</span></span> <span data-ttu-id="46ef1-142">*Hello   World* 變成 *HelloWorld*。</span><span class="sxs-lookup"><span data-stu-id="46ef1-142">*Hello   World* becomes *HelloWorld*.</span></span>
     - <span data-ttu-id="46ef1-143">符號：刪除所有符號和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="46ef1-143">Symbols: Removes all symbols and special characters.</span></span> <span data-ttu-id="46ef1-144">*Head&Shoulder* 變成 *HeadShoulder*。</span><span class="sxs-lookup"><span data-stu-id="46ef1-144">*Head&Shoulder* becomes *HeadShoulder*.</span></span>
     - <span data-ttu-id="46ef1-145">文字為小寫：將所有字元轉換為小寫。</span><span class="sxs-lookup"><span data-stu-id="46ef1-145">Text to lower case: Converts all character to lower case.</span></span> <span data-ttu-id="46ef1-146">*ALL CAPS and Title Case* 變成 *all caps and title case*。</span><span class="sxs-lookup"><span data-stu-id="46ef1-146">*ALL CAPS and Title Case* becomes *all caps and title case*.</span></span>
     - <span data-ttu-id="46ef1-147">Unicode 到 ASCII：將 Unicode 轉換為 ASCII 字元。</span><span class="sxs-lookup"><span data-stu-id="46ef1-147">Unicode to ASCII: Converts unicode notation to ASCII characters.</span></span> <span data-ttu-id="46ef1-148">*/u00B2* 變成 *2*。</span><span class="sxs-lookup"><span data-stu-id="46ef1-148">*/u00B2* becomes *2*.</span></span>
     - <span data-ttu-id="46ef1-149">數字：將其他數字系統 (如羅馬數字) 轉換為阿拉伯數位。</span><span class="sxs-lookup"><span data-stu-id="46ef1-149">Numerals: Converts other numeral systems, such as Roman numerals, to Arabic numerals.</span></span> <span data-ttu-id="46ef1-150">*VIII* 變成 *8*。</span><span class="sxs-lookup"><span data-stu-id="46ef1-150">*VIII* becomes *8*.</span></span>
     - <span data-ttu-id="46ef1-151">語義類型：標準化姓名、標題、電話號碼、地址等等。</span><span class="sxs-lookup"><span data-stu-id="46ef1-151">Semantic types: Standardizes names, titles, phone numbers, addresses, etc.</span></span> 

   - <span data-ttu-id="46ef1-152">**精度**：設定適用此條件的精準度等級。</span><span class="sxs-lookup"><span data-stu-id="46ef1-152">**Precision**: Set the level of precision to apply for this condition.</span></span> 
     - <span data-ttu-id="46ef1-153">**基本**：從 *低*、*中*、*高* 與 *完全相符* 進行選擇。</span><span class="sxs-lookup"><span data-stu-id="46ef1-153">**Basic**: Choose from *Low*, *Medium*, *High*, and *Exact*.</span></span> <span data-ttu-id="46ef1-154">選取 **完全相符** 以只比對符合 100% 的記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-154">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="46ef1-155">選取其中一個其他等級，以比對不是 100% 相同的記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-155">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
     - <span data-ttu-id="46ef1-156">**自訂**：設定記錄需要相符的百分比。</span><span class="sxs-lookup"><span data-stu-id="46ef1-156">**Custom**: Set a percentage that records need to match.</span></span> <span data-ttu-id="46ef1-157">系統將只比對超過此閾值的記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-157">The system will only match records passing this threshold.</span></span>

1. <span data-ttu-id="46ef1-158">提供規則的 **名稱**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-158">Provide a **Name** for the rule.</span></span>

1. <span data-ttu-id="46ef1-159">[新增更多條件](#add-conditions-to-a-rule)或選擇 **完成** 確定最終規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-159">[Add more conditions](#add-conditions-to-a-rule) or select **Done** to finalize the rule.</span></span>

1. <span data-ttu-id="46ef1-160">或者，[新增更多規則](#add-rules-to-a-match-pair)。</span><span class="sxs-lookup"><span data-stu-id="46ef1-160">Optionally, [add more rules](#add-rules-to-a-match-pair).</span></span>

1. <span data-ttu-id="46ef1-161">選取 **儲存** 套用變更。</span><span class="sxs-lookup"><span data-stu-id="46ef1-161">Select **Save** to apply your changes.</span></span>

### <a name="add-conditions-to-a-rule"></a><span data-ttu-id="46ef1-162">對規則新增條件</span><span class="sxs-lookup"><span data-stu-id="46ef1-162">Add conditions to a rule</span></span>

<span data-ttu-id="46ef1-163">僅在屬性滿足多個條件時比對實體，對比對規則新增更多條件。</span><span class="sxs-lookup"><span data-stu-id="46ef1-163">To match entities only if attributes meet multiple conditions, add more conditions to a match rule.</span></span> <span data-ttu-id="46ef1-164">條件以邏輯運算子 AND 相連接，只有在滿足所有條件的情況下才會執行。</span><span class="sxs-lookup"><span data-stu-id="46ef1-164">Conditions are connected with a logical AND operator and thus only executed if all conditions are met.</span></span>

1. <span data-ttu-id="46ef1-165">移至 **資料** > **整合** > **比對**，並對要新增條件的規則選擇 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-165">Go to **Data** > **Unify** > **Match** and select **Edit** on the rule you want to add conditions to.</span></span>

1. <span data-ttu-id="46ef1-166">在 **編輯規則** 窗格中，選取 **新增條件**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-166">In the **Edit rule** pane, select **Add condition**.</span></span>

1. <span data-ttu-id="46ef1-167">選取 **完成** 以儲存規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-167">Select **Done** so save the rule.</span></span>

### <a name="add-rules-to-a-match-pair"></a><span data-ttu-id="46ef1-168">將規則新增到比對組中</span><span class="sxs-lookup"><span data-stu-id="46ef1-168">Add rules to a match pair</span></span>

<span data-ttu-id="46ef1-169">比對規則代表條件組。</span><span class="sxs-lookup"><span data-stu-id="46ef1-169">Match rules represent sets of conditions.</span></span> <span data-ttu-id="46ef1-170">要以用到多個屬性的條件來比對實體，新增更多規則</span><span class="sxs-lookup"><span data-stu-id="46ef1-170">To match entities by conditions based on multiple attributes, add more rules</span></span>

1.  <span data-ttu-id="46ef1-171">移至 **資料** > **整合** > **比對**，並對要新增規則的實體選擇 **新增規則**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-171">Go to **Data** > **Unify** > **Match** and select **Add rule** on the entity you want to add rules to.</span></span>

2. <span data-ttu-id="46ef1-172">遵循[對比對組訂定規則中的 ](#define-rules-for-match-pairs)步驟。</span><span class="sxs-lookup"><span data-stu-id="46ef1-172">Follow the steps in [Define rules for match pairs](#define-rules-for-match-pairs).</span></span>

> [!NOTE]
> <span data-ttu-id="46ef1-173">規則的順序很重要。</span><span class="sxs-lookup"><span data-stu-id="46ef1-173">The order of rules matters.</span></span> <span data-ttu-id="46ef1-174">比對演算法會嘗試根據您的第一個規則進行比對，並且只有在第一個規則沒有相符的時後繼續進行第二個規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-174">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified with the first rule.</span></span>

### <a name="change-the-entity-order-in-match-rules"></a><span data-ttu-id="46ef1-175">變更比對規則中的實體順序</span><span class="sxs-lookup"><span data-stu-id="46ef1-175">Change the entity order in match rules</span></span>

<span data-ttu-id="46ef1-176">您可以為比對規則重新排序實體，以變更它們的處理順序。</span><span class="sxs-lookup"><span data-stu-id="46ef1-176">You can reorder entities for match rules to change the order in which they are processed.</span></span> <span data-ttu-id="46ef1-177">由於變更的順序而發生衝突的規則將會被移除。</span><span class="sxs-lookup"><span data-stu-id="46ef1-177">Rules that are conflicting because of a changed order will be removed.</span></span> <span data-ttu-id="46ef1-178">您必須用更新設定重新建立被移除的規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-178">You have to recreate removed rules with an updated configuration.</span></span>

1. <span data-ttu-id="46ef1-179">移至 **資料** > **統整** > **比對** 並選取 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-179">Go to **Data** > **Unify** > **Match** and select **Edit**.</span></span>

1. <span data-ttu-id="46ef1-180">在 **編輯規則** 窗格中，選取 **上移/下移** 控制項，或拖放實體以變更順序。</span><span class="sxs-lookup"><span data-stu-id="46ef1-180">In the **Edit rule** pane, select the **Move up/down** control or drag and drop entities to change the order.</span></span>

   :::image type="content" source="media/reorder-match-rules.png" alt-text="變更在 比對階段處理實體順序的選項。":::

1. <span data-ttu-id="46ef1-182">選取 **完成** 以儲存規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-182">Select **Done** so save the rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="46ef1-183">請在比對實體上定義重複資料刪除</span><span class="sxs-lookup"><span data-stu-id="46ef1-183">Define deduplication on a match entity</span></span>

<span data-ttu-id="46ef1-184">除了[跨實體比對規則](#define-rules-for-match-pairs)外，您還可以指定重複資料刪除規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-184">In addition to [cross-entity match rules](#define-rules-for-match-pairs), you can also specify deduplications rules.</span></span> <span data-ttu-id="46ef1-185">*重複資料刪除* 是比對記錄時的另一個過程。</span><span class="sxs-lookup"><span data-stu-id="46ef1-185">*Deduplication* is another process when matching records.</span></span> <span data-ttu-id="46ef1-186">它會找出重複的記錄並將其合併到一個記錄中。</span><span class="sxs-lookup"><span data-stu-id="46ef1-186">It identifies duplicate records and merges them into one record.</span></span> <span data-ttu-id="46ef1-187">來源記錄被連結到具備備用識別碼的合併後記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-187">Source records get linked to the merged record with alternate IDs.</span></span>

<span data-ttu-id="46ef1-188">重複資料刪除的記錄將用在跨實體比對流程。</span><span class="sxs-lookup"><span data-stu-id="46ef1-188">Deduplicated records will be used in the cross-entity matching process.</span></span> <span data-ttu-id="46ef1-189">重複資料刪除發生在單個實體上，可以對比對組使用的每個實體設定。</span><span class="sxs-lookup"><span data-stu-id="46ef1-189">Deduplication happens on individual entities and can be configured every entity used in match pairs.</span></span>

<span data-ttu-id="46ef1-190">指定重複資料刪除規則並非必要動作。</span><span class="sxs-lookup"><span data-stu-id="46ef1-190">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="46ef1-191">如果未組態此類規則，會套用系統定義的規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-191">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="46ef1-192">他們將所有記錄合併到單個記錄中，然後將實體數據傳遞給跨實體比對增強效能。</span><span class="sxs-lookup"><span data-stu-id="46ef1-192">They combine all records into a single record before passing the entity data to cross-entity matching for enhanced performance.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="46ef1-193">新增重複資料刪除規則</span><span class="sxs-lookup"><span data-stu-id="46ef1-193">Add deduplication rules</span></span>

1. <span data-ttu-id="46ef1-194">請前往 **資料** > **統整** > **比對**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-194">Go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="46ef1-195">請在 **合併的重複資料** 區段中選取 **設定實體**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-195">In the **Merged duplicates** section, select **Set entities**.</span></span> <span data-ttu-id="46ef1-196">如果已經建立重複資料刪除規則，請選擇 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-196">In case deduplication rules are already created, select **Edit**.</span></span>

1. <span data-ttu-id="46ef1-197">請在 **合併偏好** 窗格中選取您要執行重複資料刪除規則的實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-197">In the **Merge preferences** pane, choose the entities you want to run deduplication on.</span></span>

1. <span data-ttu-id="46ef1-198">指定合併重複資料記錄的方式並從三個選項中選擇一個：</span><span class="sxs-lookup"><span data-stu-id="46ef1-198">Specify how to combine the duplicate records and choose one of three options:</span></span>
   - <span data-ttu-id="46ef1-199">**最多填滿**：找出填滿最多屬性的記錄作為勝出記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-199">**Most filled**: Identifies the record with most populated attribute fields as the winner record.</span></span> <span data-ttu-id="46ef1-200">這是預設合併選項。</span><span class="sxs-lookup"><span data-stu-id="46ef1-200">It's the default merge option.</span></span>
   - <span data-ttu-id="46ef1-201">**最新**：根據最新情況找出贏家記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-201">**Most recent**: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="46ef1-202">需要日期或數字欄位來定義最新。</span><span class="sxs-lookup"><span data-stu-id="46ef1-202">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="46ef1-203">**最近最少情況**：根據最近最少情況找出贏家記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-203">**Least recent**: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="46ef1-204">需要日期或數字欄位來定義最新。</span><span class="sxs-lookup"><span data-stu-id="46ef1-204">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="46ef1-205">![重複資料刪除規則步驟 1](media/match-selfconflation.png "重複資料刪除規則步驟 1")</span><span class="sxs-lookup"><span data-stu-id="46ef1-205">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="46ef1-206">當選取實體並設定其合併偏好後，請選取 **新增規則**，以便在實體層級上定義重複資料刪除規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-206">Once the entities are selected and their merge preference is set, select **Add rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="46ef1-207">**選擇欄位** 列出該實體的所有可用欄位。</span><span class="sxs-lookup"><span data-stu-id="46ef1-207">**Select field** lists all the available fields from that entity.</span></span> <span data-ttu-id="46ef1-208">選擇要檢查重複的欄位。</span><span class="sxs-lookup"><span data-stu-id="46ef1-208">Choose the field you want to check for duplicates.</span></span> <span data-ttu-id="46ef1-209">選擇對每個客戶很可能是唯一的欄位。</span><span class="sxs-lookup"><span data-stu-id="46ef1-209">Choose fields that are likely unique for every single customer.</span></span> <span data-ttu-id="46ef1-210">例如，電子郵件地址，或姓名、城市和電話號碼的組合。</span><span class="sxs-lookup"><span data-stu-id="46ef1-210">For example, an email address, or the combination of name, city, and phone number.</span></span>
   - <span data-ttu-id="46ef1-211">指定正規化和精確度設定。</span><span class="sxs-lookup"><span data-stu-id="46ef1-211">Specify the normalization and precision settings.</span></span>
   - <span data-ttu-id="46ef1-212">您可以選取 **新增條件** 定義更多條件。</span><span class="sxs-lookup"><span data-stu-id="46ef1-212">Define more conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="46ef1-213">![重複資料刪除規則步驟 2](media/match-selfconflation-rules.png "重複資料刪除規則步驟 2")</span><span class="sxs-lookup"><span data-stu-id="46ef1-213">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="46ef1-214">您可以為某實體建立多個重複資料刪除規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-214">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="46ef1-215">現在執行比對流程會根據重複資料消除規則中定義的條件分組記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-215">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="46ef1-216">記錄分組之後就會套用合併規則找出贏家記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-216">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="46ef1-217">然後，此勝出記錄會傳遞至交叉實體比對，同時也會傳遞非勝出記錄 (例如，替代識別碼)，以改善比對品質。</span><span class="sxs-lookup"><span data-stu-id="46ef1-217">This winner record is then passed on to the cross-entity matching, along with the non-winner records (for example, alternate IDs) to improve the matching quality.</span></span>

1. <span data-ttu-id="46ef1-218">定義好的任何自訂的比對規則都會覆寫重複資料刪除規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-218">Any custom match rules defined overwrite deduplication rules.</span></span> <span data-ttu-id="46ef1-219">若重複資料刪除規則找出比對記錄，且自訂比對規則設定為永不符合那些記錄，則這兩筆記錄將無法符合。</span><span class="sxs-lookup"><span data-stu-id="46ef1-219">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="46ef1-220">[執行比對流程](#run-the-match-process)後，您將在關鍵計量圖格中看到重複資料刪除的統計資料。</span><span class="sxs-lookup"><span data-stu-id="46ef1-220">After [running the match process](#run-the-match-process), you will see the deduplication stats in the key metrics tiles.</span></span>

### <a name="deduplication-output-as-an-entity"></a><span data-ttu-id="46ef1-221">重複資料刪除輸出成實體</span><span class="sxs-lookup"><span data-stu-id="46ef1-221">Deduplication output as an entity</span></span>

<span data-ttu-id="46ef1-222">重複資料刪除過程為比對組中的每個實體建立一個新實體，以找出刪除重複的記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-222">The deduplication process creates a new entity for every entity from the match pairs to identify the deduplicated records.</span></span> <span data-ttu-id="46ef1-223">這些實體與 **ConflationMatchPairs:CustomerInsights** 在 **實體** 頁面的 **系統** 區段中，名稱為 **Deduplication_DataSource_Entity**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-223">These entities can be found along with the **ConflationMatchPairs:CustomerInsights** in the **System** section in the **Entities** page, with the name **Deduplication_DataSource_Entity**.</span></span>

<span data-ttu-id="46ef1-224">重複資料刪除輸出實體包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="46ef1-224">A deduplication output entity contains the following information:</span></span>
- <span data-ttu-id="46ef1-225">識別碼/金鑰</span><span class="sxs-lookup"><span data-stu-id="46ef1-225">IDs / Keys</span></span>
  - <span data-ttu-id="46ef1-226">主索引鍵欄位及其替代識別碼欄位。</span><span class="sxs-lookup"><span data-stu-id="46ef1-226">Primary key field and its alternate IDs field.</span></span> <span data-ttu-id="46ef1-227">替代識別碼欄位是由被辨識為記錄的替代識別碼所組成。</span><span class="sxs-lookup"><span data-stu-id="46ef1-227">Alternate IDs field consists of all the alternate IDs identified for a record.</span></span>
  - <span data-ttu-id="46ef1-228">根據指定的重複資料刪除欄位，Deduplication_GroupId 欄位顯示實體中辨識出的群組或叢集，裡面都是類似記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-228">Deduplication_GroupId field shows the group or cluster identified within an entity that groups all the similar records based on the specified deduplication fields.</span></span> <span data-ttu-id="46ef1-229">為系統處理的需求而被使用。</span><span class="sxs-lookup"><span data-stu-id="46ef1-229">It's used for system processing purposes.</span></span> <span data-ttu-id="46ef1-230">如果未指定手動重複資料刪除規則，並套用系統定義的重複資料刪除規則，您就不會在重複資料刪除輸出實體中找到此欄位。</span><span class="sxs-lookup"><span data-stu-id="46ef1-230">If there are no manual deduplication rules specified and system defined deduplication rules apply, you may not find this field in the deduplication output entity.</span></span>
  - <span data-ttu-id="46ef1-231">Deduplication_WinnerId：此欄位包含的勝出識別碼來自於已辨識的群組或叢集。</span><span class="sxs-lookup"><span data-stu-id="46ef1-231">Deduplication_WinnerId: This field contains the winner ID from the identified groups or clusters.</span></span> <span data-ttu-id="46ef1-232">如果 Deduplication_WinnerId 與記錄的主索引鍵相同，則表示該記錄是勝出的記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-232">If the Deduplication_WinnerId is same as the Primary key value for a record, it means that the record is the winner record.</span></span>
- <span data-ttu-id="46ef1-233">用來定義重複資料刪除規則的欄位。</span><span class="sxs-lookup"><span data-stu-id="46ef1-233">Fields used to define the deduplication rules.</span></span>
- <span data-ttu-id="46ef1-234">規則和分數欄位，表示所套用的重複資料刪除規則和比對演算法回傳的分數。</span><span class="sxs-lookup"><span data-stu-id="46ef1-234">Rule and Score fields to denote which of the deduplication rules got applied and the score returned by the matching algorithm.</span></span>
   
## <a name="run-the-match-process"></a><span data-ttu-id="46ef1-235">執行比對程序</span><span class="sxs-lookup"><span data-stu-id="46ef1-235">Run the match process</span></span>

<span data-ttu-id="46ef1-236">設定好比對規則，包括跨實體比對和重複資料刪除規則後，您可以執行比對程序。</span><span class="sxs-lookup"><span data-stu-id="46ef1-236">With configured match rules, including cross-entity matching and deduplication rules, you can run the match process.</span></span> 

<span data-ttu-id="46ef1-237">前往 **資料** > **整合** > **比對** 並選擇 **執行** 啟動程序。</span><span class="sxs-lookup"><span data-stu-id="46ef1-237">Go to **Data** > **Unify** > **Match** and select **Run** to start the process.</span></span> <span data-ttu-id="46ef1-238">比對演算法需要一些時間來完成，執行完成前您無法更改設定。</span><span class="sxs-lookup"><span data-stu-id="46ef1-238">The matching algorithm takes some time to complete and you can't change the configuration until it completes.</span></span> <span data-ttu-id="46ef1-239">若要變更，您可以取消執行：</span><span class="sxs-lookup"><span data-stu-id="46ef1-239">To make changes, you can cancel the run.</span></span> <span data-ttu-id="46ef1-240">選擇工作的狀態，並在 **程序詳細資訊** 窗格上選擇 **取消工作**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-240">Select the status of the job and select **Cancel job** on the **Progress details** pane.</span></span>

<span data-ttu-id="46ef1-241">在 **實體** 頁面上，您將找到成功執行的結果(整合的客戶個人資料實體)。</span><span class="sxs-lookup"><span data-stu-id="46ef1-241">You'll find the result of a successful run, the unified customer profile entity, on the **Entities** page.</span></span> <span data-ttu-id="46ef1-242">在 **個人資料** 區段，您的整合客戶實體名稱為 **客戶**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-242">Your unified customer entity is called **Customers** in the **Profiles** section.</span></span> <span data-ttu-id="46ef1-243">第一次成功的比對執行建立了整合 *客戶* 實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-243">The first successful match run creates the unified *Customer* entity.</span></span> <span data-ttu-id="46ef1-244">後續所有比對執行都會擴充該實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-244">All subsequent match runs expand that entity.</span></span>

> [!TIP]
> <span data-ttu-id="46ef1-245">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="46ef1-245">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="46ef1-246">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="46ef1-246">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="46ef1-247">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="46ef1-247">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="46ef1-248">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="46ef1-248">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="46ef1-249">檢閱和驗證您的比對</span><span class="sxs-lookup"><span data-stu-id="46ef1-249">Review and validate your matches</span></span>

<span data-ttu-id="46ef1-250">前往 **資料** > **整合** > **比對**，評估比對組的品質，必要時對進行修改。</span><span class="sxs-lookup"><span data-stu-id="46ef1-250">Go to **Data** > **Unify** > **Match** to evaluate the quality of your match pairs and refine them if necessary.</span></span>

<span data-ttu-id="46ef1-251">頁面頂部的圖格顯示關鍵計量，摘要相符的記錄和重複。</span><span class="sxs-lookup"><span data-stu-id="46ef1-251">The tiles on top of the page show key metrics, summarizing the number of matched records and duplicates.</span></span>

:::image type="content" source="media/match-KPIs.png" alt-text="比對頁面上關鍵計量的螢幕擷取畫面 (已裁剪)，畫面上有數字和詳細資訊。":::

- <span data-ttu-id="46ef1-253">**唯一來源記錄** 顯示上次比對執行處理的個別來源記錄的數量。</span><span class="sxs-lookup"><span data-stu-id="46ef1-253">**Unique source records** shows the number of individual source records that were processed in last match run.</span></span>
- <span data-ttu-id="46ef1-254">**比對和未比對的記錄** 醒目提示比對規則處理後保留多少唯一記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-254">**Matched and non-matched records** highlights how many unique records remain after processing the match rules.</span></span>
- <span data-ttu-id="46ef1-255">**相符的記錄僅** 顯示所有比對組的相符數量。</span><span class="sxs-lookup"><span data-stu-id="46ef1-255">**Matched records only** shows the number of matches across all of your match pairs.</span></span>

<span data-ttu-id="46ef1-256">您可以在 **相符紀錄詳細資料** 表中評估每個比對組的結果及其規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-256">You can assess the results of each match pair and its rules in the **Matched records details** table.</span></span> <span data-ttu-id="46ef1-257">比較來自一組比對組對的記錄數量與成功相符記錄的百分比。</span><span class="sxs-lookup"><span data-stu-id="46ef1-257">Compare the number of records that came from a match pair against the percentage of successfully matched records.</span></span>

<span data-ttu-id="46ef1-258">檢閱比對組的規則，在規則等級查看成功相符記錄的百分比。</span><span class="sxs-lookup"><span data-stu-id="46ef1-258">Review the rules of a match pair to see the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="46ef1-259">選擇省略符號 (...)，然後選擇 **比對預覽**，在規則等級上查看這些全部記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-259">Select the ellipsis (...) and then select **Match preview** to view all these records on the rule level.</span></span> <span data-ttu-id="46ef1-260">我們建議您查看一些記錄，以驗證它們是否正確比對。</span><span class="sxs-lookup"><span data-stu-id="46ef1-260">We recommend that you take a look at some records to validate that they were matched correctly.</span></span>

<span data-ttu-id="46ef1-261">在條件上嘗試不同的精度度閾值來找到最佳值。</span><span class="sxs-lookup"><span data-stu-id="46ef1-261">Try different precision thresholds on conditions to find the optimal value.</span></span>

  1. <span data-ttu-id="46ef1-262">選擇要試驗的規則其省略符號 (...)，並選擇 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-262">Select the ellipsis (...) for the rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="46ef1-263">在您要修訂的條件中，調整精準度的值。</span><span class="sxs-lookup"><span data-stu-id="46ef1-263">Change the precisions values in the conditions you want to revise.</span></span>

  3. <span data-ttu-id="46ef1-264">選擇 **預覽**，查看選擇的條件的相符和不相符的記錄數量。</span><span class="sxs-lookup"><span data-stu-id="46ef1-264">Select **Preview** so see the number of matched and unmatched records for the selected condition.</span></span>

## <a name="manage-match-rules"></a><span data-ttu-id="46ef1-265">管理比對規則</span><span class="sxs-lookup"><span data-stu-id="46ef1-265">Manage match rules</span></span>

<span data-ttu-id="46ef1-266">您可以重新設定和微調大部分的比對參數。</span><span class="sxs-lookup"><span data-stu-id="46ef1-266">You can reconfigure and fine-tune most of the match parameters.</span></span>

:::image type="content" source="media/match-rules-management.png" alt-text="下拉式功能表上比對規則選項的螢幕擷取畫面。":::

- <span data-ttu-id="46ef1-268">**變更您的規則順序**：若您定義了多個規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-268">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="46ef1-269">您可以通過選擇 **向上移動** 和 **向下移動** 選項或通過拖放來重新排序比對規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-269">You can reorder the match rules by selecting the **Move Up** and **Move Down** options or by drag and drop.</span></span>

- <span data-ttu-id="46ef1-270">藉由選擇 **編輯** 和選擇不同的欄位來 **變更規則條件**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-270">**Change rule conditions** by selecting **Edit** and choose different fields.</span></span>

- <span data-ttu-id="46ef1-271">**停用規則**，從比對程序排除規則時，保留比對規則。</span><span class="sxs-lookup"><span data-stu-id="46ef1-271">**Deactivate a rule** to retain a match rule while excluding it from the matching process.</span></span>

- <span data-ttu-id="46ef1-272">**複製您的規則**，如果你已經定義了比對規則，並希望以修改建立類似的規則，選擇 **複製**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-272">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications, select **Duplicate**.</span></span>

- <span data-ttu-id="46ef1-273">選擇 **刪除** 符號 **刪除規則**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-273">**Delete a rule** by selecting the **Delete** symbol.</span></span>

## <a name="specify-custom-match-conditions"></a><span data-ttu-id="46ef1-274">指定自訂比對條件</span><span class="sxs-lookup"><span data-stu-id="46ef1-274">Specify custom match conditions</span></span>

<span data-ttu-id="46ef1-275">您可以指定某些記錄應一律比對或絕不比對的條件。</span><span class="sxs-lookup"><span data-stu-id="46ef1-275">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="46ef1-276">可以上傳這些規則覆寫標準比對過程。</span><span class="sxs-lookup"><span data-stu-id="46ef1-276">These rules can be uploaded to override the standard match process.</span></span> <span data-ttu-id="46ef1-277">例如，如果我們的記錄中有約翰．多伊一世和約翰．多伊二世，系統可能會將他們比對成一個人。</span><span class="sxs-lookup"><span data-stu-id="46ef1-277">For example, if there are John Doe I and John Doe II in our records, the system might match them as one person.</span></span> <span data-ttu-id="46ef1-278">自訂比對規則讓您能指定他們的個人資料參照到不同的人。</span><span class="sxs-lookup"><span data-stu-id="46ef1-278">Custom match rules let you specify that their profiles refer to different people.</span></span> 

1. <span data-ttu-id="46ef1-279">前往 **資料** > **整合** > **比對**，並在 **相符記錄詳細資訊** 區段中選擇 **自訂比對**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-279">Go to **Data** > **Unify** > **Match** and select **Custom match** in the **Matched records details** section.</span></span>

  :::image type="content" source="media/custom-match-create.png" alt-text="比對規則區段的螢幕擷取畫面，畫面上有醒目提示自訂比對的控制項。":::

1. <span data-ttu-id="46ef1-281">如果您沒有設定自訂比對規則，您將看到一個新的 **自訂比對** 窗格，其中有更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="46ef1-281">If you have no custom match rules set, you'll see a new **Custom match** pane with more details.</span></span>

1. <span data-ttu-id="46ef1-282">選取 **填入範本** 以取得範本檔案，此範本檔案可以指定實體應一律比對或絕不比對的記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-282">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="46ef1-283">您需要在兩個不同的檔案中，分別填入「一律比對」記錄和「絕不比對」記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-283">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

1. <span data-ttu-id="46ef1-284">此範本包含欄位，指定實體以及要在自訂比對中使用的實體主索引鍵值。</span><span class="sxs-lookup"><span data-stu-id="46ef1-284">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="46ef1-285">例如，如果您希望 *銷售* 實體的主索引鍵 *12345* 永遠與 *聯繫人* 實體的主索引鍵 *34567* 相符，請寫入範本：</span><span class="sxs-lookup"><span data-stu-id="46ef1-285">For example, if you want primary key *12345* from *Sales* entity to always match with primary key *34567* from *Contact* entity, fill in the template:</span></span>
    - <span data-ttu-id="46ef1-286">Entity1：銷售</span><span class="sxs-lookup"><span data-stu-id="46ef1-286">Entity1: Sales</span></span>
    - <span data-ttu-id="46ef1-287">Entity1Key：12345</span><span class="sxs-lookup"><span data-stu-id="46ef1-287">Entity1Key: 12345</span></span>
    - <span data-ttu-id="46ef1-288">Entity2：連絡人</span><span class="sxs-lookup"><span data-stu-id="46ef1-288">Entity2: Contact</span></span>
    - <span data-ttu-id="46ef1-289">Entity2Key：34567</span><span class="sxs-lookup"><span data-stu-id="46ef1-289">Entity2Key: 34567</span></span>

   <span data-ttu-id="46ef1-290">相同的範本檔案可以指定來自多個實體的自訂比對記錄。</span><span class="sxs-lookup"><span data-stu-id="46ef1-290">The same template file can specify custom match records from multiple entities.</span></span>
   
   <span data-ttu-id="46ef1-291">如果您想要在實體上指定重複資料刪除的自訂比對，請提供相同的實體當作 Entity1 和 Entity2 ，並設定不同主索引鍵值。</span><span class="sxs-lookup"><span data-stu-id="46ef1-291">If you want to specify custom matching for deduplication on an entity, provide the same entity as both Entity1 and Entity2 and set the different primary key values.</span></span>

1. <span data-ttu-id="46ef1-292">在新增您要套用的所有覆寫之後，儲存範本檔案。</span><span class="sxs-lookup"><span data-stu-id="46ef1-292">After adding all the overrides you want to apply, save the template file.</span></span>

1. <span data-ttu-id="46ef1-293">前往 **資料** > **資料來源** 並將範本檔案內嵌為新實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-293">Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="46ef1-294">內嵌之後，您可以使用它們來指定比對設定。</span><span class="sxs-lookup"><span data-stu-id="46ef1-294">Once ingested, you can use them to specify the Match configuration.</span></span>

1. <span data-ttu-id="46ef1-295">在上傳檔案且實體可用之後，請再次選取 **自訂比對** 選項。</span><span class="sxs-lookup"><span data-stu-id="46ef1-295">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="46ef1-296">您會看到選項，以指定您想要加入的實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-296">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="46ef1-297">從下拉式功能表選取所需實體。</span><span class="sxs-lookup"><span data-stu-id="46ef1-297">Select the required entities from the drop-down menu.</span></span>

   :::image type="content" source="media/custom-match-overrides.png" alt-text="螢幕擷取畫面上為選擇覆寫自訂比對案例的對話方塊。":::

1. <span data-ttu-id="46ef1-299">選取您要用於 **一律比對** 和 **絕不比對** 的實體，選取 **完成**。</span><span class="sxs-lookup"><span data-stu-id="46ef1-299">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

1. <span data-ttu-id="46ef1-300">在 **比對** 頁面上選擇 **儲存**"套用自訂比對設定。</span><span class="sxs-lookup"><span data-stu-id="46ef1-300">Select **Save** on the **Match** page to apply the custom match configuration.</span></span>

1. <span data-ttu-id="46ef1-301">在 **比對** 頁面上選擇 **執行** 啟動比對程序。</span><span class="sxs-lookup"><span data-stu-id="46ef1-301">Select **Run** on the **Match** page to start the matching process.</span></span> <span data-ttu-id="46ef1-302">其他指定的比對規則被自訂比對設定覆寫。</span><span class="sxs-lookup"><span data-stu-id="46ef1-302">Other specified match rules are overridden by the custom match configuration.</span></span>

> [!TIP]
> <span data-ttu-id="46ef1-303">前往 **資料** > **實體** 並查看 **ConflationMatchPair** 確認套用覆寫。</span><span class="sxs-lookup"><span data-stu-id="46ef1-303">Go to **Data** > **Entities** and review the **ConflationMatchPair** entity to confirm that the overrides are applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="46ef1-304">下一個步驟</span><span class="sxs-lookup"><span data-stu-id="46ef1-304">Next step</span></span>

<span data-ttu-id="46ef1-305">在完成至少一個比對配對的比對程序之後，您可以透過 [**合併**](merge-entities.md)主題來解決資料中可能的矛盾。</span><span class="sxs-lookup"><span data-stu-id="46ef1-305">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
