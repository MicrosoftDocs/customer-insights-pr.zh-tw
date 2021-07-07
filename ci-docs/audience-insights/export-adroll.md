---
title: 匯出 Customer Insights 資料到 AdRoll
description: 了解如何設定連接並匯出至 AdRoll。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304796"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="636d5-103">將客戶細分匯出至 AdRoll (預覽版)</span><span class="sxs-lookup"><span data-stu-id="636d5-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="636d5-104">將統整客戶個人資料的客戶細分匯出至 AdRoll，並用來進行廣告。</span><span class="sxs-lookup"><span data-stu-id="636d5-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="636d5-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="636d5-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="636d5-106">您具有 [AdRoll 帳戶](https://www.adroll.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="636d5-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="636d5-107">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="636d5-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="636d5-108">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="636d5-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="636d5-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="636d5-109">Known limitations</span></span>

- <span data-ttu-id="636d5-110">您一次最多可以匯出 250,000 筆個人資料到 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="636d5-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="636d5-111">您不能將少於 100 份個人資料的客戶細分匯出至 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="636d5-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="636d5-112">對 AdRoll 的匯出被限制為客戶細分。</span><span class="sxs-lookup"><span data-stu-id="636d5-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="636d5-113">匯出最多 250,000 個人資料至 AdRoll 可能需要 10 分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="636d5-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="636d5-114">您可以匯出到 AdRoll 的個人資料數量取決於您與 AdRoll 的合約。</span><span class="sxs-lookup"><span data-stu-id="636d5-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="636d5-115">設定到 AdRoll 的連接</span><span class="sxs-lookup"><span data-stu-id="636d5-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="636d5-116">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="636d5-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="636d5-117">選取 **新增連接**，然後選擇 **AdRoll** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="636d5-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="636d5-118">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="636d5-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="636d5-119">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="636d5-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="636d5-120">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="636d5-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="636d5-121">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="636d5-121">Choose who can use this connection.</span></span> <span data-ttu-id="636d5-122">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="636d5-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="636d5-123">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="636d5-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="636d5-124">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="636d5-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="636d5-125">選取 **連接** 初始化與 AdRoll 的連接。</span><span class="sxs-lookup"><span data-stu-id="636d5-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="636d5-126">選取 **使用 AdRoll 驗證** 並提供您的 AdRoll 管理員認證。</span><span class="sxs-lookup"><span data-stu-id="636d5-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="636d5-127">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="636d5-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="636d5-128">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="636d5-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="636d5-129">設定匯出</span><span class="sxs-lookup"><span data-stu-id="636d5-129">Configure an export</span></span>

<span data-ttu-id="636d5-130">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="636d5-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="636d5-131">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="636d5-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="636d5-132">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="636d5-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="636d5-133">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="636d5-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="636d5-134">在 **匯出的連結** 欄位中，在 AdRoll 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="636d5-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="636d5-135">如果您沒有看到此區段名稱，則代表此類型中的連接沒有您可以使用的。</span><span class="sxs-lookup"><span data-stu-id="636d5-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="636d5-136">輸入您的 **AdRoll 廣告客戶識別碼**。</span><span class="sxs-lookup"><span data-stu-id="636d5-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="636d5-137">如需詳細資訊，請參閱 [AdRoll 廣告客戶個人資料](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)。</span><span class="sxs-lookup"><span data-stu-id="636d5-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="636d5-138">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="636d5-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="636d5-139">必需將客戶細分匯出至 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="636d5-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="636d5-140">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="636d5-140">Select the segments you want to export.</span></span> <span data-ttu-id="636d5-141">選取一個包含最少 100 個成員的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="636d5-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="636d5-142">您無法匯出更小的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="636d5-142">You can't export smaller segments.</span></span> <span data-ttu-id="636d5-143">此外，匯出一個客戶細分的最大數量為每個匯出 250,000 個成員。</span><span class="sxs-lookup"><span data-stu-id="636d5-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="636d5-144">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="636d5-144">Select **Save**.</span></span>

<span data-ttu-id="636d5-145">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="636d5-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="636d5-146">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="636d5-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="636d5-147">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="636d5-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="636d5-148">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="636d5-148">Data privacy and compliance</span></span>

<span data-ttu-id="636d5-149">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 AdRoll 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="636d5-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="636d5-150">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 AdRoll 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="636d5-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="636d5-151">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="636d5-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="636d5-152">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="636d5-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
