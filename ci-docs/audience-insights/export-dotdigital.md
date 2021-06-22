---
title: 匯出 Customer Insights 資料到 DotDigital
description: 了解如何設定連接並匯出至 DotDigital。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124401"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="40a32-103">將客戶細分匯出至 DotDigital (預覽版)</span><span class="sxs-lookup"><span data-stu-id="40a32-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="40a32-104">將統一的客戶設定檔區段匯出到 DotDigital 通訊錄，並用於行銷活動、電子郵件行銷及使用 DotDigital 組建客戶區段。</span><span class="sxs-lookup"><span data-stu-id="40a32-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="40a32-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="40a32-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="40a32-106">您具有 [DotDigital 帳戶](https://dotdigital.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="40a32-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="40a32-107">DotDigital 和對應的識別碼中含有現有的通訊錄。</span><span class="sxs-lookup"><span data-stu-id="40a32-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="40a32-108">當您選取和打開通訊錄時，可以在 URL 找到識別碼。</span><span class="sxs-lookup"><span data-stu-id="40a32-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="40a32-109">如需詳細資訊，請見 [DotDigital 通訊錄](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)。</span><span class="sxs-lookup"><span data-stu-id="40a32-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="40a32-110">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="40a32-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="40a32-111">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="40a32-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="40a32-112">已知限制</span><span class="sxs-lookup"><span data-stu-id="40a32-112">Known limitations</span></span>

- <span data-ttu-id="40a32-113">每個到 DotDigital 的匯出最多可達 1 百萬個設定檔。</span><span class="sxs-lookup"><span data-stu-id="40a32-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="40a32-114">匯出到 DotDigital 被限制為區段。</span><span class="sxs-lookup"><span data-stu-id="40a32-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="40a32-115">因供應商端的限制，匯出總計 1 百萬個設定檔的區段最長會耗時 3 小時。</span><span class="sxs-lookup"><span data-stu-id="40a32-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="40a32-116">您可以匯出到 DotDigital 的設定檔數量端賴且受限於您與 DotDigital 的合約。</span><span class="sxs-lookup"><span data-stu-id="40a32-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="40a32-117">設定對 DotDigital 的連接</span><span class="sxs-lookup"><span data-stu-id="40a32-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="40a32-118">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="40a32-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="40a32-119">選取 **新增連接**，然後選擇 **DotDigital** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="40a32-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="40a32-120">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="40a32-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="40a32-121">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="40a32-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="40a32-122">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="40a32-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="40a32-123">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="40a32-123">Choose who can use this connection.</span></span> <span data-ttu-id="40a32-124">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="40a32-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="40a32-125">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="40a32-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="40a32-126">輸入您的 **DotDigital 使用者名稱和密碼**。</span><span class="sxs-lookup"><span data-stu-id="40a32-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="40a32-127">輸入您的 **[DotDigital 通訊錄 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**。</span><span class="sxs-lookup"><span data-stu-id="40a32-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="40a32-128">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="40a32-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="40a32-129">選取 **連接** 初始化到 DotDigital 的連接。</span><span class="sxs-lookup"><span data-stu-id="40a32-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="40a32-130">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="40a32-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="40a32-131">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="40a32-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="40a32-132">設定匯出</span><span class="sxs-lookup"><span data-stu-id="40a32-132">Configure an export</span></span>

<span data-ttu-id="40a32-133">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="40a32-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="40a32-134">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="40a32-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="40a32-135">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="40a32-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="40a32-136">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="40a32-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="40a32-137">在 **匯出的連結** 欄位中，在 DotDigital 客戶細分中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="40a32-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="40a32-138">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="40a32-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="40a32-139">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="40a32-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="40a32-140">針對其他可選欄位如 **名字**、**姓氏**、**全名**、**性別** 和 **貼文代碼** 重複相同步驟。</span><span class="sxs-lookup"><span data-stu-id="40a32-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="40a32-141">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="40a32-141">Select the segments you want to export.</span></span> <span data-ttu-id="40a32-142">您總共最多可匯出 1 百萬個客戶設定檔到 DotDigital。</span><span class="sxs-lookup"><span data-stu-id="40a32-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="40a32-143">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="40a32-143">Select **Save**.</span></span>

<span data-ttu-id="40a32-144">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="40a32-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="40a32-145">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="40a32-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="40a32-146">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="40a32-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="40a32-147">您現在可以在 [DotDigital 通訊錄](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) 中找到您的區段。</span><span class="sxs-lookup"><span data-stu-id="40a32-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="40a32-148">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="40a32-148">Data privacy and compliance</span></span>

<span data-ttu-id="40a32-149">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 DotDigital 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="40a32-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="40a32-150">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 DotDigital 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="40a32-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="40a32-151">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="40a32-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="40a32-152">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="40a32-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
