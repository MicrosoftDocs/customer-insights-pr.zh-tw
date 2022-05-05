---
title: 客戶活動
description: 定義客戶活動，並在客戶個人資料的時間表中查看它們。
ms.date: 11/01/2021
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
ms.openlocfilehash: 29b5d3f5848d36abd8e941136a6330dbb7730016
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645778"
---
# <a name="customer-activities"></a>客戶活動

在 Dynamics 365 Customer Insights 中將[不同資料來源](data-sources.md)的客戶活動結合，以建立時間表依時間順序列出活動。 將時間表加入到具備[客戶卡片增益集](customer-card-add-in.md)解決方案的 Dynamics 365 應用程式中或加入到 Power BI 儀表板中。

## <a name="define-an-activity"></a>定義活動

您的資料來源能包含具有交易資料及活動資料的實體，這些資料可來自多個資料來源。 找出這些實體，並選取您要在客戶的時間表上檢視的活動。 選擇包含目標活動的實體。

實體必須至少有一個類型為 **日期** 的屬性，才能包含在客戶時間表中，而且您無法新增不含 **日期** 欄位的實體。 如果找不到這樣的實體，就會停用 **新增活動** 控制項。

1. 請移至 **資料** > **活動**。

1. 選取 **新增活動**，以啟動引導式體驗進行活動設定程序。

1. 在 **活動資料** 步驟中，設定下列欄位的值：

   - **活動名稱**：選取活動的名稱。
   - **實體**：選取包含交易資料或活動資料的實體。
   - **主索引鍵**：選取唯一識別記錄的欄位。 其中不得包含任何重複值、空白值或遺漏值。

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="以名稱、實體和主索引鍵來設定活動資料。":::

1. 選取 **下一步** 前往下一個步驟。

1. 在 **關係** 步驟中組態詳細資料，將您的活動資料連接對應的客戶記錄。 此步驟會視覺化呈現實體之間的連接。  

   - **第一**：活動實體中的外部欄位，用來建立與另一個實體的關聯。
   - **第二**：與活動實體關聯的對應來源客戶實體。 您只能關聯資料整合程序中使用到的來源客戶實體。
   - **第三**：如果此活動實體與選取的來源客戶實體之間的關聯已存在，則關聯名稱將會處於唯讀模式。 如果不存在這樣的關聯，則會以您在此方塊中所提供的名稱來建立新關聯。

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="定義實體關聯。":::

   > [!TIP]
   > 您可以在 B 到 B 環境的帳戶實體與其他實體之間選取。 如果您選取帳戶實體，會自動設定關聯路徑。 其他實體方面，您必須先到達客戶實體，才能在一個或多個中間實體上定義關聯路徑。

1. 選取 **下一步** 前往下一個步驟。 

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

1. 選取 **下一步** 移至下一個步驟。 要儲存設定為 **其他** 的活動類型，您可以選取 **完成並審核** 以立即儲存活動。 

1. 在 **活動類型** 步驟中，選取活動類型，然後可以選擇是否要用語意方式對應某些活動類型(以用於 Customer Insights 的其他區域)。 目前，在同意對應欄位之後，便可以在語義上對應 *Feedback*、*Loyalty*、 *SalesOrder*、*SalesOrderLine* 和 *訂閱* 活動類型。 如果活動類型與新的活動不相關，您可以選擇 *其他* 或為自訂活動類型 *建立新的活動類型*。

1. 選取 **下一步** 移至下一個步驟。 

1. 在 **檢閱** 步驟中，確認您的選取。 返回先前的任何步驟，並視需要更新資訊。

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="檢閱活動的指定欄位。":::
   
1. 選取 **儲存活動** 以套用變更，然後選取 **已完成** 回到 **資料** > **活動**。 在此處能看見在時間表中設定為要顯示的活動。 

1. 在 **活動** 頁面上，選取 **執行** 來處理活動。 

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>管理現有的活動

在 **資料** > **活動** 中，您可以查看所有已儲存的活動，並加以管理。 每個活動都是由資料列顯示，其中也包含有關來源、實體和活動類型的詳細資料。

當您選取活動時，可以使用下列動作。 

- **編輯**：在檢閱步驟上打開活動設定。 您可以從此步驟變更目前的任何或全部設定。 變更設定之後，請選取 **儲存活動**，然後選取 **執行** 來進行變更。

- **重新命名**：打開對話方塊，您可以在其中為選取的活動輸入不同的名稱。 選取 **儲存** 套用變更。

- **刪除**：打開對話方塊，確認刪除選取的活動。 您也可以一次刪除多個活動，方法是先選取活動，然後選取刪除圖示。 請選取 **刪除**，以確認刪除。

## <a name="view-activity-timelines-on-customer-profiles"></a>在客戶設定檔上檢視活動時限

組態客戶活動後，請在活動組態中選取 **顯示活動時間線**，尋找您的客戶設定檔上的所有客戶活動。

若要為客戶開啟時間表，請前往 **顧客** 並選擇您要檢視的客戶設定檔。

如果客戶已經參加您組態的活動，您可以在 **活動時間表** 區找到它。

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="在客戶設定檔中檢視組態的活動。":::

在活動時間表中篩選活動的方式如下：

- 您可以選取一個或多個活動圖示，細項分析結果，便於只納入選取的類型。

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="使用圖示篩選活動 (依類型)。":::

- 您可以選取 **篩選條件** 開啟篩選面板組態您的時間表篩選條件。

   1. 您可以按照 *活動類型* 和 *日期* 篩選
   1. 選取 **套用** 以便在時間表中使用篩選條件。

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="使用篩選面板組態篩選條件。":::

若要移除篩選，請選取套用時間表的每個篩選旁邊的 **x** 或選取 **清除篩選條件**。


> [!NOTE]
> 當您離開客戶設定檔時，會移除活動篩選條件。 每次在客戶設定檔上開啟時，您必須套用它們。

[!INCLUDE [footer-include](includes/footer-banner.md)]
