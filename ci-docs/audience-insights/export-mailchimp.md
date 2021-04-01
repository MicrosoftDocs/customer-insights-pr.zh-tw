---
title: 匯出 Customer Insights 資料到 Mailchimp
description: 瞭解如何組態到 Mailchimp 的連接。
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598191"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="9dcf4-103">適用 Mailchimp 的連接器 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="9dcf4-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="9dcf4-104">將統一客戶設定檔區段匯出到 Mailchimp，建立電子報和電子郵件行銷活動。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9dcf4-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="9dcf4-105">Prerequisites</span></span>

-   <span data-ttu-id="9dcf4-106">您具有 [Mailchimp 帳戶](https://mailchimp.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9dcf4-107">Mailchimp 和對應的識別碼中有現有的對象。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="9dcf4-108">如需詳細資訊，請參閱 [Mailchimp 對象](https://mailchimp.com/help/create-audience/)。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="9dcf4-109">您有 [組態的區段](segments.md)</span><span class="sxs-lookup"><span data-stu-id="9dcf4-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="9dcf4-110">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="9dcf4-111">連線至 Mailchimp</span><span class="sxs-lookup"><span data-stu-id="9dcf4-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="9dcf4-112">移至 **管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9dcf4-113">請在 **Mailchimp** 下方選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="9dcf4-114">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9dcf4-115">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9dcf4-116">輸入您的 **[Mailchimp 對象識別碼](https://mailchimp.com/help/find-audience-id/)** 然後選取 **連接** 初始化到 Mailchimp 的連接。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="9dcf4-117">選取 **使用 Mailchimp 驗證** 並提供您的 Mailchimp 認證。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="9dcf4-118">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="匯出 Mailchimp 連接的螢幕截取畫面":::

1. <span data-ttu-id="9dcf4-120">選取 **下一步** 以設定匯出。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="9dcf4-121">設定連接器</span><span class="sxs-lookup"><span data-stu-id="9dcf4-121">Configure the connector</span></span>

1. <span data-ttu-id="9dcf4-122">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="9dcf4-123">或者將 **名字** 和 **姓氏** 匯出為其他欄位，以建立更多個人化電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="9dcf4-124">選取 **新增屬性** 對應這些欄位。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9dcf4-125">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-125">Select the segments you want to export.</span></span> <span data-ttu-id="9dcf4-126">您總共最多可匯出 1 百萬個客戶設定檔到 Mailchimp。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="選取要匯出到 Mailchimp 的欄位和區段":::

1. <span data-ttu-id="9dcf4-128">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9dcf4-129">匯出資料</span><span class="sxs-lookup"><span data-stu-id="9dcf4-129">Export the data</span></span>

<span data-ttu-id="9dcf4-130">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9dcf4-131">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9dcf4-132">在 Mailchimp 中，您現在可以在 [Mailchimp 對象](https://mailchimp.com/help/create-audience/) 下方找到您的區段。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9dcf4-133">已知限制</span><span class="sxs-lookup"><span data-stu-id="9dcf4-133">Known limitations</span></span>

- <span data-ttu-id="9dcf4-134">每個到 Mailchimp 的匯出最多可達 1 百萬個設定檔。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="9dcf4-135">匯出到 Mailchimp 被限制為區段。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="9dcf4-136">因供應商端的限制，匯出總計 1 百萬個設定檔的區段最長耗時 3 小時。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="9dcf4-137">您可以匯出到 Mailchimp 的設定檔數量端賴且受限於您與 Mailchimp 的合約。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9dcf4-138">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="9dcf4-138">Data privacy and compliance</span></span>

<span data-ttu-id="9dcf4-139">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Mailchimp 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9dcf4-140">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Mailchimp 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9dcf4-141">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9dcf4-142">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="9dcf4-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]