---
title: 匯出 Customer Insights 資料到 Autopilot
description: 了解如何設定連接並匯出至 Autopilot。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760133"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="d9565-103">將客戶細分匯出至 Autopilot (預覽版)</span><span class="sxs-lookup"><span data-stu-id="d9565-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="d9565-104">將統整客戶設定檔的客戶細分匯出至 Autopilot，並在 Autopilot 中用來進行電子郵件行銷。</span><span class="sxs-lookup"><span data-stu-id="d9565-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d9565-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="d9565-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d9565-106">您具有 [Autopilot 帳戶](https://www.autopilothq.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="d9565-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d9565-107">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="d9565-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d9565-108">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="d9565-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d9565-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="d9565-109">Known limitations</span></span>

- <span data-ttu-id="d9565-110">您最多可匯出總共 100'000 份的客戶設定檔到 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="d9565-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="d9565-111">匯出到 Autopilot 被限制在客戶細分。</span><span class="sxs-lookup"><span data-stu-id="d9565-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="d9565-112">匯出多達 100'000 份設定檔到 Autopilot 需要花費幾個小時。</span><span class="sxs-lookup"><span data-stu-id="d9565-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="d9565-113">您可以匯出到 Autopilot 的設定檔數量是根據且受限於您與 Autopilot 的合約。</span><span class="sxs-lookup"><span data-stu-id="d9565-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="d9565-114">設定對 Autopilot 的連接</span><span class="sxs-lookup"><span data-stu-id="d9565-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="d9565-115">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="d9565-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d9565-116">選取 **新增連接**，然後選擇 **Autopilot** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="d9565-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="d9565-117">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="d9565-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d9565-118">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="d9565-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d9565-119">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="d9565-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d9565-120">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="d9565-120">Choose who can use this connection.</span></span> <span data-ttu-id="d9565-121">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="d9565-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d9565-122">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="d9565-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="d9565-123">請輸入 [Autopilot API 金鑰](https://autopilot.docs.apiary.io/#)。</span><span class="sxs-lookup"><span data-stu-id="d9565-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="d9565-124">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="d9565-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d9565-125">選取 **連接** 初始化與 Autopilot 的連接。</span><span class="sxs-lookup"><span data-stu-id="d9565-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="d9565-126">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="d9565-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d9565-127">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="d9565-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d9565-128">設定匯出</span><span class="sxs-lookup"><span data-stu-id="d9565-128">Configure an export</span></span>

<span data-ttu-id="d9565-129">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="d9565-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d9565-130">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="d9565-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d9565-131">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="d9565-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d9565-132">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="d9565-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d9565-133">在 **匯出的連結** 欄位中，在 Autopilot 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="d9565-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="d9565-134">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="d9565-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="d9565-135">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="d9565-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d9565-136">對其他可選欄位 (如 **名**、**姓**) 重複相同步驟。</span><span class="sxs-lookup"><span data-stu-id="d9565-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="d9565-137">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="d9565-137">Select the segments you want to export.</span></span> <span data-ttu-id="d9565-138">我們強烈 **建議您不要匯出總計超過 100'000 份客戶設定檔** 到 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="d9565-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="d9565-139">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="d9565-139">Select **Save**.</span></span>

<span data-ttu-id="d9565-140">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="d9565-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d9565-141">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="d9565-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d9565-142">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="d9565-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d9565-143">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="d9565-143">Data privacy and compliance</span></span>

<span data-ttu-id="d9565-144">當您啟用 Dynamics 365 Customer Insights 來傳輸資料給 Autopilot，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，其中包括潛在敏感資料 (如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="d9565-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d9565-145">Microsoft 將依據您的指示傳輸此資料，但您有責任確保 Autopilot 符合任何您承擔的隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="d9565-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d9565-146">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="d9565-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d9565-147">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="d9565-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
