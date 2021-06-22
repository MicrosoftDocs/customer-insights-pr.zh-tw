---
title: 將 Customer Insights 資料匯出至 Campaign Monitor
description: 了解如何設定連接並匯出至 Campaign Monitor。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124171"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="fd10e-103">將客戶細分匯出至 Campaign Monitor (預覽版)</span><span class="sxs-lookup"><span data-stu-id="fd10e-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="fd10e-104">將整合客戶個人資料的客戶細分匯出至 Campaign Monitor，並用於行銷活動。</span><span class="sxs-lookup"><span data-stu-id="fd10e-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd10e-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="fd10e-105">Prerequisites</span></span>

-   <span data-ttu-id="fd10e-106">您擁有一個 [Campaign Monitor 帳戶](https://www.campaignmonitor.com/)及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="fd10e-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fd10e-107">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="fd10e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="fd10e-108">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="fd10e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fd10e-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="fd10e-109">Known limitations</span></span>

- <span data-ttu-id="fd10e-110">每筆匯出中您最多可以將 1 百萬筆個人資料匯出至 Campaign Monitor。</span><span class="sxs-lookup"><span data-stu-id="fd10e-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="fd10e-111">僅限於客戶細分可被匯出至 Campaign Monitor。</span><span class="sxs-lookup"><span data-stu-id="fd10e-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="fd10e-112">將最多 1 百萬筆個人資料匯出至 Campaign Monitor 可能需要花費 20 分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="fd10e-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="fd10e-113">您可以匯出至 Campaign Monitor 的個人資料數量與 Campaign Monitor 的合約有關且受到其限制。</span><span class="sxs-lookup"><span data-stu-id="fd10e-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="fd10e-114">設定到 Campaign Monitor 的連接</span><span class="sxs-lookup"><span data-stu-id="fd10e-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="fd10e-115">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="fd10e-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fd10e-116">選取 **新增連接**，然後選擇 **Campaign Monitor** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="fd10e-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="fd10e-117">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="fd10e-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fd10e-118">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="fd10e-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fd10e-119">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="fd10e-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fd10e-120">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="fd10e-120">Choose who can use this connection.</span></span> <span data-ttu-id="fd10e-121">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="fd10e-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="fd10e-122">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="fd10e-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fd10e-123">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="fd10e-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fd10e-124">選取 **連接** 來初始化與 Campaign Monitor 的連接。</span><span class="sxs-lookup"><span data-stu-id="fd10e-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="fd10e-125">選取 **與 Campaign Monitor 驗證**，並提供管理認證給 Campaign Monitor。</span><span class="sxs-lookup"><span data-stu-id="fd10e-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="fd10e-126">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="fd10e-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fd10e-127">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="fd10e-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="fd10e-128">設定匯出</span><span class="sxs-lookup"><span data-stu-id="fd10e-128">Configure an export</span></span>

<span data-ttu-id="fd10e-129">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="fd10e-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="fd10e-130">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="fd10e-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fd10e-131">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="fd10e-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fd10e-132">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="fd10e-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="fd10e-133">在 **匯出的連結** 欄位中，在 Campaign Monitor 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="fd10e-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="fd10e-134">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="fd10e-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="fd10e-135">[**Campaign Monitor 清單識別碼**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="fd10e-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="fd10e-136">在 Campaign Monitor 的 **帳戶設定** 中[生成 API 金鑰](https://www.campaignmonitor.com/api/getting-started/)，然後再查看 API 清單識別碼。</span><span class="sxs-lookup"><span data-stu-id="fd10e-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="fd10e-137">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="fd10e-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fd10e-138">這必須匯出客戶細分到 Campaign Monitor。</span><span class="sxs-lookup"><span data-stu-id="fd10e-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="fd10e-139">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="fd10e-139">Select **Save**.</span></span>

<span data-ttu-id="fd10e-140">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="fd10e-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fd10e-141">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="fd10e-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fd10e-142">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="fd10e-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fd10e-143">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="fd10e-143">Data privacy and compliance</span></span>

<span data-ttu-id="fd10e-144">當您啟用 Dynamics 365 Customer Insights 將資料傳輸至 Campaign Monitor 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="fd10e-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fd10e-145">Microsoft 將會在您的指示下傳送這類資料，但是您必須負責確保 Campaign Monitor 符合您可能會承擔的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="fd10e-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fd10e-146">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="fd10e-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="fd10e-147">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="fd10e-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
