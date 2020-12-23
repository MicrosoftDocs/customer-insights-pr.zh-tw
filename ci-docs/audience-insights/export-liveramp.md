---
title: LiveRamp  連接器
description: 了解如何將資料匯出到 LiveRamp。
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667174"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="41739-103">LiveRamp&reg; 連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="41739-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="41739-104">在 LiveRamp 中啟用您的資料，與遍佈數位、社交和電視生態系統的 500 多個平台進行連接。</span><span class="sxs-lookup"><span data-stu-id="41739-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="41739-105">在 LiveRamp 中使用您的資料，將廣告行銷活動設為目標、抑制和個人化。</span><span class="sxs-lookup"><span data-stu-id="41739-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="41739-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="41739-106">Prerequisites</span></span>

- <span data-ttu-id="41739-107">您需要 LiveRamp 訂閱才能使用此連接器。</span><span class="sxs-lookup"><span data-stu-id="41739-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="41739-108">若要取得訂閱，請直接[與 LiveRamp 連絡](https://liveramp.com/contact/)。</span><span class="sxs-lookup"><span data-stu-id="41739-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="41739-109">[進一步了解 LiveRamp 上線](https://liveramp.com/our-platform/data-onboarding/)。</span><span class="sxs-lookup"><span data-stu-id="41739-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="41739-110">連接至 LiveRamp</span><span class="sxs-lookup"><span data-stu-id="41739-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="41739-111">在對象見解中，前往 **系統管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="41739-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="41739-112">在 **LiveRamp** 圖格中選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="41739-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="41739-113">在 **顯示名稱** 欄位中，為目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="41739-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="41739-114">為您的 LiveRamp Secure FTP (SFTP) 帳戶提供 **使用者名稱** 和 **密碼**。</span><span class="sxs-lookup"><span data-stu-id="41739-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="41739-115">這些認證可能與您的 LiveRamp 上線認證不同。</span><span class="sxs-lookup"><span data-stu-id="41739-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="41739-116">選取 **驗證** 以測試與 LiveRamp 的連接。</span><span class="sxs-lookup"><span data-stu-id="41739-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="41739-117">驗證成功後，選取 **我同意** 核取方塊，表示您對 **資料隱私權和合規性** 的同意。</span><span class="sxs-lookup"><span data-stu-id="41739-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="41739-118">選取 **下一步** 以設定 LiveRamp 連接器。</span><span class="sxs-lookup"><span data-stu-id="41739-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="41739-119">設定連接器</span><span class="sxs-lookup"><span data-stu-id="41739-119">Configure the connector</span></span>

1. <span data-ttu-id="41739-120">在 **選擇金鑰識別元** 欄位中，選取 **電子郵件**、**名稱和位址** 或 **電話** 以傳送至 LiveRamp 進行身分識別解析。</span><span class="sxs-lookup"><span data-stu-id="41739-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="41739-121">從您的統一客戶實體中對應所選金鑰識別元的相應屬性。</span><span class="sxs-lookup"><span data-stu-id="41739-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="41739-122">選取 **新增屬性**，以對應要傳送至 LiveRamp 的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="41739-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="41739-123">傳送至 LiveRamp 的金鑰識別元屬性越多，您獲得的對應率可能會越高。</span><span class="sxs-lookup"><span data-stu-id="41739-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="41739-124">選取您要匯出至 LiveRamp 的區段。</span><span class="sxs-lookup"><span data-stu-id="41739-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="41739-125">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="41739-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41739-126">![LiveRamp 連接器與屬性對應](media/export-liveramp-segments.png "LiveRamp 連接器與屬性對應")</span><span class="sxs-lookup"><span data-stu-id="41739-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="41739-127">匯出資料</span><span class="sxs-lookup"><span data-stu-id="41739-127">Export the data</span></span>

<span data-ttu-id="41739-128">如果所有匯出先決條件皆已齊備，就會立即開始匯出。</span><span class="sxs-lookup"><span data-stu-id="41739-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="41739-129">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="41739-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="41739-130">成功完成匯出之後，就可以登入 LiveRamp 上線來啟用和散發您的資料。</span><span class="sxs-lookup"><span data-stu-id="41739-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="41739-131">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="41739-131">Data privacy and compliance</span></span>

<span data-ttu-id="41739-132">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Liveramp 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="41739-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="41739-133">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Liveramp 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="41739-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="41739-134">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="41739-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="41739-135">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="41739-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>