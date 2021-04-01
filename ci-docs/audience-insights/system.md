---
title: 對象見解中的系統組態
description: 瞭解 Dynamics 365 Customer Insights 對象見解能力中的系統設定。
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 87bf8d7b9c23633ebdc929e15ac645c55cc21e4a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595370"
---
# <a name="system-configuration"></a><span data-ttu-id="6bd5c-103">系統設定</span><span class="sxs-lookup"><span data-stu-id="6bd5c-103">System configuration</span></span>

<span data-ttu-id="6bd5c-104">**系統** 頁面包括下列索引標籤：</span><span class="sxs-lookup"><span data-stu-id="6bd5c-104">The **System** page includes the following tabs:</span></span>
- [<span data-ttu-id="6bd5c-105">狀態</span><span class="sxs-lookup"><span data-stu-id="6bd5c-105">Status</span></span>](#status-tab)
- [<span data-ttu-id="6bd5c-106">排程</span><span class="sxs-lookup"><span data-stu-id="6bd5c-106">Schedule</span></span>](#schedule-tab)
- [<span data-ttu-id="6bd5c-107">API 使用情況</span><span class="sxs-lookup"><span data-stu-id="6bd5c-107">API usage</span></span>](#api-usage-tab)
- [<span data-ttu-id="6bd5c-108">關於</span><span class="sxs-lookup"><span data-stu-id="6bd5c-108">About</span></span>](#about-tab)
- [<span data-ttu-id="6bd5c-109">一般</span><span class="sxs-lookup"><span data-stu-id="6bd5c-109">General</span></span>](#general-tab)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6bd5c-110">![系統頁面](media/system-tabs.png "系統頁面")</span><span class="sxs-lookup"><span data-stu-id="6bd5c-110">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="6bd5c-111">狀態索引標籤</span><span class="sxs-lookup"><span data-stu-id="6bd5c-111">Status tab</span></span>

<span data-ttu-id="6bd5c-112">**狀態索引標籤** 可讓您追蹤資料擷取、資料匯出和數個其他重要產品程序的進度。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-112">The **Status tab** lets you track the progress of data ingestion, data exports, and several other important product processes.</span></span> <span data-ttu-id="6bd5c-113">評論此索引標籤上的資訊確保有效流程的完整性。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-113">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="6bd5c-114">此索引標籤包括的表格具備各種程序的狀態和處理中的資訊。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-114">This tab includes tables with status and processing information for various processes.</span></span> <span data-ttu-id="6bd5c-115">每個表格都會追蹤工作的 **名稱** 及其對應的實體、最近的執行 **狀態** 以及 **上次更新** 時間。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-115">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="6bd5c-116">選取工作名稱，以檢視該工作最後幾次執行的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-116">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="6bd5c-117">狀態類型</span><span class="sxs-lookup"><span data-stu-id="6bd5c-117">Status types</span></span>

<span data-ttu-id="6bd5c-118">任務目前有六種類型的狀態。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-118">There are six types of status for tasks.</span></span> <span data-ttu-id="6bd5c-119">下列狀態類型也會顯示在 *比對*、*合併*、*資料來源*、*區段*、*量值*、*擴充*、*活動* 及 *預測* 頁面：</span><span class="sxs-lookup"><span data-stu-id="6bd5c-119">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="6bd5c-120">**正在處理：** 工作正在進行中。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-120">**Processing:** Task is in progress.</span></span> <span data-ttu-id="6bd5c-121">狀態會變更為成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-121">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="6bd5c-122">**成功：** 工作已順利完成。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-122">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="6bd5c-123">**已略過：** 已跳過的工作。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-123">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="6bd5c-124">此工作相依的一個或多個下游程序失敗或已略過。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-124">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="6bd5c-125">**失敗：** 工作處理失敗。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-125">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="6bd5c-126">**已取消：** 使用者在完成之前已取消處理。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-126">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="6bd5c-127">**已佇列：** 處理已排入佇列，並會在所有上游工作都完成後開始。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-127">**Queued:** Processing is queued and will start once all the upstream tasks are completed.</span></span> <span data-ttu-id="6bd5c-128">如需詳細資訊，請參閱[重新整理原則](#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-128">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="6bd5c-129">重新整理原則</span><span class="sxs-lookup"><span data-stu-id="6bd5c-129">Refresh policies</span></span>

<span data-ttu-id="6bd5c-130">此清單顯示每個主要流程的重新整理政策：</span><span class="sxs-lookup"><span data-stu-id="6bd5c-130">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="6bd5c-131">**資料來源：** 根據 [設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-131">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6bd5c-132">不依存於任何其他程序。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-132">Doesn't depend on any other process.</span></span> <span data-ttu-id="6bd5c-133">比對依賴於此程序是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-133">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="6bd5c-134">**比對：** 根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-134">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6bd5c-135">依賴於比對定義中所使用的資料來源處理而定。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-135">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="6bd5c-136">合併依賴於程序是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-136">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="6bd5c-137">**合併**：根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-137">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6bd5c-138">依賴於比對程序是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-138">Depends on the completion of the match process.</span></span> <span data-ttu-id="6bd5c-139">區段、量值、擴充、搜尋、活動、預測和資料準備工作都依賴於程序是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-139">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="6bd5c-140">**區段**：手動執行（單次重新整理），並根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-140">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6bd5c-141">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-141">Depends on Merge.</span></span> <span data-ttu-id="6bd5c-142">見解依賴於其處理。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-142">Insights depend on its processing.</span></span>
- <span data-ttu-id="6bd5c-143">**量值**：手動執行（單次重新整理），並根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-143">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6bd5c-144">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-144">Depends on Merge.</span></span>
- <span data-ttu-id="6bd5c-145">**活動**：手動執行（單次重新整理），以及根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-145">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6bd5c-146">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-146">Depends on Merge.</span></span>
- <span data-ttu-id="6bd5c-147">**擴充**：手動執行（單次重新整理），以及根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-147">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6bd5c-148">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-148">Depends on Merge.</span></span>
- <span data-ttu-id="6bd5c-149">**搜尋**：手動執行（單次重新整理），以及根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-149">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6bd5c-150">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-150">Depends on Merge.</span></span>
- <span data-ttu-id="6bd5c-151">**資料準備：** 根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-151">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6bd5c-152">依賴於合併。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-152">Depends on Merge.</span></span>
- <span data-ttu-id="6bd5c-153">**見解**：手動執行（單次重新整理），並根據[設定的排程](#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-153">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6bd5c-154">依賴於區段。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-154">Depends on Segments.</span></span>

<span data-ttu-id="6bd5c-155">選取工作的狀態，以查看該工作所在之整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-155">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="6bd5c-156">上述的重新整理原則可以協助您了解如何處理 **已略過** 或 **已排入佇列** 的工作 。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-156">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="6bd5c-157">排程索引標籤</span><span class="sxs-lookup"><span data-stu-id="6bd5c-157">Schedule tab</span></span>

<span data-ttu-id="6bd5c-158">使用 **排程** 索引標籤排程您的所有 [內嵌資料來源](data-sources.md) 的自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-158">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="6bd5c-159">自動重新整理可協助確保資料來源更新會反映在您的統一客戶設定檔中。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-159">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="6bd5c-160">請在觀眾見解中前往 **管理員**  > **系統** 並選取 **排程** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-160">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="6bd5c-161">排程的重新整理預設狀態為 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-161">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="6bd5c-162">若要啟用排程的重新整理，請將畫面頂端的切換變更為 **開啟**。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-162">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="6bd5c-163">在 **每週**（預設）和 **每日** 重新整理之間選擇。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-163">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="6bd5c-164">如果想要排定每週重新整理，請選取一或多個要執行重新整理的天數。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-164">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="6bd5c-165">設定您的 **時區**，然後使用 **時間** 下拉式功能表來設定您的重新整理時間安排。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-165">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="6bd5c-166">完成時，選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-166">When you're finished, select **Set**.</span></span> <span data-ttu-id="6bd5c-167">如果您想要在一天中安排多次重新整理，請選取 **新增其他時間**。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-167">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="6bd5c-168">選取 **儲存** 套用變更。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-168">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="6bd5c-169">關於索引標籤</span><span class="sxs-lookup"><span data-stu-id="6bd5c-169">About tab</span></span>

<span data-ttu-id="6bd5c-170">**關於** 索引標籤包含組織的 **顯示名稱**、使用中 **環境識別碼**、**地區** 以及您的 **工作階段識別碼**。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-170">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="6bd5c-171">如果您有一個以上工作環境，您應該給每一個容易辨識的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-171">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="6bd5c-172">[一般] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="6bd5c-172">General tab</span></span>

<span data-ttu-id="6bd5c-173">**一般** 索引標籤、**語言** 和 **國家/地區格式** 中有兩個選項。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-173">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="6bd5c-174">應用程式 [支援幾種語言](supported-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-174">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="6bd5c-175">若要變更您的慣用語言，請從下拉式功能表中選擇 **語言**。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-175">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="6bd5c-176">若要變更日期、時間及數位的慣用格式，請使用 **國家/地區格式** 下拉式功能表。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-176">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="6bd5c-177">格式預覽會顯示在此欄位下。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-177">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="6bd5c-178">當您選擇新語言時，系統會自動建議一項選取項目。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-178">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="6bd5c-179">選取 **儲存** 以確認您的選擇。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-179">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="6bd5c-180">API 使用方式索引標籤</span><span class="sxs-lookup"><span data-stu-id="6bd5c-180">API usage tab</span></span>

<span data-ttu-id="6bd5c-181">尋找有關即時 API 用法的詳細資料，並查看在指定時間範圍中發生的事件。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-181">Find details about the real-time API usage and see which events happened in a given time frame.</span></span> <span data-ttu-id="6bd5c-182">在 **選取時間範圍** 下拉式功能表中選擇時間範圍。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-182">You choose the time frame in the **Select a time frame** drop-down menu.</span></span> 

<span data-ttu-id="6bd5c-183">**API 用法** 包含三個區段：</span><span class="sxs-lookup"><span data-stu-id="6bd5c-183">The **API usage** contains three sections:</span></span> 
- <span data-ttu-id="6bd5c-184">**API 呼叫** - 在選取的時間範圍中，會視覺化 API 彙總數量的圖表。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-184">**API calls** - a chart that visualizes the aggregated number of calls to the API in the selected time frame.</span></span>

- <span data-ttu-id="6bd5c-185">**資料傳輸** - 圖表上顯示選取的時間範圍中，透過 API 傳送的資料總量。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-185">**Data transfer** - a chart that shows the amount of data that was transferred through the API in the selected time frame.</span></span>

-  <span data-ttu-id="6bd5c-186">**作業** - 表格上的列是每個可用的 API 作業，以及有關作業使用方式的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-186">**Operations** - a table with rows for each available API operation and details about the usage of the operations.</span></span> <span data-ttu-id="6bd5c-187">您可以選取作業名稱並移至 [API 參考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-187">You can select an operation name to go to [the API reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

   <span data-ttu-id="6bd5c-188">使用到[即時資料擷取的操作](real-time-data-ingestion.md)的作業，其中包含帶有望遠鏡符號的按鈕，可以查看即時 API 的使用方式。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-188">Operations which use [real-time data ingestion](real-time-data-ingestion.md) contain a button with a binocular symbol to view real-time API usage.</span></span> <span data-ttu-id="6bd5c-189">選取此按鈕打開內含目前環境中即時 API 使用方式詳細資料的側窗格。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-189">Select the button to open a side pane containing usage details for the real-time API usage in the current environment.</span></span>   
   <span data-ttu-id="6bd5c-190">使用 **即時 API 使用方式** 窗格中的 **分組依據** 方塊，以選擇如何最好地呈現您的即時互動。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-190">Use the **Group by** box in the **Real-time API usage** pane to choose how to best present your real-time interactions.</span></span> <span data-ttu-id="6bd5c-191">您可以依據 API 方法、實體限定名稱 (擷取的實體)、建立者(事件來源)、結果 (成功或失敗) 或錯誤碼來分組資料。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-191">You can group the data by API method, entity qualified name (ingested entity), created by (source of the event), result (success or failure) or error codes.</span></span> <span data-ttu-id="6bd5c-192">資料可以表示為歷史圖和表格。</span><span class="sxs-lookup"><span data-stu-id="6bd5c-192">The data is available as a history chart and as a table.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]