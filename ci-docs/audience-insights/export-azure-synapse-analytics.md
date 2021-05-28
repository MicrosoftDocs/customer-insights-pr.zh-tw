---
title: 將 Customer Insights 資料匯出至 Azure Synapse Analytics
description: 了解如何設定連接到 Azure Synapse Analytics。
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977367"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="7898b-103">匯出至 Azure Synapse Analytics (預覽版)</span><span class="sxs-lookup"><span data-stu-id="7898b-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="7898b-104">Azure Synapse 是一項分析服務，減少了深入解析跨資料倉儲和巨量資料系統所需要的時間。</span><span class="sxs-lookup"><span data-stu-id="7898b-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="7898b-105">您可以在 [Azure Synapse](/azure/synapse-analytics/overview-what-is) 中內嵌和使用您的 Customer Insights 資料。</span><span class="sxs-lookup"><span data-stu-id="7898b-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7898b-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="7898b-106">Prerequisites</span></span>

<span data-ttu-id="7898b-107">若要設定從 Customer Insights 到 Azure Synapse 的連接，必須符合下列先決條件。</span><span class="sxs-lookup"><span data-stu-id="7898b-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="7898b-108">請務必根據說明來設定全部的 **角色指派**。</span><span class="sxs-lookup"><span data-stu-id="7898b-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="7898b-109">Customer Insights 的先決條件</span><span class="sxs-lookup"><span data-stu-id="7898b-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="7898b-110">您必須具備對象見解中 **系統管理員** 的角色。</span><span class="sxs-lookup"><span data-stu-id="7898b-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="7898b-111">深入瞭解如何[設定對象見解中的使用者權限](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="7898b-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="7898b-112">在 Azure 中：</span><span class="sxs-lookup"><span data-stu-id="7898b-112">In Azure:</span></span> 

- <span data-ttu-id="7898b-113">啟用中的 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="7898b-113">An active Azure subscription.</span></span>

- <span data-ttu-id="7898b-114">如果使用新的 Azure Data Lake Storage Gen2 帳戶，*對象見解的服務主體* 需要 **儲存 Blob 資料參與者** 權限。</span><span class="sxs-lookup"><span data-stu-id="7898b-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="7898b-115">瞭解更多有關 [以 Azure 服務主體連接至 Azure Data Lake Storage Gen2 帳戶，以獲得對象見解](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="7898b-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="7898b-116">Data Lake Storage Gen2 **必須** 已啟用的[階層命名空間](/azure/storage/blobs/data-lake-storage-namespace)。</span><span class="sxs-lookup"><span data-stu-id="7898b-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="7898b-117">在 Azure Synapse 工作區所在的資源群組，*服務主體* 和 *對象見解的使用者* 至少要被指派 **讀者** 權限。</span><span class="sxs-lookup"><span data-stu-id="7898b-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="7898b-118">如需詳細資訊，請參閱[使用 Azure 入口網站指派 Azure 角色](/azure/role-based-access-control/role-assignments-portal)。</span><span class="sxs-lookup"><span data-stu-id="7898b-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="7898b-119">在連結至 Azure Synapse 工作區且為資料所在的 Azure Data Lake Storage Gen2 帳戶，*使用者* 需要有 **儲存體 Blob 資料參與者** 權限。</span><span class="sxs-lookup"><span data-stu-id="7898b-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="7898b-120">深入瞭解如何[使用 Azure 入口網站指派 Azure 角色，以取得 blob 和佇列資料的存取權](/azure/storage/common/storage-auth-aad-rbac-portal)，以及[儲存體 blob 資料參與者權限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。</span><span class="sxs-lookup"><span data-stu-id="7898b-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="7898b-121">在連結至 Azure Synapse 工作區且為資料所在的 Azure Data Lake Storage Gen2 帳戶中，*[Azure Synapse 工作區受管理的身分識別](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 需要 **儲存體 Blob 資料參與者** 權限。</span><span class="sxs-lookup"><span data-stu-id="7898b-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="7898b-122">深入瞭解如何[使用 Azure 入口網站指派 Azure 角色，以取得 blob 和佇列資料的存取權](/azure/storage/common/storage-auth-aad-rbac-portal)，以及[儲存體 blob 資料參與者權限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。</span><span class="sxs-lookup"><span data-stu-id="7898b-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="7898b-123">在 Azure Synapse 工作區中，*觀眾見解的服務主體* 需要被指派 **Synapse 系統管理員** 角色。</span><span class="sxs-lookup"><span data-stu-id="7898b-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="7898b-124">如需詳細資訊，請參閱[如何設定 Synapse 工作區的存取控制](/azure/synapse-analytics/security/how-to-set-up-access-control)。</span><span class="sxs-lookup"><span data-stu-id="7898b-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="7898b-125">設定連線並輸出至 Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="7898b-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="7898b-126">設定連接</span><span class="sxs-lookup"><span data-stu-id="7898b-126">Configure a connection</span></span>

1. <span data-ttu-id="7898b-127">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="7898b-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7898b-128">選取 **新增連接**，然後選擇 **Azure Synapse Analytics**，或在 **Azure Synapse Analytics** 圖格中選取 **設定**，來設定此連接。</span><span class="sxs-lookup"><span data-stu-id="7898b-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="7898b-129">在顯示名稱中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="7898b-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="7898b-130">連接的名稱與類型說明此連接。</span><span class="sxs-lookup"><span data-stu-id="7898b-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="7898b-131">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="7898b-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7898b-132">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="7898b-132">Choose who can use this connection.</span></span> <span data-ttu-id="7898b-133">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="7898b-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7898b-134">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="7898b-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7898b-135">選取或搜尋您要在其中使用 Customer Insights 資料的訂閱。</span><span class="sxs-lookup"><span data-stu-id="7898b-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="7898b-136">選取訂閱之後，您也可以選取 **工作區**、**儲存體帳戶** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="7898b-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="7898b-137">選取 **儲存** 以儲存連結。</span><span class="sxs-lookup"><span data-stu-id="7898b-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="7898b-138">設定匯出</span><span class="sxs-lookup"><span data-stu-id="7898b-138">Configure an export</span></span>

<span data-ttu-id="7898b-139">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="7898b-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7898b-140">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="7898b-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7898b-141">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="7898b-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7898b-142">若要建立新匯出，請選取 **新增匯出**。</span><span class="sxs-lookup"><span data-stu-id="7898b-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="7898b-143">在 **匯出連結** 的欄位中，在 **Azure Synapse Analytics** 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="7898b-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="7898b-144">如果您看不到此區段名稱，代表沒有此類型的[連接](connections.md)可供您使用。</span><span class="sxs-lookup"><span data-stu-id="7898b-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="7898b-145">提供可辨識的 **顯示名稱** 給匯出並提供 **資料庫名稱**。</span><span class="sxs-lookup"><span data-stu-id="7898b-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="7898b-146">選取您要匯出到的 Azure Synapse Analytics 的實體。</span><span class="sxs-lookup"><span data-stu-id="7898b-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="7898b-147">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="7898b-147">Select **Save**.</span></span>

<span data-ttu-id="7898b-148">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="7898b-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7898b-149">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="7898b-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7898b-150">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="7898b-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="7898b-151">更新匯出</span><span class="sxs-lookup"><span data-stu-id="7898b-151">Update an export</span></span>

1. <span data-ttu-id="7898b-152">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="7898b-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7898b-153">在您想要更新的匯出上選取 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="7898b-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="7898b-154">從選項中 **新增** 或 **移除** 實體。</span><span class="sxs-lookup"><span data-stu-id="7898b-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="7898b-155">從選項中移除實體，並不會從 Synapse Analytics 資料庫中刪除它們。</span><span class="sxs-lookup"><span data-stu-id="7898b-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="7898b-156">不過，之後的資料重新整理並不會更新該資料庫中已移除的實體。</span><span class="sxs-lookup"><span data-stu-id="7898b-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="7898b-157">**變更資料庫名稱** 會建立新的 Synapse Analytics 資料庫。</span><span class="sxs-lookup"><span data-stu-id="7898b-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="7898b-158">在之後的重新整理，之前設定名稱的資料庫將不會收到任何更新。</span><span class="sxs-lookup"><span data-stu-id="7898b-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
