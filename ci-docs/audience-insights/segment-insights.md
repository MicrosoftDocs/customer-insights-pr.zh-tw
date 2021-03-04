---
title: 現有區段的區段見解
description: 洞察現有區段，以查看異同處。
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270010"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="1b3aa-103">客戶細分深入解析 (預覽)</span><span class="sxs-lookup"><span data-stu-id="1b3aa-103">Segment insights (preview)</span></span>

<span data-ttu-id="1b3aa-104">探索關於現有客戶細分的其他資訊與深入解析。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="1b3aa-105">找出兩個客戶細分的區別所在兩者的共同點。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="1b3aa-106">客戶細分重疊</span><span class="sxs-lookup"><span data-stu-id="1b3aa-106">Segment overlap</span></span>

<span data-ttu-id="1b3aa-107">客戶細分重疊分析會顯示兩個或更多客戶細分有哪些共同的客戶以及這些客戶的數量。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="1b3aa-108">例如，經常客戶的客戶細分如何與包含對服務或產品滿意之客戶的客戶細分重疊。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="1b3aa-109">您也可以分析特定屬性重疊變更的情況。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="1b3aa-110">執行重疊分析</span><span class="sxs-lookup"><span data-stu-id="1b3aa-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="1b3aa-111">移至 **客戶細分**，然後選取 **深入解析 (預覽)** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="1b3aa-112">選取 **新增**，並選擇 **選擇深入解析類型** 窗格中的 **重疊** 選項。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="1b3aa-113">選擇感興趣的客戶細分，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="1b3aa-114">或者，選擇一個或多個感興趣的欄位，以分析對每個可能欄位值的重疊，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="1b3aa-115">提供重疊分析的名稱、選擇性顯示名稱以及描述。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="1b3aa-116">選取 **儲存** 以開始進行分析。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="1b3aa-117">狀態從 [正在重新整理] 變更為 [成功] 時，重疊分析已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="1b3aa-118">檢視和最佳化重疊分析</span><span class="sxs-lookup"><span data-stu-id="1b3aa-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="1b3aa-119">完成分析之後，在 **客戶細分** > **深入解析 (預覽)** 中尋找有關此深入解析的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="客戶細分重疊深入解析詳細資料":::

<span data-ttu-id="1b3aa-121">選取深入解析以查看分析結果：</span><span class="sxs-lookup"><span data-stu-id="1b3aa-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="1b3aa-122">與所選要進行分析的客戶細分重疊的成員數目。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="1b3aa-123">包含在其中一個客戶細分中，但不在其餘客戶細分中成員的數目。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="1b3aa-124">如果您在設定重疊分析時已選取欄位，則會在對應的索引標籤中找到這些欄位。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="1b3aa-125">您可以使用篩選下拉式清單來選取任何感興趣的屬性層級，底端的表格將會顯示對應的資料。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="1b3aa-126">客戶細分獨特性</span><span class="sxs-lookup"><span data-stu-id="1b3aa-126">Segment differentiators</span></span>

<span data-ttu-id="1b3aa-127">客戶細分獨特性可協助您找出一個客戶細分與其餘客戶或與其他客戶細分的區別所在。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="1b3aa-128">您只需選取一個客戶細分，系統就會找出區分所選客戶細分的設定檔案屬性及量值。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="1b3aa-129">執行獨特性分析</span><span class="sxs-lookup"><span data-stu-id="1b3aa-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="1b3aa-130">移至 **客戶細分**，然後選取 **深入解析 (預覽)** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="1b3aa-131">選取 **新增**，並選擇 **選擇深入解析類型** 窗格中的 **重疊** 選項。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="1b3aa-132">選擇要做為 **主要客戶細分** 進行分析的客戶細分做為，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="1b3aa-133">選擇 **所有客戶** 或 **次要客戶細分** 來與主要客戶細分做比較，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="1b3aa-134">或者，選擇一個或多個感興趣的欄位，將注意力集中在分析特定屬性，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="1b3aa-135">提供重疊分析的名稱、選擇性顯示名稱以及描述。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="1b3aa-136">選取 **儲存** 以開始進行分析。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="1b3aa-137">狀態從 [正在重新整理] 變更為 [成功] 時，重疊分析已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="1b3aa-138">檢視和最佳化獨特性分析</span><span class="sxs-lookup"><span data-stu-id="1b3aa-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="1b3aa-139">完成分析之後，在 **客戶細分** > **深入解析 (預覽)** 中尋找有關此深入解析的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="客戶細分獨特性深入解析詳細資料":::

<span data-ttu-id="1b3aa-141">選取深入解析以查看分析結果。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="1b3aa-142">獨特性分析包含兩個索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="1b3aa-143">**屬性** 索引標籤列出視為獨特性的設定檔屬性。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="1b3aa-144">**量值** 索引標籤會列出獨特性。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="1b3aa-145">每個索引標籤都包含下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="1b3aa-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="1b3aa-146">獨特性的排名清單，依差異分數排序。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="1b3aa-147">每個獨特性的 **差異分數**。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="1b3aa-148">差異分數表示兩個客戶細分之間的屬性差異程度。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="1b3aa-149">差異分數越高，兩個客戶細分之間屬性就越不同。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="1b3aa-150">選取分數以開啟 **差異分數** 窗格，以及該屬性的值分佈。</span><span class="sxs-lookup"><span data-stu-id="1b3aa-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="1b3aa-151">管理客戶細分深入解析</span><span class="sxs-lookup"><span data-stu-id="1b3aa-151">Manage segment insights</span></span>

<span data-ttu-id="1b3aa-152">您可以從命令列對深入解析使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="1b3aa-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="1b3aa-153">**返回** 以返回深入解析清單</span><span class="sxs-lookup"><span data-stu-id="1b3aa-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="1b3aa-154">**重新整理** 以重新執行分析</span><span class="sxs-lookup"><span data-stu-id="1b3aa-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="1b3aa-155">**刪除** 以移除此深入解析</span><span class="sxs-lookup"><span data-stu-id="1b3aa-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]