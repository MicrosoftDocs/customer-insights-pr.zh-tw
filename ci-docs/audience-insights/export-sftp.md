---
title: 匯出 Customer Insights 資料到 SFTP 主機
description: 了解如何設定與 SFTP 主機的連接。
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643493"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="b0e6b-103">適用於 SFTP 的連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="b0e6b-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="b0e6b-104">將您的客戶資料匯出到安全檔案傳輸通訊協定 (SFTP) 主機，以便在協力廠商應用程式中使用您的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0e6b-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="b0e6b-105">Prerequisites</span></span>

- <span data-ttu-id="b0e6b-106">SFTP 主機和對應認證的可用性。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="b0e6b-107">連線至 SFTP</span><span class="sxs-lookup"><span data-stu-id="b0e6b-107">Connect to SFTP</span></span>

1. <span data-ttu-id="b0e6b-108">移至 **管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b0e6b-109">在 **SFTP** 底下選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="b0e6b-110">在 **顯示名稱** 欄位中，為目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b0e6b-111">為您的 SFTP 帳戶提供 **使用者名稱**、**密碼** 和 **主機名稱**。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="b0e6b-112">範例：如果您的 SFTP 伺服器的根資料夾是 /root/folder，而您想要將資料匯出到 /root/folder/ci_export_destination_folder 中，則主機應為 sftp://<server_address>/ci_export_destination_folder。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="b0e6b-113">選取 **驗證** 以測試連接。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="b0e6b-114">成功驗證後，選擇要將資料匯出為 **壓縮** 還是 **解壓縮**，並選取所匯出檔案的 **欄位分隔符號**。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="b0e6b-115">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b0e6b-116">選取 **下一步** 以開始設定匯出。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="b0e6b-117">設定連接</span><span class="sxs-lookup"><span data-stu-id="b0e6b-117">Configure the connection</span></span>

1. <span data-ttu-id="b0e6b-118">選取要匯出的 **客戶屬性**。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="b0e6b-119">您可以匯出一個或多個屬性。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="b0e6b-120">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-120">Select **Next**.</span></span>

1. <span data-ttu-id="b0e6b-121">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="b0e6b-122">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b0e6b-123">匯出資料</span><span class="sxs-lookup"><span data-stu-id="b0e6b-123">Export the data</span></span>

<span data-ttu-id="b0e6b-124">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b0e6b-125">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b0e6b-126">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="b0e6b-126">Data privacy and compliance</span></span>

<span data-ttu-id="b0e6b-127">當您啟用 Dynamics 365 Customer Insights 將資料透過 SFTP 傳輸時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b0e6b-128">Microsoft 將依據您的指示傳輸此資料，但您須負責確保匯出目的地符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b0e6b-129">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b0e6b-130">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b0e6b-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
