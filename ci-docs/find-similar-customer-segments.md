---
title: 使用 AI 尋找類似客戶 (含影片)
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
ms.openlocfilehash: 7877349817829f7486a63a1355a81361e1cb2c13
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645808"
---
# <a name="similar-customers-preview"></a>類似的客戶 (預覽)

此功能可讓您使用人工智慧來尋找客戶群中類似的客戶。 您必須至少已建立一個客戶細分，才能使用此功能。 擴充現有客戶細分準則有助於尋找與該客戶細分類似的客戶。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *尋找類似的客戶* 使用自動化方式來評估資料並根據該資料進行預測，因此具有可做為剖析方法使用的功能，因為該詞彙是一般資料保護規定 (「GDPR」) 所定義。 若客戶使用此功能來處理資料，可能會受到 GDPR 或其他法律或法規的制約。 您負責確保您對 Dynamics 365 Customer Insights 的使用，包括預測、符合所有適用法律和規定，包括隱私權、個人資料、生物資料、資料保護和通訊機密性相關法律。

## <a name="finding-similar-customers"></a>尋找類似的客戶

1. 請移至 **客戶細分**，並選取新客戶細分要依據的客戶細分。 這就是您的 *來源客戶細分*。

1. 在動作列中，選取 **尋找類似客戶**。

1. 檢閱建議的新客戶細分名稱，並視需要加以變更。

1. 或者，將[標籤](work-with-tags-columns.md#manage-tags)新增至新的客戶細分。

1. 檢閱定義新客戶細分的欄位。 這些欄位定義系統嘗試尋找與來源客戶細分類似之客戶的根據。 系統預設會選取建議的欄位。
  可能會大幅降低模型效能的欄位會自動排除：
  
   - 具有下列資料類型的欄位：StringType、BooleanType、CharType、LongType、IntType、DoubleType、FloatType、ShortType
   - 含基數 (欄位內元素數) 的欄位小於 2 個或大於 30 個

1. 選擇要包含在新客戶細分中的是 **所有客戶** 還是僅限 **特定現有客戶細分** 中的客戶。

1. 根據預設，系統建議您在輸出中只包含目標對象大小的 20%。 視需要編輯此閾值。 增加閾值會降低精確度。

1. 選取 **包括來源客戶細分中的成員以及類似屬性的客戶** 核取方塊，以包括來源客戶細分的客戶

1. 選取頁面底部的 **執行** 開始分析資料集的二元分類工作 (機器學習方法)。

## <a name="view-the-similar-segment"></a>檢視類似的客戶細分

處理類似的區段之後，您會在 **客戶細分** 頁面中發現列出新的客戶細分。

> [!div class="mx-imgBorder"]
> ![類似的客戶細分。](media/expanded-segment.png "類似的客戶細分")

選取 動作列中的 **檢視**，以開啟客戶細分詳細資料。 此檢視表包含[相似性分數](#about-similarity-scores)的結果分佈相關資訊。 您也會在 **客戶細分成員預覽** 中找到相似性分數值。

## <a name="use-the-output-of-a-similar-segment"></a>使用類似客戶細分的輸出

您可以[使用類似客戶細分的輸出](segments.md)，就像您對其他客戶細分所做的那樣。 例如，匯出客戶細分或建立量值。

## <a name="refresh-and-edit-a-similar-segment"></a>重新整理並編輯類似的客戶細分

若要重新整理類似的客戶細分，請在 **客戶細分** 頁面上選取該客戶細分，然後選取動作列中的 **重新整理**。

編輯類似的客戶細分會重新處理您的資料。 先前建立的客戶細分會以重新整理的資料進行更新。
若要編輯類似的客戶細分，請在 **客戶細分** 頁面上選取該客戶細分，然後選取動作列中的 **編輯**。 套用您的變更，並選取 **執行** 開始進行處理。

## <a name="delete-a-similar-segment"></a>刪除類似的客戶細分

選取 **客戶細分** 頁面上的客戶細分，然後選取動作列中的 **刪除**。 然後確認刪除。

## <a name="about-similarity-scores"></a>關於相似性分數

二元分類機器學習模型會將分數指派給類似客戶細分中的客戶。 分數是根據與來源客戶細分中客戶的相似性所建立。

- 低於 0.55 的相似性分數是系統分類為與來源客戶細分中客戶 *不類似* 的客戶
- 介於 0.55 到 0.7 之間的相似性分數是分類為 *有點類似*
- 介於 0.7 到 0.85 之間的相似性分數是分類為 *類似*
- 介於 0.85 到 1 之間的相似性分數，是系統分類為 *非常類似* 的客戶

相似性分數低於 0.4 的客戶不會包含在模型輸出中。 系統不會將這些客戶視為與來源客戶細分足夠類似。

[!INCLUDE [footer-include](includes/footer-banner.md)]
