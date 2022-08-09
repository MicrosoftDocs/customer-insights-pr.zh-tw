---
title: 客戶活動
description: 定義客戶活動，並在客戶個人資料的時間表中查看它們。
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
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
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188129"
---
# <a name="customer-activities"></a>客戶活動

客戶活動是由客戶執行的動作或事件。 例如，交易、支援通話長度、網站評論、購買或退貨。 這些活動包含在一個或多個資料來源中。 Customers Insights，從這些[資料來源](data-sources.md)中整合您的客戶活動，並將它們與客戶資料相關聯。 這些活動會依時間順序出現在客戶設定檔的時間表中。 以[客戶卡增益集](customer-card-add-in.md)解決方案將時間表加入 Dynamics 365 應用程式中。

## <a name="define-an-activity"></a>定義活動

實體必須具有至少有一個類型為 **日期** 的屬性，才能包含在客戶時間表中。 如果找不到這樣的實體，就會停用 **新增活動** 控制項。

1. 請移至 **資料** > **活動**。

1. 請選取 **新增或棟** 以開始引導式體驗。

1. 在 **活動資料** 步驟中，請輸入下列資訊：

   - **活動名稱**：活動的名稱。
   - **活動實體**：包含交易資料或活動資料的實體。
   - **主索引鍵**：唯一識別記錄的欄位。 其中不得包含任何重複值、空白值或遺漏值。

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="以名稱、實體和主索引鍵來設定活動資料。":::

1. 選取 **下一步**。

1. 在 **關聯** 步驟中，選取 **新增關聯**，將您的活動資料連接對應的客戶記錄。 此步驟會視覺化呈現實體之間的連接。  

   - **來自實體的外部索引鍵**：活動實體中的欄位，用來建立與另一個實體的關聯。
   - **至實體名稱**：與活動實體關聯的對應來源客戶實體。 您只能關聯資料整合程序中使用到的來源客戶實體。
   - **關聯名稱**：標識實體之間關聯的名稱。 如果此活動實體與選取的來源客戶實體之間的關聯已存在，則關聯名稱將為唯讀。

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
      - 選擇是否要在客戶個人資料的時間表檢視中顯示此活動。 選取 **是** 以在時間表中顯示活動，或按一下 **否** 隱藏。

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="在整合活動實體中指定客戶活動資料。":::

1. 選取 **下一步** 以選擇活動類型，或選取 **結束和檢閱** 來儲存活動，活動類型設為 **其他**。

1. 在 **活動類型** 步驟中，選取活動類型，然後可以選擇是否要用語意方式對應某些活動類型(以用於 Customer Insights 的其他區域)。 目前，*意見反應*、 *忠誠度*、*SalesOrder*、 *SalesOrderLine* 以及 *訂閱* 活動類型在同意對應欄位之後，也支援語意。 如果活動類型與新的活動不相關，您可以選擇 *其他* 或為自訂活動類型 *建立新的活動類型*。

1. 選取 **下一步**。

1. 在 **檢閱** 步驟中，確認您的選取。 返回先前的任何步驟，並視需要更新資訊。

1. 選取 **儲存活動** 以套用變更，然後選取 **已完成** 回到 **資料** > **活動**。 即會顯示建立的活動。

1. 建立所有活動之後，請選取 **執行** 來處理活動。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>管理現有的活動

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

1. 若要移除篩選，請選取 **清除篩選** 或選取 **篩選**，並清除篩選核取方塊。

> [!NOTE]
> 當您離開客戶設定檔時，會移除活動篩選條件。 每次在客戶設定檔上開啟時，您必須套用它們。

[!INCLUDE [footer-include](includes/footer-banner.md)]
