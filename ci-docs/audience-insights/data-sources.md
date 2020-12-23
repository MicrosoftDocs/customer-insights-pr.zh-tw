---
title: 使用資料來源內嵌資料
description: 了解如何從不同的來源匯入資料。
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643943"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="d61a1-103">資料來源概觀</span><span class="sxs-lookup"><span data-stu-id="d61a1-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d61a1-104">Dynamics 365 Customer Insights 中的對象見解功能從一組廣泛的來源集連接到資料。</span><span class="sxs-lookup"><span data-stu-id="d61a1-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="d61a1-105">連接至資料來源通常稱為 *資料擷取* 程序。</span><span class="sxs-lookup"><span data-stu-id="d61a1-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="d61a1-106">擷取資料之後，您可以對資料進行[統整](data-unification.md)並採取動作。</span><span class="sxs-lookup"><span data-stu-id="d61a1-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="d61a1-107">新增資料來源</span><span class="sxs-lookup"><span data-stu-id="d61a1-107">Add a data source</span></span>

<span data-ttu-id="d61a1-108">根據您所選擇的選項，參考有關如何新增資料來源的詳細文章。</span><span class="sxs-lookup"><span data-stu-id="d61a1-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="d61a1-109">有三種主要方式可以新增資料來源：</span><span class="sxs-lookup"><span data-stu-id="d61a1-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="d61a1-110">透過數十個 Power Query 連接器</span><span class="sxs-lookup"><span data-stu-id="d61a1-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="d61a1-111">從 Common Data Model 資料夾</span><span class="sxs-lookup"><span data-stu-id="d61a1-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="d61a1-112">從您自己的 Common Data Service 資料湖</span><span class="sxs-lookup"><span data-stu-id="d61a1-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="d61a1-113">您目前無法從內部部署資料來源新增資料。</span><span class="sxs-lookup"><span data-stu-id="d61a1-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="d61a1-114">檢閱擷取的資料</span><span class="sxs-lookup"><span data-stu-id="d61a1-114">Review ingested data</span></span>

<span data-ttu-id="d61a1-115">您會看到每個擷取資料來源的名稱、其狀態以及該來源上次重新整理資料的時間。</span><span class="sxs-lookup"><span data-stu-id="d61a1-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="d61a1-116">您可以依據各欄位排序資料來源清單。</span><span class="sxs-lookup"><span data-stu-id="d61a1-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d61a1-117">![新增的資料來源](media/configure-data-datasource-added.png "新增的資料來源")</span><span class="sxs-lookup"><span data-stu-id="d61a1-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="d61a1-118">Status</span><span class="sxs-lookup"><span data-stu-id="d61a1-118">Status</span></span>  |<span data-ttu-id="d61a1-119">描述</span><span class="sxs-lookup"><span data-stu-id="d61a1-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d61a1-120">成功</span><span class="sxs-lookup"><span data-stu-id="d61a1-120">Successful</span></span>   |<span data-ttu-id="d61a1-121">如果 **重新整理的** 欄位提到時間，代表已成功內嵌資料來源。</span><span class="sxs-lookup"><span data-stu-id="d61a1-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="d61a1-122">未開始</span><span class="sxs-lookup"><span data-stu-id="d61a1-122">Not started</span></span>   |<span data-ttu-id="d61a1-123">資料來源尚未內嵌任何資料或仍在草稿模式中。</span><span class="sxs-lookup"><span data-stu-id="d61a1-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="d61a1-124">正在重新整理</span><span class="sxs-lookup"><span data-stu-id="d61a1-124">Refreshing</span></span>    |<span data-ttu-id="d61a1-125">資料擷取進行中。</span><span class="sxs-lookup"><span data-stu-id="d61a1-125">Data ingestion is in progress.</span></span> <span data-ttu-id="d61a1-126">您可以選取 **動作** 欄中的 **停止重新整理** 來取消此作業。</span><span class="sxs-lookup"><span data-stu-id="d61a1-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="d61a1-127">停止重新整理資料來源會將它還原至上次重新整理的狀態。</span><span class="sxs-lookup"><span data-stu-id="d61a1-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="d61a1-128">失敗</span><span class="sxs-lookup"><span data-stu-id="d61a1-128">Failed</span></span>     |<span data-ttu-id="d61a1-129">資料擷取執行時遇到錯誤。</span><span class="sxs-lookup"><span data-stu-id="d61a1-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="d61a1-130">請選取 **重新整理狀態** 查看更新狀態的更多詳細資料，包括錯誤詳細資料與下游流程更新。</span><span class="sxs-lookup"><span data-stu-id="d61a1-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="d61a1-131">載入資料可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="d61a1-131">Loading data can take some time.</span></span> <span data-ttu-id="d61a1-132">成功重新整理之後，即可從 **實體** 頁面查看擷取的資料。</span><span class="sxs-lookup"><span data-stu-id="d61a1-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="d61a1-133">如需詳細資訊，請參閱[實體](entities.md)。</span><span class="sxs-lookup"><span data-stu-id="d61a1-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="d61a1-134">重新整理資料來源</span><span class="sxs-lookup"><span data-stu-id="d61a1-134">Refresh a data source</span></span>

<span data-ttu-id="d61a1-135">資料來源可自動排程或依照需要情況手動重新整理。</span><span class="sxs-lookup"><span data-stu-id="d61a1-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="d61a1-136">請前往 **管理員** > **系統** > [**排程**](system.md#schedule-tab)，組態您內嵌所有資料來源的重新整理排程。</span><span class="sxs-lookup"><span data-stu-id="d61a1-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="d61a1-137">若要依照需要重新整理資料來源，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d61a1-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="d61a1-138">在對象見解中，前往 **資料** > **資料來源**</span><span class="sxs-lookup"><span data-stu-id="d61a1-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="d61a1-139">請選取您要重新整理資料來源旁邊的垂直刪節號並從下拉式選單選取 **重新整理**。</span><span class="sxs-lookup"><span data-stu-id="d61a1-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="d61a1-140">資料來源現在會針對手動重新整理觸發。</span><span class="sxs-lookup"><span data-stu-id="d61a1-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="d61a1-141">重新整理資料來源將更新實體結構描述和資料來源中所有指定實體的資料。</span><span class="sxs-lookup"><span data-stu-id="d61a1-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="d61a1-142">如果您要取消現有的重新整理，且資料來源將恢復成上次重新整理狀態，請選取 **停止重新整理**。</span><span class="sxs-lookup"><span data-stu-id="d61a1-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="d61a1-143">刪除資料來源</span><span class="sxs-lookup"><span data-stu-id="d61a1-143">Delete a data source</span></span>

1. <span data-ttu-id="d61a1-144">在對象見解中，前往 **資料** > **資料來源**。</span><span class="sxs-lookup"><span data-stu-id="d61a1-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d61a1-145">選取您想要移除的資料來源旁邊的垂直省略符號，然後從下拉式功能表中選取 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="d61a1-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="d61a1-146">確認刪除。</span><span class="sxs-lookup"><span data-stu-id="d61a1-146">Confirm your deletion.</span></span>
