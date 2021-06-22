---
title: 將 Customer Insights 資料匯出到 Microsoft Advertising
description: 了解如何設定連接並匯出至 Microsoft Advertising。
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124462"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="c1175-103">將客戶細分匯出至 Microsoft Advertising (預覽版)</span><span class="sxs-lookup"><span data-stu-id="c1175-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="c1175-104">將 Customer Insights 客戶細分匯出至 Microsoft Advertising，以建立客戶相符的對象。</span><span class="sxs-lookup"><span data-stu-id="c1175-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="c1175-105">將在您的廣告行銷活動使用這些對象。</span><span class="sxs-lookup"><span data-stu-id="c1175-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c1175-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="c1175-106">Prerequisites</span></span>

-   <span data-ttu-id="c1175-107">一個 [Microsoft Advertising 帳戶](https://ads.microsoft.com/)及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="c1175-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c1175-108">您接受了客戶比對的使用條款。</span><span class="sxs-lookup"><span data-stu-id="c1175-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="c1175-109">讚對象見解中[設定客戶細分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="c1175-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c1175-110">在匯出的客戶細分中，整合的客戶個人資料包含有電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="c1175-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c1175-111">已知限制</span><span class="sxs-lookup"><span data-stu-id="c1175-111">Known limitations</span></span>

- <span data-ttu-id="c1175-112">每筆匯出中您最多可以將 50 萬筆個人資料匯出至 Microsoft Advertising。</span><span class="sxs-lookup"><span data-stu-id="c1175-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="c1175-113">匯出到 Microsoft Advertising 會被限制為客戶細分。</span><span class="sxs-lookup"><span data-stu-id="c1175-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="c1175-114">將最多 50 萬筆個人資料匯出至 Microsoft Advertising 可能需要花費 10 分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="c1175-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="c1175-115">設定連線至 Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="c1175-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="c1175-116">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="c1175-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c1175-117">選取 **新增連接**，然後選擇 **Microsoft Advertising** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="c1175-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="c1175-118">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="c1175-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c1175-119">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="c1175-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c1175-120">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="c1175-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c1175-121">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="c1175-121">Choose who can use this connection.</span></span> <span data-ttu-id="c1175-122">預設為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c1175-122">The default is administrators.</span></span> <span data-ttu-id="c1175-123">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="c1175-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c1175-124">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="c1175-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c1175-125">選取 **連接** 來初始化與 Microsoft Advertising 的連接。</span><span class="sxs-lookup"><span data-stu-id="c1175-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="c1175-126">選取 **驗證 Microsoft Advertising**，並提供您的 Microsoft Advertising 管理認證。</span><span class="sxs-lookup"><span data-stu-id="c1175-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="c1175-127">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="c1175-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c1175-128">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="c1175-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c1175-129">設定匯出</span><span class="sxs-lookup"><span data-stu-id="c1175-129">Configure an export</span></span>

<span data-ttu-id="c1175-130">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="c1175-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c1175-131">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="c1175-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c1175-132">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="c1175-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c1175-133">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="c1175-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c1175-134">在 **匯出的連結** 欄位中，在 Microsoft Advertising 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="c1175-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="c1175-135">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="c1175-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c1175-136">選取要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="c1175-136">Select the segments to export.</span></span> <span data-ttu-id="c1175-137">會以選取要匯出的客戶細分名稱自動建立 Microsoft Advertising 中客戶比對的對象。</span><span class="sxs-lookup"><span data-stu-id="c1175-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="c1175-138">每一個客戶細分都會造成不同的客戶比對對象。</span><span class="sxs-lookup"><span data-stu-id="c1175-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="c1175-139">輸入您的 **Microsoft Advertising 客戶識別碼和帳戶識別碼**。</span><span class="sxs-lookup"><span data-stu-id="c1175-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="c1175-140">當您登入 Microsoft Advertising 時，您可以在 URL 的參數中找到客戶識別碼 (`cid`) 和帳戶識別碼 (`aid`)。</span><span class="sxs-lookup"><span data-stu-id="c1175-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="c1175-141">在 **資料比對** 區段的 **電子郵件** 欄位中，在您的整合客戶個人資料中，選取具備客戶的電子郵件地址欄位。</span><span class="sxs-lookup"><span data-stu-id="c1175-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="c1175-142">這必須匯出客戶細分到 Microsoft Advertising。</span><span class="sxs-lookup"><span data-stu-id="c1175-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="c1175-143">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="c1175-143">Select **Save**.</span></span>

<span data-ttu-id="c1175-144">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="c1175-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c1175-145">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="c1175-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c1175-146">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="c1175-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c1175-147">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="c1175-147">Data privacy and compliance</span></span>

<span data-ttu-id="c1175-148">當您啟用 Dynamics 365 Customer Insights 將資料傳輸至 Microsoft Advertising 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="c1175-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c1175-149">Microsoft 將會在您的指示下傳送這類資料，但是您必須負責確保 Microsoft Advertising符合您可能會承擔的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="c1175-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c1175-150">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="c1175-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c1175-151">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，停止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="c1175-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
