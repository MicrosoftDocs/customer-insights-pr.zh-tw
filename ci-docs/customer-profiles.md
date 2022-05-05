---
title: 檢視客戶設定檔
description: 取得您的統一客戶資料的組合視圖。
ms.date: 09/30/2021
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
ms.openlocfilehash: 45ef6abcd612178a097569825e32ff9ac779de01
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645733"
---
# <a name="customer-profiles"></a>客戶設定檔

**客戶** 頁面顯示您的統一客戶設定檔的組合視圖。 一旦[建立統一客戶實體](data-unification.md)，客戶設定檔隨即可用。 本頁面讓您搜尋客戶並定義搜尋索引。

客戶可以是個人或組織。 每個客戶設定檔均以圖格呈現。 使用分頁控制項取得更多筆記錄。 本卡片依據 **搜尋 & 篩選條件索引** 中的定義顯示來自 *客戶* 實體的欄位。 每張卡片中的欄位順序皆由系統挑選。

請選取圖格並在名為[客戶詳細資料頁面](customer-profiles.md#customer-details-page)的專用頁面中查看選取客戶的資料。

> [!div class="mx-imgBorder"] 
> ![客戶頁面顯示結果圖格](media/customers-page-result-tiles-B2C.png "客戶頁面顯示結果圖格")

> [!NOTE]
> 如果當您在導覽中選取 **客戶** 時看不到圖格，系統管理員必須在 **搜尋 & 篩選條件索引** 中[至少定義一個可搜尋屬性](search-filter-index.md)。

## <a name="search-for-customers"></a>搜尋客戶

在搜尋方塊中輸入名稱或其他屬性，以搜尋客戶。 搜尋只在資料統一處理期間才能在建立的 _客戶_ 實體中進行。

做為系統管理員，您可以使用 **搜尋和篩選索引** 頁面來設定可搜尋的屬性。 如需詳細資訊，請前往[管理搜尋 & 篩選條件索引](search-filter-index.md)。

## <a name="filter-customers"></a>篩選客戶

您可以按照 _客戶_ 實體欄位篩選客戶。 與搜尋類似，您的系統管理員必須使用 **搜尋和篩選索引** 頁面，將欄位定義為可篩選。

1. 請在 **客戶** 頁面上選取 **顯示篩選條件**。

1. 選取您要用來篩選客戶的屬性旁邊的方塊。

1. 選取 **客戶** 頁面上的 **清除篩選條件** 移除您的篩選條件。

## <a name="customer-details-page"></a>客戶詳細資料頁面

選取任何客戶圖格打開 **客戶詳細資料頁面**。 此視圖表包含選取客戶的統一資訊。 客戶詳細資料包括內容如下：

**客戶設定檔圖格**：此方塊顯示統一 _客戶_ 實體中的不同值。 若選取的客戶設定檔欄位沒有任何數值，不會顯示該欄位。 圖格結構化為下列區段：  
  - 第一個區段顯示一組預定義欄位，搜尋 & 篩選條件索引一部分的所有欄位隨之在後。 如果設定檔包含此類欄位，則所有位址相關欄位會組合成單行。 
  - **此客戶的連絡人**：在商務帳戶環境中，您將看到此客戶的所有相關連絡人做為第二個區段。 每位連絡人均顯示於其欄位中。 空白欄位會隱藏。
  - **其他欄位**：顯示選取客戶的其餘欄位 (識別碼除外)。 
  - **識別碼**：列出其對應實體名稱下方的所有識別碼。 欄位根據語義辨別為識別碼，依此將欄位分類。

**活動時間表**：如果您已經組態活動，資料會顯示出來。 時間表視圖包含最近一次活動以來，選取客戶依時間排序的活動。 如需詳細資訊，請前往[客戶活動](activities.md)。

**Insights**：  
  - **量值**：顯示是否已組態一個或多個量值客戶屬性量值。 它們包括圍繞您的客戶在個別客戶等級的 KPI 計算值。 如需詳細資訊，請前往[定義和管理量值](measures.md)。

  - **潛在興趣、潛在品牌**：如果您已經組態品牌或利益相似性擴充，會顯示出來。 根據設定檔與選取客戶設定檔類似的其他客戶，呈現潛在的利益和相似性。 如需詳細資訊，請前往[以品牌和利益相似性擴充客戶設定檔](enrichment-microsoft.md)。

若要返回客戶搜尋頁面，請選取 **返回客戶**。

## <a name="next-steps"></a>後續步驟

[新增更多資料來源](data-sources.md)、[擴充統一的設定檔](enrichment-hub.md)或[建立區段](segments.md)，以便在其他應用程式中搭配統一的客戶設定檔。


[!INCLUDE [footer-include](includes/footer-banner.md)]
