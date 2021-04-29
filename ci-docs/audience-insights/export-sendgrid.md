---
title: 匯出 Customer Insights 資料到 SendGrid
description: 了解如何設定連接並匯出至 SendGrid。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759755"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="3605c-103">將客戶細分匯出至 SendGrid (預覽版)</span><span class="sxs-lookup"><span data-stu-id="3605c-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="3605c-104">將整合客戶設定檔的客戶細分匯出至 SendGrid 聯絡人清單，並在 SendGrid 中用來進行行銷活動和電子郵件行銷。</span><span class="sxs-lookup"><span data-stu-id="3605c-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="3605c-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="3605c-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="3605c-106">您具有 [SendGrid 帳戶](https://sendgrid.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="3605c-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3605c-107">有對應的識別碼且在 SendGrid 中有現有的聯絡人清單。</span><span class="sxs-lookup"><span data-stu-id="3605c-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="3605c-108">如需詳細資訊，請參閱 [SendGrid - 管理連絡人](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)。</span><span class="sxs-lookup"><span data-stu-id="3605c-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="3605c-109">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="3605c-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3605c-110">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="3605c-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3605c-111">已知限制</span><span class="sxs-lookup"><span data-stu-id="3605c-111">Known limitations</span></span>

- <span data-ttu-id="3605c-112">對 SendGrid 總計最多 100'000 份設定檔。</span><span class="sxs-lookup"><span data-stu-id="3605c-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="3605c-113">匯出到 SendGrid 被限制在客戶細分。</span><span class="sxs-lookup"><span data-stu-id="3605c-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="3605c-114">匯出多達 100'000 份設定檔到 SendGrid 需要花費幾個小時。</span><span class="sxs-lookup"><span data-stu-id="3605c-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="3605c-115">您可以匯出到 SendGrid 的設定檔數量是根據且受限於您與 SendGrid 的合約。</span><span class="sxs-lookup"><span data-stu-id="3605c-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="3605c-116">設定與 SendGrid 的連接</span><span class="sxs-lookup"><span data-stu-id="3605c-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="3605c-117">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="3605c-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3605c-118">選取 **新增連接**，然後選擇 **SendGrid** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="3605c-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="3605c-119">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="3605c-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3605c-120">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="3605c-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3605c-121">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="3605c-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3605c-122">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="3605c-122">Choose who can use this connection.</span></span> <span data-ttu-id="3605c-123">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="3605c-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3605c-124">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="3605c-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3605c-125">輸入您的 **SendGrid API 金鑰** [SendGrid API 金鑰 ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)。</span><span class="sxs-lookup"><span data-stu-id="3605c-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="3605c-126">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="3605c-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3605c-127">選取 **連接** 初始化與 SendGrid 的連接。</span><span class="sxs-lookup"><span data-stu-id="3605c-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="3605c-128">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="3605c-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3605c-129">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="3605c-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3605c-130">設定匯出</span><span class="sxs-lookup"><span data-stu-id="3605c-130">Configure an export</span></span>

<span data-ttu-id="3605c-131">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="3605c-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3605c-132">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="3605c-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3605c-133">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="3605c-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3605c-134">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="3605c-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3605c-135">在 **匯出的連結** 欄位中，在 SendGrid 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="3605c-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="3605c-136">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="3605c-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3605c-137">輸入您的 **[SendGrid 清單識別碼](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**。</span><span class="sxs-lookup"><span data-stu-id="3605c-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="3605c-138">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="3605c-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3605c-139">對其他可選欄位 (如 **名**、**姓**、**國家/地區**、**縣/市**、**市/鎮** 和 **郵遞區號**) 重複相同步驟。</span><span class="sxs-lookup"><span data-stu-id="3605c-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="3605c-140">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="3605c-140">Select the segments you want to export.</span></span> <span data-ttu-id="3605c-141">我們強烈 **建議您不要匯出總計超過 100'000 份客戶設定檔** 至 SendGrid。</span><span class="sxs-lookup"><span data-stu-id="3605c-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="3605c-142">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="3605c-142">Select **Save**.</span></span>

<span data-ttu-id="3605c-143">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="3605c-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3605c-144">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="3605c-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3605c-145">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="3605c-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3605c-146">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="3605c-146">Data privacy and compliance</span></span>

<span data-ttu-id="3605c-147">當您啟用 Dynamics 365 Customer Insights 傳輸資料給 SendGrid 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感資料 (如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="3605c-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3605c-148">Microsoft 將依據您的指示傳輸此資料，但您有責任確保 SendGrid 符合任何您承擔的隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="3605c-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="3605c-149">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="3605c-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3605c-150">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="3605c-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]