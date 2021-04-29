---
title: 客戶活動
description: 定義客戶活動，並在客戶時間表中查看它們。
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866397"
---
# <a name="customer-activities"></a><span data-ttu-id="799df-103">客戶活動</span><span class="sxs-lookup"><span data-stu-id="799df-103">Customer activities</span></span>

<span data-ttu-id="799df-104">在 Dynamics 365 Customer Insights 中將[不同資料來源](data-sources.md)的客戶活動結合，以建立時間表依時間順序列出活動。</span><span class="sxs-lookup"><span data-stu-id="799df-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="799df-105">將時間表加入到具備[客戶卡片增益集](customer-card-add-in.md)解決方案的 Dynamics 365 應用程式中或加入到 Power BI 儀表板中。</span><span class="sxs-lookup"><span data-stu-id="799df-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="799df-106">定義活動</span><span class="sxs-lookup"><span data-stu-id="799df-106">Define an activity</span></span>

<span data-ttu-id="799df-107">您的資料來源能包含具有交易資料及活動資料的實體，這些資料可來自多個資料來源。</span><span class="sxs-lookup"><span data-stu-id="799df-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="799df-108">找出這些實體，並選取您要在客戶的時間表上檢視的活動。</span><span class="sxs-lookup"><span data-stu-id="799df-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="799df-109">選擇包含目標活動的實體。</span><span class="sxs-lookup"><span data-stu-id="799df-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="799df-110">實體必須至少有一個類型為 **日期** 的屬性，才能包含在客戶時間表中，而且您無法新增不含 **日期** 欄位的實體。</span><span class="sxs-lookup"><span data-stu-id="799df-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="799df-111">如果找不到這樣的實體，就會停用 **新增活動** 控制項。</span><span class="sxs-lookup"><span data-stu-id="799df-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="799df-112">在對象見解中，前往 **資料** > **活動**。</span><span class="sxs-lookup"><span data-stu-id="799df-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="799df-113">選取 **新增活動**，以啟動引導式體驗進行活動設定程序。</span><span class="sxs-lookup"><span data-stu-id="799df-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="799df-114">在 **活動資料** 步驟中，設定下列欄位的值：</span><span class="sxs-lookup"><span data-stu-id="799df-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="799df-115">**活動名稱**：選取活動的名稱。</span><span class="sxs-lookup"><span data-stu-id="799df-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="799df-116">**實體**：選取包含交易資料或活動資料的實體。</span><span class="sxs-lookup"><span data-stu-id="799df-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="799df-117">**主索引鍵**：選取唯一識別記錄的欄位。</span><span class="sxs-lookup"><span data-stu-id="799df-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="799df-118">其中不得包含任何重複值、空白值或遺漏值。</span><span class="sxs-lookup"><span data-stu-id="799df-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="以名稱、實體和主索引鍵來設定活動資料。":::

1. <span data-ttu-id="799df-120">選取 **下一步** 前往下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="799df-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="799df-121">在 **關聯** 步驟中，設定詳細資料，將您的活動資料連接至與其對應的客戶。</span><span class="sxs-lookup"><span data-stu-id="799df-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="799df-122">此步驟會視覺化呈現實體之間的連接。</span><span class="sxs-lookup"><span data-stu-id="799df-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="799df-123">**第一**：活動實體中的外部欄位，用來建立與另一個實體的關聯。</span><span class="sxs-lookup"><span data-stu-id="799df-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="799df-124">**第二**：與活動實體關聯的對應來源客戶實體。</span><span class="sxs-lookup"><span data-stu-id="799df-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="799df-125">您只能關聯資料整合程序中使用到的來源客戶實體。</span><span class="sxs-lookup"><span data-stu-id="799df-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="799df-126">**第三**：如果此活動實體與選取的來源客戶實體之間的關聯已存在，則關聯名稱將會處於唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="799df-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="799df-127">如果不存在這樣的關聯，則會以您在此方塊中提供的名稱來建立新關聯。</span><span class="sxs-lookup"><span data-stu-id="799df-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="定義實體關聯。":::

1. <span data-ttu-id="799df-129">選取 **下一步** 前往下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="799df-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="799df-130">在 **整合活動** 步驟中，選擇活動事件和活動的開始時間。</span><span class="sxs-lookup"><span data-stu-id="799df-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="799df-131">**必填欄位**</span><span class="sxs-lookup"><span data-stu-id="799df-131">**Required fields**</span></span>
      1. <span data-ttu-id="799df-132">**活動事件**：活動事件的欄位</span><span class="sxs-lookup"><span data-stu-id="799df-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="799df-133">**時間戳記**：代表活動開始時間的欄位。</span><span class="sxs-lookup"><span data-stu-id="799df-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="799df-134">**選用欄位**</span><span class="sxs-lookup"><span data-stu-id="799df-134">**Optional fields**</span></span>
      1. <span data-ttu-id="799df-135">**其他詳細資料**：此活動相關資訊的欄位。</span><span class="sxs-lookup"><span data-stu-id="799df-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="799df-136">**圖示**：最能代表此活動類型的圖示。</span><span class="sxs-lookup"><span data-stu-id="799df-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="799df-137">**網址**：此欄位可包含有關此活動資訊的 URL。</span><span class="sxs-lookup"><span data-stu-id="799df-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="799df-138">例如，為此活動提供資訊的交易系統。</span><span class="sxs-lookup"><span data-stu-id="799df-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="799df-139">此 URL 可以是資料來源中的任何欄位，也可以使用 Power Query 轉換將其建構為新欄位。</span><span class="sxs-lookup"><span data-stu-id="799df-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="799df-140">URL 資料會儲存在 *整合活動* 實體中，而此實體可以在下游以[API](apis.md)使用。</span><span class="sxs-lookup"><span data-stu-id="799df-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="在整合活動實體中指定客戶活動資料。":::

1. <span data-ttu-id="799df-142">選取 **下一步** 移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="799df-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="799df-143">要儲存設定為 **其他** 的活動類型，您可以選取 **完成並審核** 以立即儲存活動。</span><span class="sxs-lookup"><span data-stu-id="799df-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="799df-144">在 **活動類型** 步驟中，選取活動類型，然後可以選擇是否要用語意方式對應某些活動類型(以用於 Customer Insights 的其他區域)。</span><span class="sxs-lookup"><span data-stu-id="799df-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="799df-145">目前，在同意對應欄位之後，便能以語意對應 *訂閱* & *SalesOrderLine* 的活動類型。</span><span class="sxs-lookup"><span data-stu-id="799df-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="799df-146">如果活動類型與新的活動不相關，您可以選擇 *其他* 或為自訂活動類型 *建立新的活動類型*。</span><span class="sxs-lookup"><span data-stu-id="799df-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="799df-147">選取 **下一步** 移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="799df-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="799df-148">在 **檢閱** 步驟中，確認您的選取。</span><span class="sxs-lookup"><span data-stu-id="799df-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="799df-149">回到先前的任何步驟，並視需要更新資訊。</span><span class="sxs-lookup"><span data-stu-id="799df-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="檢閱活動的指定欄位。":::
   
1. <span data-ttu-id="799df-151">選取 **儲存活動** 以套用變更，然後選取 **已完成** 回到 **資料** > **活動**。</span><span class="sxs-lookup"><span data-stu-id="799df-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="799df-152">在此處能看見在時間表中設定為要顯示的活動。</span><span class="sxs-lookup"><span data-stu-id="799df-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="799df-153">在 **活動** 頁面上，選取 **執行** 來處理活動。</span><span class="sxs-lookup"><span data-stu-id="799df-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="799df-154">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="799df-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="799df-155">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="799df-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="799df-156">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="799df-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="799df-157">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="799df-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="799df-158">管理現有的活動</span><span class="sxs-lookup"><span data-stu-id="799df-158">Manage existing activities</span></span>

<span data-ttu-id="799df-159">在 **資料** > **活動** 中，您可以查看所有已儲存的活動，並加以管理。</span><span class="sxs-lookup"><span data-stu-id="799df-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="799df-160">每個活動都是由資料列顯示，其中也包含有關來源、實體和活動類型的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="799df-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="799df-161">當您選取活動時，可以使用下列動作。</span><span class="sxs-lookup"><span data-stu-id="799df-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="799df-162">**編輯**：在檢閱步驟上打開活動設定。</span><span class="sxs-lookup"><span data-stu-id="799df-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="799df-163">您可以從此步驟變更目前的任何或全部設定。</span><span class="sxs-lookup"><span data-stu-id="799df-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="799df-164">變更設定之後，請選取 **儲存活動**，然後選取 **執行** 來進行變更。</span><span class="sxs-lookup"><span data-stu-id="799df-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="799df-165">**重新命名**：打開對話方塊，為選取的活動輸入不同的名稱。</span><span class="sxs-lookup"><span data-stu-id="799df-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="799df-166">選取 **儲存** 套用變更。</span><span class="sxs-lookup"><span data-stu-id="799df-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="799df-167">**刪除**：打開對話方塊，確認刪除選取的活動。</span><span class="sxs-lookup"><span data-stu-id="799df-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="799df-168">您也可以一次刪除多個活動，方法是先選取活動，然後選取刪除圖示。</span><span class="sxs-lookup"><span data-stu-id="799df-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="799df-169">請選取 **刪除**，以確認刪除。</span><span class="sxs-lookup"><span data-stu-id="799df-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
