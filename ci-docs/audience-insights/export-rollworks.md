---
title: 將 Customer Insights 資料匯出至 RollWorks
description: 了解如何設定連接並匯出至 RollWorks。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760488"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="0b263-103">將客戶細分清單匯出至 RollWorks (預覽版)</span><span class="sxs-lookup"><span data-stu-id="0b263-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="0b263-104">將整合客戶個人資料的客戶細分匯出至 RollWorks，並用於廣告。</span><span class="sxs-lookup"><span data-stu-id="0b263-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="0b263-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="0b263-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="0b263-106">您擁有一個 [RollWorks 帳戶](https://www.rollworks.com/)及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="0b263-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0b263-107">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="0b263-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0b263-108">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="0b263-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0b263-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="0b263-109">Known limitations</span></span>

- <span data-ttu-id="0b263-110">每筆匯出中您最多可以將 250'000 筆個人資料匯出至 RollWorks。</span><span class="sxs-lookup"><span data-stu-id="0b263-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="0b263-111">您不能將少於 100 份個人資料的客戶細分匯出至 RollWorks。</span><span class="sxs-lookup"><span data-stu-id="0b263-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="0b263-112">匯出到 RollWorks 時，會被限制為客戶細分。</span><span class="sxs-lookup"><span data-stu-id="0b263-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="0b263-113">將最多 250'000 份個人資料匯出至 RollWorks 可能需要花費 10 分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="0b263-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="0b263-114">您可以匯出至 RollWorks 的個人資料數量與 RollWorks 的合約有關且受到其限制。</span><span class="sxs-lookup"><span data-stu-id="0b263-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="0b263-115">設定對 RollWorks 的連接</span><span class="sxs-lookup"><span data-stu-id="0b263-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="0b263-116">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="0b263-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0b263-117">選取 **新增連接**，然後選擇 **RollWorks** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="0b263-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="0b263-118">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="0b263-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0b263-119">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="0b263-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0b263-120">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="0b263-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0b263-121">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="0b263-121">Choose who can use this connection.</span></span> <span data-ttu-id="0b263-122">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="0b263-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0b263-123">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="0b263-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0b263-124">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="0b263-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0b263-125">選取 **連接** 來初始化與 RollWorks 的連接。</span><span class="sxs-lookup"><span data-stu-id="0b263-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="0b263-126">選取 **與 RollWorks 驗證**，並提供系統管理員認證給 RollWorks。</span><span class="sxs-lookup"><span data-stu-id="0b263-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="0b263-127">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="0b263-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0b263-128">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="0b263-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0b263-129">設定匯出</span><span class="sxs-lookup"><span data-stu-id="0b263-129">Configure an export</span></span>

<span data-ttu-id="0b263-130">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="0b263-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0b263-131">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="0b263-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0b263-132">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="0b263-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0b263-133">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="0b263-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0b263-134">在 **匯出的連結** 欄位中，在 RollWorks 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="0b263-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="0b263-135">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="0b263-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0b263-136">輸入您的 **RollWorks 廣告客戶識別碼** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)。</span><span class="sxs-lookup"><span data-stu-id="0b263-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="0b263-137">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="0b263-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0b263-138">這必須匯出客戶細分到 RollWorks。</span><span class="sxs-lookup"><span data-stu-id="0b263-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="0b263-139">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="0b263-139">Select the segments you want to export.</span></span> <span data-ttu-id="0b263-140">選取一個包含最少 100 個成員的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="0b263-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="0b263-141">您無法匯出更小的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="0b263-141">You can't export smaller segments.</span></span> <span data-ttu-id="0b263-142">此外，會出一個客戶細分最大數量為每個匯出 250'000 個成員。</span><span class="sxs-lookup"><span data-stu-id="0b263-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="0b263-143">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="0b263-143">Select **Save**.</span></span>

<span data-ttu-id="0b263-144">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="0b263-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0b263-145">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="0b263-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0b263-146">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="0b263-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0b263-147">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="0b263-147">Data privacy and compliance</span></span>

<span data-ttu-id="0b263-148">當您啟用 Dynamics 365 Customer Insights 將資料傳輸至 RollWorks 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="0b263-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0b263-149">Microsoft 將會在您的指示下傳送這類資料，但是您必須負責確保 RollWorks 符合您可能會承擔的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="0b263-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0b263-150">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="0b263-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="0b263-151">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="0b263-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
