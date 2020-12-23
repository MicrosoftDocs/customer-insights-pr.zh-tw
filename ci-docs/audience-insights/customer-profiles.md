---
title: 檢視客戶設定檔
description: 取得您的統一客戶資料的組合視圖。
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653880"
---
# <a name="customer-profiles"></a><span data-ttu-id="72522-103">客戶設定檔</span><span class="sxs-lookup"><span data-stu-id="72522-103">Customer profiles</span></span>

<span data-ttu-id="72522-104">**客戶** 頁面會根據從 [所有資料來源](data-sources.md) 收集的設定檔資料顯示您的客戶的組合視圖。</span><span class="sxs-lookup"><span data-stu-id="72522-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="72522-105">[建立統整的客戶實體](data-unification.md)之後，客戶設定檔即可供使用。</span><span class="sxs-lookup"><span data-stu-id="72522-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="72522-106">請確定您已完成資料統整程序，以獲得更豐富的客戶檢視表。</span><span class="sxs-lookup"><span data-stu-id="72522-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="72522-107">頁面也可讓您搜尋客戶。</span><span class="sxs-lookup"><span data-stu-id="72522-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="72522-108">客戶可以是個人或組織 (預覽)。</span><span class="sxs-lookup"><span data-stu-id="72522-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="72522-109">每個客戶或組織設定檔都是以圖標表示。</span><span class="sxs-lookup"><span data-stu-id="72522-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="72522-110">選取一個圖標以查看該特定客戶或組織的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="72522-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="72522-111">使用頁面底部的分頁控制項，查看任何記錄。</span><span class="sxs-lookup"><span data-stu-id="72522-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="72522-112">![B2C 客戶設定檔](media/profiles-customers.png "B2C 客戶設定檔")</span><span class="sxs-lookup"><span data-stu-id="72522-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="72522-113">組織 (預覽)</span><span class="sxs-lookup"><span data-stu-id="72522-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="72522-114">![B2B 客戶設定檔](media/profile-customers-b2b.png "B2B 客戶設定檔")</span><span class="sxs-lookup"><span data-stu-id="72522-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="72522-115">如果您在導覽中選 **客戶** 時看不到圖標，系統管理員必須在 **搜尋和篩選索引** 中[至少定義一個可搜尋屬性](search-filter-index.md)。</span><span class="sxs-lookup"><span data-stu-id="72522-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="72522-116">搜尋客戶</span><span class="sxs-lookup"><span data-stu-id="72522-116">Search for customers</span></span>

<span data-ttu-id="72522-117">在搜尋方塊中輸入名稱或其他屬性，以搜尋客戶。</span><span class="sxs-lookup"><span data-stu-id="72522-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="72522-118">搜尋只能在資料統整處理期間建立的客戶設定檔實體中運作。</span><span class="sxs-lookup"><span data-stu-id="72522-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="72522-119">做為系統管理員，您可以使用 **搜尋和篩選索引** 頁面來設定可搜尋的屬性。</span><span class="sxs-lookup"><span data-stu-id="72522-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="72522-120">如需詳細資訊，請參閱[管理搜尋和篩選索引](search-filter-index.md)。</span><span class="sxs-lookup"><span data-stu-id="72522-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="72522-121">篩選客戶</span><span class="sxs-lookup"><span data-stu-id="72522-121">Filter customers</span></span>

<span data-ttu-id="72522-122">您可以依據客戶設定檔實體欄位來篩選客戶。</span><span class="sxs-lookup"><span data-stu-id="72522-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="72522-123">與搜尋類似，您的系統管理員必須使用 **搜尋和篩選索引** 頁面，將欄位定義為可篩選。</span><span class="sxs-lookup"><span data-stu-id="72522-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="72522-124">選取 **客戶** 頁面上的 **篩選**。</span><span class="sxs-lookup"><span data-stu-id="72522-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="72522-125">選取您要用來篩選客戶的屬性旁邊的方塊。</span><span class="sxs-lookup"><span data-stu-id="72522-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="72522-126">![客戶設定檔](media/profiles-customers3.png "客戶設定檔")</span><span class="sxs-lookup"><span data-stu-id="72522-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="72522-127">選取 **客戶** 頁面上的 **清除篩選條件** 移除您的篩選條件。</span><span class="sxs-lookup"><span data-stu-id="72522-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="72522-128">客戶詳細資料頁面</span><span class="sxs-lookup"><span data-stu-id="72522-128">Customer details page</span></span>

<span data-ttu-id="72522-129">選取任何客戶圖格打開 **客戶詳細資料頁面**。</span><span class="sxs-lookup"><span data-stu-id="72522-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="72522-130">此視圖表包含選取客戶的統一資訊。</span><span class="sxs-lookup"><span data-stu-id="72522-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="72522-131">客戶詳細資料包括：</span><span class="sxs-lookup"><span data-stu-id="72522-131">Customer details include:</span></span>

-   <span data-ttu-id="72522-132">**客戶設定檔圖格：** 此圖格顯示與統一客戶設定檔實體不同的值。</span><span class="sxs-lookup"><span data-stu-id="72522-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="72522-133">這些詳細資料會包括電子郵件地址、名稱、城市等等。</span><span class="sxs-lookup"><span data-stu-id="72522-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="72522-134">**潛在興趣、潛在品牌：** 顯示您是否已經組態第一方富集作用。</span><span class="sxs-lookup"><span data-stu-id="72522-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="72522-135">它代表客戶設定檔與此客戶可能有的類似設定檔的品牌潛在利益和關聯。</span><span class="sxs-lookup"><span data-stu-id="72522-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="72522-136">如需詳細資訊，請參閱[使用品牌及興趣同質性擴充客戶設定檔](enrichment-microsoft-graph.md)。</span><span class="sxs-lookup"><span data-stu-id="72522-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="72522-137">**量值：** 顯示您是否已經組態特定類型的一個或多個量值：客戶屬性量值。</span><span class="sxs-lookup"><span data-stu-id="72522-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="72522-138">它們包括圍繞您的客戶在個別客戶等級的 KPI 計算值。</span><span class="sxs-lookup"><span data-stu-id="72522-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="72522-139">如需詳細資訊，請見 [定義和管理量值](measures.md)。</span><span class="sxs-lookup"><span data-stu-id="72522-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="72522-140">**活動時間表：** 顯示您是否已組態活動。</span><span class="sxs-lookup"><span data-stu-id="72522-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="72522-141">時間表視圖包含最近一次活動開始，依時間先後排序的客戶活動。</span><span class="sxs-lookup"><span data-stu-id="72522-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="72522-142">如需詳細資訊，請參閱[客戶活動](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="72522-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="72522-143">選取 **返回客戶** 以退回客戶搜尋頁面。</span><span class="sxs-lookup"><span data-stu-id="72522-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="72522-144">後續步驟</span><span class="sxs-lookup"><span data-stu-id="72522-144">Next steps</span></span>

<span data-ttu-id="72522-145">[新增其他資料來源](data-sources.md)或[建立客戶區段](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="72522-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>
