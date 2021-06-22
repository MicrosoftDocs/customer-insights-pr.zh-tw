---
title: 從 Customer Insights 匯出資料
description: 管理匯出到共用資料 。
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253030"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="f2afb-103">匯出 (預覽版) 概觀</span><span class="sxs-lookup"><span data-stu-id="f2afb-103">Exports (preview) overview</span></span>

<span data-ttu-id="f2afb-104">**匯出** 頁面會顯示所有已設定的匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="f2afb-105">匯出與各種應用程式共用指定資料。</span><span class="sxs-lookup"><span data-stu-id="f2afb-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="f2afb-106">這可以包括客戶個人資料或實體、結構描述及對應詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f2afb-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="f2afb-107">每個匯出都需要[由系統管理員設定的連接，來管理驗證和存取權](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="f2afb-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="f2afb-108">移至 **資料** > **匯出** 以查看匯出頁面。</span><span class="sxs-lookup"><span data-stu-id="f2afb-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="f2afb-109">所有使用者角色都擁有存取權，可以查看設定好的匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="f2afb-110">在命令列中使用搜尋欄位，可用名稱、連接名稱或連線類型來尋找匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="f2afb-111">設定新的匯出</span><span class="sxs-lookup"><span data-stu-id="f2afb-111">Set up a new export</span></span>

<span data-ttu-id="f2afb-112">若要設定或編輯匯出，您需要有可用的連接。</span><span class="sxs-lookup"><span data-stu-id="f2afb-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="f2afb-113">連接依據您的[使用者角色](permissions.md)而定：</span><span class="sxs-lookup"><span data-stu-id="f2afb-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="f2afb-114">系統管理員可以存取所有的連接。</span><span class="sxs-lookup"><span data-stu-id="f2afb-114">Administrators have access to all connections.</span></span> <span data-ttu-id="f2afb-115">在設定匯出時，他們也可以建立新的連接。</span><span class="sxs-lookup"><span data-stu-id="f2afb-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="f2afb-116">參與者可以存取特定的連接。</span><span class="sxs-lookup"><span data-stu-id="f2afb-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="f2afb-117">他們依賴系統管理員來設定和共用連接。</span><span class="sxs-lookup"><span data-stu-id="f2afb-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="f2afb-118">匯出清單會在 **您的權限** 資料行中顯示參與者是否可以編輯或是只有查看。</span><span class="sxs-lookup"><span data-stu-id="f2afb-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="f2afb-119">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="f2afb-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="f2afb-120">檢視器只能查看現有的匯出，並不能建立。</span><span class="sxs-lookup"><span data-stu-id="f2afb-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="f2afb-121">定義新的匯出</span><span class="sxs-lookup"><span data-stu-id="f2afb-121">Define a new export</span></span>

1. <span data-ttu-id="f2afb-122">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f2afb-123">請選取 **新增匯出** 建立新匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="f2afb-124">在 **設定匯出** 窗格中，選取要使用的連接。</span><span class="sxs-lookup"><span data-stu-id="f2afb-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="f2afb-125">[連接](connections.md)是由系統管理員所管理。</span><span class="sxs-lookup"><span data-stu-id="f2afb-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="f2afb-126">提供必要的詳細資料，並選取 **儲存** 來建立匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="f2afb-127">根據現有匯出定義新的匯出</span><span class="sxs-lookup"><span data-stu-id="f2afb-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="f2afb-128">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f2afb-129">在匯出清單中，選取想要複製的匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="f2afb-130">選取命令列中的 **建立副本**，打開 **設定匯出** 窗格，其中包含選取的匯出的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f2afb-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="f2afb-131">檢閱並調整匯出，並選取 **儲存** 來建立新的匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="f2afb-132">編輯匯出</span><span class="sxs-lookup"><span data-stu-id="f2afb-132">Edit an export</span></span>

1. <span data-ttu-id="f2afb-133">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f2afb-134">在匯出清單中，選取想要編輯的匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="f2afb-135">在命令列上選取 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="f2afb-136">變更想要更新的值並選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="f2afb-137">查看匯出和匯出詳細資料</span><span class="sxs-lookup"><span data-stu-id="f2afb-137">View exports and export details</span></span>

<span data-ttu-id="f2afb-138">建立匯出目的地之後，就會列在 **資料** > **匯出** 中。</span><span class="sxs-lookup"><span data-stu-id="f2afb-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="f2afb-139">所有使用者都可以看到已共用的資料及其最新狀態。</span><span class="sxs-lookup"><span data-stu-id="f2afb-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="f2afb-140">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f2afb-141">沒有編輯權限的使用者選取 **查看** 而非 **編輯** 來查看匯出詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f2afb-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="f2afb-142">側邊窗格顯示匯出的設定。</span><span class="sxs-lookup"><span data-stu-id="f2afb-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="f2afb-143">若沒有編輯權限，就無法變更值。</span><span class="sxs-lookup"><span data-stu-id="f2afb-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="f2afb-144">選取 **關閉** 來返回匯出頁面。</span><span class="sxs-lookup"><span data-stu-id="f2afb-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="f2afb-145">排程並執行多個匯出</span><span class="sxs-lookup"><span data-stu-id="f2afb-145">Schedule and run exports</span></span>

<span data-ttu-id="f2afb-146">您設定的每個匯出都會有重新整理的排程。</span><span class="sxs-lookup"><span data-stu-id="f2afb-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="f2afb-147">在重新整理期間，系統會尋找新的或更新資料是要包含在匯出中的。</span><span class="sxs-lookup"><span data-stu-id="f2afb-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="f2afb-148">根據預設，會在每次[已排程的系統重新整理](system.md#schedule-tab)中執行匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f2afb-149">您可以自訂重新整理排程，或將它關閉以手動執行匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="f2afb-150">匯出排程可依您的環境狀態決定。</span><span class="sxs-lookup"><span data-stu-id="f2afb-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="f2afb-151">如果排程的匯出應該開始時，[相依性](system.md#refresh-policies)更新正在執行，則系統會先完成相依性，再執行匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="f2afb-152">在 **重新整理** 資料行中，您可以看到上次匯出重新整理的時間。</span><span class="sxs-lookup"><span data-stu-id="f2afb-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="f2afb-153">匯出排程</span><span class="sxs-lookup"><span data-stu-id="f2afb-153">Schedule exports</span></span>

<span data-ttu-id="f2afb-154">您可以為個別匯出定義自訂重新整理排程，或一次為複數匯出定義。</span><span class="sxs-lookup"><span data-stu-id="f2afb-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="f2afb-155">目前定義的排程會列在匯出清單 **排程** 資料行中。</span><span class="sxs-lookup"><span data-stu-id="f2afb-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="f2afb-156">變更排程的權限與[編輯與定義匯出](export-destinations.md#set-up-a-new-export)的權限相同。</span><span class="sxs-lookup"><span data-stu-id="f2afb-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="f2afb-157">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f2afb-158">選取您要排程的匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="f2afb-159">在命令列中，選取 **排程**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="f2afb-160">在 **排程匯出** 窗格中，將 **排程執行** 設定為 **開啟**，以自動執行匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="f2afb-161">將它設定為 **關閉** 以手動進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="f2afb-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="f2afb-162">若要使用自動重新整理的匯出，請選擇 **定期** 值，並指定詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f2afb-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="f2afb-163">定義的時間會套用至定期的所有執行個體。</span><span class="sxs-lookup"><span data-stu-id="f2afb-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="f2afb-164">這是匯出應該開始重新整理的時間。</span><span class="sxs-lookup"><span data-stu-id="f2afb-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="f2afb-165">選取 **儲存** 以套用並啟用變更。</span><span class="sxs-lookup"><span data-stu-id="f2afb-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="f2afb-166">編輯複數匯出的排程時，您需要在 **保留或覆寫排程** 中進行選取：</span><span class="sxs-lookup"><span data-stu-id="f2afb-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="f2afb-167">**保留單一排程**：為選取的匯出保留先前定義的排程，並只停用或啟用它們。</span><span class="sxs-lookup"><span data-stu-id="f2afb-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="f2afb-168">**為選取的所有匯出定義新排程**：在選取的匯出中覆寫現有排程。</span><span class="sxs-lookup"><span data-stu-id="f2afb-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="f2afb-169">視需要執行匯出</span><span class="sxs-lookup"><span data-stu-id="f2afb-169">Run exports on demand</span></span>

<span data-ttu-id="f2afb-170">若不等待排程的重新整理，要匯出資料，請移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="f2afb-171">若要執行所有匯出，請選取命令列中的 **全部執行**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="f2afb-172">此動作將只會在擁有使用中排程的匯出上執行。</span><span class="sxs-lookup"><span data-stu-id="f2afb-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="f2afb-173">若要執行單一匯出，請在清單中選取它，然後在命令列中選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="f2afb-174">這就是如何不使用啟用中排程來執行匯出的方式。</span><span class="sxs-lookup"><span data-stu-id="f2afb-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="f2afb-175">移除匯出</span><span class="sxs-lookup"><span data-stu-id="f2afb-175">Remove an Export</span></span>

1. <span data-ttu-id="f2afb-176">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f2afb-177">選取想要移除的匯出。</span><span class="sxs-lookup"><span data-stu-id="f2afb-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="f2afb-178">在命令列中，選取 **移除**。</span><span class="sxs-lookup"><span data-stu-id="f2afb-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="f2afb-179">在確認畫面上選取 **移除** 以確認移除。</span><span class="sxs-lookup"><span data-stu-id="f2afb-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
