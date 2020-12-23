---
title: 對象見解中的系統組態
description: 瞭解 Dynamics 365 Customer Insights 對象見解能力中的系統設定。
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405281"
---
# <a name="system-configuration"></a><span data-ttu-id="b8a4b-103">系統設定</span><span class="sxs-lookup"><span data-stu-id="b8a4b-103">System configuration</span></span>

<span data-ttu-id="b8a4b-104">**系統** 頁面包括四個索引標籤：**狀態**、**排程**、**關於** 和 **一般**。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-104">The **System** page includes four tabs: **Status**, **Schedule**, **About**, and **General**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b8a4b-105">![系統頁面](media/system-tabs.png "系統頁面")</span><span class="sxs-lookup"><span data-stu-id="b8a4b-105">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="b8a4b-106">狀態索引標籤</span><span class="sxs-lookup"><span data-stu-id="b8a4b-106">Status tab</span></span>

<span data-ttu-id="b8a4b-107">**狀態索引標籤** 可讓您追蹤資料擷取、資料匯入及數個重要產品程序的進度。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-107">The **Status tab** lets you track the progress of data ingestion, data exports, and several important product processes.</span></span> <span data-ttu-id="b8a4b-108">評論此索引標籤上的資訊確保有效流程的完整性。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-108">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="b8a4b-109">此索引標籤包含 **資料來源**、**系統程序** 和 **資料準備** 的狀態表格。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-109">This tab includes status tables for **Data sources**, **System processes**, and **Data preparation**.</span></span> <span data-ttu-id="b8a4b-110">每個表格都會追蹤工作的 **名稱** 及其對應的實體、最近的執行 **狀態** 以及 **上次更新** 時間。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-110">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="b8a4b-111">選取工作名稱，以檢視該工作最後幾次執行的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-111">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="b8a4b-112">狀態類型</span><span class="sxs-lookup"><span data-stu-id="b8a4b-112">Status types</span></span>

<span data-ttu-id="b8a4b-113">任務目前有六種類型的狀態。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-113">There are six types of status for tasks.</span></span> <span data-ttu-id="b8a4b-114">下列狀態類型也會顯示在 *比對*、*合併*、*資料來源*、*區段*、*量值*、*擴充*、*活動* 及 *預測* 頁面：</span><span class="sxs-lookup"><span data-stu-id="b8a4b-114">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="b8a4b-115">**正在處理：** 工作正在進行中。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-115">**Processing:** Task is in progress.</span></span> <span data-ttu-id="b8a4b-116">狀態會變更為成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-116">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="b8a4b-117">**成功：** 工作已順利完成。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-117">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="b8a4b-118">**已略過：** 已跳過的工作。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-118">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="b8a4b-119">此工作相依的一個或多個下游程序失敗或已略過。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-119">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="b8a4b-120">**失敗：** 工作處理失敗。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-120">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="b8a4b-121">**已取消：** 使用者在完成之前已取消處理。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-121">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="b8a4b-122">**已排入佇列：** 處理已排入佇列，並會在所有下游工作都完成後開始。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-122">**Queued:** Processing is queued and will start once all the downstream tasks are completed.</span></span> <span data-ttu-id="b8a4b-123">如需詳細資訊，請參閱[重新整理原則](#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-123">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="b8a4b-124">重新整理原則</span><span class="sxs-lookup"><span data-stu-id="b8a4b-124">Refresh policies</span></span>

<span data-ttu-id="b8a4b-125">此清單顯示每個主要流程的重新整理政策：</span><span class="sxs-lookup"><span data-stu-id="b8a4b-125">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="b8a4b-126">**資料來源：** 根據 [設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-126">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="b8a4b-127">不依存於任何其他程序。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-127">Doesn't depend on any other process.</span></span> <span data-ttu-id="b8a4b-128">比對依賴於此程序是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-128">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="b8a4b-129">**比對：** 根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-129">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="b8a4b-130">依賴於比對定義中所使用的資料來源處理而定。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-130">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="b8a4b-131">合併依賴於程序是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-131">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="b8a4b-132">**合併**：根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-132">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="b8a4b-133">依賴於比對程序是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-133">Depends on the completion of the match process.</span></span> <span data-ttu-id="b8a4b-134">區段、量值、擴充、搜尋、活動、預測和資料準備工作都依賴於程序是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-134">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="b8a4b-135">**區段**：手動執行（單次重新整理），並根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-135">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="b8a4b-136">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-136">Depends on Merge.</span></span> <span data-ttu-id="b8a4b-137">見解依賴於其處理。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-137">Insights depend on its processing.</span></span>
- <span data-ttu-id="b8a4b-138">**量值**：手動執行（單次重新整理），並根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-138">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="b8a4b-139">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-139">Depends on Merge.</span></span>
- <span data-ttu-id="b8a4b-140">**活動**：手動執行（單次重新整理），以及根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-140">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="b8a4b-141">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-141">Depends on Merge.</span></span>
- <span data-ttu-id="b8a4b-142">**擴充**：手動執行（單次重新整理），以及根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-142">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="b8a4b-143">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-143">Depends on Merge.</span></span>
- <span data-ttu-id="b8a4b-144">**搜尋**：手動執行（單次重新整理），以及根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-144">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="b8a4b-145">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-145">Depends on Merge.</span></span>
- <span data-ttu-id="b8a4b-146">**資料準備：** 根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-146">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="b8a4b-147">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-147">Depends on Merge.</span></span>
- <span data-ttu-id="b8a4b-148">**見解**：手動執行（單次重新整理），並根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-148">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="b8a4b-149">依賴於區段。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-149">Depends on Segments.</span></span>

<span data-ttu-id="b8a4b-150">選取工作的狀態，以查看該工作所在之整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-150">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="b8a4b-151">上述的重新整理原則可以協助您了解如何處理 **已略過** 或 **已排入佇列** 的工作 。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-151">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="b8a4b-152">排程索引標籤</span><span class="sxs-lookup"><span data-stu-id="b8a4b-152">Schedule tab</span></span>

<span data-ttu-id="b8a4b-153">使用 **排程** 索引標籤排程您的所有 [內嵌資料來源](data-sources.md) 的自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-153">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="b8a4b-154">自動重新整理可協助確保資料來源更新會反映在您的統一客戶設定檔中。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-154">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="b8a4b-155">請在觀眾見解中前往 **管理員**  > **系統** 並選取 **排程** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-155">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="b8a4b-156">排程的重新整理預設狀態為 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-156">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="b8a4b-157">若要啟用排程的重新整理，請將畫面頂端的切換變更為 **開啟**。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-157">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="b8a4b-158">在 **每週**（預設）和 **每日** 重新整理之間選擇。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-158">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="b8a4b-159">如果想要排定每週重新整理，請選取一或多個要執行重新整理的天數。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-159">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="b8a4b-160">設定您的 **時區**，然後使用 **時間** 下拉式功能表來設定您的重新整理時間安排。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-160">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="b8a4b-161">完成時，選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-161">When you're finished, select **Set**.</span></span> <span data-ttu-id="b8a4b-162">如果您想要在一天中安排多次重新整理，請選取 **新增其他時間**。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-162">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="b8a4b-163">選取 **儲存** 套用變更。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-163">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="b8a4b-164">關於索引標籤</span><span class="sxs-lookup"><span data-stu-id="b8a4b-164">About tab</span></span>

<span data-ttu-id="b8a4b-165">**關於** 索引標籤包含組織的 **顯示名稱**、使用中 **環境識別碼**、**地區** 以及您的 **工作階段識別碼**。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-165">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="b8a4b-166">如果您有一個以上工作環境，您應該給每一個容易辨識的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-166">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="b8a4b-167">[一般] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="b8a4b-167">General tab</span></span>

<span data-ttu-id="b8a4b-168">**一般** 索引標籤、**語言** 和 **國家/地區格式** 中有兩個選項。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-168">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="b8a4b-169">應用程式 [支援幾種語言](supported-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-169">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="b8a4b-170">若要變更您的慣用語言，請從下拉式功能表中選擇 **語言**。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-170">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="b8a4b-171">若要變更日期、時間及數位的慣用格式，請使用 **國家/地區格式** 下拉式功能表。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-171">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="b8a4b-172">格式預覽會顯示在此欄位下。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-172">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="b8a4b-173">當您選擇新語言時，系統會自動建議一項選取項目。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-173">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="b8a4b-174">選取 **儲存** 以確認您的選擇。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-174">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="b8a4b-175">API 使用方式索引標籤</span><span class="sxs-lookup"><span data-stu-id="b8a4b-175">API usage tab</span></span>

<span data-ttu-id="b8a4b-176">尋找有關即時 API 使用方式的詳細資料，並查看哪些事件是在時間範圍內發生的事件。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-176">Find details about the real-time API usage and see which events happened in a given time range.</span></span> <span data-ttu-id="b8a4b-177">如需詳細資訊，請參閱[即時資料擷取](real-time-data-ingestion.md)。</span><span class="sxs-lookup"><span data-stu-id="b8a4b-177">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>
