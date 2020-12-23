---
title: 使用 Microsoft Graph 富集客戶設定檔
description: 使用 Microsoft Graph 的專有資料，使用品牌和興趣親和性來擴充您的客戶資料。
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405249"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="baf41-103">使用品牌和興趣親和性來擴充客戶設定檔 (預覽)</span><span class="sxs-lookup"><span data-stu-id="baf41-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="baf41-104">使用 Microsoft Graph 的專有資料，使用品牌和興趣親和性來擴充您的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="baf41-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="baf41-105">這些親和性是根據與客戶有類似人口統計資料之人員的資料所決定。</span><span class="sxs-lookup"><span data-stu-id="baf41-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="baf41-106">此資訊可協助您更清楚了解客戶，並根據客戶與特定品牌及興趣的親和性建立其區段。</span><span class="sxs-lookup"><span data-stu-id="baf41-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="baf41-107">請在對象見解中前往 **資料** > **富集** 以便 [組態和檢視富集群](enrichment-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="baf41-107">In ausience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="baf41-108">若要設定品牌親和性擴充，請移至 **探索** 索引標籤 ，並選取 **品牌** 圖標上的 **擴充我的資料**。</span><span class="sxs-lookup"><span data-stu-id="baf41-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="baf41-109">若要設定興趣親和性擴充，請移至 **探索** 索引標籤 ，並選取 **興趣** 圖標上的 **擴充我的資料**。</span><span class="sxs-lookup"><span data-stu-id="baf41-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="baf41-110">![品牌與興趣圖標](media/BrandsInterest-tile-Hub.png "品牌與興趣圖標")</span><span class="sxs-lookup"><span data-stu-id="baf41-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="baf41-111">關於 Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="baf41-111">About Microsoft Graph</span></span>

<span data-ttu-id="baf41-112">我們使用 Microsoft Graph 的線上搜尋資料，在各種人口統計資料區段（依年限、性別或位置定義）尋找品牌和興趣親和性。</span><span class="sxs-lookup"><span data-stu-id="baf41-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="baf41-113">品牌或興趣的線上搜尋量，會決定人口統計區段對該品牌或興趣有多少親和性 (與其他區段相比)。</span><span class="sxs-lookup"><span data-stu-id="baf41-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="baf41-114">[深入了解 Microsoft Graph](https://docs.microsoft.com/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="baf41-114">[Learn more about Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="affinity-score-and-confidence"></a><span data-ttu-id="baf41-115">親和性分數和信賴度</span><span class="sxs-lookup"><span data-stu-id="baf41-115">Affinity score and confidence</span></span>

<span data-ttu-id="baf41-116">**親和性分數** 是以 100 分為滿分來計算，100 表示對品牌或興趣有最高親和性的區段。</span><span class="sxs-lookup"><span data-stu-id="baf41-116">The **affinity score** is calculated on a 100-point scale, with 100 representing the segment that has the highest affinity for a brand or interest.</span></span>

<span data-ttu-id="baf41-117">**親和性信賴度** 也是以 100 分為滿分來計算。</span><span class="sxs-lookup"><span data-stu-id="baf41-117">The **affinity confidence** is also calculated on a 100-point scale.</span></span> <span data-ttu-id="baf41-118">它表示某個區段與該品牌或興趣有親和性的系統信賴度等級。</span><span class="sxs-lookup"><span data-stu-id="baf41-118">It indicates the system's confidence level that a segment has an affinity for the brand or interest.</span></span> <span data-ttu-id="baf41-119">信賴度等級是根據區段大小和區段細微性而定。</span><span class="sxs-lookup"><span data-stu-id="baf41-119">Confidence level is based on the segment size and the segment granularity.</span></span> <span data-ttu-id="baf41-120">區段大小是由特定區段的資料量所決定。</span><span class="sxs-lookup"><span data-stu-id="baf41-120">Segment size is determined by the amount of data we have for a given segment.</span></span> <span data-ttu-id="baf41-121">區段資料粒度是由設定檔中可用的屬性（年齡、性別、位置）所決定。</span><span class="sxs-lookup"><span data-stu-id="baf41-121">Segment granularity is determined by how many attributes (age, gender, location) are available in a profile.</span></span>

<span data-ttu-id="baf41-122">我們不會將資料集的分數正常化。</span><span class="sxs-lookup"><span data-stu-id="baf41-122">We don't normalize the scores for your dataset.</span></span> <span data-ttu-id="baf41-123">因此，您可能看不到資料集所有可能的親和性分數值。</span><span class="sxs-lookup"><span data-stu-id="baf41-123">Consequently, you may not see all possible affinity score values for your dataset.</span></span> <span data-ttu-id="baf41-124">例如，在您的資料中，可能不會有親和性分數為 100 的任何使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="baf41-124">For example, there may be no enriched customer profile with affinity score 100 in your data.</span></span> <span data-ttu-id="baf41-125">如果人口統計區段中並未有針對給定的品牌或興趣而計分 100 的客戶，就可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="baf41-125">That's possible if no customers exist in the demographic segment that scored 100 for a given brand or interest.</span></span>

> [!TIP]
> <span data-ttu-id="baf41-126">使用親和性分數[建立區段](segments.md)時，請先檢閱資料集的親和性分數的分佈，再依據適當的分數閾值做決定。</span><span class="sxs-lookup"><span data-stu-id="baf41-126">When [creating segments](segments.md) using affinity scores, review the distribution of affinity scores for your dataset before deciding on the appropriate score thresholds.</span></span> <span data-ttu-id="baf41-127">例如，評分為 10 的親和性分數可在對特定品牌或興趣的親和性分數最高只有 25 的特定資料集中視為顯著。</span><span class="sxs-lookup"><span data-stu-id="baf41-127">For example, an affinity score of 10 can be considered significant in a dataset that has a highest affinity score of only 25 for a given brand or interest.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="baf41-128">支援的國家/地區</span><span class="sxs-lookup"><span data-stu-id="baf41-128">Supported countries/regions</span></span>

<span data-ttu-id="baf41-129">我們目前支援下列國家/地區選項：澳大利亞、加拿大 (英文)、法國、德國、英國或美國 (英文)。</span><span class="sxs-lookup"><span data-stu-id="baf41-129">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="baf41-130">若要選取國家/地區，請開啟 **品牌擴充** 或 **興趣擴充**，然後選取 **國家/地區** 旁邊的 **變更**。</span><span class="sxs-lookup"><span data-stu-id="baf41-130">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="baf41-131">在 **國家/地區設定** 窗格中，選擇選項並選取 **套用**。</span><span class="sxs-lookup"><span data-stu-id="baf41-131">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="baf41-132">與國家/地區選取相關的影響</span><span class="sxs-lookup"><span data-stu-id="baf41-132">Implications related to country selection</span></span>

- <span data-ttu-id="baf41-133">[選擇您自己的品牌](#define-your-brands-or-interests)時，我們會根據選取的國家/地區提供建議。</span><span class="sxs-lookup"><span data-stu-id="baf41-133">When [choosing your own brands](#define-your-brands-or-interests), we will provide suggestions based on the selected country/region.</span></span>

- <span data-ttu-id="baf41-134">當您[選擇產業](#define-your-brands-or-interests)時，我們會根據選取的國家/地區找出最相關的品牌或興趣。</span><span class="sxs-lookup"><span data-stu-id="baf41-134">When [choosing an industry](#define-your-brands-or-interests), we will identify the most relevant brands or interests based on the selected country/region.</span></span>

- <span data-ttu-id="baf41-135">[對應您的欄位](#map-your-fields)時，如果未對應 [國家/地區] 欄位，我們將使用所選國家/地區的 Microsoft Graph 資料來擴充您的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="baf41-135">When [mapping your fields](#map-your-fields), if the Country/Region field isn't mapped, we'll use Microsoft Graph data from the selected country/region to enrich your customer profiles.</span></span> <span data-ttu-id="baf41-136">我們也會使用該選取項目來擴充沒有提供國家/地區資料的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="baf41-136">We'll also use that selection to enrich your customer profiles that don't have country/region data available.</span></span>

- <span data-ttu-id="baf41-137">[擴充設定檔](#refresh-enrichment)時，我們會擴充所有我們有 Microsoft Graph 資料適用於所選品牌及興趣的客戶設定檔，包括不屬於所選國家/地區的設定檔。</span><span class="sxs-lookup"><span data-stu-id="baf41-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we have Microsoft Graph data available for the selected brands and interests, including profiles that are not in the selected country/region.</span></span> <span data-ttu-id="baf41-138">例如，當您選取德國時，如果我們在美國有適用於所選品牌及興趣的 Microsoft Graph 資料，則會擴充位於美國的設定檔。</span><span class="sxs-lookup"><span data-stu-id="baf41-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="baf41-139">設定擴充</span><span class="sxs-lookup"><span data-stu-id="baf41-139">Configure Enrichment</span></span>

<span data-ttu-id="baf41-140">設定品牌或興趣擴充包括兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="baf41-140">Configuring brands or interests enrichment consists of two steps:</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="baf41-141">定義您的品牌或興趣</span><span class="sxs-lookup"><span data-stu-id="baf41-141">Define your brands or interests</span></span>

<span data-ttu-id="baf41-142">選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="baf41-142">Select one of the following options:</span></span>

- <span data-ttu-id="baf41-143">**產業**：系統會找出與您的行業相關的最上層品牌或興趣，並使用它們擴充您的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="baf41-143">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="baf41-144">**自行選擇**：從與您的組織最相關的品牌或興趣清單中，選取最多五個項目。</span><span class="sxs-lookup"><span data-stu-id="baf41-144">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="baf41-145">若要新增品牌或興趣，請在輸入區域中輸入，以依據符合的字詞取得建議。</span><span class="sxs-lookup"><span data-stu-id="baf41-145">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="baf41-146">如果我們未列出您要尋找的品牌或興趣，請使用 **建議** 連結向我們傳送意見。</span><span class="sxs-lookup"><span data-stu-id="baf41-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="baf41-147">對應您的欄位</span><span class="sxs-lookup"><span data-stu-id="baf41-147">Map your fields</span></span>

<span data-ttu-id="baf41-148">將您的統整客戶實體中的欄位對應至至少兩個屬性，以定義您要用來擴充客戶資料的人口統計區段。</span><span class="sxs-lookup"><span data-stu-id="baf41-148">Map fields from your unified customer entity to at least two attributes to define the demographic segment you want us to use for enriching your customer data.</span></span> <span data-ttu-id="baf41-149">選取 **編輯** 以定義欄位對應，並在完成時選取 **套用**。</span><span class="sxs-lookup"><span data-stu-id="baf41-149">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="baf41-150">選取 **儲存** 來完成欄位對應。</span><span class="sxs-lookup"><span data-stu-id="baf41-150">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="baf41-151">支援下列格式和值，這些值不區分大小寫：</span><span class="sxs-lookup"><span data-stu-id="baf41-151">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="baf41-152">**出生日期**：建議在資料擷取期間，將出生日期轉換為日期時間類型。</span><span class="sxs-lookup"><span data-stu-id="baf41-152">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="baf41-153">或者，也可以是使用 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 格式 "yyyy-MM-dd" 或 "yyyy-MM-ddTHH:mm:ssZ" 的字串。</span><span class="sxs-lookup"><span data-stu-id="baf41-153">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="baf41-154">**性別**：男、女、未知</span><span class="sxs-lookup"><span data-stu-id="baf41-154">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="baf41-155">**郵遞區號**：美國的五位數字郵遞區號、其他地區的標準郵遞區號</span><span class="sxs-lookup"><span data-stu-id="baf41-155">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="baf41-156">**城市**：英文城市名稱</span><span class="sxs-lookup"><span data-stu-id="baf41-156">**City**: City name in English</span></span>
- <span data-ttu-id="baf41-157">**州/省**：美國和加拿大的兩字母縮寫。</span><span class="sxs-lookup"><span data-stu-id="baf41-157">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="baf41-158">澳大利亞的兩字母或三字母縮寫。</span><span class="sxs-lookup"><span data-stu-id="baf41-158">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="baf41-159">不適用於法國、德國或英國。</span><span class="sxs-lookup"><span data-stu-id="baf41-159">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="baf41-160">**國家/地區**：</span><span class="sxs-lookup"><span data-stu-id="baf41-160">**Country/Region**:</span></span>

  - <span data-ttu-id="baf41-161">US：美利堅合眾國、美國、USA、US、美國、美洲</span><span class="sxs-lookup"><span data-stu-id="baf41-161">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="baf41-162">CA：加拿大、CA</span><span class="sxs-lookup"><span data-stu-id="baf41-162">CA: Canada, CA</span></span>
  - <span data-ttu-id="baf41-163">GB：英國、UK、大不列顛、GB、大不列顛與北愛爾蘭聯合王國、大不列顛聯合王國</span><span class="sxs-lookup"><span data-stu-id="baf41-163">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="baf41-164">AU：澳大利亞、AU、澳大利亞聯邦</span><span class="sxs-lookup"><span data-stu-id="baf41-164">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="baf41-165">FR：法國、FR、法蘭西共和國</span><span class="sxs-lookup"><span data-stu-id="baf41-165">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="baf41-166">DE：德國、德文、Deutschland、Allemagne、DE、德意志聯邦共和國、德意志共和國</span><span class="sxs-lookup"><span data-stu-id="baf41-166">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="baf41-167">重新整理擴充項目</span><span class="sxs-lookup"><span data-stu-id="baf41-167">Refresh enrichment</span></span>

<span data-ttu-id="baf41-168">在為人口統計設定品牌、興趣和欄位對應之後，請執行擴充。</span><span class="sxs-lookup"><span data-stu-id="baf41-168">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="baf41-169">若要開始此程序，請在品牌或興趣設定頁面上選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="baf41-169">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="baf41-170">此外，您還可以讓系統在排程的重新整理過程中自動執行擴充。</span><span class="sxs-lookup"><span data-stu-id="baf41-170">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="baf41-171">視您的客戶資料大小而定，可能需要數分鐘的時間才能完成擴充執行。</span><span class="sxs-lookup"><span data-stu-id="baf41-171">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="baf41-172">任務/流程目前有 [六種類型的狀態](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="baf41-172">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="baf41-173">此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="baf41-173">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="baf41-174">您可以選取程序的狀態，以查看整個工作的進度詳細資料。</span><span class="sxs-lookup"><span data-stu-id="baf41-174">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="baf41-175">針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="baf41-175">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="baf41-176">擴充結果</span><span class="sxs-lookup"><span data-stu-id="baf41-176">Enrichment results</span></span>

<span data-ttu-id="baf41-177">執行擴充程序之後，移至 **我的擴充內容** 以檢閱已擴充的客戶總數，以及擴充後客戶設定檔中的品牌或興趣明細。</span><span class="sxs-lookup"><span data-stu-id="baf41-177">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="執行擴充程序之後的結果預覽":::

<span data-ttu-id="baf41-179">在圖表中選取 **查看已擴充資料**，以查看擴充後的資料。</span><span class="sxs-lookup"><span data-stu-id="baf41-179">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="baf41-180">擴充的品牌資料會移至 **BrandAffinityFromMicrosoft** 實體。</span><span class="sxs-lookup"><span data-stu-id="baf41-180">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="baf41-181">興趣資料位於 **InterestAffinityFromMicrosoft** 實體中。</span><span class="sxs-lookup"><span data-stu-id="baf41-181">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="baf41-182">您也可以 **資料** > **實體** 的 **擴充** 群組中找到這些實體。</span><span class="sxs-lookup"><span data-stu-id="baf41-182">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="baf41-183">查看客戶卡片上的擴充資料</span><span class="sxs-lookup"><span data-stu-id="baf41-183">See enrichment data on the customer card</span></span>

<span data-ttu-id="baf41-184">您也可以在個別客戶卡片上查看品牌和興趣親和性。</span><span class="sxs-lookup"><span data-stu-id="baf41-184">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="baf41-185">移至 **客戶** 並選取客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="baf41-185">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="baf41-186">在客戶卡片中，您會發現該客戶人口統計設定檔中人員所喜好品牌或興趣的圖表。</span><span class="sxs-lookup"><span data-stu-id="baf41-186">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="包含擴充資料的客戶卡片":::

## <a name="next-steps"></a><span data-ttu-id="baf41-188">後續步驟</span><span class="sxs-lookup"><span data-stu-id="baf41-188">Next steps</span></span>

<span data-ttu-id="baf41-189">建立在您擴充的客戶資料之上。</span><span class="sxs-lookup"><span data-stu-id="baf41-189">Build on top of your enriched customer data.</span></span> <span data-ttu-id="baf41-190">建立[區段](segments.md)、[量值](measures.md)，甚至[匯出資料](export-destinations.md)，以便傳送個人化體驗給您的客戶。</span><span class="sxs-lookup"><span data-stu-id="baf41-190">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>
