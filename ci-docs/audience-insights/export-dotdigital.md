---
title: 匯出 Customer Insights 資料到 DotDigital
description: 瞭解如何組態到 DotDigital 的連接。
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644438"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="858d0-103">適用 DotDigital 的連接器 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="858d0-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="858d0-104">將統一的客戶設定檔區段匯出到 DotDigital 通訊錄，並用於行銷活動、電子郵件行銷及使用 DotDigital 組建客戶區段。</span><span class="sxs-lookup"><span data-stu-id="858d0-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="858d0-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="858d0-105">Prerequisites</span></span>

-   <span data-ttu-id="858d0-106">您具有 [DotDigital 帳戶](https://dotdigital.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="858d0-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="858d0-107">DotDigital 和對應的識別碼中含有現有的通訊錄。</span><span class="sxs-lookup"><span data-stu-id="858d0-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="858d0-108">當您選取和打開通訊錄時，可以在 URL 找到識別碼。</span><span class="sxs-lookup"><span data-stu-id="858d0-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="858d0-109">如需詳細資訊，請見 [DotDigital 通訊錄](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)。</span><span class="sxs-lookup"><span data-stu-id="858d0-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="858d0-110">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="858d0-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="858d0-111">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="858d0-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="858d0-112">連接到 DotDigital</span><span class="sxs-lookup"><span data-stu-id="858d0-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="858d0-113">移至 **管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="858d0-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="858d0-114">請在 **DotDigital** 下方選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="858d0-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="858d0-115">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="858d0-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital 匯出的組態窗格。":::

1. <span data-ttu-id="858d0-117">輸入您的 **DotDigital 使用者名稱和密碼**。</span><span class="sxs-lookup"><span data-stu-id="858d0-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="858d0-118">輸入您的 **[DotDigital 通訊錄 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**。</span><span class="sxs-lookup"><span data-stu-id="858d0-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="858d0-119">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="858d0-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="858d0-120">選取 **連接** 初始化到 DotDigital 的連接。</span><span class="sxs-lookup"><span data-stu-id="858d0-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="858d0-121">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="858d0-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="858d0-122">選取 **下一步** 以設定匯出。</span><span class="sxs-lookup"><span data-stu-id="858d0-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="858d0-123">設定連接器</span><span class="sxs-lookup"><span data-stu-id="858d0-123">Configure the connector</span></span>

1. <span data-ttu-id="858d0-124">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="858d0-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="858d0-125">針對其他可選欄位如 **名字**、**姓氏**、**全名**、**性別** 和 **貼文代碼** 重複相同步驟。</span><span class="sxs-lookup"><span data-stu-id="858d0-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="858d0-126">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="858d0-126">Select the segments you want to export.</span></span> <span data-ttu-id="858d0-127">您總共最多可匯出 1 百萬個客戶設定檔到 DotDigital。</span><span class="sxs-lookup"><span data-stu-id="858d0-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="858d0-128">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="858d0-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="858d0-129">匯出資料</span><span class="sxs-lookup"><span data-stu-id="858d0-129">Export the data</span></span>

<span data-ttu-id="858d0-130">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="858d0-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="858d0-131">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="858d0-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="858d0-132">您現在可以在 [DotDigital 通訊錄](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) 中找到您的區段。</span><span class="sxs-lookup"><span data-stu-id="858d0-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="858d0-133">已知限制</span><span class="sxs-lookup"><span data-stu-id="858d0-133">Known limitations</span></span>

- <span data-ttu-id="858d0-134">每個到 DotDigital 的匯出最多可達 1 百萬個設定檔。</span><span class="sxs-lookup"><span data-stu-id="858d0-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="858d0-135">匯出到 DotDigital 被限制為區段。</span><span class="sxs-lookup"><span data-stu-id="858d0-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="858d0-136">因供應商端的限制，匯出總計 1 百萬個設定檔的區段最長會耗時 3 小時。</span><span class="sxs-lookup"><span data-stu-id="858d0-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="858d0-137">您可以匯出到 DotDigital 的設定檔數量端賴且受限於您與 DotDigital 的合約。</span><span class="sxs-lookup"><span data-stu-id="858d0-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="858d0-138">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="858d0-138">Data privacy and compliance</span></span>

<span data-ttu-id="858d0-139">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 DotDigital 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="858d0-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="858d0-140">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 DotDigital 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="858d0-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="858d0-141">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="858d0-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="858d0-142">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="858d0-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
