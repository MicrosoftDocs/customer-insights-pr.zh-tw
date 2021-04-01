---
title: 建立和管理區段
description: 建立客戶的區段，以依據各種屬性來群組。
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597041"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="26526-103">建立和管理區段</span><span class="sxs-lookup"><span data-stu-id="26526-103">Create and manage segments</span></span>

<span data-ttu-id="26526-104">區段讓您根據人口統計、交易性或行為屬性分組您的客戶。</span><span class="sxs-lookup"><span data-stu-id="26526-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="26526-105">為了達成業務目標，您可以使用區段來設定目標促銷活動、銷售活動和客戶支援動作。</span><span class="sxs-lookup"><span data-stu-id="26526-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="26526-106">您可以在客戶設定檔實體及其相關實體周圍定義複雜的篩選。</span><span class="sxs-lookup"><span data-stu-id="26526-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="26526-107">每個區段會在處理後建立一組可匯出和採取相應動作的客戶記錄。</span><span class="sxs-lookup"><span data-stu-id="26526-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="26526-108">適用若干 [服務限制](service-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="26526-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="26526-109">除非另行說明，否則所有區段均屬 **動態區段**，按照反覆排程重新整理。</span><span class="sxs-lookup"><span data-stu-id="26526-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="26526-110">下列範例說明區隔能力。</span><span class="sxs-lookup"><span data-stu-id="26526-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="26526-111">我們為在過去 90 天中至少訂購了 $500 貨物的客戶，*以及* 參與了已上呈之客戶服務通話的客戶，定義了區段。</span><span class="sxs-lookup"><span data-stu-id="26526-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="26526-112">![多個群組](media/segmentation-group1-2.png "多個群組")</span><span class="sxs-lookup"><span data-stu-id="26526-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="26526-113">建立新區段</span><span class="sxs-lookup"><span data-stu-id="26526-113">Create a new segment</span></span>

<span data-ttu-id="26526-114">區段會在 **區段** 頁面上加以管理。</span><span class="sxs-lookup"><span data-stu-id="26526-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="26526-115">請在對象見解中前往 **區段** 頁面。</span><span class="sxs-lookup"><span data-stu-id="26526-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="26526-116">選取 **新增** > **空白區段**。</span><span class="sxs-lookup"><span data-stu-id="26526-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="26526-117">在 **新增區段** 窗格中，選擇一種區段類型並提供 **名稱**。</span><span class="sxs-lookup"><span data-stu-id="26526-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="26526-118">您也可以提供顯示名稱以及有助於識別區段的描述。</span><span class="sxs-lookup"><span data-stu-id="26526-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="26526-119">選取 **下一步** 以進入 **區段建立器** 頁面，您可以在其中定義群組。</span><span class="sxs-lookup"><span data-stu-id="26526-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="26526-120">群組是一組客戶。</span><span class="sxs-lookup"><span data-stu-id="26526-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="26526-121">選擇包含您要據以建立區段之屬性的實體。</span><span class="sxs-lookup"><span data-stu-id="26526-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="26526-122">選擇要據以建立區段的屬性。</span><span class="sxs-lookup"><span data-stu-id="26526-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="26526-123">此屬性可以有四個數值類型之一：數值、字串、日期或布林值。</span><span class="sxs-lookup"><span data-stu-id="26526-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="26526-124">為選取的屬性選擇運算子與值。</span><span class="sxs-lookup"><span data-stu-id="26526-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26526-125">![自訂群組篩選](media/customer-group-numbers.png "客戶群組篩選")</span><span class="sxs-lookup"><span data-stu-id="26526-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="26526-126">號碼</span><span class="sxs-lookup"><span data-stu-id="26526-126">Number</span></span> |<span data-ttu-id="26526-127">定義</span><span class="sxs-lookup"><span data-stu-id="26526-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="26526-128">1</span><span class="sxs-lookup"><span data-stu-id="26526-128">1</span></span>     |<span data-ttu-id="26526-129">Entity</span><span class="sxs-lookup"><span data-stu-id="26526-129">Entity</span></span>          |
   |<span data-ttu-id="26526-130">2</span><span class="sxs-lookup"><span data-stu-id="26526-130">2</span></span>     |<span data-ttu-id="26526-131">屬性</span><span class="sxs-lookup"><span data-stu-id="26526-131">Attribute</span></span>          |
   |<span data-ttu-id="26526-132">3</span><span class="sxs-lookup"><span data-stu-id="26526-132">3</span></span>    |<span data-ttu-id="26526-133">運算子</span><span class="sxs-lookup"><span data-stu-id="26526-133">Operator</span></span>         |
   |<span data-ttu-id="26526-134">4</span><span class="sxs-lookup"><span data-stu-id="26526-134">4</span></span>    |<span data-ttu-id="26526-135">值</span><span class="sxs-lookup"><span data-stu-id="26526-135">Value</span></span>         |

8. <span data-ttu-id="26526-136">如果實體是透過[關聯](relationships.md)連接至統整的客戶實體，則需要定義關聯路徑來建立有效的區段。</span><span class="sxs-lookup"><span data-stu-id="26526-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="26526-137">從關聯路徑新增實體，直到您可以從下拉清單中選取 **客戶：CustomerInsights** 實體。</span><span class="sxs-lookup"><span data-stu-id="26526-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="26526-138">然後，為每個條件選取 **所有記錄**。</span><span class="sxs-lookup"><span data-stu-id="26526-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26526-139">![建立區段期間的關聯路徑](media/segments-multiple-relationships.png "建立段落期間的關聯路徑")</span><span class="sxs-lookup"><span data-stu-id="26526-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="26526-140">根據預設，客戶細分會生成一個輸出實體，其中包含所有符合已定義篩選準則的客戶個人資料屬性。</span><span class="sxs-lookup"><span data-stu-id="26526-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="26526-141">如果客戶細分依據其他實體而非 *客戶* 實體，您可以將這些實體中的多個屬性新增至輸出實體。</span><span class="sxs-lookup"><span data-stu-id="26526-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="26526-142">選取 **專案屬性**，以選擇附加至輸出實體的屬性。</span><span class="sxs-lookup"><span data-stu-id="26526-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="26526-143">範例：有一份客戶細分是根據包含與 *客戶* 實體相關的客戶活動資料實體建立的。</span><span class="sxs-lookup"><span data-stu-id="26526-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="26526-144">此客戶細分會尋找過去 60 天中電話連絡技術服務人員的所有客戶。</span><span class="sxs-lookup"><span data-stu-id="26526-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="26526-145">您可以選擇將通話長度和通話次數附加至輸出實體中所有相符的客戶記錄。</span><span class="sxs-lookup"><span data-stu-id="26526-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="26526-146">若傳送電子郵件並附上線上說明文章連結和常見問題集給經常電話連絡的客戶，此資訊可能會非常實用。</span><span class="sxs-lookup"><span data-stu-id="26526-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="26526-147">選取 **儲存** 以儲存區段。</span><span class="sxs-lookup"><span data-stu-id="26526-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="26526-148">如果所有需求均已驗證，就會儲存和處理您的區段。</span><span class="sxs-lookup"><span data-stu-id="26526-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="26526-149">否則，它會儲存為草稿。</span><span class="sxs-lookup"><span data-stu-id="26526-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="26526-150">選取 **返回區段** 以返回 **區段** 頁面。</span><span class="sxs-lookup"><span data-stu-id="26526-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="26526-151">管理現有的區段</span><span class="sxs-lookup"><span data-stu-id="26526-151">Manage existing segments</span></span>

<span data-ttu-id="26526-152">在 **區段** 頁面上，您可以查看所有已儲存的區段並加以管理。</span><span class="sxs-lookup"><span data-stu-id="26526-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="26526-153">每個區段都是由一個包含區段其他相關資訊的列所表示。</span><span class="sxs-lookup"><span data-stu-id="26526-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="26526-154">您可以選取欄標題來排序欄中的區段。</span><span class="sxs-lookup"><span data-stu-id="26526-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="26526-155">使用右上角的 **搜尋** 方塊來篩選區段。</span><span class="sxs-lookup"><span data-stu-id="26526-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="26526-156">![管理現有區段的選項](media/segments-selected-segment.png "管理現有區段的選項")</span><span class="sxs-lookup"><span data-stu-id="26526-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="26526-157">選取客戶細分時，可使用下列動作：</span><span class="sxs-lookup"><span data-stu-id="26526-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="26526-158">**檢視** 區段詳細資料，包括成員計數趨勢和區段成員的預覽。</span><span class="sxs-lookup"><span data-stu-id="26526-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="26526-159">**編輯** 區段以變更其屬性。</span><span class="sxs-lookup"><span data-stu-id="26526-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="26526-160">為客戶細分 **建立複本**。</span><span class="sxs-lookup"><span data-stu-id="26526-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="26526-161">您可以選擇立刻編輯屬性，或只是儲存複本。</span><span class="sxs-lookup"><span data-stu-id="26526-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="26526-162">**重新整理** 區段以包括最新的資料。</span><span class="sxs-lookup"><span data-stu-id="26526-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="26526-163">**啟用** 或 **停用** 區段。</span><span class="sxs-lookup"><span data-stu-id="26526-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="26526-164">客戶細分有兩種可能狀態：使用中或非使用中。</span><span class="sxs-lookup"><span data-stu-id="26526-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="26526-165">編輯客戶細分時，將會用到這些狀態。</span><span class="sxs-lookup"><span data-stu-id="26526-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="26526-166">如果是非使用中客戶細分，雖有客戶細分定義存在，但尚未包含任何客戶。</span><span class="sxs-lookup"><span data-stu-id="26526-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="26526-167">啟用客戶細分時，其狀態會從 [非使用中] 變更為 [使用中]，並且開始尋找符合區段定義的客戶。</span><span class="sxs-lookup"><span data-stu-id="26526-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="26526-168">如果設定了 [已排定重新整理](system.md#schedule-tab)，則非使用中客戶細分會將 **狀態** 列示為 **已跳過**，表示甚至未嘗試重新整理。</span><span class="sxs-lookup"><span data-stu-id="26526-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="26526-169">啟用非使用中客戶細分時，此客戶細分會重新整理，並納入已排定重新整理。</span><span class="sxs-lookup"><span data-stu-id="26526-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="26526-170">或者，也可以使用 **啟用/停用** 下拉式功能表中的 **稍後再排程** 功能，指定未來啟用和停用特定客戶細分的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="26526-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="26526-171">**重新命名** 區段。</span><span class="sxs-lookup"><span data-stu-id="26526-171">**Rename** the segment.</span></span>
- <span data-ttu-id="26526-172">將成員清單 **下載** 為 .CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="26526-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="26526-173">**新增至** 選項會傳送客戶細分中的客戶識別碼清單以供在另一個應用程式中處理。</span><span class="sxs-lookup"><span data-stu-id="26526-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="26526-174">**刪除** 區段。</span><span class="sxs-lookup"><span data-stu-id="26526-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="26526-175">重新整理區段</span><span class="sxs-lookup"><span data-stu-id="26526-175">Refresh segments</span></span>

<span data-ttu-id="26526-176">您可以選取 **區段** 頁面上的 **全部重新整理**，一次重新整理所有區段，也可以在選取一個或多個區段，並從選項中選擇 **重新整理** 時重新整理這些區段。</span><span class="sxs-lookup"><span data-stu-id="26526-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="26526-177">或者，您也可以在 **管理員** > **系統** > **排程** 設定定期重新整理。</span><span class="sxs-lookup"><span data-stu-id="26526-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="26526-178">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="26526-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="26526-179">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="26526-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="26526-180">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="26526-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="26526-181">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="26526-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="26526-182">下載和匯出區段</span><span class="sxs-lookup"><span data-stu-id="26526-182">Download and export segments</span></span>

<span data-ttu-id="26526-183">您可以將區段下載至 CSV 檔，或將它們匯出至 Dynamics 365 Sales。</span><span class="sxs-lookup"><span data-stu-id="26526-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="26526-184">將區段下載至 CSV 檔</span><span class="sxs-lookup"><span data-stu-id="26526-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="26526-185">請在對象見解中前往 **區段** 頁面。</span><span class="sxs-lookup"><span data-stu-id="26526-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="26526-186">選取特定區段圖格中的省略符號。</span><span class="sxs-lookup"><span data-stu-id="26526-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="26526-187">從 [動作] 下拉式清單中，選取 **下載為 CSV**。</span><span class="sxs-lookup"><span data-stu-id="26526-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="26526-188">將區段匯出至 Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="26526-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="26526-189">在將區段匯出至 Dynamics 365 Sales 之前，系統管理員必須為 Dynamics 365 Sales [建立匯出目的地](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="26526-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="26526-190">請在對象見解中前往 **區段** 頁面。</span><span class="sxs-lookup"><span data-stu-id="26526-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="26526-191">選取特定區段圖格中的省略符號。</span><span class="sxs-lookup"><span data-stu-id="26526-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="26526-192">從動作下拉式清單中選取 **新增至**，然後選取要將資料傳送至的匯出目的地。</span><span class="sxs-lookup"><span data-stu-id="26526-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="26526-193">區段的草稿模式</span><span class="sxs-lookup"><span data-stu-id="26526-193">Draft mode for segments</span></span>

<span data-ttu-id="26526-194">如果不符合處理區段的所有需求，您可以將區段儲存為草稿，並從 **區段** 頁面存取它。</span><span class="sxs-lookup"><span data-stu-id="26526-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="26526-195">它會儲存為非使用中區段，在生效之前無法啟用它。</span><span class="sxs-lookup"><span data-stu-id="26526-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="26526-196">新增更多條件至群組</span><span class="sxs-lookup"><span data-stu-id="26526-196">Add more conditions to a group</span></span>

<span data-ttu-id="26526-197">若要將更多條件新增至群組，您可以使用兩個邏輯運算子：</span><span class="sxs-lookup"><span data-stu-id="26526-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="26526-198">**AND** 運算子：在區段程序中兩個條件都必須符合。</span><span class="sxs-lookup"><span data-stu-id="26526-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="26526-199">當您跨不同實體定義條件時，此選項非常有用。</span><span class="sxs-lookup"><span data-stu-id="26526-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="26526-200">**OR** 運算子：在區段程序中，需要符合其中一項條件。</span><span class="sxs-lookup"><span data-stu-id="26526-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="26526-201">當您為相同實體定義多個條件時，此選項非常有用。</span><span class="sxs-lookup"><span data-stu-id="26526-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26526-202">![需要符合任一條件的 OR 運算子](media/segmentation-either-condition.png "需要符合任一條件的 OR 運算子")</span><span class="sxs-lookup"><span data-stu-id="26526-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="26526-203">目前可以將 **OR** 運算子內嵌在 **AND** 運算子之下，但相反過來不行。</span><span class="sxs-lookup"><span data-stu-id="26526-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="26526-204">結合多個群組</span><span class="sxs-lookup"><span data-stu-id="26526-204">Combine multiple groups</span></span>

<span data-ttu-id="26526-205">每個群組都會產生一組特定的客戶。</span><span class="sxs-lookup"><span data-stu-id="26526-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="26526-206">您可以將這些群組結合在一起，包括您的業務案例所需的客戶。</span><span class="sxs-lookup"><span data-stu-id="26526-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="26526-207">請在對象見解中前往 **區段** 頁面並選取某區段。</span><span class="sxs-lookup"><span data-stu-id="26526-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="26526-208">選取 **新增群組**。</span><span class="sxs-lookup"><span data-stu-id="26526-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26526-209">![客戶群組新增群組](media/customer-group-add-group.png "客戶群組新增群組")</span><span class="sxs-lookup"><span data-stu-id="26526-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="26526-210">選取下列其中一組運算子：**聯集**、**交集** 或 **除外**。</span><span class="sxs-lookup"><span data-stu-id="26526-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26526-211">![客戶群組新增聯集](media/customer-group-union.png "客戶群組新增聯集")</span><span class="sxs-lookup"><span data-stu-id="26526-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="26526-212">選取集合運算子以定義新群組。</span><span class="sxs-lookup"><span data-stu-id="26526-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="26526-213">儲存不同群組可判定保留哪些資料：</span><span class="sxs-lookup"><span data-stu-id="26526-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="26526-214">**聯集** 會聯合兩個群組。</span><span class="sxs-lookup"><span data-stu-id="26526-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="26526-215">**交集** 會重疊兩個群組。</span><span class="sxs-lookup"><span data-stu-id="26526-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="26526-216">唯有兩個群組 *共有* 的資料才會在統整群組中保留。</span><span class="sxs-lookup"><span data-stu-id="26526-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="26526-217">**差集** 會結合兩個群組。</span><span class="sxs-lookup"><span data-stu-id="26526-217">**Except** combines the two groups.</span></span> <span data-ttu-id="26526-218">唯有 *不與 B 組資料共有* 的 A 組資料才會保留。</span><span class="sxs-lookup"><span data-stu-id="26526-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="26526-219">查看處理歷史記錄和區段成員</span><span class="sxs-lookup"><span data-stu-id="26526-219">View processing history and segment members</span></span>

<span data-ttu-id="26526-220">您可以透過查看資料的詳細資料，查看關於該區段的合併資料。</span><span class="sxs-lookup"><span data-stu-id="26526-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="26526-221">在 **區段** 頁面上選取您想檢閱的區段。</span><span class="sxs-lookup"><span data-stu-id="26526-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="26526-222">此頁面的上半部分包括趨勢圖形，其中會視覺化呈現成員計數的變化。</span><span class="sxs-lookup"><span data-stu-id="26526-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="26526-223">將游標移到資料點上方可查看特定日期的成員計數。</span><span class="sxs-lookup"><span data-stu-id="26526-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="26526-224">您可以更新視覺效果的時間範圍。</span><span class="sxs-lookup"><span data-stu-id="26526-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="26526-225">![區段時間範圍](media/segment-time-range.png "區段時間範圍")</span><span class="sxs-lookup"><span data-stu-id="26526-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="26526-226">下半部分包含區段成員的清單。</span><span class="sxs-lookup"><span data-stu-id="26526-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="26526-227">此清單中顯示的欄位是根據區段實體的屬性。</span><span class="sxs-lookup"><span data-stu-id="26526-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="26526-228">此清單是相符區段成員的預覽，並顯示區段的前 100 個記錄，這樣您就可以快速評估並查看其定義（如有需要）。</span><span class="sxs-lookup"><span data-stu-id="26526-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="26526-229">若要查看所有相符的記錄，您需要[匯出區段](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="26526-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="26526-230">快速區段</span><span class="sxs-lookup"><span data-stu-id="26526-230">Quick segments</span></span>

<span data-ttu-id="26526-231">除了區段建立器以外，也有另一個建立區段的路徑。</span><span class="sxs-lookup"><span data-stu-id="26526-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="26526-232">快速客戶細分可讓您使用單一運算子快速建立簡單的客戶細分，並提供即時見解。</span><span class="sxs-lookup"><span data-stu-id="26526-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="26526-233">在 **區段** 頁面上，選取 **新增** > **快速建立來源**。</span><span class="sxs-lookup"><span data-stu-id="26526-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="26526-234">選取 **設定檔** 選項，建立基於統整客戶實體的區段。</span><span class="sxs-lookup"><span data-stu-id="26526-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="26526-235">選取 **量值** 選項，以根據您先前在 **量值** 頁面上建立的每個客戶屬性類型建立區段。</span><span class="sxs-lookup"><span data-stu-id="26526-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="26526-236">選取 **智慧** 選項，以使用 **預測** 或 **自訂模型** 功能產生的其中一個輸出實體建立區段。</span><span class="sxs-lookup"><span data-stu-id="26526-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="26526-237">在 **新增快速區段** 對話方塊中，從 **欄位** 下拉式功能表中選取屬性。</span><span class="sxs-lookup"><span data-stu-id="26526-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="26526-238">系統將提供一些其他見解，可協助您建立更佳的客戶區段。</span><span class="sxs-lookup"><span data-stu-id="26526-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="26526-239">對於類別欄位，我們會顯示 10 個最高的客戶計數。</span><span class="sxs-lookup"><span data-stu-id="26526-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="26526-240">選擇 **值** 並選取 **檢閱**。</span><span class="sxs-lookup"><span data-stu-id="26526-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="26526-241">在數值屬性中，系統會顯示落在每個客戶百分位下的屬性值。</span><span class="sxs-lookup"><span data-stu-id="26526-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="26526-242">選擇 **運算子** 和 **值**，然後選取 **檢閱**。</span><span class="sxs-lookup"><span data-stu-id="26526-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="26526-243">系統將為您提供 **估計的區段大小**。</span><span class="sxs-lookup"><span data-stu-id="26526-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="26526-244">您可以選擇是否要產生您定義的區段，或先重新檢視它以取得不同的區段大小。</span><span class="sxs-lookup"><span data-stu-id="26526-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="26526-245">![快速區段的名稱與估計](media/quick-segment-name.png "快速區段的名稱與估計")</span><span class="sxs-lookup"><span data-stu-id="26526-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="26526-246">提供區段的 **名稱**。</span><span class="sxs-lookup"><span data-stu-id="26526-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="26526-247">或者，提供 **顯示名稱**。</span><span class="sxs-lookup"><span data-stu-id="26526-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="26526-248">選取 **儲存** 以建立您的區段。</span><span class="sxs-lookup"><span data-stu-id="26526-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="26526-249">區段完成處理之後，您可以像您所建立的其他段落一樣來查看它。</span><span class="sxs-lookup"><span data-stu-id="26526-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="26526-250">在下列案例中，我們建議使用區段建立器而不是建議的區段功能：</span><span class="sxs-lookup"><span data-stu-id="26526-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="26526-251">建立篩選出類別欄位的區段（其中運算子不同於 **是** 運算子）</span><span class="sxs-lookup"><span data-stu-id="26526-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="26526-252">建立含有數值欄位篩選的區段，其中運算子不同於 **介於之間**、**大於** 和 **小於** 運算子</span><span class="sxs-lookup"><span data-stu-id="26526-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="26526-253">建立帶有日期類型欄位篩選的區段</span><span class="sxs-lookup"><span data-stu-id="26526-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="26526-254">後續步驟</span><span class="sxs-lookup"><span data-stu-id="26526-254">Next steps</span></span>

<span data-ttu-id="26526-255">[匯出區段](export-destinations.md)並探索[客戶卡片](customer-card-add-in.md)和[連接器](export-power-bi.md)，以取得客戶等級的見解。</span><span class="sxs-lookup"><span data-stu-id="26526-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]