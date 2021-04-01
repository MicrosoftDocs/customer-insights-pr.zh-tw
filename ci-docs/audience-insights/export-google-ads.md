---
title: 匯出 Customer Insights 資料到 Google Ads
description: 瞭解如何組態到 Google Ads 的連接。
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598237"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="451d4-103">Google Ads 的連接器 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="451d4-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="451d4-104">將統一客戶設定檔區段匯出到 Google Ads 對象清單，並用它們在 Google Search、Gmail、YouTube 和 Google Display Network 上刊登廣告。</span><span class="sxs-lookup"><span data-stu-id="451d4-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="451d4-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="451d4-105">Prerequisites</span></span>

-   <span data-ttu-id="451d4-106">您具有 [Google Ads 帳戶](https://ads.google.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="451d4-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="451d4-107">Google Ads 和對應的識別碼中有現有的對象。</span><span class="sxs-lookup"><span data-stu-id="451d4-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="451d4-108">如需詳細資訊，請參閱 [Google Ads 對象](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)。</span><span class="sxs-lookup"><span data-stu-id="451d4-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="451d4-109">您有 [組態的區段](segments.md)</span><span class="sxs-lookup"><span data-stu-id="451d4-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="451d4-110">匯出區段的統一客戶設定檔包含代表電子郵件地址、名字和姓氏的欄位</span><span class="sxs-lookup"><span data-stu-id="451d4-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="451d4-111">連線至 Google Ads</span><span class="sxs-lookup"><span data-stu-id="451d4-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="451d4-112">移至 **管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="451d4-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="451d4-113">請在 **Google Ads** 下方選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="451d4-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="451d4-114">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="451d4-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="451d4-115">輸入您的 **[Google Ads 客戶識別碼](https://support.google.com/google-ads/answer/1704344)**。</span><span class="sxs-lookup"><span data-stu-id="451d4-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="451d4-116">輸入您的 **[Google Ads 核准的開發人員權杖](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**。</span><span class="sxs-lookup"><span data-stu-id="451d4-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="451d4-117">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="451d4-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="451d4-118">輸入您的 **[Google Ads 對象識別碼](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** 然後選取 **連接** 初始化到 Google Ads 的連接。</span><span class="sxs-lookup"><span data-stu-id="451d4-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="451d4-119">選取 **使用 Google Ads 驗證** 並提供您的 Google Ads 認證。</span><span class="sxs-lookup"><span data-stu-id="451d4-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="451d4-120">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="451d4-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="匯出 Google Ads 連接的螢幕截取畫面":::

1. <span data-ttu-id="451d4-122">選取 **下一步** 以設定匯出。</span><span class="sxs-lookup"><span data-stu-id="451d4-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="451d4-123">設定連接器</span><span class="sxs-lookup"><span data-stu-id="451d4-123">Configure the connector</span></span>

1. <span data-ttu-id="451d4-124">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="451d4-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="451d4-125">針對 **名字** 和 **姓氏** 欄位重複相同步驟。</span><span class="sxs-lookup"><span data-stu-id="451d4-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="451d4-126">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="451d4-126">Select the segments you want to export.</span></span> <span data-ttu-id="451d4-127">您總共最多可匯出 1 百萬個客戶設定檔到 Google Ads。</span><span class="sxs-lookup"><span data-stu-id="451d4-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="451d4-128">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="451d4-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="451d4-129">匯出資料</span><span class="sxs-lookup"><span data-stu-id="451d4-129">Export the data</span></span>

<span data-ttu-id="451d4-130">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="451d4-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="451d4-131">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="451d4-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="451d4-132">在 Google Ads 中，您現在可以在 [Google Ads 對象](https://support.google.com/google-ads/answer/7558048?hl=en/) 下方找到您的區段。</span><span class="sxs-lookup"><span data-stu-id="451d4-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="451d4-133">已知限制</span><span class="sxs-lookup"><span data-stu-id="451d4-133">Known limitations</span></span>

- <span data-ttu-id="451d4-134">每個到 Google Ads 的匯出最多可達 1 百萬個設定檔。</span><span class="sxs-lookup"><span data-stu-id="451d4-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="451d4-135">匯出到 Google Ads 被限制為區段。</span><span class="sxs-lookup"><span data-stu-id="451d4-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="451d4-136">因供應商端的限制，匯出總計 1 百萬個設定檔的區段最長耗時 5 分鐘。</span><span class="sxs-lookup"><span data-stu-id="451d4-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="451d4-137">Google Ads 中的相符最長耗時 48 小時。</span><span class="sxs-lookup"><span data-stu-id="451d4-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="451d4-138">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="451d4-138">Data privacy and compliance</span></span>

<span data-ttu-id="451d4-139">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Google Ads 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="451d4-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="451d4-140">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Google Ads 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="451d4-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="451d4-141">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="451d4-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="451d4-142">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="451d4-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]