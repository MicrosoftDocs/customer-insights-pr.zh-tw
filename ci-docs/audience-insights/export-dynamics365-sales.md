---
title: 匯出 Customer Insights 資料到 Dynamics 365 Sales
description: 了解如何設定連接並匯出至 Dynamics 365 Sales。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759581"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="1a40b-103">在 Dynamics 365 Sales 中使用客戶細分 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="1a40b-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1a40b-104">使用您的客戶資料來建立行銷名單、追蹤工作流程，並透過 Dynamics 365 Sales 寄出促銷活動。</span><span class="sxs-lookup"><span data-stu-id="1a40b-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="1a40b-105">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="1a40b-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="1a40b-106">連絡人記錄必須存在於Dynamics 365 Sales 中，才能將客戶細分從 Customer Insights 匯出至 Sales。</span><span class="sxs-lookup"><span data-stu-id="1a40b-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="1a40b-107">瞭解如何[使用 Common Data Services 在 Dynamics 365 Sales 裡面](connect-power-query.md)內嵌連絡人。</span><span class="sxs-lookup"><span data-stu-id="1a40b-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="1a40b-108">將客戶細分中從對象見解中匯出到 Sales，並不會在 Sales 的執行個體中建立新的連絡人記錄。</span><span class="sxs-lookup"><span data-stu-id="1a40b-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="1a40b-109">Sales 中的連絡人記錄必須內嵌在對象見解中，並作為資料來源使用。</span><span class="sxs-lookup"><span data-stu-id="1a40b-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="1a40b-110">他們也必須包含整合客戶實體中，才能客戶細分匯出前，先將客戶識別碼對應至連絡人的識別碼。</span><span class="sxs-lookup"><span data-stu-id="1a40b-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="1a40b-111">設定與 Sales 的連線</span><span class="sxs-lookup"><span data-stu-id="1a40b-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="1a40b-112">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="1a40b-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1a40b-113">選取 **新增連接**，然後選擇 **Dynamics 365 Sales** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="1a40b-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="1a40b-114">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="1a40b-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1a40b-115">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="1a40b-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1a40b-116">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="1a40b-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1a40b-117">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="1a40b-117">Choose who can use this connection.</span></span> <span data-ttu-id="1a40b-118">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="1a40b-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1a40b-119">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="1a40b-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1a40b-120">在 **伺服器位址** 欄位中輸入組織的 Sales URL。</span><span class="sxs-lookup"><span data-stu-id="1a40b-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="1a40b-121">在 **伺服器管理帳戶** 區段中，選取 **登入**，然後選擇 Dynamics 365 Sales 帳戶。</span><span class="sxs-lookup"><span data-stu-id="1a40b-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="1a40b-122">將客戶識別碼欄位對應到 Dynamics 365 連絡人識別碼。</span><span class="sxs-lookup"><span data-stu-id="1a40b-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="1a40b-123">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="1a40b-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="1a40b-124">設定匯出</span><span class="sxs-lookup"><span data-stu-id="1a40b-124">Configure an export</span></span>

<span data-ttu-id="1a40b-125">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="1a40b-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1a40b-126">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="1a40b-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1a40b-127">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="1a40b-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1a40b-128">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="1a40b-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1a40b-129">在 **匯出的連結** 欄位中，在 Dynamics 365 Sales 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="1a40b-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="1a40b-130">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="1a40b-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1a40b-131">選擇一個或多個客戶細分。</span><span class="sxs-lookup"><span data-stu-id="1a40b-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="1a40b-132">選取 **儲存**</span><span class="sxs-lookup"><span data-stu-id="1a40b-132">Select **Save**</span></span>

<span data-ttu-id="1a40b-133">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="1a40b-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1a40b-134">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="1a40b-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1a40b-135">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="1a40b-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
