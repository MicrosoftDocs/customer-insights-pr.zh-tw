---
title: 匯出 Customer Insights 資料到 SFTP 主機
description: 了解如何設定與 SFTP 主機的連接。
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267988"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="7c521-103">適用於 SFTP 的連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="7c521-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="7c521-104">將您的客戶資料匯出到安全檔案傳輸通訊協定 (SFTP) 主機，以便在協力廠商應用程式中使用您的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="7c521-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7c521-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="7c521-105">Prerequisites</span></span>

- <span data-ttu-id="7c521-106">SFTP 主機的可存取程度及對應的認證。</span><span class="sxs-lookup"><span data-stu-id="7c521-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="7c521-107">連線至 SFTP</span><span class="sxs-lookup"><span data-stu-id="7c521-107">Connect to SFTP</span></span>

1. <span data-ttu-id="7c521-108">移至 **管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="7c521-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7c521-109">在 **SFTP** 底下選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="7c521-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="7c521-110">在 **顯示名稱** 欄位中，為目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="7c521-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7c521-111">提供 **使用者名稱**、**密碼**、 **主機名稱** 和 **匯出資料夾** 給您的 SFTP 帳戶。</span><span class="sxs-lookup"><span data-stu-id="7c521-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="7c521-112">選取 **驗證** 以測試連接。</span><span class="sxs-lookup"><span data-stu-id="7c521-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="7c521-113">在驗證成功後，選擇要以 **Gzipped** 或 **解壓縮** 的方式匯出資料，並選取匯出後檔案的 **欄位分隔符號**。</span><span class="sxs-lookup"><span data-stu-id="7c521-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="7c521-114">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="7c521-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7c521-115">選取 **下一步** 以開始設定匯出。</span><span class="sxs-lookup"><span data-stu-id="7c521-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="7c521-116">設定匯出</span><span class="sxs-lookup"><span data-stu-id="7c521-116">Configure the export</span></span>

1. <span data-ttu-id="7c521-117">選取您要匯出的實體 (例如客戶細分)。</span><span class="sxs-lookup"><span data-stu-id="7c521-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7c521-118">在匯出時最，選取的每個實體多會有五個匯出檔。</span><span class="sxs-lookup"><span data-stu-id="7c521-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="7c521-119">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="7c521-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7c521-120">匯出資料</span><span class="sxs-lookup"><span data-stu-id="7c521-120">Export the data</span></span>

<span data-ttu-id="7c521-121">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="7c521-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7c521-122">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="7c521-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7c521-123">已知限制</span><span class="sxs-lookup"><span data-stu-id="7c521-123">Known limitations</span></span>

- <span data-ttu-id="7c521-124">匯出執行時間依您的系統效能而定。</span><span class="sxs-lookup"><span data-stu-id="7c521-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="7c521-125">我們建議伺服器最小配置為兩個 CPU 核心和 1 Gb 的記憶體。</span><span class="sxs-lookup"><span data-stu-id="7c521-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="7c521-126">匯出最多 1 億份客戶設定檔的實體時，在使用兩個 CPU 核心和 1 Gb 記憶體的最少建議配置時，可能需要 90 分鐘。</span><span class="sxs-lookup"><span data-stu-id="7c521-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7c521-127">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="7c521-127">Data privacy and compliance</span></span>

<span data-ttu-id="7c521-128">當您啟用 Dynamics 365 Customer Insights 將資料透過 SFTP 傳輸時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="7c521-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7c521-129">Microsoft 將依據您的指示傳輸此資料，但您須負責確保匯出目的地符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="7c521-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7c521-130">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="7c521-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7c521-131">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="7c521-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]