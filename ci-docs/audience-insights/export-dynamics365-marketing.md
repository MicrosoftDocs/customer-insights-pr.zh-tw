---
title: 匯出 Customer Insights 資料到 Dynamics 365 Marketing
description: 了解如何設定與 Dynamics 365 Marketing 的連接。
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643763"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="e2ba2-103">Dynamics 365 Marketing 的連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="e2ba2-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e2ba2-104">使用 [區段](segments.md) 產生行銷活動並使用 Dynamics 365 Marketing 聯絡特定族群的客戶。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="e2ba2-105">如需詳細資訊，請參閱 [透過 Dynamics 365 Marketing 使用 Dynamics 365 Customer Insights 中的區段](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="e2ba2-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="e2ba2-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="e2ba2-106">Prerequisite</span></span>

<span data-ttu-id="e2ba2-107">[從 Dynamics 365 Marketing 內嵌的 Common Data Service](connect-power-query.md) 連絡人記錄。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="e2ba2-108">設定 Marketing 的連接器</span><span class="sxs-lookup"><span data-stu-id="e2ba2-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="e2ba2-109">在對象見解中，前往 **系統管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e2ba2-110">在 **Dynamics 365 Marketing** 底下，選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="e2ba2-111">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e2ba2-112">在 **伺服器位址** 欄位中輸入組織的 Marketing URL。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="e2ba2-113">在 **伺服器管理帳戶** 區段中，選取 **登入**，然後選擇 Dynamics 365 Marketing 帳戶。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="e2ba2-114">將客戶識別碼欄位對應到 Dynamics 365 連絡人識別碼。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="e2ba2-115">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-115">Select **Next**.</span></span>

1. <span data-ttu-id="e2ba2-116">選擇一個或多個客戶細分。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="e2ba2-117">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e2ba2-118">匯出資料</span><span class="sxs-lookup"><span data-stu-id="e2ba2-118">Export the data</span></span>

<span data-ttu-id="e2ba2-119">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e2ba2-120">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="e2ba2-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
