---
title: 搜尋和篩選客戶設定檔
description: 快速尋找有關所指定屬性的統整客戶設定檔和篩選的相關資訊。
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597133"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="77c01-103">客戶設定檔：搜尋及篩選索引</span><span class="sxs-lookup"><span data-stu-id="77c01-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="77c01-104">統整您的客戶資料的結果是客戶設定檔實體，可提供整體客戶群的統整檢視。</span><span class="sxs-lookup"><span data-stu-id="77c01-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="77c01-105">若要快速 [尋找特定客戶或客戶群組的資訊](customer-profiles.md)，您可以在 **客戶** 頁面上設定 **搜尋** 和 **篩選** 功能。</span><span class="sxs-lookup"><span data-stu-id="77c01-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="77c01-106">請繼續閱讀，了解管理員如何在 **搜尋和篩選索引** 頁面上編輯屬性，以供使用者用來搜尋和篩選。</span><span class="sxs-lookup"><span data-stu-id="77c01-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77c01-107">![搜尋篩選](media/search-filter.png "搜尋篩選")</span><span class="sxs-lookup"><span data-stu-id="77c01-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="77c01-108">新增欄位並指定屬性</span><span class="sxs-lookup"><span data-stu-id="77c01-108">Add fields and specify attributes</span></span>

<span data-ttu-id="77c01-109">如果是第一次以系統管理員身分定義可搜尋屬性，則必須先定義索引欄位。</span><span class="sxs-lookup"><span data-stu-id="77c01-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="77c01-110">我們建議您在 **客戶** 頁面上選擇使用者可以用來搜尋和篩選客戶的所有屬性。</span><span class="sxs-lookup"><span data-stu-id="77c01-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="77c01-111">您只能指定在資料統整程序中所建立之客戶設定檔實體中存在的屬性。</span><span class="sxs-lookup"><span data-stu-id="77c01-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="77c01-112">開啟 **客戶** 頁面，然後選取 **搜尋和篩選索引**。</span><span class="sxs-lookup"><span data-stu-id="77c01-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="77c01-113">選取 **+ 新增** 以指定索引欄位。</span><span class="sxs-lookup"><span data-stu-id="77c01-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="77c01-114">在清單中選取您要新增為索引欄位的屬性。</span><span class="sxs-lookup"><span data-stu-id="77c01-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="77c01-115">您可以選取 **新增**，以新增更多的屬性。</span><span class="sxs-lookup"><span data-stu-id="77c01-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="77c01-116">您也可以選取 **移除** 符號，移除任何選取的屬性。</span><span class="sxs-lookup"><span data-stu-id="77c01-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="77c01-117">探索已建立索引的客戶欄位表格</span><span class="sxs-lookup"><span data-stu-id="77c01-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="77c01-118">表格中呈現下列資訊。</span><span class="sxs-lookup"><span data-stu-id="77c01-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="77c01-119">**名稱**：代表屬性出現在客戶設定檔實體中的名稱。</span><span class="sxs-lookup"><span data-stu-id="77c01-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="77c01-120">**資料類型**：指定資料類型為字串、數字或日期。</span><span class="sxs-lookup"><span data-stu-id="77c01-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="77c01-121">**包含在搜尋中**：指定此屬性是否可用於使用 **搜尋** 欄位在 **客戶** 頁面上搜尋客戶。</span><span class="sxs-lookup"><span data-stu-id="77c01-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="77c01-122">**新增篩選**：控制項以定義此屬性如何在 **客戶** 頁面上用於篩選。</span><span class="sxs-lookup"><span data-stu-id="77c01-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="77c01-123">編輯給定屬性的篩選選項</span><span class="sxs-lookup"><span data-stu-id="77c01-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="77c01-124">**客戶** 頁面的 **篩選** 功能表可以包括不同數目的屬性等級（例如，不同的年齡群組以篩選客戶）。</span><span class="sxs-lookup"><span data-stu-id="77c01-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="77c01-125">在 **搜尋和篩選索引** 頁面上，為給定的屬性選取 **新增篩選**。</span><span class="sxs-lookup"><span data-stu-id="77c01-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="77c01-126">您可以定義結果的數目以及組織的順序。</span><span class="sxs-lookup"><span data-stu-id="77c01-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="77c01-127">視屬性的資料類型而定，會顯示下列其中一個窗格。</span><span class="sxs-lookup"><span data-stu-id="77c01-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="77c01-128">字串類型屬性：指定 **字串篩選選項** 窗格上所需的結果數，以及組織這些結果所依據的順序原則。</span><span class="sxs-lookup"><span data-stu-id="77c01-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="77c01-129">數值類型屬性：指定 **數字篩選選項** 窗格上包含的間隔數，以及組織這些間隔所依據的順序原則。</span><span class="sxs-lookup"><span data-stu-id="77c01-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="77c01-130">日期類型屬性：指定 **日期篩選選項** 窗格上包含的間隔數，以及組織這些間隔所依據的順序原則。</span><span class="sxs-lookup"><span data-stu-id="77c01-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="77c01-131">選取 **儲存** 套用變更。</span><span class="sxs-lookup"><span data-stu-id="77c01-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="77c01-132">當您準備好套用您的設定時，請選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="77c01-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="77c01-133">後續步驟</span><span class="sxs-lookup"><span data-stu-id="77c01-133">Next steps</span></span>

<span data-ttu-id="77c01-134">移至 **客戶** 頁面以搜尋客戶設定檔，或使用索引欄位來查看所有客戶設定檔的子集。</span><span class="sxs-lookup"><span data-stu-id="77c01-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]