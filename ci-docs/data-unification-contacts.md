---
title: 建立統一連絡人設定檔 (預覽版)
description: 完成資料整合程序，以建立連絡人的單一主要資料集。
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305016"
---
# <a name="create-a-unified-contact-profile-preview"></a>建立統一連絡人設定檔 (預覽版)

[整合商務客戶](map-entities.md)之後，您可以選擇性地為這些客戶整合連絡人，並將整合的連絡人連結至整合的客戶。 連絡人整合程序會對應多個資料來源中的連絡人資料、移除重複資料、比對不同實體的資料、設定語意對應、建立連絡人與客戶之間的關聯性，然後建立統一連絡人設定檔。

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

前幾個步驟與整合客戶步驟相同。

## <a name="prerequisites"></a>先決條件

客戶與連絡人記錄必須有一個將它們連在一起的唯一索引鍵 (稱為外部索引鍵)。 例如，存在於客戶記錄和連絡人記錄中將客戶與連絡人繫結在一起的客戶識別碼。

## <a name="preview-limitations"></a>預覽限制

- 沒有客戶連結的連絡人會遭捨棄。
- 如果已刪除重複的客戶，則會根據合併喜好設定找出入選方記錄。 落選方記錄不在選取之列，因此遭到捨棄。 將會捨棄與落選記錄相關聯的連絡人。
- 客戶可以有多個連絡人，但是連絡人只能連結至單一客戶。
- 語意對應步驟中對應的連絡人屬性是唯一可以顯示在客戶卡片上的屬性。 不過，有 17 個屬性可用。

## <a name="select-source-fields"></a>選取來源欄位

1. 在 **整合連絡人 (預覽版)** 底下，選取 **開始使用**。

1. 為連絡人資料來源[選取實體和欄位](map-entities.md)，包括主索引鍵和屬性類型。

1. 選取 **下一步**。

## <a name="remove-duplicate-records"></a>移除重複資料記錄

1. 或者，為選取的實體[定義重複資料刪除規則](remove-duplicates.md)。

1. 選取 **下一步**。

## <a name="match-conditions"></a>比對條件

1. 為跨實體比對[定義比對順序和規則](match-entities.md)。

1. 選取 **下一步**。

## <a name="unify-contact-fields"></a>整合連絡人欄位

1. [合併和排除連絡人欄位](merge-entities.md)。

1. 選取 **下一步**。

## <a name="define-the-semantic-fields-for-unified-contacts"></a>定義整合連絡人的語意欄位

整合程序中的這個步驟會將整合的連絡人欄位對應至語意類型。 在 B 到 B 中，客戶卡片會顯示客戶。 選取卡片時，所有與客戶相關聯的連絡人都會顯示。 您在此步驟中對應的欄位就是會顯示在卡片上的欄位。

1. 選取對應至整合欄位的語意類型。 如果沒有可用的語意類型，請選取 **無**。

   :::image type="content" source="media/semantic_mapping.png" alt-text="用於定義語意類型的語意欄位頁面螢幕擷取畫面。" lightbox="media/semantic_mapping.png":::

1. 對應所有的整合欄位之後，選取 **下一步**。

## <a name="set-the-relationship-between-contacts-and-accounts"></a>設定連絡人與客戶之間的關聯性

整合程序中的這個步驟會將連絡人連接至其對應的客戶資料。

1. 對每個實體，輸入下列資訊：

   - **來源連絡人實體的外部索引鍵**：選擇將連絡人實體連接至帳戶的屬性。
   - **目標帳戶實體**：選擇與連絡人產生關聯的帳戶實體。

   :::image type="content" source="media/contact_relationship.png" alt-text="用於連接連絡人與客戶實體的關聯性頁面螢幕擷取畫面。":::

1. 選取 **下一步**。

## <a name="review-contact-unification"></a>檢閱連絡人整合

檢閱變更摘要、建立統一設定檔，並檢閱結果。

### <a name="review-and-create-contact-profiles"></a>檢閱和建立連絡人設定檔

整合程序中的最後一個步驟會顯示程序中的步驟摘要，並在建立統一連絡人設定檔之前提供進行變更的機會。

:::image type="content" source="media/b2b_review_contacts.png" alt-text="檢閱和建立連絡人設定檔的螢幕擷取畫面。":::

1. 選取任一連絡人整合步驟上的 **編輯**，以檢閱並進行任何變更。

1. 如果您對選取項目滿意，請選取 **建立連絡人設定檔**。 **整合** 頁面會在建立統一連絡人設定檔時顯示。
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="整合連絡人頁面的螢幕擷取畫面，其中圖標顯示「已排入佇列」或「重新整理中」。":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

整合演算法需要一段時間才能完成，而且在完成前您無法變更設定。

### <a name="view-the-results-of-contact-unification"></a>檢視連絡人整合的結果

整合完成後，**資料** > **整合** 頁面會顯示統一連絡人設定檔的數目。 整合程序中每個步驟的結果都會顯示在各個圖標上。 例如，**來源欄位** 會顯示已對應屬性 (欄位) 數量以及 **重複記錄** 會顯示找到的重複記錄數量。

:::image type="content" source="media/unified_contacts.png" alt-text="資料整合頁面在整合連絡人之後的螢幕擷取畫面。":::

> [!TIP]
> 只有在選取多個實體時，才會顯示 **比對條件** 磚。

我們建議您審查結果，尤其是[比對規則](data-unification-update.md#manage-match-rules)品質，並且依需求加以修正。

需要時，[變更連絡人整合設定](data-unification-update.md)，然後重新執行統一設定檔。

### <a name="verify-output-entities-from-data-unification"></a>驗證資料整合的輸出實體

移至 **資料** > **實體** 以驗證輸出實體。

統一連絡人設定檔實體 (稱為 *ContactProfile*) 會顯示在 **語意實體** 區段中。 第一次成功的整合執行會建立整合的 *ContactProfile* 實體。 所有後續的執行都會展開該實體。

**設定檔** 區段中會建立並顯示 *ContactsCustomer* 實體 (預覽版)。 此實體包含沒有客戶連結的連絡人資料。 此實體用來做為對連絡人整合之語意對應及關聯性步驟的輸入。

**系統** 區段中會建立並顯示重複資料刪除和合併實體。 每個來源實體會建立已刪除重複資料的實體，名稱為 **Deduplication_DataSource_Entity**。 **ContactsConflationMatchPairs** 實體包含有關跨實體比對的實體資訊。

重複資料刪除輸出實體包含下列資訊：
- 識別碼/金鑰
  - 主索引鍵與替代識別碼欄位。 替代識別碼欄位由一個記錄識別出的所有替代識別碼組成。
  - 根據指定的重複資料刪除欄位，Deduplication_GroupId 欄位顯示實體中辨識出的群組或叢集，裡面都是類似記錄。 為系統處理的需求而被使用。 如果未指定手動重複資料刪除規則，並套用系統定義的重複資料刪除規則，您就不會在重複資料刪除輸出實體中找到此欄位。
  - Deduplication_WinnerId：此欄位包含的勝出識別碼來自於已辨識的群組或叢集。 如果 Deduplication_WinnerId 與記錄的主索引鍵相同，則表示該記錄是勝出的記錄。
- 用來定義重複資料刪除規則的欄位。
- 規則和分數欄位，表示所套用的重複資料刪除規則和比對演算法回傳的分數。

## <a name="next-step"></a>後續步驟

設定[活動](activities.md)、[擴充](enrichment-hub.md)或[關聯](relationships.md)，以進一步了解您的連絡人。
