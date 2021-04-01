---
title: 使用 Microsoft Graph 富集客戶設定檔
description: 使用 Microsoft Graph 的專有資料，使用品牌和興趣親和性來擴充您的客戶資料。
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: aa46dac4f9c0d27881371877b14a92a6725710da
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596443"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="62ce8-103">使用品牌和興趣親和性來擴充客戶設定檔 (預覽)</span><span class="sxs-lookup"><span data-stu-id="62ce8-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="62ce8-104">使用 Microsoft Graph 的專有資料，使用品牌和興趣親和性來擴充您的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="62ce8-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="62ce8-105">這些親和性是根據與客戶有類似人口統計資料之人員的資料所決定。</span><span class="sxs-lookup"><span data-stu-id="62ce8-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="62ce8-106">此資訊可協助您更清楚了解客戶，並根據客戶與特定品牌及興趣的親和性建立其區段。</span><span class="sxs-lookup"><span data-stu-id="62ce8-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="62ce8-107">請在對象見解中前往 **資料** > **擴充** 以便 [設定和檢視擴充](enrichment-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="62ce8-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="62ce8-108">若要設定品牌親和性擴充，請移至 **探索** 索引標籤 ，並選取 **品牌** 圖標上的 **擴充我的資料**。</span><span class="sxs-lookup"><span data-stu-id="62ce8-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="62ce8-109">若要設定興趣親和性擴充，請移至 **探索** 索引標籤 ，並選取 **興趣** 圖標上的 **擴充我的資料**。</span><span class="sxs-lookup"><span data-stu-id="62ce8-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="62ce8-110">![品牌與興趣圖標](media/BrandsInterest-tile-Hub.png "品牌與興趣圖標")</span><span class="sxs-lookup"><span data-stu-id="62ce8-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="62ce8-111">關於 Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="62ce8-111">About Microsoft Graph</span></span>

<span data-ttu-id="62ce8-112">我們使用 Microsoft Graph 的線上搜尋資料，在各種人口統計資料區段（依年限、性別或位置定義）尋找品牌和興趣親和性。</span><span class="sxs-lookup"><span data-stu-id="62ce8-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="62ce8-113">品牌或興趣的線上搜尋量，會決定人口統計區段對該品牌或興趣有多少親和性 (與其他區段相比)。</span><span class="sxs-lookup"><span data-stu-id="62ce8-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="62ce8-114">[深入了解 Microsoft Graph](/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="62ce8-114">[Learn more about Microsoft Graph](/graph/overview).</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="62ce8-115">親合性等級和分數</span><span class="sxs-lookup"><span data-stu-id="62ce8-115">Affinity level and score</span></span>

<span data-ttu-id="62ce8-116">每一個擴充的客戶設定檔，我們都提供兩個相關的值 – 親合性等級和親合性分數。</span><span class="sxs-lookup"><span data-stu-id="62ce8-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="62ce8-117">這些值可協助您判斷與其他人口統計資料段相比，該設定檔人口統計資料客戶細分、品牌或興趣的親和性強弱程度。</span><span class="sxs-lookup"><span data-stu-id="62ce8-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="62ce8-118">*親和性等級* 由四個等級所組成，而 *親和性分數* 是在對應親和性等級在 100 分範圍中的計算結果。</span><span class="sxs-lookup"><span data-stu-id="62ce8-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="62ce8-119">親和性等級</span><span class="sxs-lookup"><span data-stu-id="62ce8-119">Affinity level</span></span> |<span data-ttu-id="62ce8-120">親和性分數</span><span class="sxs-lookup"><span data-stu-id="62ce8-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="62ce8-121">非常高</span><span class="sxs-lookup"><span data-stu-id="62ce8-121">Very high</span></span>     | <span data-ttu-id="62ce8-122">85-100</span><span class="sxs-lookup"><span data-stu-id="62ce8-122">85-100</span></span>       |
|<span data-ttu-id="62ce8-123">高</span><span class="sxs-lookup"><span data-stu-id="62ce8-123">High</span></span>     | <span data-ttu-id="62ce8-124">70-84</span><span class="sxs-lookup"><span data-stu-id="62ce8-124">70-84</span></span>        |
|<span data-ttu-id="62ce8-125">中</span><span class="sxs-lookup"><span data-stu-id="62ce8-125">Medium</span></span>     | <span data-ttu-id="62ce8-126">35-69</span><span class="sxs-lookup"><span data-stu-id="62ce8-126">35-69</span></span>        |
|<span data-ttu-id="62ce8-127">低</span><span class="sxs-lookup"><span data-stu-id="62ce8-127">Low</span></span>     | <span data-ttu-id="62ce8-128">1-34</span><span class="sxs-lookup"><span data-stu-id="62ce8-128">1-34</span></span>        |

<span data-ttu-id="62ce8-129">根據您要測量親和性的細微程度，您可以使用親和性等級或分數。</span><span class="sxs-lookup"><span data-stu-id="62ce8-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="62ce8-130">親和性分數提供更精確的控制。</span><span class="sxs-lookup"><span data-stu-id="62ce8-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="62ce8-131">支援的國家/地區</span><span class="sxs-lookup"><span data-stu-id="62ce8-131">Supported countries/regions</span></span>

<span data-ttu-id="62ce8-132">我們目前支援下列國家/地區選項：澳大利亞、加拿大 (英文)、法國、德國、英國或美國 (英文)。</span><span class="sxs-lookup"><span data-stu-id="62ce8-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="62ce8-133">若要選取國家/地區，請開啟 **品牌擴充** 或 **興趣擴充**，然後選取 **國家/地區** 旁邊的 **變更**。</span><span class="sxs-lookup"><span data-stu-id="62ce8-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="62ce8-134">在 **國家/地區設定** 窗格中，選擇選項並選取 **套用**。</span><span class="sxs-lookup"><span data-stu-id="62ce8-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="62ce8-135">與國家/地區選取相關的影響</span><span class="sxs-lookup"><span data-stu-id="62ce8-135">Implications related to country selection</span></span>

- <span data-ttu-id="62ce8-136">當[選擇您的自有品牌](#define-your-brands-or-interests)時，系統會根據選取的國家或地區提供建議。</span><span class="sxs-lookup"><span data-stu-id="62ce8-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="62ce8-137">[選擇產業時](#define-your-brands-or-interests)，將得到與您選取的國家或地區最相關的品牌或興趣。</span><span class="sxs-lookup"><span data-stu-id="62ce8-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="62ce8-138">在[擴充設定檔](#refresh-enrichment)時，我們會針對選取的品牌和興趣資料用已取得的資料擴充所有客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="62ce8-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="62ce8-139">包括不在選取的國家或地區中的設定檔。</span><span class="sxs-lookup"><span data-stu-id="62ce8-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="62ce8-140">例如，當您選取德國時，如果我們在美國有適用於所選品牌及興趣的 Microsoft Graph 資料，則會擴充位於美國的設定檔。</span><span class="sxs-lookup"><span data-stu-id="62ce8-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="62ce8-141">設定擴充</span><span class="sxs-lookup"><span data-stu-id="62ce8-141">Configure Enrichment</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="62ce8-142">定義您的品牌或興趣</span><span class="sxs-lookup"><span data-stu-id="62ce8-142">Define your brands or interests</span></span>

<span data-ttu-id="62ce8-143">選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="62ce8-143">Select one of the following options:</span></span>

- <span data-ttu-id="62ce8-144">**產業**：系統會找出與您的行業相關的最上層品牌或興趣，並使用它們擴充您的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="62ce8-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="62ce8-145">**自行選擇**：從與您的組織最相關的品牌或興趣清單中，選取最多五個項目。</span><span class="sxs-lookup"><span data-stu-id="62ce8-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="62ce8-146">若要新增品牌或興趣，請在輸入區域中輸入，以依據符合的字詞取得建議。</span><span class="sxs-lookup"><span data-stu-id="62ce8-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="62ce8-147">如果我們未列出您要尋找的品牌或興趣，請使用 **建議** 連結向我們傳送意見。</span><span class="sxs-lookup"><span data-stu-id="62ce8-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="62ce8-148">查看擴充喜好設定</span><span class="sxs-lookup"><span data-stu-id="62ce8-148">Review enrichment preferences</span></span>

<span data-ttu-id="62ce8-149">查看預設的擴充喜好設定，並視需要加以更新。</span><span class="sxs-lookup"><span data-stu-id="62ce8-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="擴充喜好設定視窗的螢幕擷取畫面。":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="62ce8-151">選取要擴充的實體</span><span class="sxs-lookup"><span data-stu-id="62ce8-151">Select entity to enrich</span></span>

<span data-ttu-id="62ce8-152">選取 **擴充實體**，然後選擇要用 Microsoft Graph 中的公司資料進行擴充的資料集。</span><span class="sxs-lookup"><span data-stu-id="62ce8-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft Graph.</span></span> <span data-ttu-id="62ce8-153">您可以選取客戶實體來擴充所有的客戶設定檔，或選取客戶細分實體僅擴充位於該客戶細分的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="62ce8-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="62ce8-154">對應欄位</span><span class="sxs-lookup"><span data-stu-id="62ce8-154">Map your fields</span></span>

<span data-ttu-id="62ce8-155">對應統整客戶實體中的欄位，以定義您要讓系統用來擴充客戶資料的人口統計客戶細分。</span><span class="sxs-lookup"><span data-stu-id="62ce8-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="62ce8-156">對應國家/地區以及至少要出生日期或性別屬性。</span><span class="sxs-lookup"><span data-stu-id="62ce8-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="62ce8-157">此外，您至少必須對應一個市/鎮 (和縣/市) 或郵遞區號。</span><span class="sxs-lookup"><span data-stu-id="62ce8-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="62ce8-158">選取 **編輯** 以定義欄位對應，並在完成時選取 **套用**。</span><span class="sxs-lookup"><span data-stu-id="62ce8-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="62ce8-159">選取 **儲存** 來完成欄位對應。</span><span class="sxs-lookup"><span data-stu-id="62ce8-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="62ce8-160">支援下列格式和值，這些值不區分大小寫：</span><span class="sxs-lookup"><span data-stu-id="62ce8-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="62ce8-161">**出生日期**：建議在資料擷取期間，將出生日期轉換為日期時間類型。</span><span class="sxs-lookup"><span data-stu-id="62ce8-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="62ce8-162">或者，也可以是使用 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 格式 "yyyy-MM-dd" 或 "yyyy-MM-ddTHH:mm:ssZ" 的字串。</span><span class="sxs-lookup"><span data-stu-id="62ce8-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="62ce8-163">**性別**：男、女、未知</span><span class="sxs-lookup"><span data-stu-id="62ce8-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="62ce8-164">**郵遞區號**：美國的五位數字郵遞區號、其他地區的標準郵遞區號</span><span class="sxs-lookup"><span data-stu-id="62ce8-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="62ce8-165">**城市**：英文城市名稱</span><span class="sxs-lookup"><span data-stu-id="62ce8-165">**City**: City name in English</span></span>
- <span data-ttu-id="62ce8-166">**州/省**：美國和加拿大的兩字母縮寫。</span><span class="sxs-lookup"><span data-stu-id="62ce8-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="62ce8-167">澳大利亞的兩字母或三字母縮寫。</span><span class="sxs-lookup"><span data-stu-id="62ce8-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="62ce8-168">不適用於法國、德國或英國。</span><span class="sxs-lookup"><span data-stu-id="62ce8-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="62ce8-169">**國家/地區**：</span><span class="sxs-lookup"><span data-stu-id="62ce8-169">**Country/Region**:</span></span>

  - <span data-ttu-id="62ce8-170">US：美利堅合眾國、美國、USA、US、美國、美洲</span><span class="sxs-lookup"><span data-stu-id="62ce8-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="62ce8-171">CA：加拿大、CA</span><span class="sxs-lookup"><span data-stu-id="62ce8-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="62ce8-172">GB：英國、UK、大不列顛、GB、大不列顛與北愛爾蘭聯合王國、大不列顛聯合王國</span><span class="sxs-lookup"><span data-stu-id="62ce8-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="62ce8-173">AU：澳大利亞、AU、澳大利亞聯邦</span><span class="sxs-lookup"><span data-stu-id="62ce8-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="62ce8-174">FR：法國、FR、法蘭西共和國</span><span class="sxs-lookup"><span data-stu-id="62ce8-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="62ce8-175">DE：德國、德文、Deutschland、Allemagne、DE、德意志聯邦共和國、德意志共和國</span><span class="sxs-lookup"><span data-stu-id="62ce8-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="62ce8-176">重新整理擴充項目</span><span class="sxs-lookup"><span data-stu-id="62ce8-176">Refresh enrichment</span></span>

<span data-ttu-id="62ce8-177">在為人口統計設定品牌、興趣和欄位對應之後，請執行擴充。</span><span class="sxs-lookup"><span data-stu-id="62ce8-177">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="62ce8-178">若要開始此程序，請在品牌或興趣設定頁面上選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="62ce8-178">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="62ce8-179">此外，您還可以讓系統在排程的重新整理過程中自動執行擴充。</span><span class="sxs-lookup"><span data-stu-id="62ce8-179">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="62ce8-180">視您的客戶資料大小而定，可能需要數分鐘的時間才能完成擴充執行。</span><span class="sxs-lookup"><span data-stu-id="62ce8-180">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="62ce8-181">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="62ce8-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="62ce8-182">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="62ce8-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="62ce8-183">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="62ce8-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="62ce8-184">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="62ce8-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="62ce8-185">擴充結果</span><span class="sxs-lookup"><span data-stu-id="62ce8-185">Enrichment results</span></span>

<span data-ttu-id="62ce8-186">執行擴充程序之後，移至 **我的擴充內容** 以檢閱已擴充的客戶總數，以及擴充後客戶設定檔中的品牌或興趣明細。</span><span class="sxs-lookup"><span data-stu-id="62ce8-186">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="執行擴充程序之後的結果預覽":::

<span data-ttu-id="62ce8-188">在圖表中選取 **查看已擴充資料**，以查看擴充後的資料。</span><span class="sxs-lookup"><span data-stu-id="62ce8-188">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="62ce8-189">擴充的品牌資料會移至 **BrandAffinityFromMicrosoft** 實體。</span><span class="sxs-lookup"><span data-stu-id="62ce8-189">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="62ce8-190">興趣資料位於 **InterestAffinityFromMicrosoft** 實體中。</span><span class="sxs-lookup"><span data-stu-id="62ce8-190">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="62ce8-191">您也可以 **資料** > **實體** 的 **擴充** 群組中找到這些實體。</span><span class="sxs-lookup"><span data-stu-id="62ce8-191">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="62ce8-192">查看客戶卡片上的擴充資料</span><span class="sxs-lookup"><span data-stu-id="62ce8-192">See enrichment data on the customer card</span></span>

<span data-ttu-id="62ce8-193">您也可以在個別客戶卡片上查看品牌和興趣親和性。</span><span class="sxs-lookup"><span data-stu-id="62ce8-193">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="62ce8-194">移至 **客戶** 並選取客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="62ce8-194">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="62ce8-195">在客戶卡片中，您會發現該客戶人口統計設定檔中人員所喜好品牌或興趣的圖表。</span><span class="sxs-lookup"><span data-stu-id="62ce8-195">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="包含擴充資料的客戶卡片":::

## <a name="next-steps"></a><span data-ttu-id="62ce8-197">後續步驟</span><span class="sxs-lookup"><span data-stu-id="62ce8-197">Next steps</span></span>

<span data-ttu-id="62ce8-198">建立在您擴充的客戶資料之上。</span><span class="sxs-lookup"><span data-stu-id="62ce8-198">Build on top of your enriched customer data.</span></span> <span data-ttu-id="62ce8-199">建立[區段](segments.md)、[量值](measures.md)，甚至[匯出資料](export-destinations.md)，以便傳送個人化體驗給您的客戶。</span><span class="sxs-lookup"><span data-stu-id="62ce8-199">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]