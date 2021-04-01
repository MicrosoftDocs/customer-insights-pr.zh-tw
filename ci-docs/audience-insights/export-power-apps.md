---
title: Power Apps 連接器
description: 連接 Power Apps 和 Power Automate。
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598145"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="f24e7-103">Microsoft Power Apps 連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="f24e7-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="f24e7-104">透過 Power Apps 將統整的客戶設定檔帶入您的個人化應用程式。</span><span class="sxs-lookup"><span data-stu-id="f24e7-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="f24e7-105">連接 Power Apps 和 Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f24e7-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="f24e7-106">Customer Insights 是 [Power Apps 中許多可用資料來源](/powerapps/maker/canvas-apps/working-with-data-sources)之一。</span><span class="sxs-lookup"><span data-stu-id="f24e7-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="f24e7-107">請參閱 Power Apps 文件，了解如何[將資料連線新增至應用程式](/powerapps/maker/canvas-apps/add-data-connection)。</span><span class="sxs-lookup"><span data-stu-id="f24e7-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="f24e7-108">建議您另外檢閱 [Power Apps 如何使用委派來處理畫布應用程式中的大型資料集](/powerapps/maker/canvas-apps/delegation-overview)。</span><span class="sxs-lookup"><span data-stu-id="f24e7-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="f24e7-109">可用的實體</span><span class="sxs-lookup"><span data-stu-id="f24e7-109">Available entities</span></span>

<span data-ttu-id="f24e7-110">將 Customer Insights 新增為資料連線之後，您可以在 Power Apps 中選擇下列實體：</span><span class="sxs-lookup"><span data-stu-id="f24e7-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="f24e7-111">客戶：使用[統整客戶設定檔](customer-profiles.md)中的資料。</span><span class="sxs-lookup"><span data-stu-id="f24e7-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="f24e7-112">統整的活動：在應用程式上顯示[活動時間表](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="f24e7-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="f24e7-113">限制</span><span class="sxs-lookup"><span data-stu-id="f24e7-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="f24e7-114">可擷取的實體</span><span class="sxs-lookup"><span data-stu-id="f24e7-114">Retrievable entities</span></span>

<span data-ttu-id="f24e7-115">您只能透過 Power Apps 連接器擷取 **客戶**、**UnifiedActivity** 和 **客戶細分** 實體。</span><span class="sxs-lookup"><span data-stu-id="f24e7-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="f24e7-116">顯示其他實體，因為基礎連接器會透過 Power Automate 中的觸發程序支援這些實體。</span><span class="sxs-lookup"><span data-stu-id="f24e7-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="f24e7-117">委派</span><span class="sxs-lookup"><span data-stu-id="f24e7-117">Delegation</span></span>

<span data-ttu-id="f24e7-118">委派適用於客戶實體和 UnifiedActivity 實體。</span><span class="sxs-lookup"><span data-stu-id="f24e7-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="f24e7-119">**客戶** 實體的委派：若要使用此實體的委派，必須在 [搜尋 & 篩選條件索引](search-filter-index.md) 中編製欄位索引。</span><span class="sxs-lookup"><span data-stu-id="f24e7-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="f24e7-120">**UnifiedActivity** 的委派：此實體的委派僅適用於 **ActivityId** 和 **CustomerId** 欄位。</span><span class="sxs-lookup"><span data-stu-id="f24e7-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="f24e7-121">如需委派的詳細資訊，請參閱 [Power Apps 可委派的函數和作業](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps)。</span><span class="sxs-lookup"><span data-stu-id="f24e7-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="f24e7-122">範例庫控制項</span><span class="sxs-lookup"><span data-stu-id="f24e7-122">Example gallery control</span></span>

<span data-ttu-id="f24e7-123">例如，您將客戶設定檔新增到 [資源庫控制項](/powerapps/maker/canvas-apps/add-gallery)。</span><span class="sxs-lookup"><span data-stu-id="f24e7-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="f24e7-124">將 **資源庫** 控制項新增至您要建立的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f24e7-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f24e7-125">![新增資源庫元素](media/connector-powerapps9.png "新增資源庫元素")</span><span class="sxs-lookup"><span data-stu-id="f24e7-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="f24e7-126">選取 **客戶** 做為項目的資料來源。</span><span class="sxs-lookup"><span data-stu-id="f24e7-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f24e7-127">![選取資料來源](media/choose-datasource-powerapps.png "選取資料來源")</span><span class="sxs-lookup"><span data-stu-id="f24e7-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="f24e7-128">您可以在右邊變更資料面板，以選取要在資源庫上顯示之客戶實體欄位。</span><span class="sxs-lookup"><span data-stu-id="f24e7-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="f24e7-129">如果您想要在資源庫中顯示所選客戶的任何欄位，請填入標籤的 Text 屬性：**{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="f24e7-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="f24e7-130">範例：Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="f24e7-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="f24e7-131">若要顯示客戶的統整時間表，請新增資源庫元素，並新增 Items 屬性：**Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="f24e7-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="f24e7-132">範例：Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="f24e7-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]