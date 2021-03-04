---
title: 匯出 Customer Insights 資料到 Dynamics 365 Marketing
description: 了解如何設定與 Dynamics 365 Marketing 的連接。
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269044"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="dd4f6-103">Dynamics 365 Marketing 的連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="dd4f6-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="dd4f6-104">使用 [區段](segments.md) 產生行銷活動並使用 Dynamics 365 Marketing 聯絡特定族群的客戶。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="dd4f6-105">如需詳細資訊，請參閱 [透過 Dynamics 365 Marketing 使用 Dynamics 365 Customer Insights 中的區段](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="dd4f6-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="dd4f6-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="dd4f6-106">Prerequisite</span></span>

- <span data-ttu-id="dd4f6-107">連絡人記錄必須在 Dynamics 365 Marketing 中，才能將客戶細分從 Customer Insights 匯出至 Marketing。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="dd4f6-108">瞭解如何[用 Common Data Services 在 Dynamics 365 Marketing 裡面](connect-power-query.md)內嵌連絡人 。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="dd4f6-109">將客戶細分中從對象見解中匯出到 Marketing，並不會在 Marketing 的執行個體中建立新的連絡人記錄。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="dd4f6-110">Marketing 中的連絡人記錄必須內嵌在對象見解中，並當成資料來源使用。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="dd4f6-111">他們也必須包含整合客戶實體中，才能客戶細分匯出前，先將客戶識別碼對應至連絡人的識別碼。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="dd4f6-112">設定 Marketing 的連接器</span><span class="sxs-lookup"><span data-stu-id="dd4f6-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="dd4f6-113">在對象見解中，前往 **系統管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dd4f6-114">在 **Dynamics 365 Marketing** 底下，選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="dd4f6-115">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="dd4f6-116">在 **伺服器位址** 欄位中輸入組織的 Marketing URL。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="dd4f6-117">在 **伺服器管理帳戶** 區段中，選取 **登入**，然後選擇 Dynamics 365 Marketing 帳戶。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="dd4f6-118">將客戶識別碼欄位對應到 Dynamics 365 連絡人識別碼。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="dd4f6-119">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-119">Select **Next**.</span></span>

1. <span data-ttu-id="dd4f6-120">選擇一個或多個客戶細分。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="dd4f6-121">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dd4f6-122">匯出資料</span><span class="sxs-lookup"><span data-stu-id="dd4f6-122">Export the data</span></span>

<span data-ttu-id="dd4f6-123">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="dd4f6-124">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="dd4f6-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]