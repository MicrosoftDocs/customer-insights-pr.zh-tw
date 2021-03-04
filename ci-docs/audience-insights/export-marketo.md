---
title: 匯出 Customer Insights 資料到 Marketo
description: 瞭解如何組態到 Marketo 的連接。
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267071"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="abc30-103">適用 Marketo 的連接器 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="abc30-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="abc30-104">匯出統一的客戶設定檔區段以便產生行銷活動，提供電子郵件行銷及使用含 Marketo 的特定族群客戶。</span><span class="sxs-lookup"><span data-stu-id="abc30-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abc30-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="abc30-105">Prerequisites</span></span>

-   <span data-ttu-id="abc30-106">您具有 [Marketo 帳戶](https://login.marketo.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="abc30-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="abc30-107">Marketo 和對應的識別碼中有現有的清單。</span><span class="sxs-lookup"><span data-stu-id="abc30-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="abc30-108">如需詳細資訊，請參閱 [ Marketo 清單](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)。</span><span class="sxs-lookup"><span data-stu-id="abc30-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="abc30-109">您有 [組態的區段](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="abc30-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="abc30-110">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="abc30-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="abc30-111">連線到 Marketo</span><span class="sxs-lookup"><span data-stu-id="abc30-111">Connect to Marketo</span></span>

1. <span data-ttu-id="abc30-112">移至 **管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="abc30-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="abc30-113">請在 **Marketo** 下方選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="abc30-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="abc30-114">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="abc30-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="abc30-115">輸入您的 **[Marketo 用戶端識別碼、用戶端秘密和 REST 端點主機名稱](https://developers.marketo.com/rest-api/authentication/)**。</span><span class="sxs-lookup"><span data-stu-id="abc30-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="abc30-116">輸入您的 **[Marketo 清單識別碼](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="abc30-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="abc30-117">選取 **我同意** 以便確認 **資料隱私權與合規性** 和選取 **連線** 初始化到 Marketo 的連接。</span><span class="sxs-lookup"><span data-stu-id="abc30-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="abc30-118">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="abc30-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="匯出 Marketo 連接的螢幕截取畫面":::

1. <span data-ttu-id="abc30-120">選取 **下一步** 以設定匯出。</span><span class="sxs-lookup"><span data-stu-id="abc30-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="abc30-121">設定連接器</span><span class="sxs-lookup"><span data-stu-id="abc30-121">Configure the connector</span></span>

1. <span data-ttu-id="abc30-122">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="abc30-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="abc30-123">或者將 **名字**、**姓氏**、**城市**、**州** 和 **國家/區域** 匯出為其他欄位，以建立更多個人化電子郵件。</span><span class="sxs-lookup"><span data-stu-id="abc30-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="abc30-124">選取 **新增屬性** 對應這些欄位。</span><span class="sxs-lookup"><span data-stu-id="abc30-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="abc30-125">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="abc30-125">Select the segments you want to export.</span></span> <span data-ttu-id="abc30-126">您總共最多可匯出 1 百萬個客戶設定檔到 Marketo。</span><span class="sxs-lookup"><span data-stu-id="abc30-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="選取要匯出到 Marketo 的欄位和區段":::

1. <span data-ttu-id="abc30-128">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="abc30-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="abc30-129">匯出資料</span><span class="sxs-lookup"><span data-stu-id="abc30-129">Export the data</span></span>

<span data-ttu-id="abc30-130">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="abc30-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="abc30-131">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="abc30-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="abc30-132">在 Marketo 中，您現在可以在 [Marketo 清單](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) 下方找到您的區段。</span><span class="sxs-lookup"><span data-stu-id="abc30-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="abc30-133">已知限制</span><span class="sxs-lookup"><span data-stu-id="abc30-133">Known limitations</span></span>

- <span data-ttu-id="abc30-134">每個到 Marketo 的匯出最多可達 1 百萬個設定檔。</span><span class="sxs-lookup"><span data-stu-id="abc30-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="abc30-135">匯出到 Marketo 被限制為區段。</span><span class="sxs-lookup"><span data-stu-id="abc30-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="abc30-136">匯出總計為 1 百萬個設定檔的分段可能需要 3 小時的時間。</span><span class="sxs-lookup"><span data-stu-id="abc30-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="abc30-137">您可以匯出到 Marketo 的設定檔數量端賴且受限於您與 Marketo 的合約。</span><span class="sxs-lookup"><span data-stu-id="abc30-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="abc30-138">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="abc30-138">Data privacy and compliance</span></span>

<span data-ttu-id="abc30-139">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Marketo 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="abc30-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="abc30-140">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Marketo 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="abc30-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="abc30-141">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="abc30-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="abc30-142">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="abc30-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]