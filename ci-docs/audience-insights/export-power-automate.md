---
title: Power Automate 連接器 | Microsoft Docs
description: 在 Microsoft Power Automate 中從 Dynamics 365 Customer Insights 建立流程。
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405237"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="65207-103">Power Automate 連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="65207-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="65207-104">資料變更時觸發自動發生的特定事件，或直接在 [Power Automate](https://flow.microsoft.com/) 中管理更複雜的流程。</span><span class="sxs-lookup"><span data-stu-id="65207-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="65207-105">Power Automate 觸發程序</span><span class="sxs-lookup"><span data-stu-id="65207-105">Power Automate triggers</span></span>

<span data-ttu-id="65207-106">您可以使用各種允許您建立流程的觸發程序來自動化重複性工作，例如通知或其他進階動作。</span><span class="sxs-lookup"><span data-stu-id="65207-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="65207-107">當資料來源重新整理失敗時觸發。</span><span class="sxs-lookup"><span data-stu-id="65207-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="65207-108">當資料來源重新整理成功時觸發。</span><span class="sxs-lookup"><span data-stu-id="65207-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="65207-109">在區段上越過閾值時觸發。</span><span class="sxs-lookup"><span data-stu-id="65207-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="65207-110">觸發程序受限在需要超過閾值以上。</span><span class="sxs-lookup"><span data-stu-id="65207-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="65207-111">在業務量值上越過閾值時觸發。</span><span class="sxs-lookup"><span data-stu-id="65207-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="65207-112">觸發程序限制為必須超過閾值以上。</span><span class="sxs-lookup"><span data-stu-id="65207-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="65207-113">當完成 (資料來源、區段、量值，...) 的完整重新整理時，會引發發射鍵。</span><span class="sxs-lookup"><span data-stu-id="65207-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="65207-114">在完成統整程序 (對應、比對、合併) 機重新整理時觸發。</span><span class="sxs-lookup"><span data-stu-id="65207-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="65207-115">[在 Power Automate 中設定您的觸發程序](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)。</span><span class="sxs-lookup"><span data-stu-id="65207-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="65207-116">Power Automate 動作</span><span class="sxs-lookup"><span data-stu-id="65207-116">Power Automate actions</span></span>
<span data-ttu-id="65207-117">Power Automate 連接器提供可用觸發程序以外的動作。</span><span class="sxs-lookup"><span data-stu-id="65207-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="65207-118">如需詳細資訊，請參閱《[Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)》。</span><span class="sxs-lookup"><span data-stu-id="65207-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="65207-119">在對象見解中建立 Power Automate 流程</span><span class="sxs-lookup"><span data-stu-id="65207-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="65207-120">請在對象見解中前往 **管理員** > **系統**。</span><span class="sxs-lookup"><span data-stu-id="65207-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="65207-121">在 **系統** 頁面上，選取 **狀態** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="65207-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="65207-122">在 **資料來源** 區段中，選取 **流程**，然後從下拉式清單中選取 **建立流程**。</span><span class="sxs-lookup"><span data-stu-id="65207-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65207-123">![顯示建立流程動作的 Power Automate 連接器](media/power-automate-connector-create-flow.png "顯示建立流程動作的 Power Automate 連接器")</span><span class="sxs-lookup"><span data-stu-id="65207-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="65207-124">在 Power Automate 中，選取其中一個可用的觸發程序，以建立您喜歡的流程。</span><span class="sxs-lookup"><span data-stu-id="65207-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="65207-125">如果您正在建立第一個流程，則必須先使用 Power Automate 連接器進行驗證。</span><span class="sxs-lookup"><span data-stu-id="65207-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
