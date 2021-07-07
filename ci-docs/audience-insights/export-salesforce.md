---
title: 將 Customer Insights 資料匯出到 Salesforce Marketing Cloud
description: 了解如何設定連接並匯出到 Salesforce Marketing Cloud。
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314585"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="10cc9-103">匯出客戶細分和其他資料到 Salesforce Marketing Cloud (預覽版)</span><span class="sxs-lookup"><span data-stu-id="10cc9-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="10cc9-104">通過安全檔案傳輸協定 (SFTP) 位置匯出客戶資料，在 Salesforce Marketing Cloud 中使用它們。</span><span class="sxs-lookup"><span data-stu-id="10cc9-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="10cc9-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="10cc9-105">Prerequisites for connection</span></span>

- <span data-ttu-id="10cc9-106">可用的 SFTP 主機和相應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="10cc9-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="10cc9-107">如何為 Salesforce Marketing Cloud 設定 SFTP 位置</span><span class="sxs-lookup"><span data-stu-id="10cc9-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="10cc9-108">已知限制</span><span class="sxs-lookup"><span data-stu-id="10cc9-108">Known limitations</span></span>

- <span data-ttu-id="10cc9-109">匯出執行時間依您的系統效能而定。</span><span class="sxs-lookup"><span data-stu-id="10cc9-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="10cc9-110">我們建議伺服器最小配置為兩個 CPU 核心和 1 Gb 的記憶體。</span><span class="sxs-lookup"><span data-stu-id="10cc9-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="10cc9-111">使用推薦的最低配置時，輸出多達 1 億筆客戶個人資料的實體可能需要 90 分鐘。</span><span class="sxs-lookup"><span data-stu-id="10cc9-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="10cc9-112">設置與 Salesforce Marketing Cloud 的連接</span><span class="sxs-lookup"><span data-stu-id="10cc9-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="10cc9-113">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="10cc9-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="10cc9-114">選擇 **新增連接** 並選擇 **Salesforce Marketing Cloud** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="10cc9-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="10cc9-115">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="10cc9-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="10cc9-116">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="10cc9-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="10cc9-117">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="10cc9-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="10cc9-118">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="10cc9-118">Choose who can use this connection.</span></span> <span data-ttu-id="10cc9-119">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="10cc9-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="10cc9-120">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="10cc9-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="10cc9-121">提供 **使用者名稱**、**密碼**、 **主機名稱** 和 **匯出資料夾** 給您的 SFTP 帳戶。</span><span class="sxs-lookup"><span data-stu-id="10cc9-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="10cc9-122">選取 **驗證** 以測試連接。</span><span class="sxs-lookup"><span data-stu-id="10cc9-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="10cc9-123">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="10cc9-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="10cc9-124">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="10cc9-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="10cc9-125">設定匯出</span><span class="sxs-lookup"><span data-stu-id="10cc9-125">Configure an export</span></span>

<span data-ttu-id="10cc9-126">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="10cc9-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="10cc9-127">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="10cc9-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="10cc9-128">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="10cc9-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="10cc9-129">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="10cc9-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="10cc9-130">在 **匯出的連結** 欄位中，在 SFTP 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="10cc9-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="10cc9-131">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="10cc9-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="10cc9-132">選擇是否要以 **Gzipped** 或 **解壓縮** 方式匯出您的資料，以及匯出檔案的 **欄位分隔符號**。</span><span class="sxs-lookup"><span data-stu-id="10cc9-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="10cc9-133">選取您要匯出的實體 (例如客戶細分)。</span><span class="sxs-lookup"><span data-stu-id="10cc9-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="10cc9-134">匯出時，每個選取的實體會分割成最多五個輸出檔。</span><span class="sxs-lookup"><span data-stu-id="10cc9-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="10cc9-135">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="10cc9-135">Select **Save**.</span></span>

<span data-ttu-id="10cc9-136">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="10cc9-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="10cc9-137">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="10cc9-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="10cc9-138">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="10cc9-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="10cc9-139">將 Customer Insights 資料從 SFTP 位置匯入到 Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="10cc9-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="10cc9-140">建立 [Salesforce Marketing Cloud 中的資料擴充](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)，以便從 SFTP 位置匯入 Customer Insights 資料檔案。</span><span class="sxs-lookup"><span data-stu-id="10cc9-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="10cc9-141">[將來自 SFTP 位置的資料匯入 ](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) 到 Salesforce Marketing Cloud 資料擴充。</span><span class="sxs-lookup"><span data-stu-id="10cc9-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="10cc9-142">設定自動化，將資料匯入資料擴充。</span><span class="sxs-lookup"><span data-stu-id="10cc9-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="10cc9-143">了解有關[檔案卸除自動化和排程自動化](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)。</span><span class="sxs-lookup"><span data-stu-id="10cc9-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="10cc9-144">定義 [檔案卸除自動化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5)或[排程自動化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)。</span><span class="sxs-lookup"><span data-stu-id="10cc9-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="10cc9-145">這是 [SFTP 自動化](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)的範例。</span><span class="sxs-lookup"><span data-stu-id="10cc9-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="10cc9-146">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="10cc9-146">Data privacy and compliance</span></span>

<span data-ttu-id="10cc9-147">當您啟用 Dynamics 365 Customer Insights 將資料透過 SFTP 傳輸時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="10cc9-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="10cc9-148">Microsoft 將依據您的指示傳輸此資料，但您須負責確保匯出目的地符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="10cc9-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="10cc9-149">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="10cc9-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="10cc9-150">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="10cc9-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
