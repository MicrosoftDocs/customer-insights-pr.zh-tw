---
title: 使用增強型地址擴充客戶個人資料 (含影片)
description: 使用 Microsoft 模型擴充和標準化客戶個人資料的地址資訊。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080839"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>使用增強型地址擴充客戶個人資料

資料中的地址可能未結構化、不完整或不正確。 使用 Microsoft 的模型，標準化地址並擴充成 [Common Data Model 格式](/common-data-model/schema/core/applicationcommon/address)，以取得更佳的準確性和洞察力。

您也可以在[資料來源上擴充地址](data-sources-enrichment.md)，以改善資料整合程序中的比對精確性。 

## <a name="how-we-enhance-addresses"></a>我們如何增強地址

我們的模型以二步驟流程來增強地址。 首先，它會解析地址找出其組成部分，並將它們設定為結構化格式。 然後，我們使用 AI 來更正、完成並標準化地址中的值。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>範例

地址資訊可能以非標準格式存在，並包含拼寫錯誤。 此模型可以修正這些問題，並在整合的客戶個人資料中建立一致的地址。

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>限制

增強型地址只會對在內嵌地址資料中已存在的值使用。 模型不能：

1. 確認地址是否為有效的地址。
2. 確認任何值 (如郵遞區號或街道名稱) 是有效的。
3. 變更無法識別的值。

此模型使用機器學習技術來增強地址。 與任何機器學習的模型一樣，不能保證 100% 的準確性。

## <a name="supported-countries-or-regions"></a>支援的國家或地區

目前我們在這些國家或地區支援增強地址：

- 澳洲
- 加拿大
- 法國
- 德國
- 義大利
- 日本
- 英國
- 美國

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 **增強地址** 圖格中，選取 **擴充資料**。

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="增強地址圖格的螢幕擷取畫面。":::

1. 檢閱概覽，然後選擇 **下一步**。

1. **選取顧客資料集**，然後選擇要擴充的個人資料或客戶細分。 *Customer* 實體可擴充所有客戶個人資料，然而客戶細分實體僅擴充位於該客戶細分的客戶個人資料。

1. 選取在資料集中格式化地址的方式。 若資料中的地址使用單一欄位，請選擇 **單一屬性位址**。 若資料中的地址使用超過一個資料欄位，請選擇 **複數屬性地址**。

1. 選取 **下一步**，然後對應整合客戶實體中的地址欄位。

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="增強地址的欄位對應頁面。":::

   > [!NOTE]
   > 單屬性和多屬性位址都必須有國家/地區。 缺乏有效或受支援的國家/地區值的地址將不會被擴充。

1. 請選取 **下一步**，完成欄位對應。

1. 提供擴充與 **輸出實體** 的 **名稱**。

1. 檢閱選擇之後，請選取 **儲存擴充**。

## <a name="view-enrichment-results"></a>查看擴充結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**已擴充欄位的客戶數** 可讓您向下鑽研到每個擴充的欄位。

### <a name="overview-card"></a>概覽卡片

 **客戶變更摘要** 卡片顯示擴充覆蓋率的詳細資料：

- **已處理且已變更的地址**：已成功擴充的客戶個人資料的地址數量。
- **處理好卻未變更的地址**：識別完成但無法變更的客戶個人資料地址數量。 當輸入資料有效且無法由擴充改善時，通常會發生此問題。
- **未處理也未變更的地址**：無法識別的客戶個人資料地址數量。 通常表示輸入資料無效或擴充不支援的輸入資料。

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
