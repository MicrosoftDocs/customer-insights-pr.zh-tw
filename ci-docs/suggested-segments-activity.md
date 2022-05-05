---
title: 以活動為基礎的客戶細分建議。
description: 讓機器學習協助您根據客戶活動尋找新的且值得注意的客戶細分。
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 85c3cef3a8d531b31b64a7e5decbdc122c4383fc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645850"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>以活動資料為基礎的客戶細分建議 (預覽版)

根據內嵌到 Customer Insights 的客戶活動資料，探索值得注意客戶細分。 活動資料的範例包括交易、支援通話長度、交易或退貨。 為了建議客戶細分，會針對新近程度、頻率和金額值 (或期間) 來分析活動資料。 或者，您也可以生成[建議的客戶細分來改善量值或更清楚地瞭解屬性影響](suggested-segments.md)。

:::image type="content" source="media/suggested-segments-tab.png" alt-text="建議的客戶細分索引標籤顯示的客戶細分建議是基於活動和基於屬性建立的。":::

## <a name="categorize-customers-by-activity"></a>依活動分類客戶

透過 Customer Insights 中提供的[活動資料](activities.md)，我們可以生成建議來表現客戶群組：

- 最活躍的客戶 
- 進行過最多購買的客戶 
- 產生最多營收的客戶 
- 最近沒有使用的客戶 
- 經常與您的企業互動的客戶  

如果您有零售業務，您可以找出哪些客戶產生最多的營收並使用優惠券回饋。 您也可以找出不定期客戶，並向他們提議加入獎勵計畫，讓他們更常造訪您的業務。
如果您是醫療保健商務的一份子，提供大眾醫療保健，而您的目標是把對個別患者的開銷降至最低。 若要這樣做，一種方式是在最少的訪視中，提供最好的服務，以減少定期訪視。 在此案例中，您的目標是保持較低的訪視頻率，並將患者的定期成本減至最小。 或者您也可以找出經預約和大量定期成本的患者客戶細分，並分析這些案例來改善個人的治療。 

## <a name="required-data"></a>必要的資料

建議會根據所選的輸入資料生成。 

- 客戶個人資料：特定客戶細分的所有客戶或成員。 

- 時段期間：上個月、去年或任何自訂時間範圍。

- 活動類型：購買、零售交易、線上交易、客戶支援案例、訂閱等等。  

- Customer Insights 中包含活動資料的實體：整合活動實體或特定活動的實體。 

- 要包含的維度：新近度、頻率或金額維度，視您的業務需求而定。

## <a name="generate-suggested-segments"></a>生成建議的客戶細分

1. 前往 **區段**。

1. 選取 **建議 (預覽版)** 索引標籤。

1. 選取 **尋找新建議**，然後選擇 **查看或預測客戶行為**。 選取 **開始** 執行引導式體驗。

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="根據活動建立建議的客戶細分的設定精靈，其第一個步驟。":::

1. 提供必要的輸入資料，並選取 **下一步** 繼續。

   - 選擇客戶：包括所有客戶或特定客戶細分。
   - 選擇活動：選取活動類型以及說明該活動的實體。
   - 喜好設定：設定要考量的時段期間、建議因素以及對應屬性。

1. 檢閱您的輸入，並選取 **執行** 來執行模型生成建議。

1. 視客戶個人資料數量和選取的活動數量而定，可能需要幾分鐘的時間完成。 

生成建議之後，您可以依據您最感興趣的維度或值來篩選它們。 

## <a name="view-details-of-a-suggested-segment"></a>檢視建議的客戶細分詳細資料

建議生成之後，可以在 **客戶細分** > **建議 (預覽版)** **基於活動建立的客戶細分建議** 區段中找到。

:::image type="content" source="media/suggested-segments-details.png" alt-text="展開的側窗格，顯示建議客戶細分的詳細資料。":::

選取建議的客戶細分區段上的 **查看建議**，以查看該客戶細分的詳細資料。 側面窗格提供如各維度範圍與目標群組比較的詳細資料。 也會醒目提示客戶細分中潛在成員的數量，以及總客戶數量相應的百分比。 如果您要將建議保留為客戶細分，請選取 **建立客戶細分**。    

## <a name="save-a-suggestion-as-a-segment"></a>將建議另存為客戶細分

1. 移至 **客戶細分** > **建議 (預覽版)**。

1. 選取您要儲存的客戶細分。 

1. 在側面窗格中，選取 **建立客戶細分**。 

1. 儲存客戶細分之後，它便會顯示在所有 **客戶細分** 索引標籤的客戶細分清單中。現在[就像其他任何區段一樣可以重新整理或刪除](segments.md)。 您不可以編輯客戶細分詳細資料。 但是，您可以變更建議的輸入準則，並生成不同的建議。

## <a name="refresh-or-edit-a-set-of-suggestions"></a>重新整理或編輯一組建議

1. 移至 **客戶細分** > **建議 (預覽版)**，並在 **基於活動的建議** 區段中尋找客戶細分。

1. 選取 **重新整理建議**，以使用維持設定好的屬性，重新整理建議。 或選取 **編輯建議** 修改已設定的屬性。 系統將會重新執行程序，並根據最新的資料生成客戶細分建議，並取代目前的建議。

[!INCLUDE [footer-include](includes/footer-banner.md)]
