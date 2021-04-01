---
title: 匯出 Customer Insights 資料到 AdRoll
description: 瞭解如何設定到 AdRoll 的連接。
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697064"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="acdd2-103">AdRoll 的連接器 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="acdd2-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="acdd2-104">將統整客戶個人資料的客戶細分匯出至 AdRoll，並用來進行廣告。</span><span class="sxs-lookup"><span data-stu-id="acdd2-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="acdd2-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="acdd2-105">Prerequisites</span></span>

-   <span data-ttu-id="acdd2-106">您具有 [AdRoll 帳戶](https://www.adroll.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="acdd2-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="acdd2-107">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="acdd2-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="acdd2-108">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="acdd2-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="acdd2-109">連線至 AdRoll</span><span class="sxs-lookup"><span data-stu-id="acdd2-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="acdd2-110">移至 **管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="acdd2-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="acdd2-111">請在 **AdRoll** 下方選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="acdd2-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="acdd2-112">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="acdd2-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll 連接的設定窗格。":::

1. <span data-ttu-id="acdd2-114">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="acdd2-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="acdd2-115">選取 **連接** 初始化與 AdRoll 的連接。</span><span class="sxs-lookup"><span data-stu-id="acdd2-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="acdd2-116">選取 **使用 AdRoll 驗證** 並提供您的 AdRoll 管理員認證。</span><span class="sxs-lookup"><span data-stu-id="acdd2-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="acdd2-117">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="acdd2-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="acdd2-118">輸入您的 **AdRoll 廣告客戶識別碼**[AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles)。</span><span class="sxs-lookup"><span data-stu-id="acdd2-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="acdd2-119">選取 **下一步** 以設定匯出。</span><span class="sxs-lookup"><span data-stu-id="acdd2-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="acdd2-120">設定連接器</span><span class="sxs-lookup"><span data-stu-id="acdd2-120">Configure the connector</span></span>

1. <span data-ttu-id="acdd2-121">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="acdd2-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="acdd2-122">必需將客戶細分匯出至 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="acdd2-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="acdd2-123">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="acdd2-123">Select the segments you want to export.</span></span> <span data-ttu-id="acdd2-124">選取一個包含最少 100 個成員的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="acdd2-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="acdd2-125">您無法匯出更小的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="acdd2-125">You can't export smaller segments.</span></span> <span data-ttu-id="acdd2-126">此外，會出一個客戶細分最大數量為每個匯出 250'000 個成員。</span><span class="sxs-lookup"><span data-stu-id="acdd2-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="acdd2-127">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="acdd2-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="acdd2-128">匯出資料</span><span class="sxs-lookup"><span data-stu-id="acdd2-128">Export the data</span></span>

<span data-ttu-id="acdd2-129">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="acdd2-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="acdd2-130">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="acdd2-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="acdd2-131">已知限制</span><span class="sxs-lookup"><span data-stu-id="acdd2-131">Known limitations</span></span>

- <span data-ttu-id="acdd2-132">每個匯出最多可匯出總共 250'000 份的個人資料到 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="acdd2-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="acdd2-133">您不能將少於 100 份個人資料的客戶細分匯出至 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="acdd2-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="acdd2-134">對 AdRoll 的匯出被限制為客戶細分。</span><span class="sxs-lookup"><span data-stu-id="acdd2-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="acdd2-135">匯出最多 250'000 個人資料至 AdRoll 可能需要 10 分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="acdd2-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="acdd2-136">您可以匯出到 AdRoll 的個人資料數量依照且受限於您與 AdRoll 的合約。</span><span class="sxs-lookup"><span data-stu-id="acdd2-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="acdd2-137">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="acdd2-137">Data privacy and compliance</span></span>

<span data-ttu-id="acdd2-138">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 AdRoll 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="acdd2-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="acdd2-139">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 AdRoll 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="acdd2-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="acdd2-140">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="acdd2-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="acdd2-141">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="acdd2-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
