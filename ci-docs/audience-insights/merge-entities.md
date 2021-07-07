---
title: 將實體合併到資料統整中
description: 合併實體以建立統整的客戶設定檔。
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305616"
---
# <a name="merge-entities"></a><span data-ttu-id="3ac0a-103">合併實體</span><span class="sxs-lookup"><span data-stu-id="3ac0a-103">Merge entities</span></span>

<span data-ttu-id="3ac0a-104">合併階段是資料統整程序的最後一個階段。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="3ac0a-105">其目的在於協調衝突的資料。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="3ac0a-106">衝突資料的範例包括位於兩個資料集中的客戶名稱，但在各資料集中略有不同 (例如「Grant Marshall」與「Grant Marshal」)，或是格式不同的電話號碼 (617-803-091X 與 617803091X)。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="3ac0a-107">合併這些相互衝突的資料點，是依屬性逐一進行。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="資料統整處理中的合併頁面，顯示定義整合客戶個人資料且具有合併欄位的表格。":::

<span data-ttu-id="3ac0a-109">完成 [比對階段](match-entities.md)之後，您可以透過在 **統整** 頁面上選取 **合併** 圖標來開始合併階段。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="3ac0a-110">檢閱系統建議</span><span class="sxs-lookup"><span data-stu-id="3ac0a-110">Review system recommendations</span></span>

<span data-ttu-id="3ac0a-111">在 **資料** > **統整** > **合併** 中，您可以選擇並排除一些屬性，不要合併到整合客戶個人資料實體中。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="3ac0a-112">整合客戶個人資料是資料統整處理的結果。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="3ac0a-113">某些屬性會由系統自動合併。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="3ac0a-114">若要查看包含在自動合併屬性中的任一種屬性，請在表格的 **客戶欄位** 索引標籤中，選取該合併屬性。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="3ac0a-115">構成該合併屬性的屬性會顯示在合併屬性下方的兩個新列中。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="3ac0a-116">分割、重新命名、排除及編輯合併欄位</span><span class="sxs-lookup"><span data-stu-id="3ac0a-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="3ac0a-117">您可以變更系統處理合併屬性的方式，生成整合客戶個人資料。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="3ac0a-118">選取 **顯示詳細資訊**，然後選擇要變更的內容。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="顯示更多的下拉式功能表中的選項，可管理合併屬性。":::

<span data-ttu-id="3ac0a-120">如需詳細資訊，請參閱下節。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="3ac0a-121">分割合併欄位</span><span class="sxs-lookup"><span data-stu-id="3ac0a-121">Separate merged fields</span></span>

<span data-ttu-id="3ac0a-122">若要分割合併欄位，請在表格中尋找屬性。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="3ac0a-123">分割欄位會以個別資料點顯示在整合的客戶個人資料上。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="3ac0a-124">選取合併欄位。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="3ac0a-125">選取 **顯示更多**，然後選擇 **分割欄位**。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="3ac0a-126">確認分割。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-126">Confirm the separation.</span></span>

1. <span data-ttu-id="3ac0a-127">選取 **儲存** 並 **執行** 來處理變更。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="3ac0a-128">重新命名合併欄位</span><span class="sxs-lookup"><span data-stu-id="3ac0a-128">Rename merged fields</span></span>

<span data-ttu-id="3ac0a-129">變更合併屬性的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="3ac0a-130">您無法變更輸出實體的名稱。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="3ac0a-131">選取合併欄位。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="3ac0a-132">選取 **顯示更多**，然後選擇 **重新命名**。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="3ac0a-133">確認變更顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="3ac0a-134">選取 **儲存** 並 **執行** 來處理變更。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="3ac0a-135">排除合併欄位</span><span class="sxs-lookup"><span data-stu-id="3ac0a-135">Exclude merged fields</span></span>

<span data-ttu-id="3ac0a-136">從整合的客戶個人資料中排除屬性。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="3ac0a-137">如果欄位是用於其他程序中 (例如，客戶細分)，則請先從這些程序中移除該欄位，然後再從客戶個人資料中排除它。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="3ac0a-138">選取合併欄位。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="3ac0a-139">選取 **顯示更多**，然後選擇 **排除**。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="3ac0a-140">確認排除。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="3ac0a-141">選取 **儲存** 並 **執行** 來處理變更。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="3ac0a-142">在 **合併** 頁面上，選取 **排除欄位** 以查看所有排除欄位的清單。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="3ac0a-143">此窗格可新增排除欄位。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="3ac0a-144">手動結合欄位</span><span class="sxs-lookup"><span data-stu-id="3ac0a-144">Manually combine fields</span></span>

<span data-ttu-id="3ac0a-145">手動指定合併屬性。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="3ac0a-146">在 **合併** 頁面上，選取 **結合欄位**。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="3ac0a-147">提供 **名稱** 和 **輸出欄位名稱**。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="3ac0a-148">選擇欄位以新增。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-148">Choose a field to add.</span></span> <span data-ttu-id="3ac0a-149">選擇 **新增欄位** 結合更多欄位。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="3ac0a-150">確認排除。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="3ac0a-151">選取 **儲存** 並 **執行** 來處理變更。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="3ac0a-152">變更欄位順序</span><span class="sxs-lookup"><span data-stu-id="3ac0a-152">Change the order of fields</span></span>

<span data-ttu-id="3ac0a-153">某些實體比其他實體包含更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-153">Some entities contain more details than others.</span></span> <span data-ttu-id="3ac0a-154">如果實體包含欄位的最新資料，您可以在合併值時，設定它優先於其他實體。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="3ac0a-155">選取合併欄位。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="3ac0a-156">選取 **顯示更多**，然後選擇 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="3ac0a-157">在 **合併欄位** 窗格中，選取 **上移/下移** 來設定順序，或將它們拖放至想要的位置。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="3ac0a-158">確認變更。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-158">Confirm the change.</span></span>

1. <span data-ttu-id="3ac0a-159">選取 **儲存** 並 **執行** 來處理變更。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="3ac0a-160">執行合併</span><span class="sxs-lookup"><span data-stu-id="3ac0a-160">Run your merge</span></span>

<span data-ttu-id="3ac0a-161">不論您手動合併屬性或讓系統合併，您都可以執行合併。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="3ac0a-162">在 **合併** 頁面上，選取 **執行** 來開始處理。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3ac0a-163">![資料合併儲存與執行](media/configure-data-merge-save-run.png "資料合併儲存與執行")</span><span class="sxs-lookup"><span data-stu-id="3ac0a-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="3ac0a-164">若只想要查看反映在整合客戶實體中的輸出，請選取 **只執行合併**。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="3ac0a-165">下游程序將會按照[排程中定義的重新整理](system.md#schedule-tab)來重新整理。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="3ac0a-166">選擇 **執行合併及下游程序** 以變更來重新整理系統。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="3ac0a-167">所有程序 (包括擴充、客戶細分和量值) 都會自動重新執行。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="3ac0a-168">在所有下游程序完成後，客戶個人資料會反映出您做的所有變更。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="3ac0a-169">若要進行更多變更並重新執行步驟，您可以取消進行中的合併。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="3ac0a-170">選取 **重新整理中...**，然後在出現的側面窗格中選取 **取消工作**。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="3ac0a-171">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3ac0a-172">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3ac0a-173">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3ac0a-174">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="3ac0a-175">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3ac0a-175">Next Step</span></span>

<span data-ttu-id="3ac0a-176">設定[活動](activities.md)、[擴充](enrichment-hub.md)或[關聯](relationships.md)，以進一步了解您的客戶。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="3ac0a-177">如果您已設定活動、擴充或客戶細分，則會自動處理它們，以使用最新的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="3ac0a-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
