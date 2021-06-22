---
title: 將 Customer Insights 資料匯出至 LinkedIn Ads
description: 了解如何設定連接並匯出至 LinkedIn Ads。
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124464"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="3f62a-103">將客戶細分匯出至 LinkedIn Ads (預覽版)</span><span class="sxs-lookup"><span data-stu-id="3f62a-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="3f62a-104">將整合客戶個人資料的客戶細分匯出至LinkedIn Ads，以建立符合的對象。</span><span class="sxs-lookup"><span data-stu-id="3f62a-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="3f62a-105">使用符合對象給公司鎖定和連絡人鎖定。</span><span class="sxs-lookup"><span data-stu-id="3f62a-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f62a-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="3f62a-106">Prerequisites</span></span>

-   <span data-ttu-id="3f62a-107">您擁有一個　[LinkedIn Campaign Manager 帳戶](https://business.linkedin.com/marketing-solutions/ads) 及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="3f62a-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3f62a-108">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="3f62a-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3f62a-109">在匯出客戶細分中的客戶個人資料，包含有電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="3f62a-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3f62a-110">已知限制</span><span class="sxs-lookup"><span data-stu-id="3f62a-110">Known limitations</span></span>

- <span data-ttu-id="3f62a-111">每次匯出中您最多可以將 10 萬筆個人資料匯出至 LinkedIn Ads。</span><span class="sxs-lookup"><span data-stu-id="3f62a-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="3f62a-112">匯出到 LinkedIn Ads 時，會被限制為客戶細分。</span><span class="sxs-lookup"><span data-stu-id="3f62a-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="3f62a-113">將最多 10 萬筆個人資料匯出至 LinkedIn Ads 可能需要花費 10 分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="3f62a-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="3f62a-114">設定連線至 LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="3f62a-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="3f62a-115">在對象見解中，移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="3f62a-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3f62a-116">選取 **新增連接**，然後選擇 **LinkedIn Ads** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="3f62a-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="3f62a-117">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="3f62a-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3f62a-118">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="3f62a-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3f62a-119">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="3f62a-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3f62a-120">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="3f62a-120">Choose who can use this connection.</span></span> <span data-ttu-id="3f62a-121">如果您不採取任何動作，預設值是系統管理員。</span><span class="sxs-lookup"><span data-stu-id="3f62a-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="3f62a-122">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="3f62a-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3f62a-123">提供您的 [LinkedIn Campaign Manager 帳戶識別碼](https://www.linkedin.com/help/lms/answer/a424270)。</span><span class="sxs-lookup"><span data-stu-id="3f62a-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="3f62a-124">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="3f62a-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3f62a-125">選取 **連接** 來初始化與 Campaign Monitor 的連接。</span><span class="sxs-lookup"><span data-stu-id="3f62a-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="3f62a-126">選取 **驗證 LinkedIn**，並提供 LinkedIn Campaign Manager 的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="3f62a-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="3f62a-127">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="3f62a-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3f62a-128">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="3f62a-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3f62a-129">設定匯出</span><span class="sxs-lookup"><span data-stu-id="3f62a-129">Configure an export</span></span>

<span data-ttu-id="3f62a-130">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="3f62a-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="3f62a-131">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="3f62a-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3f62a-132">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="3f62a-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3f62a-133">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="3f62a-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3f62a-134">在 **匯出的連結** 欄位中，在 LinkedIn Ads 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="3f62a-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="3f62a-135">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="3f62a-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3f62a-136">選擇您是否要匯出資料，以執行 LinkedIn 上的[連絡人鎖定](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting)或[公司鎖定](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)。</span><span class="sxs-lookup"><span data-stu-id="3f62a-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="3f62a-137">在 **資料比對** 區段的電子郵件欄位中，在您的整合客戶個人資料中，選取呈現客戶的電子郵件地址欄位。</span><span class="sxs-lookup"><span data-stu-id="3f62a-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3f62a-138">這必須匯出客戶細分到 LinkedIn Ads。</span><span class="sxs-lookup"><span data-stu-id="3f62a-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="3f62a-139">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="3f62a-139">Select the segments you want to export.</span></span> <span data-ttu-id="3f62a-140">使用您選取要匯出的區段名稱，LinkedIn Campaign Manager 中的符合對象會自動建立。</span><span class="sxs-lookup"><span data-stu-id="3f62a-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="3f62a-141">每一個客戶細分都會造成不同的符合對象。</span><span class="sxs-lookup"><span data-stu-id="3f62a-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="3f62a-142">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="3f62a-142">Select **Save**.</span></span>

<span data-ttu-id="3f62a-143">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="3f62a-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3f62a-144">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="3f62a-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3f62a-145">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="3f62a-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3f62a-146">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="3f62a-146">Data privacy and compliance</span></span>

<span data-ttu-id="3f62a-147">當您啟用 Dynamics 365 Customer Insights 將資料傳輸至 LinkedIn Ads 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="3f62a-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3f62a-148">Microsoft 將會在您的指示下傳送這類資料，但是您必須負責確保 LinkedIn Ads 符合您可能會承擔的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="3f62a-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="3f62a-149">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="3f62a-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="3f62a-150">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，停止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="3f62a-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
