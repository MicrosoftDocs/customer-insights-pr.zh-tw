---
title: LiveRamp  連接器
description: 了解如何設定連接並匯出至 LiveRamp。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760317"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="ccb49-103">將客戶細分匯出至 LiveRamp&reg; (預覽版)</span><span class="sxs-lookup"><span data-stu-id="ccb49-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="ccb49-104">在 LiveRamp 中啟動您的資料，便能連接超過 500 多個平台，橫跨數位、社群和電視等領域。</span><span class="sxs-lookup"><span data-stu-id="ccb49-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="ccb49-105">在 LiveRamp 中使用您的資料，將廣告行銷活動設為目標、抑制和個人化。</span><span class="sxs-lookup"><span data-stu-id="ccb49-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ccb49-106">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="ccb49-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="ccb49-107">您需要 LiveRamp 訂閱才能使用此連接器。</span><span class="sxs-lookup"><span data-stu-id="ccb49-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="ccb49-108">若要取得訂閱，請直接[與 LiveRamp 連絡](https://liveramp.com/contact/)。</span><span class="sxs-lookup"><span data-stu-id="ccb49-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="ccb49-109">[進一步了解 LiveRamp 上線](https://liveramp.com/our-platform/data-onboarding/)。</span><span class="sxs-lookup"><span data-stu-id="ccb49-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="ccb49-110">設定與 LiveRamp 的連接</span><span class="sxs-lookup"><span data-stu-id="ccb49-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="ccb49-111">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="ccb49-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ccb49-112">選取 **新增連接**，然後選擇 **LiveRamp** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="ccb49-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="ccb49-113">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="ccb49-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ccb49-114">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="ccb49-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ccb49-115">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="ccb49-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ccb49-116">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="ccb49-116">Choose who can use this connection.</span></span> <span data-ttu-id="ccb49-117">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="ccb49-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ccb49-118">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="ccb49-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ccb49-119">為您的 LiveRamp Secure FTP (SFTP) 帳戶提供 **使用者名稱** 和 **密碼**。</span><span class="sxs-lookup"><span data-stu-id="ccb49-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="ccb49-120">這些認證可能與您的 LiveRamp 上線認證不同。</span><span class="sxs-lookup"><span data-stu-id="ccb49-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="ccb49-121">選取 **驗證** 以測試與 LiveRamp 的連接。</span><span class="sxs-lookup"><span data-stu-id="ccb49-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="ccb49-122">驗證成功後，選取 **我同意** 核取方塊，表示您對 **資料隱私權和合規性** 的同意。</span><span class="sxs-lookup"><span data-stu-id="ccb49-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="ccb49-123">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="ccb49-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ccb49-124">設定匯出</span><span class="sxs-lookup"><span data-stu-id="ccb49-124">Configure an export</span></span>

<span data-ttu-id="ccb49-125">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="ccb49-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ccb49-126">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="ccb49-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ccb49-127">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="ccb49-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ccb49-128">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="ccb49-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ccb49-129">在 **匯出的連結** 欄位中，在 LiveRamp 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="ccb49-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="ccb49-130">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="ccb49-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ccb49-131">在 **選擇金鑰識別元** 欄位中，選取 **電子郵件**、**名稱和位址** 或 **電話** 以傳送至 LiveRamp 進行身分識別解析。</span><span class="sxs-lookup"><span data-stu-id="ccb49-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ccb49-132">![LiveRamp 連接器與屬性對應](media/export-liveramp-segments.png "LiveRamp 連接器與屬性對應")</span><span class="sxs-lookup"><span data-stu-id="ccb49-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="ccb49-133">從您的統一客戶實體中對應所選金鑰識別元的相應屬性。</span><span class="sxs-lookup"><span data-stu-id="ccb49-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="ccb49-134">選取 **新增屬性** 對應更多屬性，以傳送至 LiveRamp。</span><span class="sxs-lookup"><span data-stu-id="ccb49-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="ccb49-135">傳送至 LiveRamp 的金鑰識別元屬性越多，您獲得的對應率可能會越高。</span><span class="sxs-lookup"><span data-stu-id="ccb49-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="ccb49-136">選取您要匯出至 LiveRamp 的區段。</span><span class="sxs-lookup"><span data-stu-id="ccb49-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="ccb49-137">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="ccb49-137">Select **Save**.</span></span>

<span data-ttu-id="ccb49-138">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="ccb49-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ccb49-139">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="ccb49-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ccb49-140">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="ccb49-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ccb49-141">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="ccb49-141">Data privacy and compliance</span></span>

<span data-ttu-id="ccb49-142">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Liveramp 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="ccb49-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ccb49-143">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Liveramp 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="ccb49-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ccb49-144">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="ccb49-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ccb49-145">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ccb49-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
