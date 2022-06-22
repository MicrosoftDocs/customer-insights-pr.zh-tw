---
title: 更新整合設定
description: 在整合設定中，更新重複規則、比對規則或整合欄位。
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 590a2996cf8b2b1c6def59b78583169ec1910b59
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844030"
---
# <a name="update-the-unification-settings"></a>更新整合設定

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

若要在建立整合個人資料後，立即審查或變更任何整合設定，請執行下列步驟。

1. 請前往 **資料** > **整合**。

   :::image type="content" source="media/m3_unified.png" alt-text="資料整合後，資料整合頁面的螢幕擷取畫面。":::

   > [!TIP]
   > 只有在選取多個實體時，才會顯示 **比對條件** 磚。

1. 選取你想要更新的部分：
   - [來源欄位](#edit-source-fields)，可新增實體或屬性或變更屬性類型。
   - [重複資料記錄](#manage-deduplication-rules)，可管理重複資料刪除規則或合併喜好設定。
   - [比對條件](#manage-match-rules)，可在兩個或多個實體之間更新比對規則。
   - [整合客戶欄位](#manage-unified-fields)，可合併或排除欄位。 您也可以將相關個人資料群組成叢集。

1. 進行變更之後，請選取您的下一個選項：

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="頁面螢幕擷取畫面：醒目提示 [整合] 選項的資料整合頁面。":::

   - [執行比對條件](#run-matching-conditions)可以在不更新整合個人資料的情況下，快速評估比對條件 (重複資料刪除和比對規則) 的品質，。 單一實體不會顯示 **僅執行比對條件** 選項。
   - [整合客戶個人資料](#run-updates-to-the-unified-customer-profile)以執行比對規則並更新整合客戶個人資料實體，且不影響相依性 (例如擴充、客戶細分或量值)。 相依程序不會執行，但是會根據[重新整理排程](system.md#schedule-tab)的定義進行重新整理。
   - [整合客戶個人資料與相依性](#run-updates-to-the-unified-customer-profile)以執行比對規則並更新整合客戶個人資料實體以及所有相依性 (例如擴充、客戶細分或量值)。 所有程式都會自動重新執行。

## <a name="edit-source-fields"></a>編輯來源欄位

如果屬性或實體已經是整合的，您無法移除。

1. 在 **來源欄位** 磚上選取 **編輯**。

   :::image type="content" source="media/m3_source_edit.png" alt-text="螢幕擷取畫面：顯示主鍵數、對應和未對應欄位的來源欄位頁面":::

   顯示的對應與未對應欄位數量。

1. 選取 **選取實體及欄位** 新增其他屬性或實體。 使用搜尋或捲動方式，尋找並選取感興趣的屬性及實體。 選取 **套用**。

1. 您也可以選擇變更實體、屬性類型的主索引鍵，以及開啟或關閉 **智慧對應**。 如需詳細資訊，請參閱 [選取屬性的主索引鍵及語義類型](map-entities.md#select-primary-key-and-semantic-type-for-attributes)。

1. 選取 **下一步** 以變更重複資料刪除規則，或選取 **儲存後關閉** 並返回[更新整合設定](#update-the-unification-settings)。

## <a name="manage-deduplication-rules"></a>管理重複資料刪除規則

1. 在 **重複資料紀錄** 磚上選取 **編輯**。

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="螢幕擷取畫面：顯示重複資料記錄數量的重複資料記錄頁面" lightbox="media/m3_duplicates_edit.png":::

   找到的重複資料記錄數量會顯示在 **重複資料** 下。 **記錄重複** 欄會顯示出現重複資料記錄的實體以及重複資料記錄的百分比。

1. 如果新增了已擴充的實體，請選取 **使用已擴充實體**。 如需詳細資訊，請參閱[資料來源擴充](data-sources-enrichment.md)。

1. 若要管理重複資料刪除規則，請選擇下列任一選項：
   - **建立新規則**：在適當實體下方選取 **新增規則**。 如需更多資訊，請見 [定義重複資料刪除規則](remove-duplicates.md#define-deduplication-rules)。
   - **變更規則條件**：選取規則，然後 **編輯**。 變更欄位、新增或移除條件，或是新增或移除例外。
   - **預覽**：選取規則，然後進行 **預覽**，可查看此規則的上次執行結果。
   - **停用規則**：選取規則，然後選取 **停用**，保留重復資料刪除規則，同時從比對程序中排除它。
   - **複製規則**：選取規則，然後進行 **複製**，可運用修改來建立的類似規則。
   - **刪除規則**：選取規則，然後選取 **刪除**。

1. 若要變更合併喜好設定，請選取該實體。 只有在建立規則後，才能變更喜好設定。
   1. 選取 **編輯合併喜好選項**，並變更 **保留記錄** 選項。
   1. 若要變更實體各別屬性的合併喜好設定，請選取 **進階** 並進行必要變更。

      :::image type="content" source="media/m3_adv_merge.png" alt-text="進階合併喜好設定的螢幕擷取畫面，其中顯示最新近的電子郵件和最完整的地址":::

   1. 選取 **完成**。

1. 選取 **下一步** 來變更比對條件，或選取 **儲存後關閉** 並返回[更新整合設定](#update-the-unification-settings)。

## <a name="manage-match-rules"></a>管理比對規則

您可以重新設定和微調大部分的比對參數。 您無法新增或刪除實體。 比對規則不適用於單一實體。

1. 在 **比對條件** 磚上選取 **編輯**。

   :::image type="content" source="media/m3_match_edit.png" alt-text="包含統計資料的比對規則及條件頁面的螢幕擷取畫面。" lightbox="media/m3_match_edit.png":::

   此頁面會顯示比對順序及已定義的規則以及下列統計資料：
   - **唯一來源記錄** 顯示上次比對執行處理的個別來源記錄的數量。
   - **比對和未比對的記錄** 醒目提示比對規則處理後保留多少唯一記錄。
   - **僅限相符的記錄** 顯示所有比對組的相符數量。

1. 若要查看所有規則及其分數的結果，請選取 **查看上次執行**。 其結果會顯示，並包括替代連絡人識別碼。 您可以下載結果。

1. 若要查看特定規則的結果和分數，請選取規則，然後進行 **預覽**。 顯示結果。 您可以下載結果。

1. 若要在規則上查看特定條件的結果和分數，請選取規則，然後選取 **編輯**。 在編輯窗格，在條件下選取 **預覽**。 您可以下載結果。

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="不相符和相符記錄的圖形化呈現，並包含資料的清單。":::

1. 如果新增了已擴充的實體，請選取 **使用已擴充實體**。 如需詳細資訊，請參閱[資料來源擴充](data-sources-enrichment.md)。

1. 若要管理規則，請選擇下列任一選項：
   - **建立新規則**：在適當實體下方選取 **新增規則**。 如需詳細資訊，請參閱 [定義比對配對組的規則](match-entities.md#define-rules-for-match-pairs)。
   - 如果您定義多個規則，**請變更規則的順序**：將規則拖曳並放入想要的順序位置。 更多詳細資訊，請參閱 [指定比對順序](match-entities.md#specify-the-match-order)。
   - **變更規則條件**：選取規則，然後 **編輯**。 變更欄位、新增或移除條件，或是新增或移除例外。
   - **停用規則**：選取規則，然後選取 **停用**，保留比對規則，同時從比對程序中排除它。
   - **複製規則**：選取規則，然後進行 **複製**，可運用修改來建立的類似規則。
   - **刪除規則**：選取規則，然後選取 **刪除**。

1. 選取 **下一步** 來變更整合欄位，或選取 **儲存後關閉** 並返回[更新整合設定](#update-the-unification-settings)。

## <a name="manage-unified-fields"></a>管理整合欄位

1. 在 **整合客戶欄位** 磚上選取 **編輯**。

    :::image type="content" source="media/m3_merge_edit.png" alt-text="整合客戶欄位的螢幕擷取畫面":::

1. 請檢查合併和排除的欄位，並進行任何需要的變更。 在叢集中新增或編輯 CustomerID 索引鍵或群組設定檔。 如需詳細資訊，請參閱[整合客戶欄位](merge-entities.md)。

1. 選取 **下一步** 可審查整合設定並 [更新整合個人資料和相依性](#run-updates-to-the-unified-customer-profile)，或者選取 **儲存後關閉** 並返回[更新整合設定](#update-the-unification-settings)進行更多變更。

## <a name="run-matching-conditions"></a>執行比對條件

執行比對條件僅執行重複資料刪除及比對規則，同時將更新 *Deduplication_* 與 *ConflationMatchPair* 實體。

1. 在 **資料** > **整合** 頁面中，選取 **只執行比對條件**。

   **重複資料記錄** 和 **比對條件** 磚會顯示 **已排入佇列** 或 **正在重新整理** 狀態。

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. 當比對程序完成時，請在 **比對條件** 磚上選取 **編輯**。

   :::image type="content" source="media/match-KPIs.png" alt-text="比對頁面上關鍵計量的螢幕擷取畫面 (已裁剪)，畫面上有數字和詳細資訊。":::

1. 若要進行變更，請參閱 [管理重複資料刪除規則](#manage-deduplication-rules)或 [管理比對規則](#manage-match-rules)。

1. 重新執行比對程序，或[執行客戶個人資料的更新](#run-updates-to-the-unified-customer-profile)。

## <a name="run-updates-to-the-unified-customer-profile"></a>執行整合客戶個人資料的更新

1. 從 **資料** > **整合** 頁面中，選取：

   - **整合客戶個人資料**：執行比對規則並更新整合客戶個人資料實體，且不影響相依性 (例如擴充、客戶細分或量值)。 相依程序不會執行，但是會根據[重新整理排程](system.md#schedule-tab)的定義進行重新整理。

   - **整合客戶個人資料和相依性**：執行比對規則並更新整合個人資料和所有相依性。 所有程式都會自動重新執行。 在所有下游程序完成後，客戶個人資料就會反映更新的資料。

   **重複資料記錄**、**比對條件**，和 **整合客戶欄位** 磚會顯示 **已排入佇列** 或 **正在重新整理** 狀態。

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

在 **整合** 頁面上成功執行的結果，會顯示整合客戶個人資料的數量。
