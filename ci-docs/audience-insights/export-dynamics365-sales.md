---
title: 匯出 Customer Insights 資料到 Dynamics 365 Sales
description: 了解如何設定與 Dynamics 365 Sales 的連接。
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268998"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="de759-103">Dynamics 365 Sales 的連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="de759-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="de759-104">使用您的客戶資料來建立行銷名單、追蹤工作流程，並透過 Dynamics 365 Sales 寄出促銷活動。</span><span class="sxs-lookup"><span data-stu-id="de759-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="de759-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="de759-105">Prerequisite</span></span>

1. <span data-ttu-id="de759-106">連絡人記錄必須存在於Dynamics 365 Sales 中，才能將客戶細分從 Customer Insights 匯出至 Sales。</span><span class="sxs-lookup"><span data-stu-id="de759-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="de759-107">瞭解如何[使用 Common Data Services 在 Dynamics 365 Sales 裡面](connect-power-query.md)內嵌連絡人。</span><span class="sxs-lookup"><span data-stu-id="de759-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="de759-108">將客戶細分中從對象見解中匯出到 Sales，並不會在 Sales 的執行個體中建立新的連絡人記錄。</span><span class="sxs-lookup"><span data-stu-id="de759-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="de759-109">Sales 中的連絡人記錄必須內嵌在對象見解中，並作為資料來源使用。</span><span class="sxs-lookup"><span data-stu-id="de759-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="de759-110">他們也必須包含整合客戶實體中，才能客戶細分匯出前，先將客戶識別碼對應至連絡人的識別碼。</span><span class="sxs-lookup"><span data-stu-id="de759-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="de759-111">設定 Sales 的連接器</span><span class="sxs-lookup"><span data-stu-id="de759-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="de759-112">在對象見解中，前往 **系統管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="de759-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="de759-113">在 **Dynamics 365 Sales** 底下，選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="de759-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="de759-114">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="de759-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="de759-115">在 **伺服器位址** 欄位中輸入組織的 Sales URL。</span><span class="sxs-lookup"><span data-stu-id="de759-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="de759-116">在 **伺服器管理帳戶** 區段中，選取 **登入**，然後選擇 Dynamics 365 Sales 帳戶。</span><span class="sxs-lookup"><span data-stu-id="de759-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="de759-117">將客戶識別碼欄位對應到 Dynamics 365 連絡人識別碼。</span><span class="sxs-lookup"><span data-stu-id="de759-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="de759-118">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="de759-118">Select **Next**.</span></span>

1. <span data-ttu-id="de759-119">選擇一個或多個客戶細分。</span><span class="sxs-lookup"><span data-stu-id="de759-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="de759-120">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="de759-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="de759-121">匯出資料</span><span class="sxs-lookup"><span data-stu-id="de759-121">Export the data</span></span>

<span data-ttu-id="de759-122">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="de759-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="de759-123">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="de759-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]