---
title: 對象見解中的客戶細分
description: 客戶細分概觀及如何建立並管理它們。
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306247"
---
# <a name="segments-overview"></a><span data-ttu-id="f46da-103">客戶細分概觀</span><span class="sxs-lookup"><span data-stu-id="f46da-103">Segments overview</span></span>

<span data-ttu-id="f46da-104">區段讓您根據人口統計、交易性或行為屬性分組您的客戶。</span><span class="sxs-lookup"><span data-stu-id="f46da-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="f46da-105">為了達成業務目標，您可以使用區段來設定目標促銷活動、銷售活動和客戶支援動作。</span><span class="sxs-lookup"><span data-stu-id="f46da-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="f46da-106">符合客戶細分定義篩選的客戶個人資料稱為客戶細分的 *成員*。</span><span class="sxs-lookup"><span data-stu-id="f46da-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="f46da-107">適用若干 [服務限制](service-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="f46da-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="f46da-108">建立新區段</span><span class="sxs-lookup"><span data-stu-id="f46da-108">Create a new segment</span></span>

<span data-ttu-id="f46da-109">有很多方式可以建立新的客戶細分：</span><span class="sxs-lookup"><span data-stu-id="f46da-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="f46da-110">具備客戶細分產生器的複雜客戶細分：[空白客戶細分](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="f46da-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="f46da-111">具有一個運算子的簡單客戶細分：[快速客戶細分](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="f46da-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="f46da-112">以 AI 支援的方式尋找類似客戶：[類似客戶](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="f46da-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="f46da-113">基於量值或屬性，由 AI支援的建議：[改善量值的建議客戶細分](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="f46da-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="f46da-114">根據活動提出的建議：[根據客戶活動所建議的客戶細分](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="f46da-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="f46da-115">管理現有的區段</span><span class="sxs-lookup"><span data-stu-id="f46da-115">Manage existing segments</span></span>

<span data-ttu-id="f46da-116">移至 **客戶細分** 頁面，以查看所有已儲存的客戶細分並加以管理。</span><span class="sxs-lookup"><span data-stu-id="f46da-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="f46da-117">每個區段都是由一個包含區段其他相關資訊的列所表示。</span><span class="sxs-lookup"><span data-stu-id="f46da-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="選定的客戶細分，有選項下拉式清單和可用選項。":::

<span data-ttu-id="f46da-119">選取客戶細分時，可使用下列動作：</span><span class="sxs-lookup"><span data-stu-id="f46da-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="f46da-120">**檢視** 區段詳細資料，包括成員計數趨勢和區段成員的預覽。</span><span class="sxs-lookup"><span data-stu-id="f46da-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="f46da-121">**編輯** 區段以變更其屬性。</span><span class="sxs-lookup"><span data-stu-id="f46da-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="f46da-122">為客戶細分 **建立複本**。</span><span class="sxs-lookup"><span data-stu-id="f46da-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="f46da-123">您可以選擇立刻編輯屬性，或只是儲存複本。</span><span class="sxs-lookup"><span data-stu-id="f46da-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="f46da-124">**重新整理** 區段以包括最新的資料。</span><span class="sxs-lookup"><span data-stu-id="f46da-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="f46da-125">**啟用** 或 **停用** 區段。</span><span class="sxs-lookup"><span data-stu-id="f46da-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="f46da-126">客戶細分有兩種可能狀態：使用中或非使用中。</span><span class="sxs-lookup"><span data-stu-id="f46da-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="f46da-127">編輯客戶細分時，將會用到這些狀態。</span><span class="sxs-lookup"><span data-stu-id="f46da-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="f46da-128">如果是非使用中客戶細分，雖有客戶細分定義存在，但尚未包含任何客戶。</span><span class="sxs-lookup"><span data-stu-id="f46da-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="f46da-129">啟用客戶細分時，其狀態會從 [非使用中] 變更為 [使用中]，並且開始尋找符合區段定義的客戶。</span><span class="sxs-lookup"><span data-stu-id="f46da-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="f46da-130">如果設定了 [已排定重新整理](system.md#schedule-tab)，則非使用中客戶細分會將 **狀態** 列示為 **已跳過**，表示甚至未嘗試重新整理。</span><span class="sxs-lookup"><span data-stu-id="f46da-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="f46da-131">啟用非使用中客戶細分時，此客戶細分會重新整理，並納入已排定重新整理。</span><span class="sxs-lookup"><span data-stu-id="f46da-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="f46da-132">或者，也可以使用 **啟用/停用** 下拉式功能表中的 **稍後再排程** 功能，指定未來啟用和停用特定客戶細分的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="f46da-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="f46da-133">**重新命名** 區段。</span><span class="sxs-lookup"><span data-stu-id="f46da-133">**Rename** the segment.</span></span>
- <span data-ttu-id="f46da-134">將成員清單 **下載** 為 .CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="f46da-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="f46da-135">**管理匯出**，以查看匯出相關的客戶細分並加以管理。</span><span class="sxs-lookup"><span data-stu-id="f46da-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="f46da-136">深入了解匯出。</span><span class="sxs-lookup"><span data-stu-id="f46da-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="f46da-137">**刪除** 區段。</span><span class="sxs-lookup"><span data-stu-id="f46da-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="f46da-138">重新整理區段</span><span class="sxs-lookup"><span data-stu-id="f46da-138">Refresh segments</span></span>

<span data-ttu-id="f46da-139">您可以選取 **區段** 頁面上的 **全部重新整理**，一次重新整理所有區段，也可以在選取一個或多個區段，並從選項中選擇 **重新整理** 時重新整理這些區段。</span><span class="sxs-lookup"><span data-stu-id="f46da-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="f46da-140">或者，您也可以在 **管理員** > **系統** > **排程** 設定定期重新整理。</span><span class="sxs-lookup"><span data-stu-id="f46da-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="f46da-141">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="f46da-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f46da-142">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="f46da-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f46da-143">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f46da-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f46da-144">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="f46da-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="f46da-145">匯出區段</span><span class="sxs-lookup"><span data-stu-id="f46da-145">Export segments</span></span>

<span data-ttu-id="f46da-146">您可以從客戶細分頁面或[匯出頁面](export-destinations.md)匯出客戶細分。</span><span class="sxs-lookup"><span data-stu-id="f46da-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="f46da-147">移至 **區段** 頁。</span><span class="sxs-lookup"><span data-stu-id="f46da-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="f46da-148">在您要匯出的客戶細分上，選取 **顯示更多 [...]**。</span><span class="sxs-lookup"><span data-stu-id="f46da-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="f46da-149">從動作下拉式清單中選擇 **管理匯出**。</span><span class="sxs-lookup"><span data-stu-id="f46da-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="f46da-150">會打開 **匯出客戶細分 (預覽版)** 頁面。</span><span class="sxs-lookup"><span data-stu-id="f46da-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="f46da-151">您可以看到已設定的匯出，匯出會分成包含目前的客戶細分，或不包含的。</span><span class="sxs-lookup"><span data-stu-id="f46da-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="f46da-152">若要將選取的客戶細分新增至匯出，請在清單中選取匯出，然後選取 **新增客戶細分**。</span><span class="sxs-lookup"><span data-stu-id="f46da-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="f46da-153">若要使用選取的客戶細分建立新匯出，請選取 **新增匯出**。</span><span class="sxs-lookup"><span data-stu-id="f46da-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="f46da-154">如需建立匯出的詳細資訊，請參閱[設定新匯出](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="f46da-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f46da-155">選取 **上一步** 以返回至客戶細分的主要頁面。</span><span class="sxs-lookup"><span data-stu-id="f46da-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="f46da-156">查看處理歷史記錄和區段成員</span><span class="sxs-lookup"><span data-stu-id="f46da-156">View processing history and segment members</span></span>

<span data-ttu-id="f46da-157">您可以透過查看資料的詳細資料，查看關於該區段的合併資料。</span><span class="sxs-lookup"><span data-stu-id="f46da-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="f46da-158">在 **區段** 頁面上選取您想檢閱的區段。</span><span class="sxs-lookup"><span data-stu-id="f46da-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="f46da-159">此頁面的上半部分包括趨勢圖形，其中會視覺化呈現成員計數的變化。</span><span class="sxs-lookup"><span data-stu-id="f46da-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="f46da-160">將游標移到資料點上方可查看特定日期的成員計數。</span><span class="sxs-lookup"><span data-stu-id="f46da-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="f46da-161">您可以更新視覺效果的時間範圍。</span><span class="sxs-lookup"><span data-stu-id="f46da-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f46da-162">![區段時間範圍](media/segment-time-range.png "區段時間範圍")</span><span class="sxs-lookup"><span data-stu-id="f46da-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="f46da-163">下半部分包含區段成員的清單。</span><span class="sxs-lookup"><span data-stu-id="f46da-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="f46da-164">此清單中顯示的欄位是根據區段實體的屬性。</span><span class="sxs-lookup"><span data-stu-id="f46da-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="f46da-165">此清單是相符區段成員的預覽，並顯示區段的前 100 個記錄，這樣您就可以快速評估並查看其定義（如有需要）。</span><span class="sxs-lookup"><span data-stu-id="f46da-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="f46da-166">若要查看所有相符的記錄，您需要[匯出區段](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="f46da-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
