---
title: 檢閱資料整合
description: 檢閱資料整合步驟、建立統一客戶設定檔，以及檢閱結果
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303957"
---
# <a name="review-data-unification"></a>檢閱資料整合

檢閱變更摘要、建立統一設定檔，並檢閱結果。

## <a name="review-and-create-customer-profiles"></a>檢閱和建立客戶設定檔

整合程序的最後一個步驟會顯示程序中的步驟摘要，並在建立統一設定檔前提供變更的機會。

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="檢閱和建立客戶設定檔的螢幕擷取畫面。":::

1. 若要查看並進行任何變更，請在任一資料整合步驟上選取 **編輯**。

1. 如果您對選取項目滿意，請選取 **建立客戶設定檔** (或 B 到 B 的 **建立客戶設定檔**)。 建立統一客戶設定檔時，會顯示 **整合** 頁面。

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="整合頁面的螢幕擷取畫面，顯示「已排入佇列」或「重新整理中」的磚。":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

整合演算法需要一段時間才能完成，而且在完成前您無法變更設定。

## <a name="view-the-results-of-data-unification"></a>檢閱資料整合結果

整合後，**資料** > **整合** 頁面會顯示統一客戶設定檔 (或 B 到 B 的客戶設定檔) 的數目。 整合程序中的每個步驟的結果都會顯示在各個磚上。 例如，**來源欄位** 會顯示已對應屬性 (欄位) 數量以及 **重複記錄** 會顯示找到的重複記錄數量。

:::image type="content" source="media/m3_unified.png" alt-text="資料整合後，資料整合頁面的螢幕擷取畫面。":::

> [!TIP]
> 只有在選取多個實體時，才會顯示 **比對條件** 磚。

我們建議您檢閱結果，尤其是[比對規則](data-unification-update.md#manage-match-rules)品質，並且依需求加以修正。

如有需要，[請變更整合設定](data-unification-update.md)，然後重新執行統一設定檔。

### <a name="verify-output-entities-from-data-unification"></a>驗證資料整合的輸出實體

移至 **資料** > **實體** 以驗證輸出實體。

統一客戶設定檔實體 (稱為 *客戶*) 會顯示在 **設定檔** 區段中。 第一次成功的整合執行會建立整合的 *Customer* 實體。 所有後續的執行都會展開該實體。

**系統** 區段中會建立並顯示重複資料刪除和合併實體。 每個來源實體會建立已刪除重複資料的實體，名稱為 **Deduplication_DataSource_Entity**。 **ConflationMatchPairs** 實體包含有關跨實體比對的實體資訊。

重複資料刪除輸出實體包含下列資訊：
- 識別碼/金鑰
  - 主索引鍵與替代識別碼欄位。 替代識別碼欄位由一個記錄識別出的所有替代識別碼組成。
  - 根據指定的重複資料刪除欄位，Deduplication_GroupId 欄位顯示實體中辨識出的群組或叢集，裡面都是類似記錄。 為系統處理的需求而被使用。 如果未指定手動重複資料刪除規則，並套用系統定義的重複資料刪除規則，您就不會在重複資料刪除輸出實體中找到此欄位。
  - Deduplication_WinnerId：此欄位包含的勝出識別碼來自於已辨識的群組或叢集。 如果 Deduplication_WinnerId 與記錄的主索引鍵相同，則表示該記錄是勝出的記錄。
- 用來定義重複資料刪除規則的欄位。
- 規則和分數欄位，表示所套用的重複資料刪除規則和比對演算法回傳的分數。

## <a name="next-step"></a>後續步驟

- 如果是 B 到 B，可選擇執行[連絡人整合](data-unification-contacts.md)。

- 至於 B 到 C，請設定[活動](activities.md)、[擴充](enrichment-hub.md)、[關聯性](relationships.md)或 [量值](measures.md)，以進一步了解您的客戶。

[!INCLUDE[footer-include](includes/footer-banner.md)]
