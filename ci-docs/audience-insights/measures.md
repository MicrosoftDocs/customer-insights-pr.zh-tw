---
title: 建立和管理量值
description: 定義要分析並反映商務效能的量值。
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269918"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="27c95-103">定義和管理量值</span><span class="sxs-lookup"><span data-stu-id="27c95-103">Define and manage measures</span></span>

<span data-ttu-id="27c95-104">量值可從 [整合設定檔](data-unification.md)擷取相關值，協助您更好地瞭解客戶行為和業務效能。</span><span class="sxs-lookup"><span data-stu-id="27c95-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="27c95-105">例如，公司想要查看 *每位客戶的總消費額* 瞭解每個客戶的購買歷史。</span><span class="sxs-lookup"><span data-stu-id="27c95-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="27c95-106">或衡量 *公司的總銷售額* 瞭解全部業務的彙總營收。</span><span class="sxs-lookup"><span data-stu-id="27c95-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="27c95-107">量值可以使用量值建立器工具 (一種包含各種運算子和簡單對應選項的資料查詢平臺) 建立。</span><span class="sxs-lookup"><span data-stu-id="27c95-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="27c95-108">它可讓您篩選資料、分組結果、偵測 [實體關聯路徑](relationships.md)，以及預覽輸出。</span><span class="sxs-lookup"><span data-stu-id="27c95-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="27c95-109">規劃商務活動時，您可以使用量值建立工具查詢客戶資料並抽取見解。</span><span class="sxs-lookup"><span data-stu-id="27c95-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="27c95-110">例如，建立 *每個客戶的總消費額* 以及 *每個客戶的總利潤額*，能協助找出大量消費額度高且利潤高的客戶。</span><span class="sxs-lookup"><span data-stu-id="27c95-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="27c95-111">您可以[建立一個區段](segments.md)來推動下一個最佳動作。</span><span class="sxs-lookup"><span data-stu-id="27c95-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="27c95-112">建立量值</span><span class="sxs-lookup"><span data-stu-id="27c95-112">Create a measure</span></span>

<span data-ttu-id="27c95-113">本節將引導您從頭開始建立新的量值。</span><span class="sxs-lookup"><span data-stu-id="27c95-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="27c95-114">以資料屬性建立量值，資料屬性來自的資料實體，已設定關聯連接到客戶實體。</span><span class="sxs-lookup"><span data-stu-id="27c95-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="27c95-115">請在對象見解中前往 **量值**。</span><span class="sxs-lookup"><span data-stu-id="27c95-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="27c95-116">選取 **新增**。</span><span class="sxs-lookup"><span data-stu-id="27c95-116">Select **New**.</span></span>

1. <span data-ttu-id="27c95-117">選取 **編輯名稱**，並提供量值的 **名稱**。</span><span class="sxs-lookup"><span data-stu-id="27c95-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="27c95-118">如果您的新量值設定只有兩個欄位 (例如：CustomerID 和一個計算)，則會在名稱為 Customer_Measure 的系統生成實體中將輸出新增為新資料行。</span><span class="sxs-lookup"><span data-stu-id="27c95-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="27c95-119">而且，您將可以在整合客戶設定檔中看到量值的值。</span><span class="sxs-lookup"><span data-stu-id="27c95-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="27c95-120">其他量值會生成自己的實體。</span><span class="sxs-lookup"><span data-stu-id="27c95-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="27c95-121">在設定區域中，於 **選取函數** 下拉式功能表中選擇彙總函式。</span><span class="sxs-lookup"><span data-stu-id="27c95-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="27c95-122">彙總函式包括：</span><span class="sxs-lookup"><span data-stu-id="27c95-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="27c95-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="27c95-123">**Sum**</span></span>
   - <span data-ttu-id="27c95-124">**平均值**</span><span class="sxs-lookup"><span data-stu-id="27c95-124">**Average**</span></span>
   - <span data-ttu-id="27c95-125">**計數**</span><span class="sxs-lookup"><span data-stu-id="27c95-125">**Count**</span></span>
   - <span data-ttu-id="27c95-126">**計數唯一**</span><span class="sxs-lookup"><span data-stu-id="27c95-126">**Count Unique**</span></span>
   - <span data-ttu-id="27c95-127">**最大**</span><span class="sxs-lookup"><span data-stu-id="27c95-127">**Max**</span></span>
   - <span data-ttu-id="27c95-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="27c95-128">**Min**</span></span>
   - <span data-ttu-id="27c95-129">**第一個**：提取資料記錄的第一個值</span><span class="sxs-lookup"><span data-stu-id="27c95-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="27c95-130">**最後一個**：提取新增至資料記錄的最後一個值</span><span class="sxs-lookup"><span data-stu-id="27c95-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="用於量值計算的運算子。":::

1. <span data-ttu-id="27c95-132">選取 **新增屬性** 來選取您要建立此量值所需的資料。</span><span class="sxs-lookup"><span data-stu-id="27c95-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="27c95-133">選取 **屬性** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="27c95-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="27c95-134">資料實體：選擇實體，其屬性是您想要測量的。</span><span class="sxs-lookup"><span data-stu-id="27c95-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="27c95-135">資料屬性：選擇要在彙總函式中用來計算量值的屬性。</span><span class="sxs-lookup"><span data-stu-id="27c95-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="27c95-136">您一次只能選取一個屬性。</span><span class="sxs-lookup"><span data-stu-id="27c95-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="27c95-137">透過 **量值** 索引標籤，您也可以選取從現有的量值中選取資料屬性。或者，您可以搜尋實體或量值名稱。</span><span class="sxs-lookup"><span data-stu-id="27c95-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="27c95-138">選取 **新增**，將選取的屬性新增至量值。</span><span class="sxs-lookup"><span data-stu-id="27c95-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="選取要在計算中使用的屬性。":::

1. <span data-ttu-id="27c95-140">若要建立更複雜的量值，您可以新增更多屬性，或在量值函數上使用數學運算子。</span><span class="sxs-lookup"><span data-stu-id="27c95-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="使用數學運算子建立複雜的量值。":::

1. <span data-ttu-id="27c95-142">若要新增篩選，請在設定區域中選取 **篩選**。</span><span class="sxs-lookup"><span data-stu-id="27c95-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="27c95-143">在 **篩選** 窗格的 **新增屬性** 區段中，選取您要用來建立篩選的屬性。</span><span class="sxs-lookup"><span data-stu-id="27c95-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="27c95-144">設定篩選運算子，為已選取的每個屬性定義篩選。</span><span class="sxs-lookup"><span data-stu-id="27c95-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="27c95-145">選取 **套用**，新增篩選至量值。</span><span class="sxs-lookup"><span data-stu-id="27c95-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="27c95-146">若要新增維度，請在設定區域中選取 **維度**。</span><span class="sxs-lookup"><span data-stu-id="27c95-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="27c95-147">在量值輸出實體中，維度將顯示為欄。</span><span class="sxs-lookup"><span data-stu-id="27c95-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="27c95-148">選取 **編輯維度**，以新增您要用來分組量值的資料屬性。</span><span class="sxs-lookup"><span data-stu-id="27c95-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="27c95-149">例如市/鎮或性別。</span><span class="sxs-lookup"><span data-stu-id="27c95-149">For example, city or gender.</span></span> <span data-ttu-id="27c95-150">根據預設，會選取 *CustomerID* 維度以建立 *客戶層級的量值*。</span><span class="sxs-lookup"><span data-stu-id="27c95-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="27c95-151">如果您要建立 *業務層級的量值*，您可以移除預設維度。</span><span class="sxs-lookup"><span data-stu-id="27c95-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="27c95-152">選取 **完成**，新增維度至量值。</span><span class="sxs-lookup"><span data-stu-id="27c95-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="27c95-153">如果已對應的資料實體與客戶實體之間有多個路徑，您必須選擇一個已識別的[實體關聯路徑](relationships.md)。</span><span class="sxs-lookup"><span data-stu-id="27c95-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="27c95-154">視所選取的路徑而定，量值結果可能會不同。</span><span class="sxs-lookup"><span data-stu-id="27c95-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="27c95-155">選取 **資料喜好設定**，然後選擇應該用來識別量值的實體路徑。</span><span class="sxs-lookup"><span data-stu-id="27c95-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="27c95-156">選取 **完成** 以套用至您的選取。</span><span class="sxs-lookup"><span data-stu-id="27c95-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="為量值選取實體路徑。":::

1. <span data-ttu-id="27c95-158">若要對量值新增更多計算，請選取 **新增計算**。</span><span class="sxs-lookup"><span data-stu-id="27c95-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="27c95-159">要使用實體進行新的計算，您只能在相同實體路徑進行。</span><span class="sxs-lookup"><span data-stu-id="27c95-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="27c95-160">在量值輸出實體中，更多計算將顯示為新的欄。</span><span class="sxs-lookup"><span data-stu-id="27c95-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="27c95-161">選取計算上的 **...**，從量值 **複製**、**重新命名** 或 **移除** 計算。</span><span class="sxs-lookup"><span data-stu-id="27c95-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="27c95-162">在 **預覽** 區域中，您會看到量值輸出實體的資料架構，其中包括篩選和維度。</span><span class="sxs-lookup"><span data-stu-id="27c95-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="27c95-163">預覽會動態反應設定中的變更。</span><span class="sxs-lookup"><span data-stu-id="27c95-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="27c95-164">選取 **執行**，為設定完成的量值計算結果。</span><span class="sxs-lookup"><span data-stu-id="27c95-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="27c95-165">如果您要保留目前的設定稍後執行測量，請選取 **儲存後關閉**。</span><span class="sxs-lookup"><span data-stu-id="27c95-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="27c95-166">移至 **量值**，以查看清單中的新建立的量值。</span><span class="sxs-lookup"><span data-stu-id="27c95-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="27c95-167">管理您的量值</span><span class="sxs-lookup"><span data-stu-id="27c95-167">Manage your measures</span></span>

<span data-ttu-id="27c95-168">至少 [建立一個量值](#create-a-measure)後，您將在 **量值** 頁面上看到量值清單。</span><span class="sxs-lookup"><span data-stu-id="27c95-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="27c95-169">您可以找到有關量值類型、建立者、建立日期、狀態及狀況的資訊。</span><span class="sxs-lookup"><span data-stu-id="27c95-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="27c95-170">當您從清單中選取量值時，您可以預覽輸出並下載 CSV 檔。</span><span class="sxs-lookup"><span data-stu-id="27c95-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="27c95-171">若要同時重新整理所有的量值，請選取 **全部重新整理**，而不選取特定的量值。</span><span class="sxs-lookup"><span data-stu-id="27c95-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="27c95-172">![管理單一量值的動作](media/measure-actions.png "管理單一量值的動作")</span><span class="sxs-lookup"><span data-stu-id="27c95-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="27c95-173">為下列選項，從清單中選取量值。</span><span class="sxs-lookup"><span data-stu-id="27c95-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="27c95-174">選取量值名稱以查看其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="27c95-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="27c95-175">**編輯** 量值的設定。</span><span class="sxs-lookup"><span data-stu-id="27c95-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="27c95-176">**重新整理** 根據最新資料的量值。</span><span class="sxs-lookup"><span data-stu-id="27c95-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="27c95-177">**重新命名** 量值。</span><span class="sxs-lookup"><span data-stu-id="27c95-177">**Rename** the measure.</span></span>
- <span data-ttu-id="27c95-178">**刪除** 量值。</span><span class="sxs-lookup"><span data-stu-id="27c95-178">**Delete** the measure.</span></span>
- <span data-ttu-id="27c95-179">**啟用** 或 **停用**。</span><span class="sxs-lookup"><span data-stu-id="27c95-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="27c95-180">停用量值時，不會在[排程的重新整理](system.md#schedule-tab)時進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="27c95-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="27c95-181">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="27c95-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="27c95-182">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="27c95-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="27c95-183">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="27c95-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="27c95-184">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="27c95-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="27c95-185">下一個步驟</span><span class="sxs-lookup"><span data-stu-id="27c95-185">Next step</span></span>

<span data-ttu-id="27c95-186">您可以使用現有的量值來建立[客戶細分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="27c95-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]