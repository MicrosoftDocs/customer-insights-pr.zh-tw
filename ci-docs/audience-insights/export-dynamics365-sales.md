---
title: 匯出 Customer Insights 資料到 Dynamics 365 Sales
description: 了解如何設定與 Dynamics 365 Sales 的連接。
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643808"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="ff19c-103">Dynamics 365 Sales 的連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="ff19c-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ff19c-104">使用您的客戶資料來建立行銷名單、追蹤工作流程，並透過 Dynamics 365 Sales 寄出促銷活動。</span><span class="sxs-lookup"><span data-stu-id="ff19c-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="ff19c-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="ff19c-105">Prerequisite</span></span>

<span data-ttu-id="ff19c-106">[從 Dynamics 365 Sales 內嵌使用 Common Data Service](connect-power-query.md) 的連絡人記錄。</span><span class="sxs-lookup"><span data-stu-id="ff19c-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="ff19c-107">設定 Sales 的連接器</span><span class="sxs-lookup"><span data-stu-id="ff19c-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="ff19c-108">在對象見解中，前往 **系統管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="ff19c-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ff19c-109">在 **Dynamics 365 Sales** 底下，選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="ff19c-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="ff19c-110">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="ff19c-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ff19c-111">在 **伺服器位址** 欄位中輸入組織的 Sales URL。</span><span class="sxs-lookup"><span data-stu-id="ff19c-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="ff19c-112">在 **伺服器管理帳戶** 區段中，選取 **登入**，然後選擇 Dynamics 365 Sales 帳戶。</span><span class="sxs-lookup"><span data-stu-id="ff19c-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="ff19c-113">將客戶識別碼欄位對應到 Dynamics 365 連絡人識別碼。</span><span class="sxs-lookup"><span data-stu-id="ff19c-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="ff19c-114">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="ff19c-114">Select **Next**.</span></span>

1. <span data-ttu-id="ff19c-115">選擇一個或多個客戶細分。</span><span class="sxs-lookup"><span data-stu-id="ff19c-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="ff19c-116">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="ff19c-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ff19c-117">匯出資料</span><span class="sxs-lookup"><span data-stu-id="ff19c-117">Export the data</span></span>

<span data-ttu-id="ff19c-118">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="ff19c-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ff19c-119">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="ff19c-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
