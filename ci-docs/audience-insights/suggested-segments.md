---
title: 由機器學習支援的客戶細分
description: 讓機器學習協助您根據客戶屬性尋找全新且值得注意的客戶細分。
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: bbc22adcd7b6e756fa6128abd855795de7480f2d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597075"
---
# <a name="suggested-segments-preview"></a><span data-ttu-id="c61a2-103">建議客戶細分 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="c61a2-103">Suggested segments (preview)</span></span>

<span data-ttu-id="c61a2-104">運用 AI 模型的協助在您的客戶中探索值得注意的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="c61a2-104">Discover interesting segments of your customers with the help of an AI model.</span></span> <span data-ttu-id="c61a2-105">此機器學習支援的功能會依照量值或客戶屬性建議客戶細分。</span><span class="sxs-lookup"><span data-stu-id="c61a2-105">This machine learning powered feature suggests segments based on measures or customer attributes.</span></span> <span data-ttu-id="c61a2-106">它可以協助改善您的 KPI，或更好地瞭解屬性在其他屬性的環境中受到的影響。</span><span class="sxs-lookup"><span data-stu-id="c61a2-106">It can help improve your KPIs or better understand the influence of attributes in context of other attributes.</span></span> 

> [!NOTE]
> <span data-ttu-id="c61a2-107">建議客戶細分的功能使用自動方法來評估資料，並根據該資料進行預測，因此可當作是剖析的方法，也就是由一般資料保護規定 (「GDPR」) 定義那個術語「剖析」。</span><span class="sxs-lookup"><span data-stu-id="c61a2-107">The suggested segments feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="c61a2-108">您使用此功能來處理資料將受到 GDPR 或其他法律或規定的制約。</span><span class="sxs-lookup"><span data-stu-id="c61a2-108">Your use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="c61a2-109">您有責任確保您對 Dynamics 365 Customer Insights 的使用，包括此功能、符合所有適用法律和規定，包括隱私權、個人資料、生物資料、資料保護和通訊保密性的相關法律。</span><span class="sxs-lookup"><span data-stu-id="c61a2-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including this feature, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="在 Customer Insights 中的建議客戶細分頁面，在側邊窗格顯示建議的詳細資料。":::

## <a name="suggested-segments-to-improve-your-kpis"></a><span data-ttu-id="c61a2-111">改善 KPI 的建議客戶細分</span><span class="sxs-lookup"><span data-stu-id="c61a2-111">Suggested segments to improve your KPIs</span></span>

<span data-ttu-id="c61a2-112">作為對象見解的使用者，您很可能會建立一系列的[量值](measures.md)，協助您追蹤關鍵效能指標 (KPI)。</span><span class="sxs-lookup"><span data-stu-id="c61a2-112">As a user of audience insights, you likely have a series of [measures created](measures.md) that help track your Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="c61a2-113">若要建立客戶細分並執行非常精準的行銷活動，重點是要瞭解某些屬性如何影響此 KPI。</span><span class="sxs-lookup"><span data-stu-id="c61a2-113">It's important to understand how certain attributes influence this KPI to create segments and run a highly targeted campaign.</span></span>   
<span data-ttu-id="c61a2-114">例如，您要追蹤名為 *TotalSpendPerCustomer* 的量值。</span><span class="sxs-lookup"><span data-stu-id="c61a2-114">For example, you track a measure called *TotalSpendPerCustomer*.</span></span> <span data-ttu-id="c61a2-115">作為業務，您會想要看到此數字增長。</span><span class="sxs-lookup"><span data-stu-id="c61a2-115">As a business, you’d like to see this number grow.</span></span> <span data-ttu-id="c61a2-116">選取量值作為主要屬性，可讓您選取要評估影響的屬性。</span><span class="sxs-lookup"><span data-stu-id="c61a2-116">Choosing a measure as primary attribute, lets you select the attributes that you want to assess for influence.</span></span> <span data-ttu-id="c61a2-117">假設是 *成員資格階層*、*成員資格期間* 和 *職業*。</span><span class="sxs-lookup"><span data-stu-id="c61a2-117">Let's say *membership tier*, *membership period*, and *occupation*.</span></span> <span data-ttu-id="c61a2-118">接著，Customer Insights 會建議一個客戶細分，告訴您該量值受到的最大影響。</span><span class="sxs-lookup"><span data-stu-id="c61a2-118">Customer Insights can then suggest a segment that tells you who are the biggest influence of that measure.</span></span> <span data-ttu-id="c61a2-119">例如，*金牌* 成員且為 *會計*，與您的業務往來 *至少有五年*，影響 *TotalSpendPerCustomer* 最大。</span><span class="sxs-lookup"><span data-stu-id="c61a2-119">For example, *Accountants* who are *Gold* members, and who have been with your business for *at least five years* are the biggest influencer of *TotalSpendPerCustomer*.</span></span> <span data-ttu-id="c61a2-120">您將會取得每個建議的估計客戶細分大小。</span><span class="sxs-lookup"><span data-stu-id="c61a2-120">You’ll get an estimated segment size for every suggestion.</span></span> <span data-ttu-id="c61a2-121">您可以使用此資訊來建立目標聽眾的行銷活動。</span><span class="sxs-lookup"><span data-stu-id="c61a2-121">You can use this information to create campaigns for the targeted audiences.</span></span>

## <a name="understand-what-influences-a-customer-attribute"></a><span data-ttu-id="c61a2-122">瞭解什麼會影響客戶屬性</span><span class="sxs-lookup"><span data-stu-id="c61a2-122">Understand what influences a customer attribute</span></span>

<span data-ttu-id="c61a2-123">您可以選擇客戶屬性而非量值作為主要屬性。</span><span class="sxs-lookup"><span data-stu-id="c61a2-123">You can choose a customer attribute instead of a measure as the primary attribute.</span></span> <span data-ttu-id="c61a2-124">根據您選擇的影響屬性，AI 模型會建立一系列建議，以顯示選取的屬性如何影響主要屬性。</span><span class="sxs-lookup"><span data-stu-id="c61a2-124">Based on your choice of influencing attributes, the AI model creates a series of suggestions that show how the selected attributes influence the primary attribute.</span></span>   
<span data-ttu-id="c61a2-125">例如，您可以選擇 *獎勵成員 (是/否)* 作為主要屬性。</span><span class="sxs-lookup"><span data-stu-id="c61a2-125">For example, you choose *Rewards Member (Yes/No)* as the primary attribute.</span></span> <span data-ttu-id="c61a2-126">*會員期間*、*職業* 及 *支援票證數量* 會設定為其他影響屬性。</span><span class="sxs-lookup"><span data-stu-id="c61a2-126">*Tenure*, *Occupation*, and *Number of Support Tickets* are set as other influencing attributes.</span></span> <span data-ttu-id="c61a2-127">AI 模型可能會建議客戶細分，標示大部分會員期間超過 2 年的 IT 專業人員是獎勵成員。</span><span class="sxs-lookup"><span data-stu-id="c61a2-127">The AI model could suggest segments indicating mostly IT professionals with tenure over two years are rewards members.</span></span> <span data-ttu-id="c61a2-128">另一個建議重點標註會員期間在一年內，少於三個支援票證的會計為獎勵成員。</span><span class="sxs-lookup"><span data-stu-id="c61a2-128">Another suggestion could highlight that accountants with tenure over one year and fewer than three support tickets are rewards members.</span></span> 

## <a name="artificial-intelligence-usage"></a><span data-ttu-id="c61a2-129">人工智慧使用方式</span><span class="sxs-lookup"><span data-stu-id="c61a2-129">Artificial intelligence usage</span></span>

<span data-ttu-id="c61a2-130">使用主要屬性和影響屬性，決策樹演算法會建議值得注意的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="c61a2-130">Using the primary attribute and influencing attributes, a decision tree algorithm suggests interesting segments.</span></span> <span data-ttu-id="c61a2-131">這些建議是根據 AI 演算法所挑選的規則或模式而定。</span><span class="sxs-lookup"><span data-stu-id="c61a2-131">The suggestions are based on rules or patterns that were picked up by the AI algorithm.</span></span> <span data-ttu-id="c61a2-132">只有與母體平均明顯不同的細分，才會顯示為建議。</span><span class="sxs-lookup"><span data-stu-id="c61a2-132">Only segments that significantly differ from the average population are shown as suggestions.</span></span> <span data-ttu-id="c61a2-133">會根據選取的量值或主要屬性與母體平均比較。</span><span class="sxs-lookup"><span data-stu-id="c61a2-133">The comparison to the average population is based on the selected measure or primary attribute.</span></span>

### <a name="responsible-ai"></a><span data-ttu-id="c61a2-134">負責的 AI</span><span class="sxs-lookup"><span data-stu-id="c61a2-134">Responsible AI</span></span>

<span data-ttu-id="c61a2-135">建議的客戶細分可讓您選取屬性來建立新的客戶細分，並處理您選取的資料。</span><span class="sxs-lookup"><span data-stu-id="c61a2-135">Suggested segments lets you select attributes to create new segments and process the data you select.</span></span> <span data-ttu-id="c61a2-136">選擇屬性 (包括種族、性傾向或性別等敏感屬性) 時，您必須確保您能夠且應該處理該資料。</span><span class="sxs-lookup"><span data-stu-id="c61a2-136">When choosing attributes, including sensitive attributes like race, sexual orientation, or gender, you must ensure that you can and should process that data.</span></span> <span data-ttu-id="c61a2-137">您有責任遵守所有適用於您組織的法律，並符合組織的原則和隱私權策略。</span><span class="sxs-lookup"><span data-stu-id="c61a2-137">You are responsible to comply with any laws applicable to your organization and adhere to your organization’s principles and privacy policies.</span></span>

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a><span data-ttu-id="c61a2-138">使用分類和數值值，主要屬性不同的結果</span><span class="sxs-lookup"><span data-stu-id="c61a2-138">Different results for primary attributes with categorical and numeric values</span></span>

<span data-ttu-id="c61a2-139">選擇數值屬性或分類屬性作為主要屬性，客戶細分建議會有不同。</span><span class="sxs-lookup"><span data-stu-id="c61a2-139">Segment suggestions are different if you choose a numeric attribute or a categorical attribute as the primary attribute.</span></span> <span data-ttu-id="c61a2-140">分類屬性中的值包含兩個以上的類別或類型。</span><span class="sxs-lookup"><span data-stu-id="c61a2-140">Values in a categorical attribute contain two or more categories or types.</span></span> <span data-ttu-id="c61a2-141">數值屬性包含量化資料，以及一種與其相關的合理測量方式。</span><span class="sxs-lookup"><span data-stu-id="c61a2-141">A numeric attribute contains quantitative data and has a sense of measurement associated with it.</span></span>

<span data-ttu-id="c61a2-142">使用數值屬性 (例如 *年收入* 或 *會員期間* 作為主要屬性)，系統會建議的客戶細分，是數值屬性的平均值比所有客戶高或低的。</span><span class="sxs-lookup"><span data-stu-id="c61a2-142">With a numeric attribute like *annual income* or *membership period* as the primary attribute, the system suggests segments that have a higher or lower average value of the numeric attribute when compared to all customers.</span></span>

<span data-ttu-id="c61a2-143">分類屬性 (如 *客戶滿意度*) 當作主要屬性，結果會建議的客戶細分，是在特定類別中擁有較高或較低的百分比的客戶 (比較屬於相同類別的所有客戶百分比)。</span><span class="sxs-lookup"><span data-stu-id="c61a2-143">A categorical attribute like *customer satisfaction* as the primary attribute results in suggested segments that have a higher or lower percentage of customers belonging to a particular category when compared to the percentage of all customers belonging to that same category.</span></span> <span data-ttu-id="c61a2-144">例如，*將客戶滿意度* 選為主要屬性，並且此屬性由三個類別 (*低*、*中* 和 *高*)組成。</span><span class="sxs-lookup"><span data-stu-id="c61a2-144">For example, *customer satisfaction* is chosen as the primary attribute and it consists of three categories (*Low*, *Medium* and *High*).</span></span> <span data-ttu-id="c61a2-145">對於每個類別，會建議的客戶細分是對比所有客戶在該類別的比例，相同類別百分比明顯較高或較低的客戶。</span><span class="sxs-lookup"><span data-stu-id="c61a2-145">For each category, segments will be suggested that have a significantly higher or lower percentage of customers belonging to that category as compared to the proportion of all customers in same category.</span></span> <span data-ttu-id="c61a2-146">如果所有客戶中的 22% 都有 *高* 滿意度，則只有 *高* 滿意度明顯較高或較低比例的客戶細分 (與22% 相比) 會在該類別被建議。</span><span class="sxs-lookup"><span data-stu-id="c61a2-146">If 22% of all customers have a *High* satisfaction, then, only segments that have a significantly higher or lower proportion of customers with a *High* satisfaction as compared to 22% will be suggested for that category.</span></span> <span data-ttu-id="c61a2-147">同樣地，如果具備統計上的顯著，每個其他類別 (*低* 和 *中*) 都會有建議的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="c61a2-147">Similarly, segments will be suggested for each of the other categories (*Low* and *Medium*) if they are statistically significant.</span></span>

> [!NOTE]
> <span data-ttu-id="c61a2-148">目前，我們僅支援的主要分類屬性最多具備 10 個類別。</span><span class="sxs-lookup"><span data-stu-id="c61a2-148">Currently, we only support primary categorical attributes that have up to 10 categories.</span></span> <span data-ttu-id="c61a2-149">如果您想要根據超過 10 個類別的主要屬性查看客戶細分建議，我們建議您將某些類別分成一組，將類別數減少到 10 個以下 (含)。</span><span class="sxs-lookup"><span data-stu-id="c61a2-149">If you want to see segment suggestions based on a primary attribute with more than 10 categories, we recommend to group some of the categories to reduce the number of categories to 10 or fewer.</span></span> <span data-ttu-id="c61a2-150">這項限制只適用在主要屬性。</span><span class="sxs-lookup"><span data-stu-id="c61a2-150">This limitation only applies to primary attributes.</span></span> <span data-ttu-id="c61a2-151">若是影響分類屬性，目前最多支援 100 個類別。</span><span class="sxs-lookup"><span data-stu-id="c61a2-151">For influencing categorical attributes, we currently support a maximum of 100 categories.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="c61a2-152">生成建議的客戶細分</span><span class="sxs-lookup"><span data-stu-id="c61a2-152">Generate suggested segments</span></span>

1. <span data-ttu-id="c61a2-153">前往 **區段**。</span><span class="sxs-lookup"><span data-stu-id="c61a2-153">Go to **Segments**.</span></span>

1. <span data-ttu-id="c61a2-154">選取 **建議 (預覽版)** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c61a2-154">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="c61a2-155">選取 **取得新的建議** 以開始指南體驗。</span><span class="sxs-lookup"><span data-stu-id="c61a2-155">Select **Get new suggestions** to start the guided experience.</span></span>

1. <span data-ttu-id="c61a2-156">選擇量值或客戶屬性作為主要屬性，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="c61a2-156">Choose a measure or a customer attribute as the primary attribute and select **Next**.</span></span>

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="在建議的客戶細分中，為建議選擇主要屬性。":::

1. <span data-ttu-id="c61a2-158">選取影響屬性，並選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="c61a2-158">Select the influencing attributes and select **Save**.</span></span>
   
   > [!TIP]
   > <span data-ttu-id="c61a2-159">選取多個影響屬性能改善評估其影響主要屬性的風險。</span><span class="sxs-lookup"><span data-stu-id="c61a2-159">Selecting multiple influencing attributes improves the chances of evaluating how they influence the primary attribute.</span></span> <span data-ttu-id="c61a2-160">不要加入不會影響主要屬性的屬性。</span><span class="sxs-lookup"><span data-stu-id="c61a2-160">Don't include attributes that have no influence the primary attribute.</span></span> <span data-ttu-id="c61a2-161">例如，如果您的所有客戶都來自特定的國家/地區，請不要加入 *國家/地區* 屬性，因為它不會影響其輸出。</span><span class="sxs-lookup"><span data-stu-id="c61a2-161">For example, if all your customers are from a specific country, don't include the *country* attribute because it won't have any impact on the output.</span></span>

1. <span data-ttu-id="c61a2-162">視客戶設定檔和選取的屬性數量而定，這可能需要幾分鐘的時間來處理選取的屬性。</span><span class="sxs-lookup"><span data-stu-id="c61a2-162">Depending on the number of customer profiles and selected attributes, it can take a few minutes to process the selected attributes.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="c61a2-163">檢視建議的客戶細分詳細資料</span><span class="sxs-lookup"><span data-stu-id="c61a2-163">View details of a suggested segment</span></span>

<span data-ttu-id="c61a2-164">當 AI 模型生成好建議之後，您會發現它們列在 **客戶細分** > **建議 (預覽版)**。</span><span class="sxs-lookup"><span data-stu-id="c61a2-164">Once the AI model has generated the suggestions, you'll find them listed on **Segments** > **Suggestions (preview)**.</span></span>
 
<span data-ttu-id="c61a2-165">選取建議的客戶細分，以檢閱該建議的詳細資料，包括平均值與客戶細分成員的比較。</span><span class="sxs-lookup"><span data-stu-id="c61a2-165">Select a suggested segment to review the details of that suggestion including a comparison of the average value and the number of segment members.</span></span> <span data-ttu-id="c61a2-166">您也可以檢閱 AI 模型習得用來建議選取的區段的屬性值或規則。</span><span class="sxs-lookup"><span data-stu-id="c61a2-166">You can also review the attribute values or rules that the AI model learned to suggest the selected segment.</span></span>

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="c61a2-167">將建議另存為客戶細分</span><span class="sxs-lookup"><span data-stu-id="c61a2-167">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="c61a2-168">移至 **客戶細分** > **建議 (預覽版)**。</span><span class="sxs-lookup"><span data-stu-id="c61a2-168">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="c61a2-169">選取您要儲存的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="c61a2-169">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="c61a2-170">在側邊窗格中，選取 **儲存為客戶細分**。</span><span class="sxs-lookup"><span data-stu-id="c61a2-170">In the side pane, select **Save as segment**.</span></span> 

1. <span data-ttu-id="c61a2-171">儲存客戶細分之後，它便會顯示在 **所有客戶細分** 索引標籤的客戶細分清單中。它現在[與任何其他客戶細分一樣，能重新整理、編輯或刪除](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="c61a2-171">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed, edited, or deleted like any other segment](segments.md).</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="c61a2-172">重新整理或編輯一組建議</span><span class="sxs-lookup"><span data-stu-id="c61a2-172">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="c61a2-173">移至 **客戶細分** > **建議 (預覽版)**。</span><span class="sxs-lookup"><span data-stu-id="c61a2-173">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="c61a2-174">選取 **重新整理建議**，以使用維持設定好的屬性，重新整理建議。</span><span class="sxs-lookup"><span data-stu-id="c61a2-174">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="c61a2-175">或選取 **編輯屬性** 修改已設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="c61a2-175">Or select **Edit attributes** to modify the configured attributes.</span></span> <span data-ttu-id="c61a2-176">系統將會重新執行 AI 模型，並根據最新的資料生成客戶細分建議，取代目前的建議。</span><span class="sxs-lookup"><span data-stu-id="c61a2-176">The system will rerun the AI model, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

## <a name="limitations"></a><span data-ttu-id="c61a2-177">限制</span><span class="sxs-lookup"><span data-stu-id="c61a2-177">Limitations</span></span>

1. <span data-ttu-id="c61a2-178">估計的客戶細分大小不相符：如果您選擇的主要屬性包含空值，則會客戶細分建議中影響估計的客戶細分大小。</span><span class="sxs-lookup"><span data-stu-id="c61a2-178">Estimated segment size mismatch: If you choose a primary attribute that contains empty values, it can affect the estimated segment size in the segment suggestions.</span></span> <span data-ttu-id="c61a2-179">儲存這類客戶細分時，實際的客戶細分大小可能會與原始估計不同。</span><span class="sxs-lookup"><span data-stu-id="c61a2-179">When saving such segment, the actual segment size can be different to the original estimation.</span></span>
 
2. <span data-ttu-id="c61a2-180">布林值類型的主要屬性無法運作：目前，我們只支援資料的字串和數值型別作為主要屬性。</span><span class="sxs-lookup"><span data-stu-id="c61a2-180">Boolean type primary attributes don't work: Currently, we only support string and numeric types of data as the primary attribute.</span></span>

3. <span data-ttu-id="c61a2-181">建議的客戶細分不夠顯著：請記住，選取的屬性和這些屬性值的分佈會影響結果。</span><span class="sxs-lookup"><span data-stu-id="c61a2-181">Suggested segments aren't distinct enough: Keep in mind that the selected attributes and the distribution of values of those attributes influences the results.</span></span> <span data-ttu-id="c61a2-182">您可以變更影響屬性，甚至是主要屬性，以取得不同的結果。</span><span class="sxs-lookup"><span data-stu-id="c61a2-182">You can change your influencing attributes or even your primary attribute to get different results.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]