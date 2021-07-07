---
title: 透過 Power Query 連接器內嵌資料
description: 以 Power Query 為基礎的資料來源連接器。
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305881"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="24fea-103">連接至 Power Query 資料來源</span><span class="sxs-lookup"><span data-stu-id="24fea-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="24fea-104">Power Query 提供一組廣泛的連接器以擷取資料。</span><span class="sxs-lookup"><span data-stu-id="24fea-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="24fea-105">Dynamics 365 Customer Insights 支援大部分這些連接器。</span><span class="sxs-lookup"><span data-stu-id="24fea-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="24fea-106">新增以 Power Query 連接器為基礎的資料來源通常要依照下一節中所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="24fea-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="24fea-107">不過，視您使用的連接器而定，也需要不同的資訊。</span><span class="sxs-lookup"><span data-stu-id="24fea-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="24fea-108">如需詳細資訊，請參閱 [Power Query 連接器參考](/power-query/connectors/)中個別連接器的文件。</span><span class="sxs-lookup"><span data-stu-id="24fea-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="24fea-109">建立新的資料來源</span><span class="sxs-lookup"><span data-stu-id="24fea-109">Create a new data source</span></span>

1. <span data-ttu-id="24fea-110">在對象見解中，前往 **資料** > **資料來源**。</span><span class="sxs-lookup"><span data-stu-id="24fea-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="24fea-111">選取 **新增資料來源**。</span><span class="sxs-lookup"><span data-stu-id="24fea-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="24fea-112">選擇 **匯入資料** 方法，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="24fea-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="24fea-113">提供資料來源的 **名稱**，然後選取 **下一步** 以建立資料來源。</span><span class="sxs-lookup"><span data-stu-id="24fea-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="24fea-114">命名方針：</span><span class="sxs-lookup"><span data-stu-id="24fea-114">Name guidelines:</span></span> 
   - <span data-ttu-id="24fea-115">名稱必須以字母開頭。</span><span class="sxs-lookup"><span data-stu-id="24fea-115">Start with a letter.</span></span>
   - <span data-ttu-id="24fea-116">只能使用字母和數字。</span><span class="sxs-lookup"><span data-stu-id="24fea-116">Use letters and numbers only.</span></span> <span data-ttu-id="24fea-117">不可以使用空格和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="24fea-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="24fea-118">接受 3 到 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="24fea-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="24fea-119">選取其中一個[可用的連接器](#available-power-query-data-sources)。</span><span class="sxs-lookup"><span data-stu-id="24fea-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="24fea-120">在此範例中，我們選取 **文字/CSV** 連接器。</span><span class="sxs-lookup"><span data-stu-id="24fea-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="24fea-121">在所選連接器的 **連接設定** 中輸入必要的詳細資料，然後選取 **下一步** 以查看資料的預覽。</span><span class="sxs-lookup"><span data-stu-id="24fea-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="24fea-122">選取 **轉換資料**。</span><span class="sxs-lookup"><span data-stu-id="24fea-122">Select **Transform data**.</span></span> <span data-ttu-id="24fea-123">在此步驟中，您會將實體新增至資料來源中。</span><span class="sxs-lookup"><span data-stu-id="24fea-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="24fea-124">實體是資料集。</span><span class="sxs-lookup"><span data-stu-id="24fea-124">Entities are datasets.</span></span> <span data-ttu-id="24fea-125">如果您有包含多個資料集的資料庫，則每個資料集都是其自己的實體。</span><span class="sxs-lookup"><span data-stu-id="24fea-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="24fea-126">**Power Query - 編輯查詢** 對話方塊可讓您檢閱和精簡資料。</span><span class="sxs-lookup"><span data-stu-id="24fea-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="24fea-127">系統在所選取資料來源中識別的實體會出現在左窗格中。</span><span class="sxs-lookup"><span data-stu-id="24fea-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="24fea-128">![編輯查詢對話方塊](media/data-manager-configure-edit-queries.png "編輯查詢對話方塊")</span><span class="sxs-lookup"><span data-stu-id="24fea-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="24fea-129">您也可以轉換資料。</span><span class="sxs-lookup"><span data-stu-id="24fea-129">You can also transform your data.</span></span> <span data-ttu-id="24fea-130">選取要編輯或變換的實體。</span><span class="sxs-lookup"><span data-stu-id="24fea-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="24fea-131">使用 Power Query 視窗中的選項來套用變換。</span><span class="sxs-lookup"><span data-stu-id="24fea-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="24fea-132">每個轉換都會在 **套用的步驟** 底下列出。</span><span class="sxs-lookup"><span data-stu-id="24fea-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="24fea-133">Power Query 提供許多預建轉換選項。</span><span class="sxs-lookup"><span data-stu-id="24fea-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="24fea-134">如需詳細資訊，請參閱 [Power Query 轉換](/power-query/power-query-what-is-power-query#transformations)。</span><span class="sxs-lookup"><span data-stu-id="24fea-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="24fea-135">您可以在 **編輯查詢** 對話方塊中選取 **取得資料**，將其他實體新增至您的資料來源。</span><span class="sxs-lookup"><span data-stu-id="24fea-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="24fea-136">強烈建議您進行這些轉換：</span><span class="sxs-lookup"><span data-stu-id="24fea-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="24fea-137">如果您要從 CSV 檔案擷取資料，則第一列通常會包含標題。</span><span class="sxs-lookup"><span data-stu-id="24fea-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="24fea-138">移至 **轉換表格**，並選取 **以標題做為第一列**。</span><span class="sxs-lookup"><span data-stu-id="24fea-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="24fea-139">確定資料類型已正確設定。</span><span class="sxs-lookup"><span data-stu-id="24fea-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="24fea-140">選取 Power Query 視窗底端的 **儲存**，以儲存轉換。</span><span class="sxs-lookup"><span data-stu-id="24fea-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="24fea-141">儲存後，您會在 **資料** > **資料來源** 上找到您的資料來源。</span><span class="sxs-lookup"><span data-stu-id="24fea-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="24fea-142">在 **資料來源** 頁面上，您會發現新的資料來源處於 **重新整理** 狀態。</span><span class="sxs-lookup"><span data-stu-id="24fea-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="24fea-143">可用的 Power Query 資料來源</span><span class="sxs-lookup"><span data-stu-id="24fea-143">Available Power Query data sources</span></span>

<span data-ttu-id="24fea-144">如需可選來將資料匯入至 Customer Insights 之連接器的最新清單，請參閱 [Power Query 連接器參考](/power-query/connectors/)。</span><span class="sxs-lookup"><span data-stu-id="24fea-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="24fea-145">在 **Customer Insights (資料流程)** 欄中有核取記號的連接器可用來建立以 Power Query 為基礎的新資料來源。</span><span class="sxs-lookup"><span data-stu-id="24fea-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="24fea-146">檢閱特定連接器的文件，進一步了解其先決條件、限制及其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="24fea-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="24fea-147">編輯 Power Query 資料來源</span><span class="sxs-lookup"><span data-stu-id="24fea-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="24fea-148">您可能無法變更目前用於應用程式程序之一（例如 *區段化*、*比對* 或 *合併*）的資料來源。</span><span class="sxs-lookup"><span data-stu-id="24fea-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="24fea-149">您可以使用 **設定** 頁面來追蹤每個使用中程序的進度。</span><span class="sxs-lookup"><span data-stu-id="24fea-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="24fea-150">當程序完成時，您可以返回 **資料來源** 頁面並進行變更。</span><span class="sxs-lookup"><span data-stu-id="24fea-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="24fea-151">在對象見解中，前往 **資料** > **資料來源**。</span><span class="sxs-lookup"><span data-stu-id="24fea-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="24fea-152">在您要變更的資料來源旁邊選取垂直省略號，然後從下拉式功能表中選取 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="24fea-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the dropdown menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="24fea-153">![編輯選項](media/edit-option-data-sources.png "編輯選項")</span><span class="sxs-lookup"><span data-stu-id="24fea-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="24fea-154">在 **Power Query - 編輯查詢** 對話方塊中套用您的變更和轉換，如[建立新的資料來源](#create-a-new-data-source)一節中所述。</span><span class="sxs-lookup"><span data-stu-id="24fea-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="24fea-155">完成編輯後，選取 Power Query 中的 **儲存** 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="24fea-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]