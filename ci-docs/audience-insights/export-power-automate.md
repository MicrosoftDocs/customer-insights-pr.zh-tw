---
title: Power Automate 連接器 | Microsoft Docs
description: 在 Dynamics 365 Customer Insights 中建立 Microsoft Power Automate 的流程。
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597915"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="a0185-103">Power Automate 連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="a0185-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="a0185-104">資料變更時觸發自動發生的特定事件，或直接在 [Power Automate](https://flow.microsoft.com/) 中管理更複雜的流程。</span><span class="sxs-lookup"><span data-stu-id="a0185-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="a0185-105">Power Automate 觸發程序</span><span class="sxs-lookup"><span data-stu-id="a0185-105">Power Automate triggers</span></span>

<span data-ttu-id="a0185-106">使用觸發程序來建立雲端流程並自動化重複工作，例如通知或更多進階動作。</span><span class="sxs-lookup"><span data-stu-id="a0185-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="a0185-107">當資料來源重新整理失敗時觸發。</span><span class="sxs-lookup"><span data-stu-id="a0185-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="a0185-108">當資料來源重新整理成功時觸發。</span><span class="sxs-lookup"><span data-stu-id="a0185-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="a0185-109">在區段上越過閾值時觸發。</span><span class="sxs-lookup"><span data-stu-id="a0185-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="a0185-110">觸發程序受限在需要超過閾值以上。</span><span class="sxs-lookup"><span data-stu-id="a0185-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="a0185-111">在業務量值上越過閾值時觸發。</span><span class="sxs-lookup"><span data-stu-id="a0185-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="a0185-112">觸發程序限制為必須超過閾值以上。</span><span class="sxs-lookup"><span data-stu-id="a0185-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="a0185-113">當完成 (資料來源、區段、量值，...) 的完整重新整理時，會引發發射鍵。</span><span class="sxs-lookup"><span data-stu-id="a0185-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="a0185-114">在完成統整程序 (對應、比對、合併) 機重新整理時觸發。</span><span class="sxs-lookup"><span data-stu-id="a0185-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="a0185-115">[在 Power Automate 中設定您的觸發程序](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)。</span><span class="sxs-lookup"><span data-stu-id="a0185-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="a0185-116">Power Automate 動作</span><span class="sxs-lookup"><span data-stu-id="a0185-116">Power Automate actions</span></span>
<span data-ttu-id="a0185-117">Power Automate 連接器提供可用觸發程序以外的動作。</span><span class="sxs-lookup"><span data-stu-id="a0185-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="a0185-118">如需詳細資訊，請參閱《[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)》。</span><span class="sxs-lookup"><span data-stu-id="a0185-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="a0185-119">建立 Power Automate 流程</span><span class="sxs-lookup"><span data-stu-id="a0185-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="a0185-120">在對象見解中，前往 **系統管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="a0185-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a0185-121">在 **Power Automate** 圖格中，選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="a0185-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="a0185-122">Power Automate 中的 Customer Insights 連結器 (preview) 開啟。</span><span class="sxs-lookup"><span data-stu-id="a0185-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="a0185-123">**登入** Power Automate。</span><span class="sxs-lookup"><span data-stu-id="a0185-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="a0185-124">選擇其中一個可用的觸發程序，並在新流程中新增更多步驟。</span><span class="sxs-lookup"><span data-stu-id="a0185-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="a0185-125">如需詳細資訊，請參閱[在 Power Automate 中建立雲端工作流程](/power-automate/get-started-logic-flow)。</span><span class="sxs-lookup"><span data-stu-id="a0185-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="a0185-126">如何使用流程的範例：</span><span class="sxs-lookup"><span data-stu-id="a0185-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="a0185-127">若資料來源重新整理失敗，請將訊息張貼到 Microsoft Teams 頻道。</span><span class="sxs-lookup"><span data-stu-id="a0185-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="a0185-128">達到客戶細分上的閾值時，將電子郵件傳送給資料負責人。</span><span class="sxs-lookup"><span data-stu-id="a0185-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]