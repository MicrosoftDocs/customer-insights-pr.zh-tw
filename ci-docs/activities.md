---
title: 客戶或商務連絡人活動
description: 定義客戶或商務連絡人活動，並在客戶設定檔的時間表中檢視這些活動。
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: bbb8bc30d079273bc935181c628915bb3c02d982
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304095"
---
# <a name="customer-or-business-contact-activities"></a>客戶或商務連絡人活動

客戶活動是由客戶或商務連絡人所執行的動作或事件。 例如，交易、支援通話長度、網站評論、購買或退貨。 這些活動包含在一個或多個資料來源中。 Customers Insights，從這些[資料來源](data-sources.md)中整合您的客戶活動，並將它們與客戶資料相關聯。 這些活動會依時間順序出現在客戶設定檔的時間表中。 以[客戶卡增益集](customer-card-add-in.md)解決方案將時間表加入 Dynamics 365 應用程式中。

## <a name="define-a-customer-activity"></a>定義客戶活動

實體必須具有至少有一個類型為 **日期** 的屬性，才能包含在客戶時間表中。 如果找不到這樣的實體，就會停用 **新增活動** 控制項。

1. 請移至 **資料** > **活動**。

1. 請選取 **新增或棟** 以開始引導式體驗。

1. 在 **活動資料** 步驟中，請輸入下列資訊：

   - **活動名稱**：選取活動的名稱。
   - **活動實體**：選取包含交易資料或活動資料的實體。
   - **主索引鍵**：選取唯一識別記錄的欄位。 其中不得包含任何重複值、空白值或遺漏值。

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="以名稱、實體和主索引鍵來設定活動資料。":::

1. 選取 **下一步**。

1. 在 **關聯** 步驟中，選取 **新增關聯**，將您的活動資料連接對應的客戶記錄。 此步驟會視覺化呈現實體之間的連接。  

   - **外部索引鍵**：活動實體中用於與其他實體建立關聯性的外部欄位。
   - **至實體名稱**：與活動實體關聯的對應來源客戶實體。 您只能關聯資料整合程序中使用到的來源客戶實體。
   - **關聯性名稱**：如果此活動實體與所選來源客戶實體之間已經有關聯性，則關聯性名稱將處於唯讀模式。 如果不存在這樣的關聯，則會以您在此方塊中所提供的名稱來建立新關聯。

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="定義實體關聯。":::

   > [!TIP]
   > 您可以在 B 到 B 環境的帳戶實體與其他實體之間選取。 如果您選取帳戶實體，會自動設定關聯路徑。 其他實體方面，您必須先到達客戶實體，才能在一個或多個中間實體上定義關聯路徑。

1. 選取 **套用** 以建立關聯性。

1. 選取 **下一步**。

1. 在 **整合活動** 步驟中，選擇活動事件和活動的開始時間。
   - **必填欄位**
      - **活動事件**：活動事件的欄位。
      - **時間戳記**：代表活動開始時間的欄位。

   - **選用欄位**
      - **其他詳細資料**：此活動相關資訊的欄位。
      - **圖示**：最能代表此活動類型的圖示。
      - **網址**：此欄位可包含有關此活動資訊的 URL。 例如，為此活動提供資訊的交易系統。 此 URL 可以是資料來源中的任何欄位，也可以使用 Power Query 轉換來構建成新的欄位。 URL 資料會儲存在 *整合活動* 實體中，而此實體可以在下游以[API](apis.md)使用。

   - **顯示在時間表中**
      - 選擇是否要在客戶設定檔的時間表檢視中顯示此活動。 選取 **是** 以在時間表中顯示活動，或按一下 **否** 隱藏。

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="在整合活動實體中指定客戶活動資料。":::

1. 選取 **下一步** 以選擇活動類型，或選取 **結束和檢閱** 來儲存活動，活動類型設為 **其他**。

1. 在 **活動類型** 步驟中，選取活動類型，然後可以選擇是否要用語意方式對應某些活動類型(以用於 Customer Insights 的其他區域)。 目前，*意見反應*、 *忠誠度*、*SalesOrder*、 *SalesOrderLine* 以及 *訂閱* 活動類型在同意對應欄位之後，也支援語意。 如果活動類型與新的活動不相關，您可以選擇 *其他* 或為自訂活動類型 *建立新的活動類型*。

1. 選取 **下一步**。

1. 在 **檢閱** 步驟中，確認您的選取。 返回先前的任何步驟，並視需要更新資訊。

1. 選取 **儲存活動** 以套用變更，然後選取 **已完成** 回到 **資料** > **活動**。 即會顯示建立的活動。

1. 建立所有活動之後，請選取 **執行** 來處理活動。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>管理現有的客戶活動

移至 **資料** > **活動**，以查看您已儲存的活動、其來源實體、活動類型，以及它們是否包含在客戶時間表中。 您可以用任何資料行來排序活動清單，或是使用搜尋方塊尋找您要管理的活動。

選取活動來查看可用的動作。

- **編輯** 活動以變更其設定。 設定會在檢閱步驟中打開。 變更設定之後，請選取 **儲存活動**，然後選取 **執行** 來進行變更。
- **重新命名** 活動。 選取 **儲存** 套用變更。
- **刪除** 活動。 若要一次刪除多個活動，請先選取活動，然後選取 **刪除**。 確認刪除。

## <a name="view-activity-timelines-on-customer-profiles"></a>在客戶設定檔上檢視活動時限

1. 如果您已在活動設定中選擇 **在活動時間表中顯示**，請前往 **客戶** 並選擇客戶設定檔，以在 **活動時間表** 區段中查看客戶的活動。

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="在客戶設定檔中檢視組態的活動。":::

1. 若要篩選活動時間表中的活動：

   - 選取一個或多個活動圖示，細項分析結果，便於只納入選取的類型。

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="使用圖示篩選活動 (依類型)。":::

   - 選取 **篩選條件** 開啟篩選面板組態您的時間表篩選條件。 按照 *活動類型* 和/或 *日期* 篩選。 選取 **套用**。

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="使用篩選面板組態篩選條件。":::

> [!NOTE]
> 當您離開客戶設定檔時，會移除活動篩選條件。 每次在客戶設定檔上開啟時，您必須套用它們。

## <a name="define-a-contact-activity"></a>定義連絡人活動

對於商務客戶 (B 到 B)，使用 *ContactProfile* 實體來擷取連絡人的活動。 您可以在帳戶的活動時間表中查看每個活動負責的連絡人。 大部分步驟都遵循客戶活動對應設定。

   > [!NOTE]
   > 若要定義連絡人層級活動，必須將 *ContactProfile* 實體建立為[統一連絡人設定檔](data-unification-contacts.md)，或透過[語義對應](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping)來建立。
   >
   > 活動資料中的每個記錄的都必須同時具有 **AccountID** 和 **ContactID** 屬性。
  
1. 請移至 **資料** > **活動**。

1. 選取 **新增活動**。

1. 為活動命名，選取來源活動實體，然後選取活動實體的主索引鍵。

1. 在 **關聯** 步驟中，以中間實體方式，建立活動來源資料與客戶之間的間接關係。 如需詳細資訊，請查看[直接和間接關聯路徑](relationships.md#relationship-paths)。
   - 一個活動的關聯範例，名字是 *採購*：
      - 在 **ContactID** 屬性上的 **購買來源活動資料** > **連絡人資料**
      - 在屬性 **AccountID** 上的 **連絡人資料** > **客戶資料**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="範例關聯設定。":::

1. 設定關聯之後，請選取 **下一步**，然後完成活動對應設定。 如需建立活動的詳細步驟，請參閱[定義客戶活動](#define-a-customer-activity)。

1. 執行您的活動對應。

1. 您的連絡人層級活動現在會顯示在您的客戶時間表上。

   :::image type="content" source="media/Contact_Activities2.png" alt-text="設定連絡人活動後的最終結果":::

## <a name="contact-level-activity-timeline-filtering"></a>連絡人層級活動時間表篩選

在設定連絡人層級活動對應並執行之後，您的客戶活動時間表將會更新。 根據您的 *ContactProfile* 設定而定，這會包含他們所處理之活動的識別碼或名稱。 您可以根據時間表中的連絡人來篩選活動，查看您有興趣的特定連絡人。 此外，透過選取 **未對應至連絡人的活動**，您可以查看未指派給特定連絡人的所有活動。

   :::image type="content" source="media/Contact_Activities3.png" alt-text="連絡人層級活動可用的篩選選項。":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
