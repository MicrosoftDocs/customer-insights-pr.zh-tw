---
title: 匯出 Customer Insights 資料到 Google Ads
description: 了解如何設定連接並匯出至 Google Ads。
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976308"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="8f526-103">將客戶細分匯出至 Google Ads (預覽版)</span><span class="sxs-lookup"><span data-stu-id="8f526-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="8f526-104">將統一客戶設定檔區段匯出到 Google Ads 對象清單，並用它們在 Google Search、Gmail、YouTube 和 Google Display Network 上刊登廣告。</span><span class="sxs-lookup"><span data-stu-id="8f526-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="8f526-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="8f526-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="8f526-106">您具有 [Google Ads 帳戶](https://ads.google.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="8f526-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8f526-107">您擁有[受核准的 Google Ads 開發人員權杖](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="8f526-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="8f526-108">您滿足[客戶比對原則](https://support.google.com/adspolicy/answer/6299717)的要求</span><span class="sxs-lookup"><span data-stu-id="8f526-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="8f526-109">您滿足[再行銷清單大小](https://support.google.com/google-ads/answer/7558048)的要求</span><span class="sxs-lookup"><span data-stu-id="8f526-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="8f526-110">Google Ads 和對應的識別碼中有現有的對象。</span><span class="sxs-lookup"><span data-stu-id="8f526-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="8f526-111">如需詳細資訊，請參閱 [Google Ads 對象](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)。</span><span class="sxs-lookup"><span data-stu-id="8f526-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="8f526-112">您有 [組態的區段](segments.md)</span><span class="sxs-lookup"><span data-stu-id="8f526-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="8f526-113">匯出區段的統一客戶設定檔包含代表電子郵件地址、名字和姓氏的欄位</span><span class="sxs-lookup"><span data-stu-id="8f526-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8f526-114">已知限制</span><span class="sxs-lookup"><span data-stu-id="8f526-114">Known limitations</span></span>

- <span data-ttu-id="8f526-115">每個到 Google Ads 的匯出最多可達 1 百萬個設定檔。</span><span class="sxs-lookup"><span data-stu-id="8f526-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="8f526-116">匯出到 Google Ads 被限制為區段。</span><span class="sxs-lookup"><span data-stu-id="8f526-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="8f526-117">因供應商端的限制，匯出總計 1 百萬個設定檔的區段最長耗時 5 分鐘。</span><span class="sxs-lookup"><span data-stu-id="8f526-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="8f526-118">Google Ads 中的相符最長耗時 48 小時。</span><span class="sxs-lookup"><span data-stu-id="8f526-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="8f526-119">設定與 Google Ads 的連接</span><span class="sxs-lookup"><span data-stu-id="8f526-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="8f526-120">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="8f526-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8f526-121">選取 **新增連接**，然後選擇 **Google Ads** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="8f526-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="8f526-122">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="8f526-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8f526-123">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="8f526-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8f526-124">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="8f526-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8f526-125">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="8f526-125">Choose who can use this connection.</span></span> <span data-ttu-id="8f526-126">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="8f526-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8f526-127">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="8f526-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8f526-128">輸入您的 **[Google Ads 客戶識別碼](https://support.google.com/google-ads/answer/1704344)**。</span><span class="sxs-lookup"><span data-stu-id="8f526-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="8f526-129">輸入您的 **[Google Ads 核准的開發人員權杖](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**。</span><span class="sxs-lookup"><span data-stu-id="8f526-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="8f526-130">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="8f526-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8f526-131">選取 **使用 Google Ads 驗證** 並提供您的 Google Ads 認證。</span><span class="sxs-lookup"><span data-stu-id="8f526-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="8f526-132">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="8f526-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8f526-133">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="8f526-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="8f526-134">設定匯出</span><span class="sxs-lookup"><span data-stu-id="8f526-134">Configure an export</span></span>

<span data-ttu-id="8f526-135">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="8f526-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8f526-136">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="8f526-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8f526-137">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="8f526-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8f526-138">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="8f526-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8f526-139">在 **匯出的連結** 欄位中，在 Google Ads 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="8f526-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="8f526-140">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="8f526-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8f526-141">輸入您的 **[Google Ads 對象識別碼](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** 然後選取 **連接** 初始化到 Google Ads 的連接。</span><span class="sxs-lookup"><span data-stu-id="8f526-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="8f526-142">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="8f526-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8f526-143">針對 **名字** 和 **姓氏** 欄位重複相同步驟。</span><span class="sxs-lookup"><span data-stu-id="8f526-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="8f526-144">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="8f526-144">Select the segments you want to export.</span></span> <span data-ttu-id="8f526-145">您總共最多可匯出 1 百萬個客戶設定檔到 Google Ads。</span><span class="sxs-lookup"><span data-stu-id="8f526-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="8f526-146">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="8f526-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8f526-147">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="8f526-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8f526-148">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="8f526-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8f526-149">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="8f526-149">Data privacy and compliance</span></span>

<span data-ttu-id="8f526-150">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Google Ads 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="8f526-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8f526-151">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Google Ads 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="8f526-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8f526-152">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="8f526-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8f526-153">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="8f526-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
