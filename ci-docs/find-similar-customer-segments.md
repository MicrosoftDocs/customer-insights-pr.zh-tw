---
title: 使用 AI 尋找類似客戶 (預覽版) (含影片)
description: 使用人工智慧尋找類似的客戶細分。
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170717"
---
# <a name="find-similar-customers-with-ai-preview"></a>使用 AI 尋找類似客戶 (預覽版)

使用人工智慧，在您的客戶群中尋找類似的客戶。 您至少需要建立一個客戶細分，才能使用此功能。 擴充現有客戶細分準則有助於尋找與該客戶細分類似的客戶。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *尋找類似的客戶*，使用自動化方式來評估資料，並根據該資料進行預測。 因此，它有能力用作分析方法，因為該術語是由一般資料保護規定 (“GDPR”) 所定義。 若客戶使用此功能來處理資料，可能會受到 GDPR 或其他法律或法規的制約。 您負責確保您對 Dynamics 365 Customer Insights 的使用，包括預測、符合所有適用法律和規定，包括隱私權、個人資料、生物資料、資料保護和通訊機密性相關法律。

## <a name="find-similar-customers"></a>尋找類似的客戶

1. 請移至 **客戶細分**，並選取新客戶細分要依據的客戶細分。 這就是您的 *來源客戶細分*。

1. 選取 **尋找類似的客戶**。

1. 檢閱建議的新客戶細分名稱，並視需要加以變更。

1. 或者，將[標籤](work-with-tags-columns.md#manage-tags)新增至新的客戶細分。

1. 檢閱定義新客戶細分的欄位。 這些欄位定義系統嘗試尋找與來源客戶細分類似之客戶的根據。 系統預設會選取建議的欄位。 如果需要，請新增更多欄位。
  可能會大幅降低模型效能的欄位會自動排除：
  
   - 具有下列資料類型的欄位：StringType、BooleanType、CharType、LongType、IntType、DoubleType、FloatType、ShortType
   - 含基數 (欄位內元素數) 的欄位小於 2 個或大於 30 個

1. 選擇要包含在新客戶細分中的是 **所有客戶** (來源客戶細分除外)，還是僅限 **不同客戶細分** 中的客戶。

1. 根據預設，系統建議您在輸出中只包含目標對象大小的 20%。 視需要編輯此閾值。 增加閾值會降低精確度。

1. 選取 **包括來源客戶細分中的成員以及類似屬性的客戶** 核取方塊，以包括來源客戶細分的客戶

1. 選取頁面底部的 **執行** 開始分析資料集的[二元分類工作](#about-similarity-scores) (機器學習方法)。

## <a name="view-the-similar-segment"></a>檢視類似的客戶細分

處理類似的區段之後，您會在 **客戶細分** 頁面上找到類行為 **擴充** 的客戶細分。

選取 **檢視**，以查看 **客戶細分成員預覽** 底下的[相似度分數](#about-similarity-scores)和 相似度分數值的結果分佈。

:::image type="content" source="media/expanded-segment.png" alt-text="類似的客戶細分。":::

## <a name="manage-a-similar-segment"></a>管理類似的客戶細分

[使用和管理類似的客戶細分](segments.md#manage-existing-segments)，就像您對其他客戶細分所做的那樣。 例如，匯出客戶細分或建立量值。

編輯、重新整理、重新命名、下載和刪除類似的客戶細分。 編輯類似的客戶細分會重新處理您的資料。 先前建立的客戶細分會以重新整理的資料進行更新。

## <a name="about-similarity-scores"></a>關於相似性分數

二元分類機器學習模型會將分數指派給類似客戶細分中的客戶。 分數是根據與來源客戶細分中客戶的相似性所建立。

- 低於 0.55 的相似性分數是系統分類為與來源客戶細分中客戶 *不類似* 的客戶
- 介於 0.55 到 0.7 之間的相似性分數是分類為 *有點類似*
- 介於 0.7 到 0.85 之間的相似性分數是分類為 *類似*
- 介於 0.85 到 1 之間的相似性分數，是系統分類為 *非常類似* 的客戶

相似性分數低於 0.4 的客戶不會包含在模型輸出中。 系統不會將這些客戶視為與來源客戶細分足夠類似。

[!INCLUDE [footer-include](includes/footer-banner.md)]
