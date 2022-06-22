---
title: 公司資料增強
description: 使用 Microsoft 模型來擴充和標準化公司資料。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953939"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>使用增強型公司設定資料來擴充公司資料

使用 Microsoft 模型及已彙集的公司資料，來更正、補充和標準化您的公司設定資料。 我們將使用 [Common Data Model 格式 ](/common-data-model/schema/core/applicationcommon/account)，以取得更佳的準確性和見解。

您也可以在[資料來源上擴充公司資料](data-sources-enrichment.md)，以改善資料整合程序中的比對精確性。

對於美國的上市公司，可提供如收入、股票代號、產業及其他的資訊。  

## <a name="how-we-enhance-company-data"></a>我們如何增強公司資料

我們的模型經過兩步驟程序，來增強公司設定資料。 首先，它會標準化公司名稱。 例如，*Microsoft Corp* 將會被修正並標準化至 *Microsoft Corporation*。 它會嘗試在 Microsoft 已彙集的公司資料中尋找相符項目。 如果找到相符項目，我們就會使用我們所搜集的公司資料 (包括公司名稱) 來擴充公司設定資料。

### <a name="example"></a>範例

您的公司資訊可能不符合標準格式，並包含拼寫錯誤。 模型會嘗試修正這些問題，並建立一致的資訊。

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>限制

模型不能：

- 確認公司的身份。 我們不會驗證輸入內容是否為現有的組織，或驗證是否有公司使用輸出內容做為其標準名稱。
- 全面涵蓋全球公司。 Microsoft 的已彙集的公司資料可涵蓋全球範圍，但提供的涵蓋區域大部分在澳大利亞、加拿大、英國和美國。
- 以全面標準化公司地址。 目前我們支援標準化這些國家/地區中的地址：澳大利亞、加拿大、法國、德國、義大利、日本、英國和美國。
- 保證資料的準確性或新穎度。 隨著商務資訊經常變更，我們無法保證提供的增強型公司資料總是準確或最新的。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 **增強型公司資料** 圖格中，選取 **擴充我的資料**。

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="在擴充中心的公司資料擴充圖格。":::

1. 檢閱概覽，然後選擇 **下一步**。

1. **選取顧客資料集**，然後選擇要擴充的個人資料或客戶細分。 *Customer* 實體可擴充所有客戶個人資料，然而客戶細分實體僅擴充位於該客戶細分的客戶個人資料。

1. 在您的公司設定資料中選取要用來與 Microsoft 已彙集的公司資料比對的欄位類型。 這項選取將會影響在下一個步驟中可以存取的對應欄位。

1. 選取 **下一步**。

1. 將公司欄位對應至 Microsoft 的公司資料。 為了提高比對精準度，請新增更多的欄位。

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="設定公司擴充時的資料對應步驟。":::

1. 請選取 **下一步**，完成欄位對應。

1. 提供擴充與 **輸出實體** 的 **名稱**。

1. 檢閱選擇之後，請選取 **儲存擴充**。

1. 選取 **執行** 以開始擴充程序，或者直接關閉返回至 **擴充** 頁面。

## <a name="enrichment-results"></a>擴充結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>概覽卡片

 **客戶變更摘要** 磚顯示擴充覆蓋率的詳細資料

- **已處理且已變更的公司**：已成功擴充的客戶公司個人資料數量。
- **處理好卻未變更的公司**：識別完成但無法變更的客戶公司個人資料數量。 當輸入資料有效且無法由擴充改善時，通常會發生此問題。
- **未處理也未變更的公司**：無法識別的客戶公司個人資料數量。 通常發生在輸入資料無效或擴充不支援的輸入資料。

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
