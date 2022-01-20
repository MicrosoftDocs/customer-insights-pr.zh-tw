---
title: 地址增強擴充 (包括影片)
description: 使用 Microsoft 模型擴充和標準化客戶個人資料的地址資訊。
ms.date: 12/16/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: afb1a6b4805702697889bb91ca36a96a714cba3d
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934913"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>以增強的地址擴充的客戶個人資料

資料中的地址可能未結構化、不完整或不正確。 使用 Microsoft 的模型，標準化地址並擴充成 [Common Data Model 格式](/common-data-model/schema/core/applicationcommon/address)，以取得更佳的準確性和洞察力。

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

增強位址只能用在已擷取的地址資料中現有的值。 模型不能： 

1. 確認地址是否為有效的地址。
2. 確認任何值 (如郵遞區號或街道名稱) 是有效的。
3. 變更無法識別的值。

此模型使用機器學習技術來增強地址。 雖然在模型更改輸入值時，我們套用了高信賴度閾值，但與任何基於機器學習的模型一樣，無法保證 100% 的準確性。

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

地址必須包含國家/地區值。 不支援的國家或地區的地址以及沒有提供國家或地區的地址，無法處理。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**。

1. 在 **增強地址** 圖格中，選取 **擴充資料**。

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="增強地址圖格的螢幕擷取畫面。":::

1. 選取 **客戶資料集**，並選擇包含要擴充地址的實體。 您可以選取 *客戶* 實體來擴充所有客戶個人資料中的位址，或者選取一個客戶細分實體來擴充只在該客戶細分中包含的客戶個人資料內的位址。

1. 選取在資料集中格式化地址的方式。 若資料中的地址使用單一欄位，請選擇 **單一屬性位址**。 若資料中的地址使用超過一個資料欄位，請選擇 **複數屬性地址**。

   > [!NOTE]
   > 單屬性和多屬性位址都必須有國家/地區。 缺乏有效或受支援的國家/地區值的地址將不會被擴充。

1.  請從整合客戶實體對應至地址欄位。

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="增強地址的欄位對應頁面。":::

1. 請選取 **下一步**，完成欄位對應。

1. 提供擴充與輸出實體的名稱。

1. 檢閱選擇之後，請選取 **儲存擴充**。

## <a name="enrichment-results"></a>擴充結果

若要開始擴充程序，請從命令列中選取 **執行**。 您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。 處理時間視客戶資料的大小而定。

擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。 此外，您還會找到上次更新時間以及已擴充的設定檔數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

### <a name="overview-card"></a>概覽卡片

概覽卡片顯示擴充覆蓋率的詳細資料。 

* **已處理且已變更的客戶**：已成功擴充的客戶個人資料數量。

* **處理好卻未變更的客戶**：識別完成但無法變更的客戶個人資料數量。 當輸入資料有效且無法由擴充改善時，通常會發生此問題。

* **未處理且未變更的客戶**：無法識別的客戶個人資料數量。 通常表示輸入資料無效或擴充不支援的輸入資料。

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
