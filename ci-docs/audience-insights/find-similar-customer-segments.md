---
title: 使用 AI 尋找類似的客戶
description: 使用人工智慧尋找類似的客戶細分。
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268860"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="4b3f8-103">類似的客戶 (預覽)</span><span class="sxs-lookup"><span data-stu-id="4b3f8-103">Similar Customers (preview)</span></span>

<span data-ttu-id="4b3f8-104">此功能可讓您使用人工智慧來尋找客戶群中類似的客戶。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="4b3f8-105">您必須至少已建立一個客戶細分，才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="4b3f8-106">擴充現有客戶細分準則有助於尋找與該客戶細分類似的客戶。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3f8-107">*尋找類似的客戶* 使用自動化方式來評估資料並根據該資料進行預測，因此具有可做為剖析方法使用的功能，因為該詞彙是一般資料保護規定 (「GDPR」) 所定義。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="4b3f8-108">若客戶使用此功能來處理資料，可能會受到 GDPR 或其他法律或法規的制約。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="4b3f8-109">您負責確保您對 Dynamics 365 Customer Insights 的使用，包括預測、符合所有適用法律和規定，包括隱私權、個人資料、生物資料、資料保護和通訊機密性相關法律。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="4b3f8-110">尋找類似的客戶</span><span class="sxs-lookup"><span data-stu-id="4b3f8-110">Finding similar customers</span></span>

1. <span data-ttu-id="4b3f8-111">在觀眾見解中，請前往 **區段** 並選取新區段要依據的區段。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="4b3f8-112">這就是您的 *來源客戶細分*。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="4b3f8-113">在動作列中，選取 **尋找類似客戶**。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="4b3f8-114">檢閱建議的新客戶細分名稱，並視需要加以變更。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="4b3f8-115">檢閱定義新客戶細分的欄位。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="4b3f8-116">這些欄位定義系統嘗試尋找與來源客戶細分類似之客戶的根據。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="4b3f8-117">系統預設會選取建議的欄位。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="4b3f8-118">可能會大幅降低模型效能的欄位會自動排除：</span><span class="sxs-lookup"><span data-stu-id="4b3f8-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="4b3f8-119">具有下列資料類型的欄位：StringType、BooleanType、CharType、LongType、IntType、DoubleType、FloatType、ShortType</span><span class="sxs-lookup"><span data-stu-id="4b3f8-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="4b3f8-120">含基數 (欄位內元素數) 的欄位小於 2 個或大於 30 個</span><span class="sxs-lookup"><span data-stu-id="4b3f8-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="4b3f8-121">選擇要包含在新客戶細分中的是 **所有客戶** 還是僅限 **特定現有客戶細分** 中的客戶。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="4b3f8-122">選取 **排除源客戶細分中的所有人** 核取方塊，以排除來源客戶細分中的客戶 。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="4b3f8-123">根據預設，系統建議您在輸出中只包含目標對象大小的 20%。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="4b3f8-124">視需要編輯此閾值。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-124">Edit this threshold as needed.</span></span> <span data-ttu-id="4b3f8-125">增加閾值會降低精確度。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="4b3f8-126">選取頁面底部的 **執行** 開始分析資料集的二元分類工作 (機器學習方法)。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="4b3f8-127">檢視類似的客戶細分</span><span class="sxs-lookup"><span data-stu-id="4b3f8-127">View the similar segment</span></span>

<span data-ttu-id="4b3f8-128">處理類似的區段之後，您會在 **客戶細分** 頁面中發現列出新的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4b3f8-129">![類似的客戶細分](media/expanded-segment.png "類似的客戶細分")</span><span class="sxs-lookup"><span data-stu-id="4b3f8-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="4b3f8-130">選取 動作列中的 **檢視**，以開啟客戶細分詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="4b3f8-131">此檢視表包含[相似性分數](#about-similarity-scores)的結果分佈相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="4b3f8-132">您也會在 **客戶細分成員預覽** 中找到相似性分數值。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="4b3f8-133">使用類似客戶細分的輸出</span><span class="sxs-lookup"><span data-stu-id="4b3f8-133">Use the output of a similar segment</span></span>

<span data-ttu-id="4b3f8-134">您可以[使用類似客戶細分的輸出](segments.md)，就像您對其他客戶細分所做的那樣。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="4b3f8-135">例如，匯出客戶細分或建立量值。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="4b3f8-136">重新整理並編輯類似的客戶細分</span><span class="sxs-lookup"><span data-stu-id="4b3f8-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="4b3f8-137">若要重新整理類似的客戶細分，請在 **客戶細分** 頁面上選取該客戶細分，然後選取動作列中的 **重新整理**。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="4b3f8-138">編輯類似的客戶細分會重新處理您的資料。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="4b3f8-139">先前建立的客戶細分會以重新整理的資料進行更新。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="4b3f8-140">若要編輯類似的客戶細分，請在 **客戶細分** 頁面上選取該客戶細分，然後選取動作列中的 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="4b3f8-141">套用您的變更，並選取 **執行** 開始進行處理。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="4b3f8-142">刪除類似的客戶細分</span><span class="sxs-lookup"><span data-stu-id="4b3f8-142">Delete a similar segment</span></span>

<span data-ttu-id="4b3f8-143">選取 **客戶細分** 頁面上的客戶細分，然後選取動作列中的 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="4b3f8-144">然後確認刪除。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="4b3f8-145">關於相似性分數</span><span class="sxs-lookup"><span data-stu-id="4b3f8-145">About similarity scores</span></span>

<span data-ttu-id="4b3f8-146">二元分類機器學習模型會將分數指派給類似客戶細分中的客戶。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="4b3f8-147">分數是根據與來源客戶細分中客戶的相似性所建立。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="4b3f8-148">低於 0.55 的相似性分數是系統分類為與來源客戶細分中客戶 *不類似* 的客戶</span><span class="sxs-lookup"><span data-stu-id="4b3f8-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="4b3f8-149">介於 0.55 到 0.7 之間的相似性分數是分類為 *有點類似*</span><span class="sxs-lookup"><span data-stu-id="4b3f8-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="4b3f8-150">介於 0.7 到 0.85 之間的相似性分數是分類為 *類似*</span><span class="sxs-lookup"><span data-stu-id="4b3f8-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="4b3f8-151">介於 0.85 到 1 之間的相似性分數，是系統分類為 *非常類似* 的客戶</span><span class="sxs-lookup"><span data-stu-id="4b3f8-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="4b3f8-152">相似性分數低於 0.4 的客戶不會包含在模型輸出中。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="4b3f8-153">系統不會將這些客戶視為與來源客戶細分足夠類似。</span><span class="sxs-lookup"><span data-stu-id="4b3f8-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]