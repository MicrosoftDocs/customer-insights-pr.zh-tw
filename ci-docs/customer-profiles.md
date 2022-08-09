---
title: 檢視客戶設定檔
description: 以各種方式查看整合客戶資料，包括使用搜尋和篩選
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188083"
---
# <a name="view-customer-profiles"></a>檢視客戶設定檔

[建立統一 *客戶* 實體之後](data-unification.md)，客戶設定檔即可供使用。 **客戶** 頁面會顯示您的統一客戶設定檔的組合視圖。 客戶可以是個人或組織。

前往 **客戶** 頁面以查看您的客戶及其設定檔。 每個客戶設定檔均以圖格呈現。 使用分頁控制項取得更多筆記錄。 本卡片依據 **搜尋 & 篩選條件索引** 中的定義顯示來自 *客戶* 實體的欄位。 每張卡片中的欄位順序皆由系統挑選。

> [!NOTE]
> 如果當您在選取 **客戶** 時看不到圖格，系統管理員必須在 **搜尋 & 篩選條件索引** 中[至少定義一個可搜尋屬性](search-filter-index.md)。

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="客戶頁面顯示結果圖格。":::

選取下列其中一個動作：
- [檢視客戶詳細資料](#view-customer-details)
- [管理搜尋 & 篩選索引](search-filter-index.md) (僅限管理員)
- [篩選客戶](#filter-customers)
- **展開卡片** 或 **摺疊卡片** 以展開或摺疊客戶圖貼上顯示的資訊
- **排序依據** 特定屬性
- [搜尋客戶](#search-for-customers)

  > [!NOTE]
  > 若要使用搜尋及篩選，管理員必須設定可搜尋的屬性，並使用 [搜尋 & 篩選] 索引來定義可篩選的欄位。

## <a name="search-for-customers"></a>搜尋客戶

在 **搜尋客戶** 中輸入名稱或其他屬性，以搜尋客戶。 可搜尋的屬性是由管理員定義，來自統一的 *客戶* 實體。

> [!NOTE]
> **字串** 是唯一包含在搜尋中的資料類型。 請在 [客戶] 頁面的 **搜尋客戶** 欄位中使用它來搜尋客戶。

## <a name="filter-customers"></a>篩選客戶

可按照 *客戶* 實體欄位篩選客戶。 可篩選的欄位是由管理員定義。

1. 在 **客戶** 頁面上選取 **顯示篩選**。 篩選窗格隨即出現。

1. 選取您要用來篩選客戶的屬性旁邊的方塊。

1. 選取 **清除篩選**，或清除所選屬性旁邊的核取方塊來移除所有篩選。

1. 選取 **隱藏篩選** 關閉篩選窗格。

1. 若要將篩選結果另存為 [客戶細分](segments.md)，請選取 **將篩選另存為客戶細分**。
   1. 輸入客戶細分的名稱
   1. 選取 **儲存** 以儲存客戶細分。
   1. 稍後選取 **啟用**，或 **稍後** 執行，以選擇是否要立即執行該客戶細分。

## <a name="view-customer-details"></a>檢視客戶詳細資料

在 **客戶** 頁面上，選取 [客戶] 圖格以檢視所選客戶的詳細資料。

:::image type="content" source="media/customers-details-B2C.png" alt-text="客戶詳細資料頁面。":::

客戶詳細資料包括：

**客戶設定檔圖格**：顯示統一 *客戶* 實體中的不同值。 除了地址欄位，若選定的客戶個人資料欄位沒有任何值，則不會顯示該欄位。 圖格結構化為下列區段：

- 第一個區段顯示一組預定義欄位，搜尋 & 篩選條件索引一部分的所有欄位隨之在後。 所有地址相關欄位會組合成單列，即便個人資料中不存在地址資訊，此列仍會顯示。
- **此客戶的連絡人** 顯示在企業帳戶環境中。 每位連絡人均顯示於其欄位中。 空白欄位會隱藏。
- **其他欄位**：顯示選取客戶的其餘欄位 (識別碼除外)。
- **識別碼**：列出其對應實體名稱下方的所有識別碼。 欄位會根據其語義標識為識別碼。

如果您已經設定 [活動](activities.md)，**活動時間表** 會顯示資料。 時間表視圖包含最近一次活動以來，選取客戶依時間排序的活動。

**Insights**：

- **量值** 會顯示您是否已設定[客戶屬性量值](measures.md)。 它們包括圍繞您的客戶在個別客戶等級的 KPI 計算值。

- **潛在興趣、潛在品牌** 會顯示您是否已設定[品牌或利益相似性擴充](enrichment-microsoft.md)。 根據設定檔與選取客戶設定檔類似的其他客戶，呈現潛在的利益和相似性。

若要返回 **客戶** 頁面，請選取 **返回客戶**。

## <a name="next-steps"></a>後續步驟

[新增更多資料來源](data-sources.md)、[擴充統一的設定檔](enrichment-hub.md)或[建立區段](segments.md)，以便在其他應用程式中搭配統一的客戶設定檔。

[!INCLUDE [footer-include](includes/footer-banner.md)]
