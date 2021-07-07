---
title: 將 Customer Insights 資料匯出到 Sendinblue
description: 了解如何設定連接並匯出到 Sendinblue。
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314586"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="b4a4c-103">匯出客戶細分到 Sendinblue (預覽版)</span><span class="sxs-lookup"><span data-stu-id="b4a4c-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="b4a4c-104">匯出整合個人資料的客戶細分，以使用 Sendinblue 建立行銷活動、提供電子郵件行銷，並使用特定客戶群組。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b4a4c-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="b4a4c-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="b4a4c-106">您有一個 [Sendinblue 帳戶](https://www.sendinblue.com/)和相應的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b4a4c-107">Sendinblue 中存在現有清單和相應的識別碼。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="b4a4c-108">您有 [組態的區段](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="b4a4c-109">匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b4a4c-110">已知限制</span><span class="sxs-lookup"><span data-stu-id="b4a4c-110">Known limitations</span></span>

- <span data-ttu-id="b4a4c-111">對多匯出 1 百萬個客戶個人資料到 Sendinblue。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="b4a4c-112">匯出到 Sendinblue 僅限於客戶細分。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="b4a4c-113">匯出總共 1 百萬筆個人資料的客戶細分最多可能需要 90 分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="b4a4c-114">您與 Sendinblue 的合約決定並限制您可以匯出到 Sendinblue 的個人資料數量。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="b4a4c-115">設定到 Sendinblue 連接</span><span class="sxs-lookup"><span data-stu-id="b4a4c-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="b4a4c-116">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b4a4c-117">選擇 **新增連接** 並選擇 **Sendinblue** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="b4a4c-118">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b4a4c-119">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b4a4c-120">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b4a4c-121">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-121">Choose who can use this connection.</span></span> <span data-ttu-id="b4a4c-122">根據預設，只有系統管理員。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-122">By default it's only administrators.</span></span> <span data-ttu-id="b4a4c-123">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b4a4c-124">請輸入 **[SendinBlue API 金鑰](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="b4a4c-125">選擇 **我同意** 確認 **資料隱私和合規性**，並選擇 **連接** 以初始化 Sendinblue 的連接。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="b4a4c-126">選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b4a4c-127">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b4a4c-128">設定匯出</span><span class="sxs-lookup"><span data-stu-id="b4a4c-128">Configure an export</span></span>

<span data-ttu-id="b4a4c-129">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b4a4c-130">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b4a4c-131">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b4a4c-132">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b4a4c-133">在 **匯出連接** 欄位中，從 Sendinblue 區段選擇連接。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="b4a4c-134">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b4a4c-135">輸入您的 **Sendinblue 清單識別碼**</span><span class="sxs-lookup"><span data-stu-id="b4a4c-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="b4a4c-136">在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="b4a4c-137">或者，您可以匯出 **名字**、**姓氏** 和 **電話** 建立更個人化的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="b4a4c-138">選取 **新增屬性** 對應這些欄位。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="b4a4c-139">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="b4a4c-140">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-140">Select **Save**.</span></span>

<span data-ttu-id="b4a4c-141">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b4a4c-142">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b4a4c-143">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b4a4c-144">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="b4a4c-144">Data privacy and compliance</span></span>

<span data-ttu-id="b4a4c-145">當您啟用 Dynamics 365 Customer Insights 將資料傳輸到 Sendinblue 時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在的敏感性資料 (例如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b4a4c-146">Microsoft 將會依您的指示傳送這類資料，但是您必須負責確保 Sendinblue 符合您可能會承擔的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b4a4c-147">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b4a4c-148">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b4a4c-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
