---
title: 將 Customer Insights 資料匯出至 Snapchat
description: 了解如何設定連接並匯出至 Snapchat。
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760485"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="eea7d-103">將客戶細分清單匯出至 Snapchat (預覽版)</span><span class="sxs-lookup"><span data-stu-id="eea7d-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="eea7d-104">將整合客戶個人資料的客戶細分匯出至 Snapchat，並用於廣告。</span><span class="sxs-lookup"><span data-stu-id="eea7d-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="eea7d-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="eea7d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="eea7d-106">您擁有 [Snapchat 商務帳號](https://business.snapchat.com/)、[Snapchat 廣告帳號](https://ads.snapchat.com/)以及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="eea7d-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="eea7d-107">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="eea7d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="eea7d-108">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="eea7d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="eea7d-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="eea7d-109">Known limitations</span></span>

- <span data-ttu-id="eea7d-110">匯出到 Snapchat 時，會被限制為客戶細分。</span><span class="sxs-lookup"><span data-stu-id="eea7d-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="eea7d-111">將最多 1 百萬筆個人資料匯出至 Snapchat 可能需要花費 15 分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="eea7d-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="eea7d-112">設定與 Snapchat 的連接</span><span class="sxs-lookup"><span data-stu-id="eea7d-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="eea7d-113">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="eea7d-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="eea7d-114">選取 **新增連接**，然後選擇 **Snapchat** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="eea7d-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="eea7d-115">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="eea7d-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="eea7d-116">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="eea7d-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="eea7d-117">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="eea7d-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="eea7d-118">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="eea7d-118">Choose who can use this connection.</span></span> <span data-ttu-id="eea7d-119">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="eea7d-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="eea7d-120">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="eea7d-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="eea7d-121">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="eea7d-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="eea7d-122">選取 **連接** 來初始化與 Snapchat 的連接。</span><span class="sxs-lookup"><span data-stu-id="eea7d-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="eea7d-123">選取 **與 Snapchat 驗證**，並提供系統管理員認證給 Snapchat。</span><span class="sxs-lookup"><span data-stu-id="eea7d-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="eea7d-124">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="eea7d-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="eea7d-125">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="eea7d-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="eea7d-126">設定匯出</span><span class="sxs-lookup"><span data-stu-id="eea7d-126">Configure an export</span></span>

<span data-ttu-id="eea7d-127">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="eea7d-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="eea7d-128">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="eea7d-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="eea7d-129">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="eea7d-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="eea7d-130">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="eea7d-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="eea7d-131">在 **匯出的連結** 欄位中，在 Snapchat 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="eea7d-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="eea7d-132">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="eea7d-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="eea7d-133">輸入 [**Snapchat 對象識別碼**](https://businesshelp.snapchat.com/s/article/custom-audiences)。</span><span class="sxs-lookup"><span data-stu-id="eea7d-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="eea7d-134">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="eea7d-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="eea7d-135">這必須匯出客戶細分到 Snapchat。</span><span class="sxs-lookup"><span data-stu-id="eea7d-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="eea7d-136">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="eea7d-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="eea7d-137">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="eea7d-137">Select **Save**.</span></span>

<span data-ttu-id="eea7d-138">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="eea7d-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="eea7d-139">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="eea7d-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="eea7d-140">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="eea7d-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="eea7d-141">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="eea7d-141">Data privacy and compliance</span></span>

<span data-ttu-id="eea7d-142">當您啟用 Dynamics 365 Customer Insights 將資料傳輸至 Snapchat 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="eea7d-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="eea7d-143">Microsoft 將會在您的指示下傳送這類資料，但是您必須負責確保 Snapchat 符合您可能會承擔的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="eea7d-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="eea7d-144">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="eea7d-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="eea7d-145">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="eea7d-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
