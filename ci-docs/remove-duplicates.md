---
title: 在整合資料之前移除重復資料
description: 整合程序的第二個步驟是在找到重複資料時，選取要保留的記錄。
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 7f4829cfc14af623f724c6594e834f3fac1c15a9
ms.sourcegitcommit: 10dcfc32eaf8ec0903be96136dca7bb4e250276a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2022
ms.locfileid: "9213617"
---
# <a name="remove-duplicates-before-unifying-data"></a>在整合資料之前移除重復資料

整合中的此可選步驟，可讓您設定規則以刪除實體 **中** 的重複記錄。 重複資料刪除會識別客戶的多個記錄，並選取要保留的最佳記錄 (根據基本合併喜好設定)，或將記錄合併成一個 (根據進階合併喜好設定)。 來源記錄被連結到具備備用識別碼的合併後記錄。 如果未設定規則，則會套用系統定義的規則。

## <a name="default-deduplication"></a>預設重複資料刪除

如果未新增重複資料刪除規則，會套用系統定義的規則。

- 主索引鍵會刪除重複資料。
  對於具有相同主索引鍵的任何記錄，最 **填滿最多的** 記錄 (null 值最少的那個記錄) 為入選方。
- 任何跨實體比對規則都會套用至實體。
  例如，在比對步驟中，如果實體 A 與實體 B 在 *FullName* 和 *DateofBirth* 進行比對，則實體 A 也會在 *FullName* 和 *DateofBirth* 刪除重複資料。 因為 *FullName* 和 *DateofBirth* 是用來標識實體 A 中之客戶的有效索引鍵，所以這些索引鍵也可以用來識別實體 A 中的重複客戶。

## <a name="include-enriched-entities-preview"></a>包括已擴充的實體 (預覽版)

如果您在資料來源層級擴充實體來改善您的整合結果，請選取它們。 如需詳細資訊，請參閱[資料來源擴充](data-sources-enrichment.md)。

1. 在 **重複資料記錄** 頁面上方，選取 **使用已擴充實體**。

1. 從使用 **已擴充的實體** 窗格中，選取一個或多個已擴充的實體。

1. 選取 **完成**。

## <a name="define-deduplication-rules"></a>定義重復資料刪除規則

1. 在 **重複資料記錄** 頁面上，選取一個實體，然後選取 **新增規則** 來定義重複資料刪除規則。

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="螢幕擷取畫面：醒目提示 [顯示更多] 的重複資料記錄頁面":::

   1. 在 **新增規則** 窗格上輸入下列資訊：
      - **選取欄位**：對於檢查重複資料的實體，在其可用的欄位清單中選擇。 選擇對每個客戶很可能是唯一的欄位。 例如，電子郵件地址，或姓名、城市和電話號碼的組合。
      - **正規化**：為選取的屬性從以下正規化選項中進行選擇。
        - **數字**：將其他數字系統 (如羅馬數字) 轉換為阿拉伯數字。 *VIII* 變成 *8*。
        - **符號**：刪除所有符號和特殊字元。 *Head&Shoulder* 變成 *HeadShoulder*。
        - **文字為小寫：將所有字元轉換為小寫**。 *ALL CAPS and Title Case* 變成 *all caps and title case*。
        - **類型 (電話、名稱、位址、組織)**：標準化名稱、職稱、電話號碼、地址等。
        - **Unicode 到 ASCII**：將 Unicode 轉換為 ASCII 字元。 */u00B2* 變成 *2*。
        - **空白字元**：刪除所有空白。 *Hello   World* 變成 *HelloWorld*。
      - **精度**：設定適用此條件的精準度等級。
        - **基本**：從 *低 (30%)*、*中 (60%)*、*高 (80%)* 與 *完全相符 (100%)* 進行選擇。 選取 **全字詞**，只比對 100% 相符的記錄。
        - **自訂**：設定記錄需要相符的百分比。 系統將只比對超過此閾值的記錄。
      - **名稱**：規則的名稱。

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="螢幕擷取畫面：移除重複資料的新增規則窗格。":::

   1. 或者，選取 **新增** > **新增條件**，將更多條件新增至規則。 條件以邏輯運算子 AND 相連接，只有在滿足所有條件的情況下才會執行。

   1. 或者，**新增** > **新增例外**，[ 將例外新增至規則](match-entities.md#add-exceptions-to-a-rule)。 例外是用來處理誤判和漏判的少數案例。

   1. 選取 **完成** 以建立規則。

1. 或者，[新增更多規則](#define-deduplication-rules)。

1. 選取一個實體，然後選取 **編輯合併喜好設定**。

1. 在 **合併喜好設定** 窗格中：
   1. 選擇三個選項之一，以決定發現重複資料時要保留的記錄：
      - **最多填滿**：找出填滿最多屬性的記錄作為勝出記錄。 這是預設合併選項。
      - **最新**：根據最新情況找出贏家記錄。 需要日期或數字欄位來定義最新。
      - **時間最接近**：以新近度最接近的，找出入選方記錄。 需要日期或數字欄位來定義新近度。
      
      在繫結事件中，入選方記錄就是具有最大值 (PK) 或較大主索引鍵值的那一個。
      
   1. 或者，若要在實體的各個屬性上定義合併喜好設定，請在窗格下方選取 **進階**。 例如，您可以選擇保留最近的電子郵件，「及」來自不同記錄的最完整地址。 展開實體以查看其所有屬性，並定義要用於個別屬性的選項。 如果您選擇基於新近度的選項，也需要指定定義新近度的日期/時間欄位。

      :::image type="content" source="media/m3_adv_merge.png" alt-text="進階合併喜好設定窗格顯示新近的電子郵件和完整的地址":::

   1. 選取 **完成** 套用合併喜好設定。

1. 定義重複資料刪除規則和合併喜好設定之後，請選取 **下一步**。
  
> [!div class="nextstepaction"]
> [單一實體的下一個步驟：整合欄位](merge-entities.md)

> [!div class="nextstepaction"]
> [多個實體的下一個步驟：比對條件](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>將重複資料刪除輸出成實體

重複資料刪除程序會為每個來源實體建立新的重複資料刪除實體。 這些實體與 **ConflationMatchPairs:CustomerInsights** 在 **實體** 頁面的 **系統** 區段中，名稱為 **Deduplication_DataSource_Entity**。

重複資料刪除輸出實體包含下列資訊：

- 識別碼/金鑰
  - 主索引鍵與替代識別碼欄位。 替代識別碼欄位由一個記錄識別出的所有替代識別碼組成。
  - 根據指定的重複資料刪除欄位，Deduplication_GroupId 欄位顯示實體中辨識出的群組或叢集，裡面都是類似記錄。 為系統處理的需求而被使用。 如果未指定手動重複資料刪除規則，並套用系統定義的重複資料刪除規則，您就不會在重複資料刪除輸出實體中找到此欄位。
  - Deduplication_WinnerId：此欄位包含的勝出識別碼來自於已辨識的群組或叢集。 如果 Deduplication_WinnerId 與記錄的主索引鍵相同，則表示該記錄是勝出的記錄。
- 用來定義重複資料刪除規則的欄位。
- 規則和分數欄位，表示所套用的重複資料刪除規則和比對演算法回傳的分數。

[!INCLUDE[footer-include](includes/footer-banner.md)]
