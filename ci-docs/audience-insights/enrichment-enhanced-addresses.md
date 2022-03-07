---
title: 地址增強擴充
description: 使用 Microsoft 模型擴充和標準化客戶個人資料的地址資訊。
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965568"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>以增強的地址擴充的客戶個人資料

資料中的地址可能未結構化、不完整或不正確。 使用 Microsoft 的模型，標準化地址並擴充成 [Common Data Model 格式](/common-data-model/schema/core/applicationcommon/address)，以取得更佳的準確性和洞察力。

## <a name="how-we-enhance-addresses"></a>我們如何增強地址

我們的模型以二步驟流程來增強地址。 首先，它會解析地址找出其組成部分，並將它們設定為結構化格式。 然後，我們使用人工智慧來更正、完成和標準化地址中的值。

### <a name="example"></a>範例

地址資訊可能是非標準格式且含有拼寫錯誤。 此模型可以修正這些問題，並在整合的客戶個人資料中建立一致的地址。

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

此模型使用機器學習技術來增強地址。 在模型變更輸入值時套用高的信賴度閥值，則與任何使用中的模型一樣，不能保證 100% 準確性。

## <a name="supported-countries-or-regions"></a>支援的國家或地區

目前我們在這些國家或地區支援增強地址： 

- 澳洲
- 加拿大
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
   > 國家/地區在單一屬性和複數屬性位址中都是必要的。 缺乏有效或受支援的國家/地區值的地址將不會被擴充

1.  請從整合客戶實體對應至地址欄位。

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="增強地址的欄位對應頁面。":::

1. 請選取 **下一步**，完成欄位對應。

1. 提供擴充與輸出實體的名稱。

1. 檢閱選擇之後，請選取 **儲存擴充**。

## <a name="enrichment-results"></a>擴充結果

若要開始擴充程序，請從命令列中選取 **執行**。 您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。 處理時間視客戶資料的大小而定。

擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。 此外，您還會找到上次更新時間以及已擴充的設定檔數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

## <a name="next-steps"></a>後續步驟

建立在您擴充的客戶資料之上。 建立[客戶細分](segments.md)、[量值](measures.md)，甚至[匯出資料](export-destinations.md)，以便傳送個人化體驗給您的客戶。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
