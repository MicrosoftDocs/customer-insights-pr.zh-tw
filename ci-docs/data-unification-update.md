---
title: 更新客戶、帳戶或連絡人的整合設定
description: 更新客戶或帳戶整合設定中的重複規則、比對規則或整合欄位。
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304325"
---
# <a name="update-unification-settings"></a>更新整合設定

若要在建立統一設定檔後立即檢閱或變更任何整合設定，請執行下列步驟。

1. 請前往 **資料** > **整合**。

   對於個別客戶 (B 到 C)，**整合** 頁面會顯示統一客戶設定檔的數目，以及每個整合步驟的圖標。

   :::image type="content" source="media/m3_unified.png" alt-text="資料整合後，資料整合頁面的螢幕擷取畫面。" lightbox="media/m3_unified.png":::

   對於商務客戶 (B 到 B)，**整合** 頁面會顯示統一客戶設定檔的數目，以及每個客戶整合步驟的圖標。 如果連絡人已整合，則會顯示統一連絡人設定檔的數目，以及每個連絡人整合步驟的圖標。 根據您要更新的資訊，在 **整合帳戶** 或 **整合連絡人 (預覽版)** 底下選擇適當的圖標。

   :::image type="content" source="media/b2b_unified.png" alt-text="資料整合頁面在整合帳戶和連絡人資料後的螢幕擷取畫面。" lightbox="media/b2b_unified.png":::

   > [!TIP]
   > 只有在選取多個實體時，才會顯示 **比對條件** 磚。

1. 選取你想要更新的部分：
   - [來源欄位](#edit-source-fields)，可新增實體或屬性或變更屬性類型。
   - [重複資料記錄](#manage-deduplication-rules)，可管理重複資料刪除規則或合併喜好設定。
   - [比對條件](#manage-match-rules)，可在兩個或多個實體之間更新比對規則。
   - [整合客戶欄位](#manage-unified-fields)，可合併或排除欄位。 您也可以將相關設定檔群組成叢集。
   - [語意欄位](#manage-semantic-fields-for-unified-contacts)，用於管理整合連絡人欄位的語意類型。
   - [關聯性](#manage-contact-and-account-relationships)，用於管理連絡人對帳戶的關聯。

1. 進行變更之後，請選取您的下一個選項：

   - [執行比對條件](#run-matching-conditions)可以在不更新統一設定檔的情況下，快速評估比對條件 (重複資料刪除和比對規則) 的品質。 單一實體不會顯示 **僅執行比對條件** 選項。
   - [整合設定檔](#run-updates-to-the-unified-profile)，用於執行比對條件，以及在不影響相依性 (例如擴充、客戶細分或量值) 的情況下更新統一設定檔實體。 相依程序不會執行，但是會根據[重新整理排程](schedule-refresh.md)的定義進行重新整理。
   - [整合設定檔與相依性](#run-updates-to-the-unified-profile)，用於執行比對條件、更新統一設定檔實體，以及更新所有相依性 (例如擴充、客戶細分或量值)。 所有程式都會自動重新執行。 在 B 到 B 中，對於更新統一設定檔的帳戶和連絡人實體都會執行整合。

## <a name="edit-source-fields"></a>編輯來源欄位

如果屬性或實體已經是整合的，您無法移除。

1. 在 **來源欄位** 磚上選取 **編輯**。

   :::image type="content" source="media/m3_source_edit.png" alt-text="螢幕擷取畫面：顯示主鍵數、對應和未對應欄位的來源欄位頁面":::

   顯示的對應與未對應欄位數量。

1. 若要新增其他屬性或實體，請選擇 **選取實體及欄位**。

1. 您也可以選擇變更實體、屬性類型的主索引鍵，以及開啟或關閉 **智慧對應**。 如需詳細資訊，請參閱[選取來源欄位](map-entities.md)。

1. 選取 **下一步** 以變更重複資料刪除規則，或選取 **儲存後關閉** 並返回[更新整合設定](#update-unification-settings)。

## <a name="manage-deduplication-rules"></a>管理重複資料刪除規則

1. 在 **重複資料紀錄** 磚上選取 **編輯**。

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="螢幕擷取畫面：顯示重複資料記錄數量的重複資料記錄頁面" lightbox="media/m3_duplicates_edit.png":::

   找到的重複資料記錄數量會顯示在 **重複資料** 下。 **記錄重複** 欄會顯示出現重複資料記錄的實體以及重複資料記錄的百分比。

1. 若要使用已擴充的實體，請選取 **使用已擴充實體**。 如需詳細資訊，請參閱[資料來源擴充](data-sources-enrichment.md)。

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

   1. 選取 **完成**。

1. 選取 **下一步** 以變更比對條件，或選取 **儲存後關閉** 並返回[更新整合設定](#update-unification-settings)。

## <a name="manage-match-rules"></a>管理比對規則

您可以重新設定和微調大部分的比對參數。 您無法新增或刪除實體。 比對規則不適用於單一實體。

1. 在 **比對條件** 磚上選取 **編輯**。

   :::image type="content" source="media/m3_match_edit.png" alt-text="包含統計資料的比對規則及條件頁面的螢幕擷取畫面。" lightbox="media/m3_match_edit.png":::

   此頁面會顯示比對順序及已定義的規則以及下列統計資料：
   - **唯一來源記錄** 顯示上次比對執行所處理個別來源記錄的數量。
   - **比對和未比對的記錄** 醒目提示處理比對規則後剩餘多少不重複的記錄。
   - **僅限相符的記錄** 顯示所有比對組的相符項目數量。

1. 若要查看所有規則及其分數的結果，請選取 **查看上次執行**。 結果隨即顯示，並包括替代連絡人識別碼。 您可以下載結果。

1. 若要查看特定規則的結果和分數，請選取規則，然後進行 **預覽**。 結果隨即顯示。 您可以下載結果。

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

1. 選取 **下一步** 以變更整合欄位，或選取 **儲存後關閉** 並返回[更新整合設定](#update-unification-settings)。

## <a name="manage-unified-fields"></a>管理整合欄位

1. 在 **整合客戶欄位** 磚上選取 **編輯**。

    :::image type="content" source="media/m3_merge_edit.png" alt-text="整合客戶欄位的螢幕擷取畫面":::

1. 請檢查合併和排除的欄位，並進行任何需要的變更。 在叢集中新增或編輯 CustomerID 索引鍵或群組設定檔。 如需詳細資訊，請參閱[整合客戶欄位](merge-entities.md)。

1. 對於客戶或帳戶，選取 **下一步** 以檢閱並[更新統一設定檔和相依性](#run-updates-to-the-unified-profile)。 或選取 **儲存後關閉** 並返回[更新整合設定](#update-unification-settings)以進行其他變更。

   對於連絡人，選取 **下一步** 以管理語意欄位。 或選取 **儲存後關閉** 並返回[更新整合設定](#update-unification-settings)以進行其他變更。

## <a name="manage-semantic-fields-for-unified-contacts"></a>管理整合連絡人的語意欄位

1. 選取 **語意欄位** 圖標上的 **編輯**。

1. 若要變更整合欄位的語意類型，請選取新的類型。 如需詳細資訊，請參閱[定義整合連絡人的語意欄位](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts)。

1. 選取 **下一步** 以管理帳戶或連絡人關聯性，或選取 **儲存後關閉** 並返回[更新整合設定](#update-unification-settings)以進行其他變更。

## <a name="manage-contact-and-account-relationships"></a>管理連絡人與帳戶關聯性

1. 選取 **關聯性** 圖標上的 **編輯**。

1. 若要變更連絡人與帳戶關聯性，請變更下列任何資訊：

   - **來源連絡人實體的外部索引鍵**：選擇將連絡人實體連接至帳戶的屬性。
   - **目標帳戶實體**：選擇與連絡人產生關聯的帳戶實體。

1. 選取 **下一步** 以檢閱整合設定並 [更新統一設定檔和相依性](#run-updates-to-the-unified-profile)，或選取 **儲存後關閉** 並返回[更新整合設定](#update-unification-settings)以進行其他變更。

## <a name="run-matching-conditions"></a>執行比對條件

執行比對條件僅執行重複資料刪除及比對規則，同時將更新 *Deduplication_* 與 *ConflationMatchPair* 實體。

1. 在 **資料** > **整合** 頁面中，選取 **只執行比對條件**。

   **重複資料記錄** 和 **比對條件** 磚會顯示 **已排入佇列** 或 **正在重新整理** 狀態。

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. 當比對程序完成時，請在 **比對條件** 磚上選取 **編輯**。

   :::image type="content" source="media/match-KPIs.png" alt-text="比對頁面上關鍵計量的螢幕擷取畫面 (已裁剪)，畫面上有數字和詳細資訊。":::

1. 若要進行變更，請參閱 [管理重複資料刪除規則](#manage-deduplication-rules)或 [管理比對規則](#manage-match-rules)。

1. 重新執行比對程序，或[執行對設定檔的更新](#run-updates-to-the-unified-profile)。

## <a name="run-updates-to-the-unified-profile"></a>執行對統一設定檔的更新

- 若要執行比對條件，並在 *不* 影響相依性 (例如客戶卡片、擴充、客戶細分或量值) 的情況下更新統一設定檔實體，請選取 **整合客戶設定檔**。 對於帳戶，選取 **整合帳戶** > **整合設定檔**。 對於連絡人，選取 **整合連絡人 (預覽版)** > **整合設定檔**。 相依程序不會執行，但是會根據[重新整理排程](schedule-refresh.md)的定義進行重新整理。
- 若要執行比對條件、更新統一設定檔並執行所有相依性，請選取 **整合客戶設定檔和相依性**。 所有程式都會自動重新執行。 對於帳戶和連絡人，選取 **整合帳戶** > **整合設定檔和相依性**。 對更新這兩個統一設定檔的帳戶和連絡人執行比對條件，並執行所有其他相依性。

所有除了 **來源欄位** 以外的圖標都會顯示 **已排入佇列** 或 **重新整理中**。

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

成功執行的結果會顯示在出現統一設定檔數目的 **整合** 頁面上。
