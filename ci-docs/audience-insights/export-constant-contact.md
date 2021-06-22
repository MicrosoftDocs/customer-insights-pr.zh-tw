---
title: 將 Customer Insights 資料匯出至 Constant Contact
description: 了解如何設定連接並匯出至 Constant Contact。
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124263"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="76138-103">將客戶細分匯出至 Constant Contact (預覽版)</span><span class="sxs-lookup"><span data-stu-id="76138-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="76138-104">將整合客戶個人資料的客戶細分匯出至 Constant Contact，並用於行銷活動。</span><span class="sxs-lookup"><span data-stu-id="76138-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="76138-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="76138-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="76138-106">您擁有一個 [Constant Contact 帳戶](https://www.constantcontact.com/account-home)及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="76138-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="76138-107">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="76138-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="76138-108">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="76138-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="76138-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="76138-109">Known limitations</span></span>

- <span data-ttu-id="76138-110">每筆匯出中您最多可以將 1 百萬筆個人資料匯出至 Constant Contact。</span><span class="sxs-lookup"><span data-stu-id="76138-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="76138-111">匯出到 Constant Contact 時，會被限制為客戶細分。</span><span class="sxs-lookup"><span data-stu-id="76138-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="76138-112">將最多 1 百萬筆個人資料匯出至 Constant Contact 可能需要花費 1 小時的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="76138-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="76138-113">您可以匯出至 Constant Contact 的個人資料數量與 Constant Contact 的合約有關且受到其限制。</span><span class="sxs-lookup"><span data-stu-id="76138-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="76138-114">設定與 Constant Contact 的連結</span><span class="sxs-lookup"><span data-stu-id="76138-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="76138-115">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="76138-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="76138-116">選取 **新增連接**，然後選擇 **Constant Contact** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="76138-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="76138-117">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="76138-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="76138-118">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="76138-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="76138-119">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="76138-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="76138-120">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="76138-120">Choose who can use this connection.</span></span> <span data-ttu-id="76138-121">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="76138-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="76138-122">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="76138-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="76138-123">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="76138-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="76138-124">選取 **連接** 來初始化與 Constant Contact 的連接。</span><span class="sxs-lookup"><span data-stu-id="76138-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="76138-125">選取 **與 AdRoll 驗證**，並提供系統管理員認證給 Constant Contact。</span><span class="sxs-lookup"><span data-stu-id="76138-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="76138-126">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="76138-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="76138-127">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="76138-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="76138-128">設定匯出</span><span class="sxs-lookup"><span data-stu-id="76138-128">Configure an export</span></span>

<span data-ttu-id="76138-129">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="76138-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="76138-130">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="76138-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="76138-131">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="76138-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="76138-132">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="76138-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="76138-133">在 **匯出的連結** 欄位中，在 Constant Contact 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="76138-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="76138-134">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="76138-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="76138-135">輸入您的 [**Constant Contact 清單識別碼**](https://app.constantcontact.com/pages/contacts/ui#lists)。</span><span class="sxs-lookup"><span data-stu-id="76138-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="76138-136">在 Constant Contact 中打開清單，以尋找 URL 中的清單識別碼。</span><span class="sxs-lookup"><span data-stu-id="76138-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="76138-137">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="76138-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="76138-138">這必須匯出客戶細分到 Constant Contact。</span><span class="sxs-lookup"><span data-stu-id="76138-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="76138-139">或者將 名字 和 姓氏 匯出為其他欄位，以建立更多個人化電子郵件。</span><span class="sxs-lookup"><span data-stu-id="76138-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="76138-140">選取 **新增屬性** 對應這些欄位。</span><span class="sxs-lookup"><span data-stu-id="76138-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="76138-141">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="76138-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="76138-142">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="76138-142">Select **Save**.</span></span>

<span data-ttu-id="76138-143">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="76138-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="76138-144">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="76138-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="76138-145">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="76138-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="76138-146">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="76138-146">Data privacy and compliance</span></span>

<span data-ttu-id="76138-147">當您啟用 Dynamics 365 Customer Insights 將資料傳輸至 Constant Contact 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="76138-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="76138-148">Microsoft 將會在您的指示下傳送這類資料，但是您必須負責確保 Constant Contact 符合您可能會承擔的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="76138-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="76138-149">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="76138-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="76138-150">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="76138-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
