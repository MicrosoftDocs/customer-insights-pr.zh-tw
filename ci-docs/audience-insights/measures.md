---
title: 建立和編輯量值
description: 定義客戶相關的量值，以分析和反映特定業務領域的績效。
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405280"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="5c71c-103">定義和管理量值</span><span class="sxs-lookup"><span data-stu-id="5c71c-103">Define and manage measures</span></span>

<span data-ttu-id="5c71c-104">**量值** 代表反映特定業務領域之績效和健康情況的關鍵效能指標 (KPI)。</span><span class="sxs-lookup"><span data-stu-id="5c71c-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="5c71c-105">對象見解提供直覺式體驗方便組建不同類型的量值，使用不需要您手動編碼或驗證量值的查詢組建程式。</span><span class="sxs-lookup"><span data-stu-id="5c71c-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="5c71c-106">您可以在 **首頁** 追蹤您的業務量值、在 **客戶卡片** 上查看特定客戶的量值，以及使用量值來定義 **區段** 頁面上的客戶區段。</span><span class="sxs-lookup"><span data-stu-id="5c71c-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="5c71c-107">建立量值</span><span class="sxs-lookup"><span data-stu-id="5c71c-107">Create a measure</span></span>

<span data-ttu-id="5c71c-108">本節將引導您從頭開始建立量值。</span><span class="sxs-lookup"><span data-stu-id="5c71c-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="5c71c-109">您可以使用透過客戶實體連接的多個資料來源中的資料來建立量值。</span><span class="sxs-lookup"><span data-stu-id="5c71c-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="5c71c-110">適用若干 [服務限制](service-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="5c71c-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="5c71c-111">請在對象見解中前往 **量值**。</span><span class="sxs-lookup"><span data-stu-id="5c71c-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="5c71c-112">選取 **新增量值**。</span><span class="sxs-lookup"><span data-stu-id="5c71c-112">Select **New measure**.</span></span>

3. <span data-ttu-id="5c71c-113">選擇量值 **類型**：</span><span class="sxs-lookup"><span data-stu-id="5c71c-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="5c71c-114">**客戶屬性**：每個客戶的單一欄位，會反映客戶的分數、值或狀態。</span><span class="sxs-lookup"><span data-stu-id="5c71c-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="5c71c-115">客戶屬性會在新的系統產生實體中建立為屬性，稱為 **Customer_Measure**。</span><span class="sxs-lookup"><span data-stu-id="5c71c-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="5c71c-116">**客戶量值**：根據選取的維度而解析的客戶行為見解。</span><span class="sxs-lookup"><span data-stu-id="5c71c-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="5c71c-117">會為每個量值產生新的實體，這可能會針對每個客戶有多個記錄。</span><span class="sxs-lookup"><span data-stu-id="5c71c-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="5c71c-118">**業務量值**：追蹤業務績效和業務的健康情況。</span><span class="sxs-lookup"><span data-stu-id="5c71c-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="5c71c-119">業務量值可以有兩種不同的輸出：顯示在 **首頁** 的數字輸出，或是您在 **實體** 頁面上找到的新實體。</span><span class="sxs-lookup"><span data-stu-id="5c71c-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="5c71c-120">提供 **名稱** 及選擇性 **顯示名稱**，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="5c71c-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="5c71c-121">在 **實體** 區段中，從下拉式清單選取第一個實體。</span><span class="sxs-lookup"><span data-stu-id="5c71c-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="5c71c-122">此時，您應該決定量值定義是否需要其他實體。</span><span class="sxs-lookup"><span data-stu-id="5c71c-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c71c-123">![量值定義](media/measure-definition.png "量值定義")</span><span class="sxs-lookup"><span data-stu-id="5c71c-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="5c71c-124">若要新增更多的實體，請選取 **新增實體**，並選取要用於量值的實體。</span><span class="sxs-lookup"><span data-stu-id="5c71c-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5c71c-125">您只能選取與您的開始實體有關聯的實體。</span><span class="sxs-lookup"><span data-stu-id="5c71c-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="5c71c-126">如需有關定義關聯的詳細資訊，請參閱[關聯](relationships.md)。</span><span class="sxs-lookup"><span data-stu-id="5c71c-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="5c71c-127">您也可以選擇設定變數。</span><span class="sxs-lookup"><span data-stu-id="5c71c-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="5c71c-128">在 **變數** 區段中，選取 **新增變數**。</span><span class="sxs-lookup"><span data-stu-id="5c71c-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="5c71c-129">變數是在每個所選記錄上進行的計算。</span><span class="sxs-lookup"><span data-stu-id="5c71c-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="5c71c-130">例如，加總銷售點 (POS) 和每個客戶記錄的線上銷售。</span><span class="sxs-lookup"><span data-stu-id="5c71c-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="5c71c-131">提供變數的 **名稱**。</span><span class="sxs-lookup"><span data-stu-id="5c71c-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="5c71c-132">在 **運算式** 區域中，選取要用來開始計算的欄位。</span><span class="sxs-lookup"><span data-stu-id="5c71c-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="5c71c-133">在選擇要納入計算中的其他欄位時，請在 **運算式** 區域中輸入運算式。</span><span class="sxs-lookup"><span data-stu-id="5c71c-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5c71c-134">目前只支援算術運算式。</span><span class="sxs-lookup"><span data-stu-id="5c71c-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="5c71c-135">此外，不同[實體路徑](relationships.md)中的實體不支援變數計算。</span><span class="sxs-lookup"><span data-stu-id="5c71c-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="5c71c-136">選取 **完成**。</span><span class="sxs-lookup"><span data-stu-id="5c71c-136">Select **Done**.</span></span>

11. <span data-ttu-id="5c71c-137">在 **量值定義** 區段中，您將定義如何在新的量值實體或屬性中彙總選取的實體與計算變數。</span><span class="sxs-lookup"><span data-stu-id="5c71c-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="5c71c-138">選取 **新增維度**。</span><span class="sxs-lookup"><span data-stu-id="5c71c-138">Select **New dimension**.</span></span> <span data-ttu-id="5c71c-139">您可以將維度視為 *群組依據* 函數。</span><span class="sxs-lookup"><span data-stu-id="5c71c-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="5c71c-140">您的量值實體或屬性的資料輸出將會根據您定義的所有維度進行分組。</span><span class="sxs-lookup"><span data-stu-id="5c71c-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5c71c-141">![選擇彙總週期](media/measures-businessreport-measure-definition2.png "選擇彙總週期")</span><span class="sxs-lookup"><span data-stu-id="5c71c-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="5c71c-142">選取或輸入下列資訊做為維度定義的一部分：</span><span class="sxs-lookup"><span data-stu-id="5c71c-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="5c71c-143">**實體**：如果您定義一個量值實體，則它至少應包括一個屬性。</span><span class="sxs-lookup"><span data-stu-id="5c71c-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="5c71c-144">如果您定義一個量值屬性，預設只會包含一個屬性。</span><span class="sxs-lookup"><span data-stu-id="5c71c-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="5c71c-145">這項選擇是關於如何選擇包含該屬性的實體。</span><span class="sxs-lookup"><span data-stu-id="5c71c-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="5c71c-146">**欄位**：選擇要在您的量值實體或屬性中包含的特定屬性。</span><span class="sxs-lookup"><span data-stu-id="5c71c-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="5c71c-147">**貯體**：選擇是要依據每天、每月或每年來匯總資料。</span><span class="sxs-lookup"><span data-stu-id="5c71c-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="5c71c-148">只有在您已選取日期類型屬性時，它才是必要的選取。</span><span class="sxs-lookup"><span data-stu-id="5c71c-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="5c71c-149">**做為**：定義新欄位的名稱。</span><span class="sxs-lookup"><span data-stu-id="5c71c-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="5c71c-150">**顯示名稱**：定義欄位的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="5c71c-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5c71c-151">您的業務量值會儲存為單數實體，並顯示在 **首頁** 上，除非您將更多維度新增至您的量值。</span><span class="sxs-lookup"><span data-stu-id="5c71c-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="5c71c-152">在新增更多維度之後，此量值就 *不會* 顯示在 **首頁** 上。</span><span class="sxs-lookup"><span data-stu-id="5c71c-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="5c71c-153">或者，新增彙總函數。</span><span class="sxs-lookup"><span data-stu-id="5c71c-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="5c71c-154">您建立的任何彙總都會在量值實體或屬性中產生新的值。</span><span class="sxs-lookup"><span data-stu-id="5c71c-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="5c71c-155">支援的彙總函數包括：**最小值**、**最大值**、**平均**、**中位數**、**總和**、**計數唯一**、**第一個**（取得維度值的第一個記錄）和 **最後一個**（取得新增到維度值的最後一個記錄）。</span><span class="sxs-lookup"><span data-stu-id="5c71c-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="5c71c-156">選取 **儲存** 以套用對量值的變更。</span><span class="sxs-lookup"><span data-stu-id="5c71c-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="5c71c-157">管理您的量值</span><span class="sxs-lookup"><span data-stu-id="5c71c-157">Manage your measures</span></span>

<span data-ttu-id="5c71c-158">建立至少一個量值後，您將在 **量值** 頁面上看到量值清單。</span><span class="sxs-lookup"><span data-stu-id="5c71c-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="5c71c-159">您將會找到有關量值類別、建立者、建立日期和時間、上次編輯日期和時間、狀態（該量值為使用中、非使用中或失敗）以及上次重新整理日期和時間的資訊。</span><span class="sxs-lookup"><span data-stu-id="5c71c-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="5c71c-160">當您從清單中選取量值時，您可以查看其輸出的預覽。</span><span class="sxs-lookup"><span data-stu-id="5c71c-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="5c71c-161">若要同時重新整理所有的量值，請選取 **全部重新整理**，而不選取特定的量值。</span><span class="sxs-lookup"><span data-stu-id="5c71c-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5c71c-162">![管理單一量值的動作](media/measure-actions.png "管理單一量值的動作")</span><span class="sxs-lookup"><span data-stu-id="5c71c-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="5c71c-163">或者，從清單中選取一個量值，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="5c71c-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="5c71c-164">選取量值名稱以查看其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5c71c-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="5c71c-165">**編輯** 量值的設定。</span><span class="sxs-lookup"><span data-stu-id="5c71c-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="5c71c-166">**重新命名** 量值。</span><span class="sxs-lookup"><span data-stu-id="5c71c-166">**Rename** the measure.</span></span>
- <span data-ttu-id="5c71c-167">**刪除** 量值。</span><span class="sxs-lookup"><span data-stu-id="5c71c-167">**Delete** the measure.</span></span>
- <span data-ttu-id="5c71c-168">選取省略符號 (...)，然後 **重新整理**，以開始量值的重新整理程序。</span><span class="sxs-lookup"><span data-stu-id="5c71c-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="5c71c-169">選取省略符號 (...)，然後 **下載** 以取得量值的 .CSV 檔。</span><span class="sxs-lookup"><span data-stu-id="5c71c-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="5c71c-170">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="5c71c-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="5c71c-171">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="5c71c-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="5c71c-172">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5c71c-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="5c71c-173">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="5c71c-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="5c71c-174">下一個步驟</span><span class="sxs-lookup"><span data-stu-id="5c71c-174">Next step</span></span>

<span data-ttu-id="5c71c-175">您可使用現有的量值，在 **區段** 頁面上建立您的第一個客戶區段。</span><span class="sxs-lookup"><span data-stu-id="5c71c-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="5c71c-176">如需詳細資訊，請參閱[區段](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="5c71c-176">For more information, see [Segments](segments.md).</span></span>
