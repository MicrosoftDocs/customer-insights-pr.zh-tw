---
title: 使用 Microsoft 的品牌和興趣資料擴充客戶設定檔 (預覽版)
description: 使用 Microsoft 的專有資料，以品牌親和力和聲量佔有率擴充您的客戶資料。
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080911"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>使用 Microsoft 的品牌和興趣資料擴充客戶設定檔 (預覽版)

使用 Microsoft 的專有資料，以品牌親和度、興趣同質性，和聲量佔有率 (SoV) 擴充您的客戶資料。 這些品牌親和度與 SoV 都建立在與客戶人口統計相似之人員的資料上。 此資訊可協助您更好地瞭解您的客戶，並根據客戶對特定的品牌和興趣的親合度或 SoV 進一步區分。

## <a name="how-we-determine-affinities-and-sov"></a>我們如何判斷親合度與 SoV

我們使用 Microsoft 的線上搜尋資料，找出各種人口統計資料區段 (由年齡、性別或地點定義) 對品牌的親合度和 SoV。 品牌或興趣表單的線上搜尋量，是判斷親合度或 SoV 的基礎。 不過，這些都能提供不同的視角來瞭解您的客戶。

- 親合度是各人口統計區段間的比較。 您可以使用此資訊來找出與其他區段相比，對指定品牌或興趣有最高親度的人口統計資料區段。

- 聲量佔有率則是在您選取的品牌或興趣之間進行比較。 您可以使用此資訊來找出對指定人口統計資料區段哪個品牌或興趣有最高聲量佔有率 (與所選的其他品牌或興趣相比)。

## <a name="affinity-level-and-score"></a>親合性等級和分數

每一個擴充的客戶個人資料，我們都提供兩個相關的值：親合性等級和親合性分數。 這些值可協助您判斷與其他人口統計資料段相比，該設定檔人口統計資料客戶細分、品牌或興趣的親和性強弱程度。

*親和性等級* 由四個等級所組成，而 *親和性分數* 是在對應親和性等級在 100 分範圍中的計算結果。

|親和性等級 |親和性分數  |
|---------|---------|
|非常高     | 85-100       |
|高     | 70-84        |
|中     | 35-69        |
|低     | 1-34        |

根據您要測量親和性的細微程度，您可以使用親和性等級或分數。 親和性分數提供更精確的控制。

## <a name="share-of-voice-sov"></a>聲量佔有率 (SoV)

我們以 100 點的範圍計算 SoV。 每一個擴充的客戶個人資料，其對所有品牌或興趣的 SoV 總額增加上限為 100。 與親合度不同，SoV 是相對於您所選取的品牌和興趣。 例如，如果選取的品牌是 ('Microsoft'，'GitHub') 或 ('Microsoft' 'LinkedIn')，'Microsoft' 的 SoV 值可能是不同的。

## <a name="supported-countriesregions"></a>支援的國家/地區

我們目前支援下列國家/地區選項：澳大利亞、加拿大 (英文)、法國、德國、英國或美國 (英文)。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

   - 若要設定品牌親合性和 SoV 擴充，請到 **品牌** 磚上，選取 **擴充我的資料**。

   - 若要設定興趣親合性和 SoV 擴充，請到 **興趣** 磚上，選取 **擴充我的資料**。

   > [!div class="mx-imgBorder"]
   > ![編輯品牌與興趣圖標。](media/BrandsInterest-tile-Hub.png "品牌與興趣圖標")

1. 檢閱概覽，然後選擇 **下一步**。

1. 若要變更您的國家或地區，請選取 **國家/地區** 旁邊的 **變更**。 在 **國家/地區設定** 窗格中，選取 [支援的國家/地區](#supported-countriesregions)，並選取 **套用**。

   > [!NOTE]
   > 當選擇您的自有品牌時，系統會根據選取的國家或地區提供建議。 選擇產業時，將得到與您選取的國家或地區最相關的品牌或興趣。

1. 使用下列其中一或兩個選項，最多選擇五個品牌或興趣：

   - **產業**：從下拉式清單選取您的產業，然後選擇該產業的最大品牌或興趣。
   - **自行選擇**：輸入與您的組織相關的品牌或興趣，然後從符合的建議中選擇。 如果我們未列出您要尋找的品牌或興趣，請使用 **建議** 連結向我們傳送意見。

1. 選取 **下一步** 並檢閱預設的擴充喜好設定，並視需要更新。

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="擴充喜好設定視窗的螢幕擷取畫面。":::

1. 選取 **下一步**。

1. 選取 **客戶資料集**，然後選擇要使用 Microsoft 的資料進行擴充的個人資料或客戶細分。 *Customer* 實體可擴充所有客戶個人資料，然而客戶細分實體僅擴充位於該客戶細分的客戶個人資料。

1. 選取 **下一步**。

1. 將整合客戶實體的欄位對應至 Microsoft 資料。

   > [!NOTE]
   > 至少需要出生日期或性別屬性。 必須有國家/地區及至少是城市 (和州/省) 或郵遞區號。 我們建議在資料擷取期間，將出生日期轉換為 DateTime 類型。 或者，它可以是 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 的字串，格式為 "yyyy-mm-dd" 或 "yyyy-MM-ddTHH:mm:ss"。

1. 請選取 **下一步**，完成欄位對應。

1. 提供擴充的名稱。 **輸出實體名稱** 隨即自動選取。

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="興趣檢閱及命名頁面。":::

1. 檢閱選擇之後，請選取 **儲存擴充**。

1. 選取 **執行** 以開始擴充程序，或者直接關閉返回至 **擴充** 頁面。

   當擴充個人資料時，我們會擴充在已選的品牌和興趣取得資料的客戶個人資料，包括不屬於選取的國家/地區的個人資料。 例如，如果您選取德國，而選取的品牌和興趣在美國我們有資料可以使用，我們將會擴充位於美國的個人資料。

## <a name="view-enrichment-results"></a>查看擴充結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="執行擴充程序之後的結果預覽。":::

結果包括 **親和性等級** 或 **聲量佔有率** 圖表。

從擴充建立的實體會列在 **資料** > **實體** 的 **擴充** 群組中。 品牌的擴充資料會移至 **BrandAffinityFromMicrosoft** 與 **BrandShareOfVoiceFromMicrosoft** 實體。 興趣的資料位於 **InterestAffinityFromMicrosoft** 和 **InterestShareOfVoiceFromMicrosoft** 實體中。

## <a name="see-enrichment-data-on-the-customer-card"></a>查看客戶卡片上的擴充資料

您也可以在各個客戶卡片上查看品牌和興趣 SoV。 移至 **客戶** 並選取客戶設定檔。 在客戶卡片中，您會找到品牌或興趣 SoV 的圖表，是根據屬於該客戶個人資料的人口統計的人員建立的。

:::image type="content" source="media/enrichment-customer-card.png" alt-text="包含擴充資料的客戶卡片。":::

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
