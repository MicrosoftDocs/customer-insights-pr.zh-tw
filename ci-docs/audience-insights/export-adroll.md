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
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124355"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="96361-103">將客戶細分匯出至 AdRoll (預覽版)</span><span class="sxs-lookup"><span data-stu-id="96361-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="96361-104">將統整客戶個人資料的客戶細分匯出至 AdRoll，並用來進行廣告。</span><span class="sxs-lookup"><span data-stu-id="96361-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="96361-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="96361-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="96361-106">您具有 [AdRoll 帳戶](https://www.adroll.com/) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="96361-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="96361-107">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="96361-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="96361-108">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="96361-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="96361-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="96361-109">Known limitations</span></span>

- <span data-ttu-id="96361-110">每個匯出最多可匯出總共 250'000 份的個人資料到 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="96361-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="96361-111">您不能將少於 100 份個人資料的客戶細分匯出至 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="96361-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="96361-112">對 AdRoll 的匯出被限制為客戶細分。</span><span class="sxs-lookup"><span data-stu-id="96361-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="96361-113">匯出最多 250'000 個人資料至 AdRoll 可能需要 10 分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="96361-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="96361-114">您可以匯出到 AdRoll 的個人資料數量依照且受限於您與 AdRoll 的合約。</span><span class="sxs-lookup"><span data-stu-id="96361-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="96361-115">設定到 AdRoll 的連接</span><span class="sxs-lookup"><span data-stu-id="96361-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="96361-116">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="96361-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="96361-117">選取 **新增連接**，然後選擇 **AdRoll** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="96361-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="96361-118">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="96361-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="96361-119">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="96361-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="96361-120">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="96361-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="96361-121">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="96361-121">Choose who can use this connection.</span></span> <span data-ttu-id="96361-122">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="96361-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="96361-123">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="96361-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="96361-124">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="96361-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="96361-125">選取 **連接** 初始化與 AdRoll 的連接。</span><span class="sxs-lookup"><span data-stu-id="96361-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="96361-126">選取 **使用 AdRoll 驗證** 並提供您的 AdRoll 管理員認證。</span><span class="sxs-lookup"><span data-stu-id="96361-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="96361-127">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="96361-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="96361-128">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="96361-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="96361-129">設定匯出</span><span class="sxs-lookup"><span data-stu-id="96361-129">Configure an export</span></span>

<span data-ttu-id="96361-130">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="96361-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="96361-131">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="96361-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="96361-132">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="96361-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="96361-133">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="96361-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="96361-134">在 **匯出的連結** 欄位中，在 AdRoll 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="96361-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="96361-135">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="96361-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="96361-136">輸入您的 **AdRoll 廣告客戶識別碼**。如需詳細資訊，請參閱 [AdRoll 廣告客戶個人資料](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)。</span><span class="sxs-lookup"><span data-stu-id="96361-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="96361-137">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="96361-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="96361-138">必需將客戶細分匯出至 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="96361-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="96361-139">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="96361-139">Select the segments you want to export.</span></span> <span data-ttu-id="96361-140">選取一個包含最少 100 個成員的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="96361-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="96361-141">您無法匯出更小的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="96361-141">You can't export smaller segments.</span></span> <span data-ttu-id="96361-142">此外，會出一個客戶細分最大數量為每個匯出 250'000 個成員。</span><span class="sxs-lookup"><span data-stu-id="96361-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="96361-143">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="96361-143">Select **Save**.</span></span>

<span data-ttu-id="96361-144">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="96361-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="96361-145">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="96361-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="96361-146">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="96361-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="96361-147">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="96361-147">Data privacy and compliance</span></span>

<span data-ttu-id="96361-148">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 AdRoll 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="96361-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="96361-149">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 AdRoll 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="96361-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="96361-150">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="96361-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="96361-151">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="96361-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
