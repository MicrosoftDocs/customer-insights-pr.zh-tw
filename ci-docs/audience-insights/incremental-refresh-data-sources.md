---
title: 對 Power Query 式資料來源的增量重新整理
description: 針對以 Power Query 為基礎的大型資料來源重新整理其新增及更新資料。
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 03f76bcfc7336d8430146e8a26ffa649c6a17db0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596811"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="6bae9-103">適用於以 Power Query 為基礎之資料來源的累加重新整理</span><span class="sxs-lookup"><span data-stu-id="6bae9-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="6bae9-104">對資料來源進行累加重新整理可提供下列好處：</span><span class="sxs-lookup"><span data-stu-id="6bae9-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="6bae9-105">**更快速的重新整理** -只有已變更的資料才會重新整理。</span><span class="sxs-lookup"><span data-stu-id="6bae9-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="6bae9-106">例如，您可能只會重新整理過去五天的歷史資料集。</span><span class="sxs-lookup"><span data-stu-id="6bae9-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="6bae9-107">**提高的可靠性** - 進行較小量的重新整理時，您不需要長時間維持與動態來源系統的連線，並可減少發生連線問題的風險。</span><span class="sxs-lookup"><span data-stu-id="6bae9-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="6bae9-108">**減少資源消耗** - 僅重新整理總體資料的一部分，才能更有效率地使用運算資源，並減少環境的磁碟使用量。</span><span class="sxs-lookup"><span data-stu-id="6bae9-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="6bae9-109">設定累加重新整理</span><span class="sxs-lookup"><span data-stu-id="6bae9-109">Configure incremental refresh</span></span>

<span data-ttu-id="6bae9-110">對象見解允許透過支援增量內嵌的 Power Query，對匯入的資料來源增量重新整理。</span><span class="sxs-lookup"><span data-stu-id="6bae9-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="6bae9-111">例如，包含日期和時間欄位 (表示資料記錄上次更新時間) 的 Azure SQL 資料庫。</span><span class="sxs-lookup"><span data-stu-id="6bae9-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="6bae9-112">[以 Power Query 為基礎建立新的資料來源](connect-power-query.md)。</span><span class="sxs-lookup"><span data-stu-id="6bae9-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="6bae9-113">提供資料來源的名稱。</span><span class="sxs-lookup"><span data-stu-id="6bae9-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="6bae9-114">選取支援增量重新整理的資料來源，例如 Azure SQL 資料庫。</span><span class="sxs-lookup"><span data-stu-id="6bae9-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="6bae9-115">選取要內嵌的實體或資料表。</span><span class="sxs-lookup"><span data-stu-id="6bae9-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="6bae9-116">完成轉換步驟，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="6bae9-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="6bae9-117">在 **設定增量重新整理** 對話方塊中，選取 **設定** 以開啟 **增量重新整理設定**。</span><span class="sxs-lookup"><span data-stu-id="6bae9-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="6bae9-118">如果您選取 **略過**，資料來源將會重新整理整個資料集。</span><span class="sxs-lookup"><span data-stu-id="6bae9-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="6bae9-119">您也可以編輯現有的資料來源，稍後再套用增量更新。</span><span class="sxs-lookup"><span data-stu-id="6bae9-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="6bae9-120">在 **增量重新整理設定** 中，您可以為所有在建立資料來源時選取的所有實體設定增量重新整理。</span><span class="sxs-lookup"><span data-stu-id="6bae9-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6bae9-121">![設定資料來源中的實體以進行增量重新整理](media/incremental-refresh-settings.png "設定資料來源中的實體以進行增量重新整理")</span><span class="sxs-lookup"><span data-stu-id="6bae9-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="6bae9-122">選取實體，並提供下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="6bae9-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="6bae9-123">**定義主索引鍵**：選取實體或資料表的主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="6bae9-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="6bae9-124">**定義 [上次更新] 欄位**：此欄位只會顯示日期或時間類型的屬性。</span><span class="sxs-lookup"><span data-stu-id="6bae9-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="6bae9-125">選取表示記錄上次更新時間的屬性。</span><span class="sxs-lookup"><span data-stu-id="6bae9-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="6bae9-126">這會用來找出落在累加重新整理時間範圍內的記錄。</span><span class="sxs-lookup"><span data-stu-id="6bae9-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="6bae9-127">**檢查更新間隔**：指定您想要的增量重新整理時間範圍的時間長度。</span><span class="sxs-lookup"><span data-stu-id="6bae9-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="6bae9-128">選取 **儲存** 以完成建立資料來源的作業。</span><span class="sxs-lookup"><span data-stu-id="6bae9-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="6bae9-129">初始資料重新整理會是完整重新整理。</span><span class="sxs-lookup"><span data-stu-id="6bae9-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="6bae9-130">此後，增量資料重新整理會依照上一個步驟中所設定的方式進行。</span><span class="sxs-lookup"><span data-stu-id="6bae9-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]