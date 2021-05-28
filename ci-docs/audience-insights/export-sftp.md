---
title: 匯出 Customer Insights 資料到 SFTP 主機
description: 了解如何設定連接並匯出至 SFTP 位置。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976883"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="bdf66-103">將客戶細分清單和其他資料匯出至 SFTP (預覽版)</span><span class="sxs-lookup"><span data-stu-id="bdf66-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="bdf66-104">要在協力廠商應用程式中使用客戶資料，請將客戶資料匯出至安全檔案傳輸通訊協定 (SFTP) 位置。</span><span class="sxs-lookup"><span data-stu-id="bdf66-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="bdf66-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="bdf66-105">Prerequisites for connection</span></span>

- <span data-ttu-id="bdf66-106">SFTP 主機的可存取程度及對應的認證。</span><span class="sxs-lookup"><span data-stu-id="bdf66-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bdf66-107">已知限制</span><span class="sxs-lookup"><span data-stu-id="bdf66-107">Known limitations</span></span>

- <span data-ttu-id="bdf66-108">匯出執行時間依您的系統效能而定。</span><span class="sxs-lookup"><span data-stu-id="bdf66-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="bdf66-109">我們建議伺服器最小配置為兩個 CPU 核心和 1 Gb 的記憶體。</span><span class="sxs-lookup"><span data-stu-id="bdf66-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="bdf66-110">匯出最多 1 億份客戶設定檔的實體時，在使用兩個 CPU 核心和 1 Gb 記憶體的最少建議配置時，可能需要 90 分鐘。</span><span class="sxs-lookup"><span data-stu-id="bdf66-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="bdf66-111">設定與 SFTP 的連線</span><span class="sxs-lookup"><span data-stu-id="bdf66-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="bdf66-112">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="bdf66-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bdf66-113">選取 **新增連接**，然後選擇 **SFTP** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="bdf66-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="bdf66-114">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="bdf66-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bdf66-115">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="bdf66-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bdf66-116">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="bdf66-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bdf66-117">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="bdf66-117">Choose who can use this connection.</span></span> <span data-ttu-id="bdf66-118">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="bdf66-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bdf66-119">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="bdf66-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bdf66-120">提供 **使用者名稱**、**密碼**、 **主機名稱** 和 **匯出資料夾** 給您的 SFTP 帳戶。</span><span class="sxs-lookup"><span data-stu-id="bdf66-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="bdf66-121">選取 **驗證** 以測試連接。</span><span class="sxs-lookup"><span data-stu-id="bdf66-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="bdf66-122">選擇是否要以 **Gzipped** 或 **解壓縮** 方式匯出您的資料，以及匯出檔案的 **欄位分隔符號**。</span><span class="sxs-lookup"><span data-stu-id="bdf66-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="bdf66-123">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="bdf66-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bdf66-124">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="bdf66-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bdf66-125">設定匯出</span><span class="sxs-lookup"><span data-stu-id="bdf66-125">Configure an export</span></span>

<span data-ttu-id="bdf66-126">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="bdf66-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bdf66-127">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="bdf66-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bdf66-128">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="bdf66-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bdf66-129">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="bdf66-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bdf66-130">在 **匯出的連結** 欄位中，在 SFTP 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="bdf66-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="bdf66-131">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="bdf66-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bdf66-132">選取您要匯出的實體 (例如客戶細分)。</span><span class="sxs-lookup"><span data-stu-id="bdf66-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bdf66-133">匯出時，每個選取的實體會分割成最多五個輸出檔。</span><span class="sxs-lookup"><span data-stu-id="bdf66-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="bdf66-134">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="bdf66-134">Select **Save**.</span></span>

<span data-ttu-id="bdf66-135">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="bdf66-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bdf66-136">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="bdf66-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bdf66-137">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="bdf66-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bdf66-138">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="bdf66-138">Data privacy and compliance</span></span>

<span data-ttu-id="bdf66-139">當您啟用 Dynamics 365 Customer Insights 將資料透過 SFTP 傳輸時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="bdf66-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bdf66-140">Microsoft 將依據您的指示傳輸此資料，但您須負責確保匯出目的地符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="bdf66-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bdf66-141">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="bdf66-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bdf66-142">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="bdf66-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
