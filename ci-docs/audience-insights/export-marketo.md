---
title: 匯出 Customer Insights 資料到 Marketo
description: 了解如何設定連接並匯出至 Marketo。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059306"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="f0edd-103">將客戶細分匯出至 Marketo (預覽版)</span><span class="sxs-lookup"><span data-stu-id="f0edd-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="f0edd-104">匯出統一的客戶設定檔區段以便產生行銷活動，提供電子郵件行銷及使用含 Marketo 的特定族群客戶。</span><span class="sxs-lookup"><span data-stu-id="f0edd-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="f0edd-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="f0edd-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="f0edd-106">您具有 [Marketo 帳戶](https://login.marketo.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="f0edd-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f0edd-107">Marketo 和對應的識別碼中有現有的清單。</span><span class="sxs-lookup"><span data-stu-id="f0edd-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="f0edd-108">如需詳細資訊，請參閱 [ Marketo 清單](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)。</span><span class="sxs-lookup"><span data-stu-id="f0edd-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="f0edd-109">您有 [組態的區段](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="f0edd-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="f0edd-110">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="f0edd-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f0edd-111">已知限制</span><span class="sxs-lookup"><span data-stu-id="f0edd-111">Known limitations</span></span>

- <span data-ttu-id="f0edd-112">每個到 Marketo 的匯出最多可達 1 百萬個設定檔。</span><span class="sxs-lookup"><span data-stu-id="f0edd-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="f0edd-113">匯出到 Marketo 被限制為區段。</span><span class="sxs-lookup"><span data-stu-id="f0edd-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="f0edd-114">匯出總計為 1 百萬個設定檔的分段可能需要 3 小時的時間。</span><span class="sxs-lookup"><span data-stu-id="f0edd-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="f0edd-115">您可以匯出到 Marketo 的設定檔數量端賴且受限於您與 Marketo 的合約。</span><span class="sxs-lookup"><span data-stu-id="f0edd-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="f0edd-116">設定對 Marketo 的連接</span><span class="sxs-lookup"><span data-stu-id="f0edd-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="f0edd-117">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="f0edd-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f0edd-118">選取 **新增連接**，然後選擇 **Marketo** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="f0edd-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="f0edd-119">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="f0edd-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f0edd-120">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="f0edd-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f0edd-121">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="f0edd-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f0edd-122">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="f0edd-122">Choose who can use this connection.</span></span> <span data-ttu-id="f0edd-123">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="f0edd-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f0edd-124">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="f0edd-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f0edd-125">輸入您的 **[Marketo 用戶端識別碼、用戶端秘密和 REST 端點主機名稱](https://developers.marketo.com/rest-api/authentication/)**。</span><span class="sxs-lookup"><span data-stu-id="f0edd-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="f0edd-126">REST 端點主機名稱僅是主機名稱，沒有 `https://`。</span><span class="sxs-lookup"><span data-stu-id="f0edd-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="f0edd-127">範例：`xyz-abc-123.mktorest.com`。</span><span class="sxs-lookup"><span data-stu-id="f0edd-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="f0edd-128">選取 **我同意** 以便確認 **資料隱私權與合規性** 和選取 **連線** 初始化到 Marketo 的連接。</span><span class="sxs-lookup"><span data-stu-id="f0edd-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="f0edd-129">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="f0edd-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f0edd-130">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="f0edd-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f0edd-131">設定匯出</span><span class="sxs-lookup"><span data-stu-id="f0edd-131">Configure an export</span></span>

<span data-ttu-id="f0edd-132">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="f0edd-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f0edd-133">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="f0edd-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f0edd-134">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="f0edd-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f0edd-135">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="f0edd-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f0edd-136">在 **匯出的連結** 欄位中，在 Marketo 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="f0edd-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="f0edd-137">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="f0edd-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f0edd-138">輸入您的 **[Marketo 清單識別碼](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**。</span><span class="sxs-lookup"><span data-stu-id="f0edd-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="f0edd-139">清單 ID 是純數字值。</span><span class="sxs-lookup"><span data-stu-id="f0edd-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="f0edd-140">例如，如果您的 Marketo 清單 ID 是 ST12345A7，請移除數字前後的字元，然後輸入 `12345`。</span><span class="sxs-lookup"><span data-stu-id="f0edd-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="f0edd-141">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="f0edd-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="f0edd-142">或者，您可以匯出 **名**、**姓**、**市/鎮**、**縣/市** 和 **國家/地區**，以建立更多的個人化電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f0edd-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="f0edd-143">選取 **新增屬性** 對應這些欄位。</span><span class="sxs-lookup"><span data-stu-id="f0edd-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="f0edd-144">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="f0edd-144">Select the segments you want to export.</span></span> <span data-ttu-id="f0edd-145">您總共最多可匯出 1 百萬個客戶設定檔到 Marketo。</span><span class="sxs-lookup"><span data-stu-id="f0edd-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="f0edd-146">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="f0edd-146">Select **Save**.</span></span>

<span data-ttu-id="f0edd-147">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="f0edd-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f0edd-148">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="f0edd-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f0edd-149">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="f0edd-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="f0edd-150">在 Marketo 中，您現在可以在 [Marketo 清單](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) 下方找到您的區段。</span><span class="sxs-lookup"><span data-stu-id="f0edd-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f0edd-151">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="f0edd-151">Data privacy and compliance</span></span>

<span data-ttu-id="f0edd-152">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Marketo 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="f0edd-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f0edd-153">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Marketo 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="f0edd-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f0edd-154">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="f0edd-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f0edd-155">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="f0edd-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
