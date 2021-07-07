---
title: 將 Customer Insights 資料匯出到 ActiveCampaign
description: 了解如何設定連接並匯出到 ActiveCampaign。
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314587"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="888e1-103">匯出客戶細分到 ActiveCampaign (預覽版)</span><span class="sxs-lookup"><span data-stu-id="888e1-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="888e1-104">將整合客戶個人資料的客戶細分匯出到 ActiveCampaign ，並將其用在行銷活動上。</span><span class="sxs-lookup"><span data-stu-id="888e1-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="888e1-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="888e1-105">Prerequisites</span></span>

-   <span data-ttu-id="888e1-106">您有一個 [ActiveCampaign 帳戶](https://www.activecampaign.com/)和相應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="888e1-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="888e1-107">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="888e1-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="888e1-108">在匯出的客戶細分中，整合的客戶個人資料包含有電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="888e1-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="888e1-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="888e1-109">Known limitations</span></span>

- <span data-ttu-id="888e1-110">您最多可以匯出 1 百萬筆客戶個人資料到 ActiveCampaign，這可能需要 90 分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="888e1-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="888e1-111">匯出到 ActiveCampaign 僅限於客戶細分。</span><span class="sxs-lookup"><span data-stu-id="888e1-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="888e1-112">您可以匯出到 ActiveCampaign 的個人資料數量取決於您與 ActiveCampaign 的合約。</span><span class="sxs-lookup"><span data-stu-id="888e1-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="888e1-113">設定到 ActiveCampaign 的連接</span><span class="sxs-lookup"><span data-stu-id="888e1-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="888e1-114">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="888e1-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="888e1-115">選擇 **新增連接** 並選擇 **ActiveCampaign** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="888e1-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="888e1-116">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="888e1-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="888e1-117">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="888e1-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="888e1-118">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="888e1-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="888e1-119">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="888e1-119">Choose who can use this connection.</span></span> <span data-ttu-id="888e1-120">根據預設，只有系統管理員。</span><span class="sxs-lookup"><span data-stu-id="888e1-120">By default, it's only administrators.</span></span> <span data-ttu-id="888e1-121">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="888e1-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="888e1-122">輸入您的 [ActiveCampaign API 金鑰與 REST 端點主機名稱](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key)。</span><span class="sxs-lookup"><span data-stu-id="888e1-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="888e1-123">REST 端點主機名稱僅是主機名稱，沒有 https://。</span><span class="sxs-lookup"><span data-stu-id="888e1-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="888e1-124">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="888e1-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="888e1-125">選取 **連接** 來初始化 ActiveCampaign 連接。</span><span class="sxs-lookup"><span data-stu-id="888e1-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="888e1-126">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="888e1-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="888e1-127">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="888e1-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="888e1-128">設定匯出</span><span class="sxs-lookup"><span data-stu-id="888e1-128">Configure an export</span></span>

<span data-ttu-id="888e1-129">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="888e1-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="888e1-130">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="888e1-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="888e1-131">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="888e1-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="888e1-132">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="888e1-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="888e1-133">在 **匯出連接** 欄位中，從 ActiveCampaign 區段選擇連接。</span><span class="sxs-lookup"><span data-stu-id="888e1-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="888e1-134">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="888e1-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="888e1-135">輸入您的 [**ActiveCampaign 清單識別碼**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign)。</span><span class="sxs-lookup"><span data-stu-id="888e1-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="888e1-136">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="888e1-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="888e1-137">這需要匯出客戶細分到 ActiveCampaign。</span><span class="sxs-lookup"><span data-stu-id="888e1-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="888e1-138">或者，您可以匯出名字、姓氏和電話來建立更個人化的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="888e1-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="888e1-139">選取 新增屬性 對應這些欄位。</span><span class="sxs-lookup"><span data-stu-id="888e1-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="888e1-140">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="888e1-140">Select **Save**.</span></span>

<span data-ttu-id="888e1-141">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="888e1-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="888e1-142">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="888e1-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="888e1-143">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="888e1-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="888e1-144">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="888e1-144">Data privacy and compliance</span></span>

<span data-ttu-id="888e1-145">當您啟用 Dynamics 365 Customer Insights 將資料傳輸到 ActiveCampaign 時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在的敏感性資料 (例如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="888e1-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="888e1-146">Microsoft 將會依您的指示傳送這類資料，但是您必須負責確保 ActiveCampaign 符合您可能會承擔的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="888e1-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="888e1-147">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="888e1-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="888e1-148">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="888e1-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
