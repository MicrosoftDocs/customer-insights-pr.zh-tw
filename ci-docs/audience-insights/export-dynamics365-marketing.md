---
title: 匯出 Customer Insights 資料到 Dynamics 365 Marketing
description: 了解如何設定連接並匯出至 Dynamics 365 Marketing。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976790"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="4c2c8-103">在 Dynamics 365 Marketing 中使用客戶細分 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="4c2c8-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4c2c8-104">使用 [區段](segments.md) 產生行銷活動並使用 Dynamics 365 Marketing 聯絡特定族群的客戶。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="4c2c8-105">如需詳細資訊，請參閱 [透過 Dynamics 365 Marketing 使用 Dynamics 365 Customer Insights 中的區段](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="4c2c8-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="4c2c8-106">連接的先決條件</span><span class="sxs-lookup"><span data-stu-id="4c2c8-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="4c2c8-107">連絡人記錄必須在 Dynamics 365 Marketing 中，才能將客戶細分從 Customer Insights 匯出至 Marketing。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="4c2c8-108">瞭解如何[用 Common Data Services 在 Dynamics 365 Marketing 裡面](connect-power-query.md)內嵌連絡人 。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="4c2c8-109">將客戶細分中從對象見解中匯出到 Marketing，並不會在 Marketing 的執行個體中建立新的連絡人記錄。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="4c2c8-110">Marketing 中的連絡人記錄必須內嵌在對象見解中，並當成資料來源使用。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="4c2c8-111">他們也必須包含整合客戶實體中，才能客戶細分匯出前，先將客戶識別碼對應至連絡人的識別碼。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="4c2c8-112">設定對 Marketing 的連接</span><span class="sxs-lookup"><span data-stu-id="4c2c8-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="4c2c8-113">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4c2c8-114">選取 **新增連接**，然後選擇 **Dynamics 365 Marketing** 來設定連接。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="4c2c8-115">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4c2c8-116">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4c2c8-117">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4c2c8-118">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-118">Choose who can use this connection.</span></span> <span data-ttu-id="4c2c8-119">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4c2c8-120">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4c2c8-121">在 **伺服器位址** 欄位中輸入組織的 Marketing URL。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="4c2c8-122">在 **伺服器管理帳戶** 區段中，選取 **登入**，然後選擇 Dynamics 365 Marketing 帳戶。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="4c2c8-123">將客戶識別碼欄位對應到 Dynamics 365 連絡人識別碼。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="4c2c8-124">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="4c2c8-125">設定匯出</span><span class="sxs-lookup"><span data-stu-id="4c2c8-125">Configure an export</span></span>

<span data-ttu-id="4c2c8-126">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4c2c8-127">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4c2c8-128">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4c2c8-129">若要建立新的匯出，請選取 **新增目的地**。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4c2c8-130">在 **匯出的連結** 欄位中，在 Dynamics 365 Marketing 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="4c2c8-131">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4c2c8-132">選擇一個或多個客戶細分。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="4c2c8-133">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-133">Select **Save**.</span></span>

<span data-ttu-id="4c2c8-134">儲存匯出並不會立即執行匯出。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4c2c8-135">每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4c2c8-136">您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="4c2c8-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
