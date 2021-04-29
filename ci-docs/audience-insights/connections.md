---
title: 從 Customer Insights 連接到其他服務。
description: 共用資料給其他服務。
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896087"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="c582a-103">連接 (預覽版) 概觀</span><span class="sxs-lookup"><span data-stu-id="c582a-103">Connections (preview) overview</span></span>

<span data-ttu-id="c582a-104">連接是與 Customer Insights 啟用資料共用的關鍵。</span><span class="sxs-lookup"><span data-stu-id="c582a-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="c582a-105">每個連接都會對特定服務建立資料共用。</span><span class="sxs-lookup"><span data-stu-id="c582a-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="c582a-106">連接是[設定協力廠商擴充](enrichment-hub.md)和[設定匯出](export-destinations.md)的基礎。</span><span class="sxs-lookup"><span data-stu-id="c582a-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="c582a-107">同一個連接可以多次使用。</span><span class="sxs-lookup"><span data-stu-id="c582a-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="c582a-108">例如，一個對 Dynamics 365 Marketing 的連結可用於多個匯出，而另一個對 Leadspace 的連接可以用來進行多個擴充。</span><span class="sxs-lookup"><span data-stu-id="c582a-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="c582a-109">移至 **管理** > **連接** 以建立和查看連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="c582a-110">**連接** 索引標籤顯示出所有使用中的連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="c582a-111">每個連接顯示為清單上的一列。</span><span class="sxs-lookup"><span data-stu-id="c582a-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="c582a-112">取得簡易概觀、說明，以及使用 **探索** 索引標籤上的每個擴充性選項，了解可以執行的動作。</span><span class="sxs-lookup"><span data-stu-id="c582a-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="c582a-113">匯出</span><span class="sxs-lookup"><span data-stu-id="c582a-113">Exports</span></span>

<span data-ttu-id="c582a-114">只有系統管理員可以設定新的連接，但是他們可以將使用現有連接的存取權授予給參與者。</span><span class="sxs-lookup"><span data-stu-id="c582a-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="c582a-115">系統管理員控制資料的流向，參與者定義符合其需求的酬載和頻率。</span><span class="sxs-lookup"><span data-stu-id="c582a-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="c582a-116">如需詳細資訊，請參閱[允許參與者使用匯出的連接](#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="c582a-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="c582a-117">擴充</span><span class="sxs-lookup"><span data-stu-id="c582a-117">Enrichments</span></span>

<span data-ttu-id="c582a-118">只有系統管理員才可以設定新的連接，但是所建立的連接都可供系統管理員和參與者使用。</span><span class="sxs-lookup"><span data-stu-id="c582a-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="c582a-119">系統管理員能管理認證並同意資料傳輸。</span><span class="sxs-lookup"><span data-stu-id="c582a-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="c582a-120">系統管理員和參與者都可以使用這些連接進行擴充。</span><span class="sxs-lookup"><span data-stu-id="c582a-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="c582a-121">新增連接</span><span class="sxs-lookup"><span data-stu-id="c582a-121">Add a new connection</span></span>

<span data-ttu-id="c582a-122">若要新增連接，您必須具備[系統管理員權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c582a-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="c582a-123">如果您連至其他 Microsoft 服務，我們預設這兩個服務位於相同的組織中。</span><span class="sxs-lookup"><span data-stu-id="c582a-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="c582a-124">移至 **管理** > **連接 (預覽版)**。</span><span class="sxs-lookup"><span data-stu-id="c582a-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="c582a-125">移至 **連結** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c582a-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="c582a-126">請選取 **新增連接** 建立新連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="c582a-127">在下拉式功能表中選擇想要建立的連接類型。</span><span class="sxs-lookup"><span data-stu-id="c582a-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="c582a-128">在 **設定連接** 窗格中，提供必要的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c582a-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="c582a-129">以連結的 **顯示名稱** 與類型設定連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="c582a-130">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="c582a-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="c582a-131">準確的欄位則依您要連接的服務而定。</span><span class="sxs-lookup"><span data-stu-id="c582a-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="c582a-132">在目標服務的相關文章中，可以了解特定連接的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c582a-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="c582a-133">選取 **儲存** 建立連結。</span><span class="sxs-lookup"><span data-stu-id="c582a-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="c582a-134">您也可以在 **探索** 索引標籤中選取圖標上的 **設定**。</span><span class="sxs-lookup"><span data-stu-id="c582a-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="c582a-135">允許參與者使用匯出連接</span><span class="sxs-lookup"><span data-stu-id="c582a-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="c582a-136">設定或編輯匯出連接時，定義[匯出](export-destinations.md)要選擇允許哪些使用者使用此特定連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="c582a-137">根據預設，具有系統管理員角色的使用者可以使用連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="c582a-138">您可以在 **選取能使用此連接的人員** 下變更此設定，並允許具備參與者角色的使用者使用此連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="c582a-139">參與者無法查看或編輯該連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="c582a-140">只有在建立匯出時，他們能看到顯示名稱及其類型。</span><span class="sxs-lookup"><span data-stu-id="c582a-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="c582a-141">透過共用連接，您可以讓參與者使用連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="c582a-142">當參與者設定匯出時，會看到共用的連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="c582a-143">他們可以管理使用此特定連接的每個匯出。</span><span class="sxs-lookup"><span data-stu-id="c582a-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="c582a-144">您可以保留參與者已定義的匯出，並變更此設定。</span><span class="sxs-lookup"><span data-stu-id="c582a-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="c582a-145">編輯連接</span><span class="sxs-lookup"><span data-stu-id="c582a-145">Edit a connection</span></span>

1. <span data-ttu-id="c582a-146">移至 **管理** > **連接 (預覽版)**。</span><span class="sxs-lookup"><span data-stu-id="c582a-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="c582a-147">移至 **連結** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c582a-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="c582a-148">對要編輯的連接，選取其垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="c582a-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="c582a-149">選取 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="c582a-149">Select **Edit**.</span></span>

1. <span data-ttu-id="c582a-150">變更想要更新的值並選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="c582a-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="c582a-151">移除連接</span><span class="sxs-lookup"><span data-stu-id="c582a-151">Remove a connection</span></span>

<span data-ttu-id="c582a-152">如果要移除的連接用在擴充或匯出，必須先進行分離或移除。</span><span class="sxs-lookup"><span data-stu-id="c582a-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="c582a-153">移除對話方塊將引導您到相關的擴充或匯出。</span><span class="sxs-lookup"><span data-stu-id="c582a-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="c582a-154">分離的擴充和匯出會變成停用。</span><span class="sxs-lookup"><span data-stu-id="c582a-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="c582a-155">您可以在[擴充](enrichment-hub.md)或[匯出](export-destinations.md)頁面上新增另一個連接給它們，以重新啟動。</span><span class="sxs-lookup"><span data-stu-id="c582a-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="c582a-156">移至 **管理** > **連接 (預覽版)**。</span><span class="sxs-lookup"><span data-stu-id="c582a-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="c582a-157">移至 **連結** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c582a-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="c582a-158">對要移除的連接，選取其垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="c582a-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="c582a-159">從下拉式功能表中選取 **移除**。</span><span class="sxs-lookup"><span data-stu-id="c582a-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="c582a-160">確認對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="c582a-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="c582a-161">如果有擴充或匯出使用此連接，請選取按鈕，以查看正在使用此連接的功能。</span><span class="sxs-lookup"><span data-stu-id="c582a-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="c582a-162">**匯出：** 要移除該連接，您可以對匯出選擇移除或中斷連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="c582a-163">若要將匯出中斷連接，系統管理員可以使用 **中斷連接** 動作。</span><span class="sxs-lookup"><span data-stu-id="c582a-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="c582a-164">此動作可使用在選取單一和多個匯出。</span><span class="sxs-lookup"><span data-stu-id="c582a-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="c582a-165">中斷連接將保留匯出設定，但除非新增另一個連接至匯出，否則不會執行匯出。</span><span class="sxs-lookup"><span data-stu-id="c582a-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="c582a-166">**擴充：** 要移除該連接，您可以對擴充選擇移除或停用連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="c582a-167">當連接不再有其他相依性時，請回到 **管理** > **連結**，然後嘗試再次移除該連接。</span><span class="sxs-lookup"><span data-stu-id="c582a-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="c582a-168">請選取 **刪除**，來確認刪除。</span><span class="sxs-lookup"><span data-stu-id="c582a-168">To confirm the deletion select **Remove**.</span></span>

