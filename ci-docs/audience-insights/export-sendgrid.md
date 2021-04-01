---
title: 匯出 Customer Insights 資料到 SendGrid
description: 瞭解如何設定與 SendGrid 的連接。
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597271"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="d6b42-103">適用 SendGrid 的連接器 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="d6b42-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="d6b42-104">將整合客戶設定檔的客戶細分匯出至 SendGrid 聯絡人清單，並在 SendGrid 中用來進行行銷活動和電子郵件行銷。</span><span class="sxs-lookup"><span data-stu-id="d6b42-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d6b42-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="d6b42-105">Prerequisites</span></span>

-   <span data-ttu-id="d6b42-106">您具有 [SendGrid 帳戶](https://sendgrid.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="d6b42-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d6b42-107">有對應的識別碼且在 SendGrid 中有現有的聯絡人清單。</span><span class="sxs-lookup"><span data-stu-id="d6b42-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="d6b42-108">如需詳細資訊，請參閱 [SendGrid - 管理連絡人](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)。</span><span class="sxs-lookup"><span data-stu-id="d6b42-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="d6b42-109">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="d6b42-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d6b42-110">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="d6b42-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="d6b42-111">連接至 SendGrid</span><span class="sxs-lookup"><span data-stu-id="d6b42-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="d6b42-112">移至 **管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="d6b42-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d6b42-113">請在 **SendGrid** 下方選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="d6b42-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="d6b42-114">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="d6b42-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid 匯出組態窗格。":::

1. <span data-ttu-id="d6b42-116">輸入您的 **SendGrid API 金鑰** [SendGrid API 金鑰 ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)。</span><span class="sxs-lookup"><span data-stu-id="d6b42-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="d6b42-117">輸入您的 **[SendGrid 清單識別碼](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**。</span><span class="sxs-lookup"><span data-stu-id="d6b42-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="d6b42-118">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="d6b42-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d6b42-119">選取 **連接** 初始化與 SendGrid 的連接。</span><span class="sxs-lookup"><span data-stu-id="d6b42-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="d6b42-120">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="d6b42-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d6b42-121">選取 **下一步** 以設定匯出。</span><span class="sxs-lookup"><span data-stu-id="d6b42-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d6b42-122">設定連接器</span><span class="sxs-lookup"><span data-stu-id="d6b42-122">Configure the connector</span></span>

1. <span data-ttu-id="d6b42-123">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="d6b42-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d6b42-124">對其他可選欄位 (如 **名**、**姓**、**國家/地區**、**縣/市**、**市/鎮** 和 **郵遞區號**) 重複相同步驟。</span><span class="sxs-lookup"><span data-stu-id="d6b42-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="d6b42-125">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="d6b42-125">Select the segments you want to export.</span></span> <span data-ttu-id="d6b42-126">我們強烈 **建議您不要匯出總計超過 100'000 份客戶設定檔** 至 SendGrid。</span><span class="sxs-lookup"><span data-stu-id="d6b42-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="d6b42-127">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="d6b42-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d6b42-128">匯出資料</span><span class="sxs-lookup"><span data-stu-id="d6b42-128">Export the data</span></span>

<span data-ttu-id="d6b42-129">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="d6b42-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d6b42-130">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="d6b42-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d6b42-131">已知限制</span><span class="sxs-lookup"><span data-stu-id="d6b42-131">Known limitations</span></span>

- <span data-ttu-id="d6b42-132">對 SendGrid 總計最多 100'000 份設定檔。</span><span class="sxs-lookup"><span data-stu-id="d6b42-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="d6b42-133">匯出到 SendGrid 被限制在客戶細分。</span><span class="sxs-lookup"><span data-stu-id="d6b42-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="d6b42-134">匯出多達 100'000 份設定檔到 SendGrid 需要花費幾個小時。</span><span class="sxs-lookup"><span data-stu-id="d6b42-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="d6b42-135">您可以匯出到 SendGrid 的設定檔數量是根據且受限於您與 SendGrid 的合約。</span><span class="sxs-lookup"><span data-stu-id="d6b42-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d6b42-136">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="d6b42-136">Data privacy and compliance</span></span>

<span data-ttu-id="d6b42-137">當您啟用 Dynamics 365 Customer Insights 傳輸資料給 SendGrid 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感資料 (如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="d6b42-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d6b42-138">Microsoft 將依據您的指示傳輸此資料，但您有責任確保 SendGrid 符合任何您承擔的隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="d6b42-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d6b42-139">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="d6b42-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d6b42-140">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="d6b42-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]