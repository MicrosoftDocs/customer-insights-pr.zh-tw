---
title: 客戶活動
description: 定義客戶活動，並在客戶時間表中查看它們。
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267422"
---
# <a name="customer-activities"></a><span data-ttu-id="7a786-103">客戶活動</span><span class="sxs-lookup"><span data-stu-id="7a786-103">Customer activities</span></span>

<span data-ttu-id="7a786-104">結合 Dynamics 365 Customer Insights 中 [各種資料來源](data-sources.md) 的客戶活動，以建立依時間順序列出活動的客戶時間表。</span><span class="sxs-lookup"><span data-stu-id="7a786-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="7a786-105">您可以透過[客戶卡片增益集](customer-card-add-in.md)在 Dynamics 365 的客戶參與應用程式中，或在 Power BI 儀表板中包含時間表。</span><span class="sxs-lookup"><span data-stu-id="7a786-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="7a786-106">定義活動</span><span class="sxs-lookup"><span data-stu-id="7a786-106">Define an activity</span></span>

<span data-ttu-id="7a786-107">您的資料來源包含具有來自多個資料來源的交易資料及活動資料的實體。</span><span class="sxs-lookup"><span data-stu-id="7a786-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="7a786-108">找出這些實體，並選取您要在客戶的時間表上檢視的活動。</span><span class="sxs-lookup"><span data-stu-id="7a786-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="7a786-109">選擇包含目標活動的實體。</span><span class="sxs-lookup"><span data-stu-id="7a786-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="7a786-110">在對象見解中，前往 **資料** > **活動**。</span><span class="sxs-lookup"><span data-stu-id="7a786-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="7a786-111">選取 **新增活動**。</span><span class="sxs-lookup"><span data-stu-id="7a786-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7a786-112">實體必須至少有一個類型為 **日期** 的屬性，才能包含在客戶時間表中，而且您無法新增不含 **日期** 欄位的實體。</span><span class="sxs-lookup"><span data-stu-id="7a786-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="7a786-113">如果找不到這樣的實體，就會停用 **新增活動** 控制項。</span><span class="sxs-lookup"><span data-stu-id="7a786-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="7a786-114">在 **新增活動** 窗格中，設定下列欄位的值：</span><span class="sxs-lookup"><span data-stu-id="7a786-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="7a786-115">**實體**：選取包含交易資料或活動資料的實體。</span><span class="sxs-lookup"><span data-stu-id="7a786-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="7a786-116">**主索引鍵**：選取唯一識別記錄的欄位。</span><span class="sxs-lookup"><span data-stu-id="7a786-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="7a786-117">其中不得包含任何重複值、空白值或遺漏值。</span><span class="sxs-lookup"><span data-stu-id="7a786-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="7a786-118">**時間戳記**：選取表示活動開始時間的欄位。</span><span class="sxs-lookup"><span data-stu-id="7a786-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="7a786-119">**事件**：選取做為活動事件的欄位。</span><span class="sxs-lookup"><span data-stu-id="7a786-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="7a786-120">**網址**：選取表示提供有關此活動其他資訊之 URL 的欄位。</span><span class="sxs-lookup"><span data-stu-id="7a786-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="7a786-121">例如，為此活動提供資訊的交易系統。</span><span class="sxs-lookup"><span data-stu-id="7a786-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="7a786-122">此 URL 可以是資料來源中的任何欄位，也可以使用 Power Query 轉換將其建構為新欄位。</span><span class="sxs-lookup"><span data-stu-id="7a786-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="7a786-123">此 URL 資料儲存於整合活動實體，您可以使用 API 順流取用此實體。</span><span class="sxs-lookup"><span data-stu-id="7a786-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="7a786-124">**詳細資料**：(選用) 選取為了取得其他詳細資料而新增的欄位。</span><span class="sxs-lookup"><span data-stu-id="7a786-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="7a786-125">**圖示**：(選用) 選取代表此活動的圖示。</span><span class="sxs-lookup"><span data-stu-id="7a786-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="7a786-126">**活動類型**：定義描述活動語義定義最貼切之 Common Data Model 的活動類型參考。</span><span class="sxs-lookup"><span data-stu-id="7a786-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="7a786-127">在 **設定關聯** 區段中，設定詳細資料，將您的活動資料連接至其對應的客戶。</span><span class="sxs-lookup"><span data-stu-id="7a786-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="7a786-128">**活動實體欄位**：選取活動實體中用來建立與另一個實體的關聯的欄位。</span><span class="sxs-lookup"><span data-stu-id="7a786-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="7a786-129">**客戶實體**：選取您的活動實體要與其關聯的對應來源客戶實體。</span><span class="sxs-lookup"><span data-stu-id="7a786-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="7a786-130">您只能關聯至資料統整處理中所使用的來源客戶實體。</span><span class="sxs-lookup"><span data-stu-id="7a786-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="7a786-131">**客戶實體欄位**：此欄位會顯示對應程序中所選取的來源客戶實體主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="7a786-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="7a786-132">來源客戶實體中的這個主索引鍵欄位是用來建立與活動實體的關聯。</span><span class="sxs-lookup"><span data-stu-id="7a786-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="7a786-133">**名稱**：如果此活動實體與所選取的源客戶實體之間的關聯已存在，則關聯名稱將為唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="7a786-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="7a786-134">如果不存在這樣的關聯，則會以此處提供的名稱建立新關聯。</span><span class="sxs-lookup"><span data-stu-id="7a786-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7a786-135">![定義實體關聯](media/activities-entities-define.png "定義實體關聯")</span><span class="sxs-lookup"><span data-stu-id="7a786-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="7a786-136">選取 **儲存** 套用變更。</span><span class="sxs-lookup"><span data-stu-id="7a786-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="7a786-137">在 **活動** 頁面上，選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="7a786-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="7a786-138">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="7a786-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="7a786-139">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="7a786-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="7a786-140">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7a786-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="7a786-141">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="7a786-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="7a786-142">編輯活動</span><span class="sxs-lookup"><span data-stu-id="7a786-142">Edit an activity</span></span>

1. <span data-ttu-id="7a786-143">在對象見解中，前往 **資料** > **活動**。</span><span class="sxs-lookup"><span data-stu-id="7a786-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="7a786-144">選取您想要編輯的活動實體並選取 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="7a786-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="7a786-145">或者，您可以將滑鼠暫留在實體列上，然後選取 **編輯** 圖示。</span><span class="sxs-lookup"><span data-stu-id="7a786-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="7a786-146">按一下 **編輯** 圖示。</span><span class="sxs-lookup"><span data-stu-id="7a786-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="7a786-147">在 **編輯活動** 窗格中，將值更新並選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="7a786-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="7a786-148">在 **活動** 頁面上，選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="7a786-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="7a786-149">刪除活動</span><span class="sxs-lookup"><span data-stu-id="7a786-149">Delete an activity</span></span>

1. <span data-ttu-id="7a786-150">在對象見解中，前往 **資料** > **活動**。</span><span class="sxs-lookup"><span data-stu-id="7a786-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="7a786-151">選取您想要移除的活動實體並選取 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="7a786-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="7a786-152">或者，您可以將滑鼠暫留在實體列上，然後選取 **刪除** 圖示。</span><span class="sxs-lookup"><span data-stu-id="7a786-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="7a786-153">此外，您也可以選取多個要同時刪除的活動實體。</span><span class="sxs-lookup"><span data-stu-id="7a786-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7a786-154">![編輯或刪除實體關聯](media/activities-entities-edit-delete.png "編輯或刪除實體關聯")</span><span class="sxs-lookup"><span data-stu-id="7a786-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="7a786-155">選取 **刪除** 圖示。</span><span class="sxs-lookup"><span data-stu-id="7a786-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="7a786-156">確認刪除。</span><span class="sxs-lookup"><span data-stu-id="7a786-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]