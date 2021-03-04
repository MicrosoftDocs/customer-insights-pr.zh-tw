---
title: 將實體合併到資料統整中
description: 合併實體以建立統整的客戶設定檔。
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268492"
---
# <a name="merge-entities"></a><span data-ttu-id="3262a-103">合併實體</span><span class="sxs-lookup"><span data-stu-id="3262a-103">Merge entities</span></span>

<span data-ttu-id="3262a-104">合併階段是資料統整程序的最後一個階段。</span><span class="sxs-lookup"><span data-stu-id="3262a-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="3262a-105">其目的在於協調衝突的資料。</span><span class="sxs-lookup"><span data-stu-id="3262a-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="3262a-106">衝突資料的範例包括位於兩個資料集中的客戶名稱，但在各資料集中略有不同 (例如「Grant Marshall」與「Grant Marshal」)，或是格式不同的電話號碼 (617-803-091X 與 617803091X)。</span><span class="sxs-lookup"><span data-stu-id="3262a-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="3262a-107">合併這些相互衝突的資料點，是依屬性逐一進行。</span><span class="sxs-lookup"><span data-stu-id="3262a-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="3262a-108">完成 [比對階段](match-entities.md)之後，您可以透過在 **統整** 頁面上選取 **合併** 圖標來開始合併階段。</span><span class="sxs-lookup"><span data-stu-id="3262a-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="3262a-109">檢閱系統建議</span><span class="sxs-lookup"><span data-stu-id="3262a-109">Review system recommendations</span></span>

<span data-ttu-id="3262a-110">在 **合併** 頁面上，您可以選擇並排除要在您的統整客戶設定檔實體 (設定程序的結果) 中合併的屬性。</span><span class="sxs-lookup"><span data-stu-id="3262a-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="3262a-111">某些屬性會由系統自動合併。</span><span class="sxs-lookup"><span data-stu-id="3262a-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="3262a-112">檢視合併的屬性</span><span class="sxs-lookup"><span data-stu-id="3262a-112">View merged attributes</span></span>

<span data-ttu-id="3262a-113">若要查看其中一個自動合併屬性所包含的屬性，請選取該合併屬性。</span><span class="sxs-lookup"><span data-stu-id="3262a-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="3262a-114">構成該合併屬性的兩個屬性會顯示在合併屬性下方的兩個新列中。</span><span class="sxs-lookup"><span data-stu-id="3262a-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3262a-115">![選取合併的屬性](media/configure-data-merge-profile-attributes.png "選取合併的屬性")</span><span class="sxs-lookup"><span data-stu-id="3262a-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="3262a-116">分割合併的屬性</span><span class="sxs-lookup"><span data-stu-id="3262a-116">Separate merged attributes</span></span>

<span data-ttu-id="3262a-117">若要分割或取消合併任何自動合併的屬性，請在 **設定檔屬性** 表格中尋找屬性。</span><span class="sxs-lookup"><span data-stu-id="3262a-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="3262a-118">選取省略符號 (...) 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3262a-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="3262a-119">在下拉式清單中，選取 **分割欄位**。</span><span class="sxs-lookup"><span data-stu-id="3262a-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="3262a-120">移除合併的屬性</span><span class="sxs-lookup"><span data-stu-id="3262a-120">Remove merged attributes</span></span>

<span data-ttu-id="3262a-121">若要從最終的客戶設定檔實體中排除屬性，請在 **設定檔屬性** 表格中找到它。</span><span class="sxs-lookup"><span data-stu-id="3262a-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="3262a-122">選取省略符號 (...) 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3262a-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="3262a-123">在下拉式清單中，選取 **不合併**。</span><span class="sxs-lookup"><span data-stu-id="3262a-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="3262a-124">屬性會移至 **已從客戶記錄中移除** 區段。</span><span class="sxs-lookup"><span data-stu-id="3262a-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="3262a-125">手動新增合併的屬性</span><span class="sxs-lookup"><span data-stu-id="3262a-125">Manually add a merged attribute</span></span>

<span data-ttu-id="3262a-126">若要新增合併的屬性，請移至 **合併** 頁面。</span><span class="sxs-lookup"><span data-stu-id="3262a-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="3262a-127">選取 **新增合併的屬性**。</span><span class="sxs-lookup"><span data-stu-id="3262a-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="3262a-128">提供 **名稱** 以供稍後在 **合併** 頁面上識別它。</span><span class="sxs-lookup"><span data-stu-id="3262a-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="3262a-129">或者，提供 **顯示名稱**，將顯示在統整客戶設定檔實體中。</span><span class="sxs-lookup"><span data-stu-id="3262a-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="3262a-130">設定 **選取重複的屬性**，以選取您要從相符的實體合併的屬性。</span><span class="sxs-lookup"><span data-stu-id="3262a-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="3262a-131">您也可以搜尋屬性。</span><span class="sxs-lookup"><span data-stu-id="3262a-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="3262a-132">設定 **依重要性排名**，以優先處理某個屬性。</span><span class="sxs-lookup"><span data-stu-id="3262a-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="3262a-133">例如，如果 *WebAccountCSV* 實體包含有關 *全名* 屬性的最準確資料，您可以選取 *WebAccountCSV*，將此實體的優先順序設定高於 *ContactCSV*。</span><span class="sxs-lookup"><span data-stu-id="3262a-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="3262a-134">因此，在提取 *全名* 屬性的值時，*WebAccountCSV* 會移至第一優先順序，而 *ContactCSV* 則移至第二優先順序。</span><span class="sxs-lookup"><span data-stu-id="3262a-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="3262a-135">執行合併</span><span class="sxs-lookup"><span data-stu-id="3262a-135">Run your merge</span></span>

<span data-ttu-id="3262a-136">不論您手動合併屬性或讓系統合併，您都可以執行合併。</span><span class="sxs-lookup"><span data-stu-id="3262a-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="3262a-137">在 **合併** 頁面上，選取 **執行** 來開始處理。</span><span class="sxs-lookup"><span data-stu-id="3262a-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3262a-138">![資料合併儲存與執行](media/configure-data-merge-save-run.png "資料合併儲存與執行")</span><span class="sxs-lookup"><span data-stu-id="3262a-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="3262a-139">若要進行其他變更並重新執行步驟，您可以取消進行中的合併。</span><span class="sxs-lookup"><span data-stu-id="3262a-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="3262a-140">選取 **重新整理中...**，然後在出現的側面窗格中選取 **取消工作**。</span><span class="sxs-lookup"><span data-stu-id="3262a-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="3262a-141">在 **重新整理中** 文字變更為 **成功** 後，已根據您定義的原則完成合併並解決資料中的衝突。</span><span class="sxs-lookup"><span data-stu-id="3262a-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="3262a-142">合併和未併入的屬性會包含在統整設定檔實體中。</span><span class="sxs-lookup"><span data-stu-id="3262a-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="3262a-143">排除的屬性不會包含在統整設定檔實體中。</span><span class="sxs-lookup"><span data-stu-id="3262a-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="3262a-144">如果這不是您第一次成功地進行合併，所有下游程序（包括擴充、區段化和量值）都會自動重新執行。</span><span class="sxs-lookup"><span data-stu-id="3262a-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="3262a-145">在所有下游程序重新執行之後，客戶設定檔會反映您所做的任何變更。</span><span class="sxs-lookup"><span data-stu-id="3262a-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="3262a-146">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="3262a-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3262a-147">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="3262a-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3262a-148">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3262a-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3262a-149">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="3262a-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="3262a-150">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3262a-150">Next Step</span></span>

<span data-ttu-id="3262a-151">設定[活動](activities.md)、[擴充](enrichment-microsoft-graph.md)或[關聯](relationships.md)，以進一步了解您的客戶。</span><span class="sxs-lookup"><span data-stu-id="3262a-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="3262a-152">如果您已設定活動、擴充或關聯，或者您已定義區段時，系統會自動加以處理來使用最新的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="3262a-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]