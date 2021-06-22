---
title: 匯出 Customer Insights 資料到 Mailchimp
description: 了解如何設定連接並匯出至 Mailchimp。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124217"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="ee062-103">將客戶細分匯出至 Mailchimp (預覽版)</span><span class="sxs-lookup"><span data-stu-id="ee062-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="ee062-104">將統一客戶設定檔區段匯出到 Mailchimp，建立電子報和電子郵件行銷活動。</span><span class="sxs-lookup"><span data-stu-id="ee062-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ee062-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="ee062-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="ee062-106">您具有 [Mailchimp 帳戶](https://mailchimp.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="ee062-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ee062-107">Mailchimp 和對應的識別碼中有現有的對象。</span><span class="sxs-lookup"><span data-stu-id="ee062-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="ee062-108">如需詳細資訊，請參閱 [Mailchimp 對象](https://mailchimp.com/help/create-audience/)。</span><span class="sxs-lookup"><span data-stu-id="ee062-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="ee062-109">您有 [組態的區段](segments.md)</span><span class="sxs-lookup"><span data-stu-id="ee062-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="ee062-110">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="ee062-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ee062-111">已知限制</span><span class="sxs-lookup"><span data-stu-id="ee062-111">Known limitations</span></span>

- <span data-ttu-id="ee062-112">每個到 Mailchimp 的匯出最多可達 1 百萬個設定檔。</span><span class="sxs-lookup"><span data-stu-id="ee062-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="ee062-113">匯出到 Mailchimp 被限制為區段。</span><span class="sxs-lookup"><span data-stu-id="ee062-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="ee062-114">匯出含 1 百萬份個人資料的客戶細分可能需要花費三個小時的時間。</span><span class="sxs-lookup"><span data-stu-id="ee062-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="ee062-115">您可以匯出到 Mailchimp 的設定檔數量端賴且受限於您與 Mailchimp 的合約。</span><span class="sxs-lookup"><span data-stu-id="ee062-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="ee062-116">設定對 Mailchimp 的連接</span><span class="sxs-lookup"><span data-stu-id="ee062-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="ee062-117">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="ee062-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ee062-118">選取 **新增連接**，然後選擇 **Autopilot** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="ee062-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="ee062-119">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="ee062-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ee062-120">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="ee062-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ee062-121">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="ee062-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ee062-122">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="ee062-122">Choose who can use this connection.</span></span> <span data-ttu-id="ee062-123">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="ee062-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ee062-124">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="ee062-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ee062-125">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="ee062-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ee062-126">選取 **連接** 來初始化與 Mailchimp 的連接。</span><span class="sxs-lookup"><span data-stu-id="ee062-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="ee062-127">選取 **使用 Mailchimp 驗證** 並提供您的 Mailchimp 認證。</span><span class="sxs-lookup"><span data-stu-id="ee062-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="ee062-128">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="ee062-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ee062-129">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="ee062-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="ee062-130">設定連接器</span><span class="sxs-lookup"><span data-stu-id="ee062-130">Configure the connector</span></span>

<span data-ttu-id="ee062-131">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="ee062-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ee062-132">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="ee062-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ee062-133">移至 **資料**> **匯出**。</span><span class="sxs-lookup"><span data-stu-id="ee062-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="ee062-134">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="ee062-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ee062-135">在 **匯出的連結** 欄位中，在 Mailchimp 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="ee062-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="ee062-136">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="ee062-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ee062-137">輸入 **[Mailchimp 對象識別碼](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="ee062-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="ee062-138">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="ee062-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="ee062-139">或者，您可以匯出 **名** 和 **姓** 以建立更多的個人化電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ee062-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="ee062-140">選取 **新增屬性** 對應這些欄位。</span><span class="sxs-lookup"><span data-stu-id="ee062-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="ee062-141">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="ee062-141">Select the segments you want to export.</span></span> <span data-ttu-id="ee062-142">您總共最多可匯出 1 百萬個客戶設定檔到 Mailchimp。</span><span class="sxs-lookup"><span data-stu-id="ee062-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="ee062-143">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="ee062-143">Select **Save**.</span></span>

<span data-ttu-id="ee062-144">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="ee062-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ee062-145">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="ee062-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ee062-146">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="ee062-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ee062-147">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="ee062-147">Data privacy and compliance</span></span>

<span data-ttu-id="ee062-148">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Mailchimp 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="ee062-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ee062-149">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Mailchimp 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="ee062-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ee062-150">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="ee062-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ee062-151">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ee062-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
