---
title: 匯出 Customer Insights 資料到 Azure Data Lake Storage Gen2
description: 瞭解如何設定與 Azure Data Lake Storage Gen2 的連接。
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477169"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="1ed42-103">適用 Azure Data Lake Storage Gen2 的連接器 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="1ed42-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="1ed42-104">將您的 Customer Insights 資料儲存在 Azure Data Lake Storage Gen2，或使用它將資料傳輸至其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="1ed42-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="1ed42-105">設定 Azure Data Lake Storage Gen2 的連接器</span><span class="sxs-lookup"><span data-stu-id="1ed42-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="1ed42-106">在對象見解中，前往 **系統管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="1ed42-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1ed42-107">請在 **Azure Data Lake Storage Gen2** 下方選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="1ed42-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="1ed42-108">在 **顯示名稱** 欄位中，為目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="1ed42-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1ed42-109">在您的 Azure Data Lake Storage Gen2 輸入 **帳戶名稱**、**帳戶金鑰** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="1ed42-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="1ed42-110">若要瞭解如何建立要可搭配 Azure Data Lake Storage Gen2 使用的儲存體帳戶，請參閱[建立儲存體帳戶](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="1ed42-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="1ed42-111">若要進一步瞭解如何尋找 Azure Data Lake Gen2 儲存體帳戶名稱及帳戶金鑰，請參閱 [在 Azure portal 中管理儲存體帳戶的設定](https://docs.microsoft.com/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="1ed42-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="1ed42-112">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1ed42-112">Select **Next**.</span></span>

1. <span data-ttu-id="1ed42-113">選取每個要匯出至此目的地之實體旁邊的方塊。</span><span class="sxs-lookup"><span data-stu-id="1ed42-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="1ed42-114">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="1ed42-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1ed42-115">匯出資料</span><span class="sxs-lookup"><span data-stu-id="1ed42-115">Export the data</span></span>

<span data-ttu-id="1ed42-116">您可以[視需要匯出資料](export-destinations.md#export-data-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="1ed42-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="1ed42-117">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="1ed42-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
