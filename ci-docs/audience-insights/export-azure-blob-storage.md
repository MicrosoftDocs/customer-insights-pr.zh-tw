---
title: 將 Customer Insights 資料匯出到 Azure Blob 儲存體
description: 了解如何設定連接並匯出至 Blob 儲存體。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760179"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="58e88-103">將客戶細分清單及其他資料匯出至 Azure Blob 儲存體 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="58e88-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="58e88-104">將您的 Customer Insights 資料儲存在 Blob 儲存體，或使用它將資料傳輸至其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="58e88-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="58e88-105">設定連線至 Blob 儲存體應用程式</span><span class="sxs-lookup"><span data-stu-id="58e88-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="58e88-106">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="58e88-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="58e88-107">選取 **新增連接**，然後選擇 **Azure Blob 儲存體** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="58e88-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="58e88-108">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="58e88-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="58e88-109">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="58e88-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="58e88-110">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="58e88-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="58e88-111">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="58e88-111">Choose who can use this connection.</span></span> <span data-ttu-id="58e88-112">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="58e88-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="58e88-113">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="58e88-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="58e88-114">為您的 Blob 儲存體帳戶輸入 **帳戶名稱**、**帳戶金鑰** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="58e88-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="58e88-115">若要進一步了解如何找到 Blob 儲存體帳戶名稱及帳戶金鑰，請參閱 [Azure 入口網站中的管理儲存體帳戶設定](/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="58e88-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="58e88-116">若要了解如何建立容器，請參閱[建立容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。</span><span class="sxs-lookup"><span data-stu-id="58e88-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="58e88-117">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="58e88-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="58e88-118">設定匯出</span><span class="sxs-lookup"><span data-stu-id="58e88-118">Configure an export</span></span>

<span data-ttu-id="58e88-119">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="58e88-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="58e88-120">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="58e88-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="58e88-121">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="58e88-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="58e88-122">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="58e88-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="58e88-123">在 **匯出的連結** 欄位中，在 Azure Blob 儲存體區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="58e88-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="58e88-124">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="58e88-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="58e88-125">選取每個要匯出至此目的地之實體旁邊的方塊。</span><span class="sxs-lookup"><span data-stu-id="58e88-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="58e88-126">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="58e88-126">Select **Save**.</span></span>

<span data-ttu-id="58e88-127">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="58e88-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="58e88-128">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="58e88-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="58e88-129">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="58e88-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="58e88-130">匯出的資料會儲存在您設定的 Blob 儲存體容器中。</span><span class="sxs-lookup"><span data-stu-id="58e88-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="58e88-131">容器中會自動建立下列資料夾路徑：</span><span class="sxs-lookup"><span data-stu-id="58e88-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="58e88-132">關於系統產生的來源實體和實體：`%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="58e88-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="58e88-133">範例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="58e88-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="58e88-134">匯出實體的 model.json 將在 %ExportDestinationName% 層級</span><span class="sxs-lookup"><span data-stu-id="58e88-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="58e88-135">範例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="58e88-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
