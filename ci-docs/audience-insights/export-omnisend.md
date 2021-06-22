---
title: 將 Customer Insights 資料匯出至 Omnisend
description: 了解如何設定連接並匯出至 Omnisend。
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124463"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="34e50-103">將客戶細分匯出至 Omnisend (預覽版)</span><span class="sxs-lookup"><span data-stu-id="34e50-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="34e50-104">將整合客戶個人資料的客戶細分匯出至 Omnisend，並用於行銷活動。</span><span class="sxs-lookup"><span data-stu-id="34e50-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34e50-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="34e50-105">Prerequisites</span></span>

-   <span data-ttu-id="34e50-106">您擁有一個 [Omnisend 帳戶](https://www.omnisend.com/)及對應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="34e50-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="34e50-107">您在對象見解中具有 [組態區域](segments.md) 權限。</span><span class="sxs-lookup"><span data-stu-id="34e50-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="34e50-108">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="34e50-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="34e50-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="34e50-109">Known limitations</span></span>

- <span data-ttu-id="34e50-110">您最多可以將每個匯出的 1 百萬設定檔匯出至 Omnisend，這最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="34e50-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="34e50-111">匯出到 Omnisend 時，會被限制為客戶細分。</span><span class="sxs-lookup"><span data-stu-id="34e50-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="34e50-112">您可以匯出至 Omnisend 的個人資料數量，視您和 Omnisend 的合約而定。</span><span class="sxs-lookup"><span data-stu-id="34e50-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="34e50-113">設定與 Omnisend 的連接</span><span class="sxs-lookup"><span data-stu-id="34e50-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="34e50-114">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="34e50-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="34e50-115">選取 **新增連接**，然後選擇 **Omnisend** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="34e50-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="34e50-116">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="34e50-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="34e50-117">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="34e50-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="34e50-118">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="34e50-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="34e50-119">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="34e50-119">Choose who can use this connection.</span></span> <span data-ttu-id="34e50-120">根據預設，只有系統管理員。</span><span class="sxs-lookup"><span data-stu-id="34e50-120">By default it's only administrators.</span></span> <span data-ttu-id="34e50-121">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="34e50-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="34e50-122">請輸入您的 [Omnisend API 金鑰](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="34e50-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="34e50-123">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="34e50-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="34e50-124">選取 **連接** 來初始化與 Omnisend 的連接。</span><span class="sxs-lookup"><span data-stu-id="34e50-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="34e50-125">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="34e50-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="34e50-126">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="34e50-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="34e50-127">設定匯出</span><span class="sxs-lookup"><span data-stu-id="34e50-127">Configure an export</span></span>

<span data-ttu-id="34e50-128">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="34e50-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="34e50-129">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="34e50-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="34e50-130">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="34e50-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="34e50-131">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="34e50-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="34e50-132">在 **匯出的連結** 欄位中，在 Omnisend 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="34e50-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="34e50-133">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="34e50-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="34e50-134">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="34e50-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="34e50-135">這必須匯出客戶細分到 Omnisend。</span><span class="sxs-lookup"><span data-stu-id="34e50-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="34e50-136">或者，您可以匯出名、姓、地址、國家/地區、市/鎮、縣/市、郵遞區號，以建立更多的個人化電子郵件。</span><span class="sxs-lookup"><span data-stu-id="34e50-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="34e50-137">選取 **新增屬性** 對應這些欄位。</span><span class="sxs-lookup"><span data-stu-id="34e50-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="34e50-138">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="34e50-138">Select **Save**.</span></span>

<span data-ttu-id="34e50-139">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="34e50-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="34e50-140">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="34e50-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="34e50-141">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="34e50-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="34e50-142">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="34e50-142">Data privacy and compliance</span></span>

<span data-ttu-id="34e50-143">當您啟用 Dynamics 365 Customer Insights 將資料傳輸至 Omnisend 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="34e50-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="34e50-144">Microsoft 將會在您的指示下傳送這類資料，但是您必須負責確保 Omnisend 符合您可能會承擔的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="34e50-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="34e50-145">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="34e50-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="34e50-146">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="34e50-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
