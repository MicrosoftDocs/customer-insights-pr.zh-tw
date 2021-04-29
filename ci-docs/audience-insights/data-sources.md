---
title: 使用資料來源內嵌資料
description: 了解如何從不同的來源匯入資料。
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887884"
---
# <a name="data-sources-overview"></a><span data-ttu-id="25aff-103">資料來源概觀</span><span class="sxs-lookup"><span data-stu-id="25aff-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="25aff-104">Dynamics 365 Customer Insights 中的對象見解功能從一組廣泛的來源集連接到資料。</span><span class="sxs-lookup"><span data-stu-id="25aff-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="25aff-105">連接至資料來源通常稱為 *資料擷取* 程序。</span><span class="sxs-lookup"><span data-stu-id="25aff-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="25aff-106">擷取資料之後，您可以對資料進行[統整](data-unification.md)並採取動作。</span><span class="sxs-lookup"><span data-stu-id="25aff-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="25aff-107">新增資料來源</span><span class="sxs-lookup"><span data-stu-id="25aff-107">Add a data source</span></span>

<span data-ttu-id="25aff-108">根據您所選擇的選項，參考有關如何新增資料來源的詳細文章。</span><span class="sxs-lookup"><span data-stu-id="25aff-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="25aff-109">有三種主要方式可以新增資料來源：</span><span class="sxs-lookup"><span data-stu-id="25aff-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="25aff-110">透過數十個 Power Query 連接器</span><span class="sxs-lookup"><span data-stu-id="25aff-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="25aff-111">從 Common Data Model 資料夾</span><span class="sxs-lookup"><span data-stu-id="25aff-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="25aff-112">從您自己的 Common Data Service 資料湖</span><span class="sxs-lookup"><span data-stu-id="25aff-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="25aff-113">從內部部署資料來源新增資料</span><span class="sxs-lookup"><span data-stu-id="25aff-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="25aff-114">Power Platform 資料流程支援在對象見解中從內部部署的資料來源內嵌資料。</span><span class="sxs-lookup"><span data-stu-id="25aff-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="25aff-115">設定環境時，[在 Microsoft Dataverse 提供環境 URL](manage-environments.md#create-an-environment-in-an-existing-organization)，便可以在 Customer Insights 中啟用資料流程。</span><span class="sxs-lookup"><span data-stu-id="25aff-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="25aff-116">將 Dataverse 環境與 Customer Insights 關聯之後，所建立的資料來源預設使用 [Power Platform 資料流程](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。</span><span class="sxs-lookup"><span data-stu-id="25aff-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="25aff-117">資料流程使用資料閘道來支援內部部署連線。</span><span class="sxs-lookup"><span data-stu-id="25aff-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="25aff-118">在關聯 Dataverse 環境之前已存在的資料來源，請移除並重新建立，以使用內部部署資料閘道。</span><span class="sxs-lookup"><span data-stu-id="25aff-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="25aff-119">來自現有 Power BI 或 Power Apps 環境的資料閘道將會顯示，並且可以在 Customer Insights 中重複使用。</span><span class="sxs-lookup"><span data-stu-id="25aff-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="25aff-120">資料來源頁面顯示的連結可前往 Power Platform 環境，並在其中查看和設定內部部署資料閘道。</span><span class="sxs-lookup"><span data-stu-id="25aff-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="資料來源頁面的螢幕擷取畫面，圖上為指向 Power Platform 環境的連結。":::

## <a name="review-ingested-data"></a><span data-ttu-id="25aff-122">檢閱擷取的資料</span><span class="sxs-lookup"><span data-stu-id="25aff-122">Review ingested data</span></span>

<span data-ttu-id="25aff-123">您會看到每個擷取資料來源的名稱、其狀態以及該來源上次重新整理資料的時間。</span><span class="sxs-lookup"><span data-stu-id="25aff-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="25aff-124">您可以依據各欄位排序資料來源清單。</span><span class="sxs-lookup"><span data-stu-id="25aff-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="25aff-125">![新增的資料來源](media/configure-data-datasource-added.png "新增的資料來源")</span><span class="sxs-lookup"><span data-stu-id="25aff-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="25aff-126">Status</span><span class="sxs-lookup"><span data-stu-id="25aff-126">Status</span></span>  |<span data-ttu-id="25aff-127">描述</span><span class="sxs-lookup"><span data-stu-id="25aff-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="25aff-128">成功</span><span class="sxs-lookup"><span data-stu-id="25aff-128">Successful</span></span>   |<span data-ttu-id="25aff-129">如果 **重新整理的** 欄位提到時間，代表已成功內嵌資料來源。</span><span class="sxs-lookup"><span data-stu-id="25aff-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="25aff-130">未開始</span><span class="sxs-lookup"><span data-stu-id="25aff-130">Not started</span></span>   |<span data-ttu-id="25aff-131">資料來源尚未內嵌任何資料或仍在草稿模式中。</span><span class="sxs-lookup"><span data-stu-id="25aff-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="25aff-132">正在重新整理</span><span class="sxs-lookup"><span data-stu-id="25aff-132">Refreshing</span></span>    |<span data-ttu-id="25aff-133">資料擷取進行中。</span><span class="sxs-lookup"><span data-stu-id="25aff-133">Data ingestion is in progress.</span></span> <span data-ttu-id="25aff-134">您可以選取 **動作** 欄中的 **停止重新整理** 來取消此作業。</span><span class="sxs-lookup"><span data-stu-id="25aff-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="25aff-135">停止重新整理資料來源會將它還原至上次重新整理的狀態。</span><span class="sxs-lookup"><span data-stu-id="25aff-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="25aff-136">失敗</span><span class="sxs-lookup"><span data-stu-id="25aff-136">Failed</span></span>     |<span data-ttu-id="25aff-137">資料擷取執行時遇到錯誤。</span><span class="sxs-lookup"><span data-stu-id="25aff-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="25aff-138">在任何資料來源中選取 **狀態** 欄中的值，以查看更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="25aff-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="25aff-139">在 **進度詳細資料** 窗格中，展開 **資料來源**。</span><span class="sxs-lookup"><span data-stu-id="25aff-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="25aff-140">請選取 **查看詳細資料** 來查看更新狀態的更多詳細資料，包括錯誤詳細資料與下游程序更新。</span><span class="sxs-lookup"><span data-stu-id="25aff-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="25aff-141">載入資料可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="25aff-141">Loading data can take some time.</span></span> <span data-ttu-id="25aff-142">成功重新整理之後，即可從 **實體** 頁面查看擷取的資料。</span><span class="sxs-lookup"><span data-stu-id="25aff-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="25aff-143">如需詳細資訊，請參閱[實體](entities.md)。</span><span class="sxs-lookup"><span data-stu-id="25aff-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="25aff-144">重新整理資料來源</span><span class="sxs-lookup"><span data-stu-id="25aff-144">Refresh a data source</span></span>

<span data-ttu-id="25aff-145">資料來源可自動排程或依照需要情況手動重新整理。</span><span class="sxs-lookup"><span data-stu-id="25aff-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="25aff-146">請前往 **管理員** > **系統** > [**排程**](system.md#schedule-tab)，組態您內嵌所有資料來源的重新整理排程。</span><span class="sxs-lookup"><span data-stu-id="25aff-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="25aff-147">若要依照需要重新整理資料來源，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="25aff-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="25aff-148">在對象見解中，前往 **資料** > **資料來源**</span><span class="sxs-lookup"><span data-stu-id="25aff-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="25aff-149">請選取您要重新整理資料來源旁邊的垂直刪節號並從下拉式選單選取 **重新整理**。</span><span class="sxs-lookup"><span data-stu-id="25aff-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="25aff-150">資料來源現在會針對手動重新整理觸發。</span><span class="sxs-lookup"><span data-stu-id="25aff-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="25aff-151">重新整理資料來源將會更新資料來源中所有指定實體的實體結構描述和資料。</span><span class="sxs-lookup"><span data-stu-id="25aff-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="25aff-152">如果您要取消現有的重新整理，且資料來源將恢復成上次重新整理狀態，請選取 **停止重新整理**。</span><span class="sxs-lookup"><span data-stu-id="25aff-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="25aff-153">刪除資料來源</span><span class="sxs-lookup"><span data-stu-id="25aff-153">Delete a data source</span></span>

1. <span data-ttu-id="25aff-154">在對象見解中，前往 **資料** > **資料來源**。</span><span class="sxs-lookup"><span data-stu-id="25aff-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="25aff-155">選取您想要移除的資料來源旁邊的垂直省略符號，然後從下拉式功能表中選取 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="25aff-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="25aff-156">確認刪除。</span><span class="sxs-lookup"><span data-stu-id="25aff-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
