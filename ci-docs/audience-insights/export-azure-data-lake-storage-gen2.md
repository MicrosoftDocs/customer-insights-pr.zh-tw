---
title: 匯出 Customer Insights 資料到 Azure Data Lake Storage Gen2
description: 瞭解如何設定與 Azure Data Lake Storage Gen2 的連接。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760041"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="ace8c-103">設定連線至 Azure Data Lake Storage Gen2 (預覽)</span><span class="sxs-lookup"><span data-stu-id="ace8c-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="ace8c-104">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="ace8c-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ace8c-105">選取 **新增連接**，然後選擇 **Azure Data Lake Gen 2** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="ace8c-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="ace8c-106">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="ace8c-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ace8c-107">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="ace8c-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ace8c-108">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="ace8c-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ace8c-109">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="ace8c-109">Choose who can use this connection.</span></span> <span data-ttu-id="ace8c-110">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="ace8c-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ace8c-111">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="ace8c-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ace8c-112">在您的 Azure Data Lake Storage Gen2 輸入 **帳戶名稱**、**帳戶金鑰** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="ace8c-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="ace8c-113">若要瞭解如何建立要可搭配 Azure Data Lake Storage Gen2 使用的儲存體帳戶，請參閱[建立儲存體帳戶](/azure/storage/blobs/create-data-lake-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="ace8c-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="ace8c-114">若要進一步了解 Azure Data Lake Gen2 帳戶名稱及帳戶金鑰，請參閱 [Azure 入口網站中的管理儲存體帳戶設定](/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="ace8c-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="ace8c-115">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="ace8c-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="ace8c-116">設定匯出</span><span class="sxs-lookup"><span data-stu-id="ace8c-116">Configure an export</span></span>

<span data-ttu-id="ace8c-117">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="ace8c-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ace8c-118">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="ace8c-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ace8c-119">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="ace8c-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ace8c-120">若要建立新匯出，請選取 **新增匯出**。</span><span class="sxs-lookup"><span data-stu-id="ace8c-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="ace8c-121">在 **匯出的連結** 欄位中，在 **Azure Data Lake** 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="ace8c-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="ace8c-122">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="ace8c-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ace8c-123">選取每個要匯出至此目的地之實體旁邊的方塊。</span><span class="sxs-lookup"><span data-stu-id="ace8c-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="ace8c-124">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="ace8c-124">Select **Save**.</span></span>

<span data-ttu-id="ace8c-125">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="ace8c-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ace8c-126">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="ace8c-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ace8c-127">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="ace8c-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="ace8c-128">匯出的資料會儲存在您設定的 Azure Data Lake Gen 2 儲存體容器中。</span><span class="sxs-lookup"><span data-stu-id="ace8c-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
