---
title: 匯出 Customer Insights 資料到 Autopilot
description: 瞭解如何設定與 Autopilot 的連接。
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269228"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="0698b-103">適用 Autopilot 的連接器 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="0698b-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="0698b-104">將統整客戶設定檔的客戶細分匯出至 Autopilot，並在 Autopilot 中用來進行電子郵件行銷。</span><span class="sxs-lookup"><span data-stu-id="0698b-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0698b-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="0698b-105">Prerequisites</span></span>

-   <span data-ttu-id="0698b-106">您具有 [Autopilot 帳戶](https://www.autopilothq.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="0698b-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0698b-107">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="0698b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0698b-108">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="0698b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="0698b-109">連接至 Autopilot</span><span class="sxs-lookup"><span data-stu-id="0698b-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="0698b-110">移至 **管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="0698b-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0698b-111">請在 **Autopilot** 下方選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="0698b-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="0698b-112">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="0698b-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot 連接的設定窗格。":::

1. <span data-ttu-id="0698b-114">輸入您的 **Autopilot API 金鑰**[Autopilot API 金鑰 ](https://autopilot.docs.apiary.io/#)。</span><span class="sxs-lookup"><span data-stu-id="0698b-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="0698b-115">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="0698b-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0698b-116">選取 **連接** 初始化與 Autopilot 的連接。</span><span class="sxs-lookup"><span data-stu-id="0698b-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="0698b-117">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="0698b-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0698b-118">選取 **下一步** 以設定匯出。</span><span class="sxs-lookup"><span data-stu-id="0698b-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0698b-119">設定連接器</span><span class="sxs-lookup"><span data-stu-id="0698b-119">Configure the connector</span></span>

1. <span data-ttu-id="0698b-120">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="0698b-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0698b-121">對其他可選欄位 (如 **名**、**姓**) 重複相同步驟。</span><span class="sxs-lookup"><span data-stu-id="0698b-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="0698b-122">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="0698b-122">Select the segments you want to export.</span></span> <span data-ttu-id="0698b-123">我們強烈 **建議您不要匯出總計超過 100'000 份客戶設定檔** 到 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="0698b-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="0698b-124">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="0698b-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0698b-125">匯出資料</span><span class="sxs-lookup"><span data-stu-id="0698b-125">Export the data</span></span>

<span data-ttu-id="0698b-126">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="0698b-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0698b-127">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="0698b-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0698b-128">已知限制</span><span class="sxs-lookup"><span data-stu-id="0698b-128">Known limitations</span></span>

- <span data-ttu-id="0698b-129">您最多可匯出總共 100'000 份的客戶設定檔到 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="0698b-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="0698b-130">匯出到 Autopilot 被限制在客戶細分。</span><span class="sxs-lookup"><span data-stu-id="0698b-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="0698b-131">匯出多達 100'000 份設定檔到 Autopilot 需要花費幾個小時。</span><span class="sxs-lookup"><span data-stu-id="0698b-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="0698b-132">您可以匯出到 Autopilot 的設定檔數量是根據且受限於您與 Autopilot 的合約。</span><span class="sxs-lookup"><span data-stu-id="0698b-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0698b-133">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="0698b-133">Data privacy and compliance</span></span>

<span data-ttu-id="0698b-134">當您啟用 Dynamics 365 Customer Insights 來傳輸資料給 Autopilot，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，其中包括潛在敏感資料 (如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="0698b-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0698b-135">Microsoft 將依據您的指示傳輸此資料，但您有責任確保 Autopilot 符合任何您承擔的隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="0698b-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0698b-136">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="0698b-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0698b-137">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="0698b-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]