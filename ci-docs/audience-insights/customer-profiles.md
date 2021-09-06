---
title: 檢視客戶設定檔
description: 取得您的統一客戶資料的組合視圖。
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 87323d15c44ef82ae8bc3cc971be6c36356121571cb9a9630be699ac2d157bf6
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032794"
---
# <a name="customer-profiles"></a>客戶設定檔

**客戶** 頁面會根據從 [所有資料來源](data-sources.md) 收集的設定檔資料顯示您的客戶的組合視圖。 [建立統整的客戶實體](data-unification.md)之後，客戶設定檔即可供使用。 請確定您已完成資料統整程序，以獲得更豐富的客戶檢視表。 頁面也可讓您搜尋客戶。

客戶可以是個人或組織 (預覽)。 每個客戶或組織設定檔都是以圖標表示。 選取一個圖標以查看該特定客戶或組織的其他資訊。 使用頁面底部的分頁控制項，查看任何記錄。

> [!div class="mx-imgBorder"] 
> ![B2C 客戶個人資料。](media/profiles-customers.png "B2C 客戶設定檔")

組織 (預覽)
> [!div class="mx-imgBorder"] 
> ![B2B 客戶個人資料。](media/profile-customers-b2b.png "B2B 客戶設定檔")

> [!NOTE]
> 如果您在導覽中選 **客戶** 時看不到圖標，系統管理員必須在 **搜尋和篩選索引** 中[至少定義一個可搜尋屬性](search-filter-index.md)。

## <a name="search-for-customers"></a>搜尋客戶

在搜尋方塊中輸入名稱或其他屬性，以搜尋客戶。 搜尋只能在資料統整處理期間建立的客戶設定檔實體中運作。

做為系統管理員，您可以使用 **搜尋和篩選索引** 頁面來設定可搜尋的屬性。 如需詳細資訊，請參閱[管理搜尋和篩選索引](search-filter-index.md)。

## <a name="filter-customers"></a>篩選客戶

您可以依據客戶設定檔實體欄位來篩選客戶。 與搜尋類似，您的系統管理員必須使用 **搜尋和篩選索引** 頁面，將欄位定義為可篩選。

1. 選取 **客戶** 頁面上的 **篩選**。

2. 選取您要用來篩選客戶的屬性旁邊的方塊。

   > [!div class="mx-imgBorder"] 
   > ![客戶個人資料。](media/profiles-customers3.png "客戶設定檔")

3. 選取 **客戶** 頁面上的 **清除篩選條件** 移除您的篩選條件。

##  <a name="customer-details-page"></a>客戶詳細資料頁面

選取任何客戶圖格打開 **客戶詳細資料頁面**。 此視圖表包含選取客戶的統一資訊。

客戶詳細資料包括：

-   **客戶個人資料圖格**：此圖格顯示與整合客戶個人資料實體不同的值。 這些詳細資料會包括電子郵件地址、名稱、城市等等。 

-   **潛在興趣、潛在品牌**：顯示您是否已經設定第一方擴充。 它代表客戶設定檔與此客戶可能有的類似設定檔的品牌潛在利益和關聯。 如需詳細資訊，請參閱[使用品牌及興趣同質性擴充客戶設定檔](enrichment-microsoft.md)。

-   **量值**：顯示您是否已經為一個特定類型「客戶屬性量值」，設定好一個或多個量值。 它們包括圍繞您的客戶在個別客戶等級的 KPI 計算值。 如需詳細資訊，請見 [定義和管理量值](measures.md)。

-   **活動時間表**：顯示您是否已設定好活動。 時間表視圖包含最近一次活動開始，依時間先後排序的客戶活動。 如需詳細資訊，請參閱[客戶活動](activities.md)。

選取 **返回客戶** 以退回客戶搜尋頁面。

## <a name="next-steps"></a>後續步驟

[新增更多資料來源](data-sources.md)、[擴充整合個人資料](enrichment-hub.md)，或[建立客戶細分](segments.md)，才能使用其他應用程式中的整合個人資料。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
