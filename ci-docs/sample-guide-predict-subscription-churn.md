---
title: 訂閱流失預測範例指南
description: 使用此範例指南試用訂閱流失創意預測模型。
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2aea6c62421b308705899e4f8af64f64bfcb2d3d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645868"
---
# <a name="subscription-churn-prediction-sample-guide"></a>訂閱流失預測範例指南

我們將以訂閱流失預測範例使用的下方範例資料從頭到尾向您說明。 

## <a name="scenario"></a>案例

Contoso 是一家公司，生產高品質咖啡和咖啡機，透過 Contoso 咖啡網站銷售。 他們最近開始客戶的訂閱業務，讓客戶定期取用咖啡。 他們的目標是瞭解哪些已訂閱的客戶可能在接下來的幾個月取消訂閱。 知道哪一位客戶 **很有可能流失** 可協助他們持續聚焦行銷力量。

## <a name="prerequisites"></a>先決條件

- 至少有 Customer Insights 中的[參與者權限](permissions.md)。
- 我們建議您 [在新環境中](manage-environments.md) 執行下列步驟。

## <a name="task-1---ingest-data"></a>任務 1 - 內嵌資料

請特別檢閱關於[資料擷取](data-sources.md)和[使用 Power Query 連接器匯入資料來源](connect-power-query.md)的文章。 下列資訊假定您大體上已熟悉內嵌資料。 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>從電子商務平台內嵌客戶資料

1. 建立稱為 **電子商務** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人 URL https://aka.ms/ciadclasscontacts。

1. 編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：

   - **DateOfBirth**：日期
   - **CreatedOn**：日期/時間/時區

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="將出生日期轉換為日期。":::

1. 請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommerceContacts**

1. 儲存資料來源。

### <a name="ingest-customer-data-from-loyalty-schema"></a>從忠實結構描述內嵌客戶資料

1. 建立稱為 **LoyaltyScheme** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人 URL https://aka.ms/ciadclasscustomerloyalty。

1. 編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：

   - **DateOfBirth**：日期
   - **RewardsPoints**: 整數
   - **CreatedOn**：日期/時間

1. 請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **loyCustomers**。

1. 儲存資料來源。

### <a name="ingest-subscription-information"></a>內嵌訂閱資訊

1. 建立稱為 **SubscriptionHistory** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人 URL https://aka.ms/ciadchurnsubscriptionhistory。

1. 編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：

   - **SubscriptioID**: 整數
   - **SubscriptionAmount**：貨幣
   - **SubscriptionEndDate**：日期/時間
   - **SubscriptionStartDate**：日期/時間
   - **TransactionDate**：日期/時間
   - **IsRecurring**：真/偽
   - **Is_auto_renew**：真/偽
   - **RecurringFrequencyInMonths**：整數

1. 請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **SubscriptionHistory**。

1. 儲存資料來源。

### <a name="ingest-customer-data-from-website-reviews"></a>從網站審查中內嵌客戶資料

1. 建立稱為 **網站** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人 URL https://aka.ms/ciadclasswebsite。

1. 編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：

   - **ReviewRating**：整數
   - **ReviewDate**：日期

1. 請在右側窗格的 '名稱' 欄位中將您的資料來源從 **查詢** 重新命名為 **webReviews**。

## <a name="task-2---data-unification"></a>任務 2 - 資料統整

內嵌資料後，我們現在就會開始 **對應、比對、合併** 流程，以建立統整的客戶設定檔。 如需更多資訊，請見 [資料統整](data-unification.md)。

### <a name="map"></a>對應

1. 內嵌資料後，將電子商務的聯絡人與忠誠度資料對應到常用資料類型。 請前往 **資料** > **統整** > **對應**。

1. 選取代表客戶設定檔的實體 – **eCommerceContacts** 和 **loyCustomers**。 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="統整電子商務與忠誠度資料來源。":::

1. 選取 **ContactId** 做為 **eCommerceContacts** 主鍵，而 **LoyaltyID** 做為 **loyCustomers** 主鍵。

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="統整 LoyaltyId 為主鍵。":::

### <a name="match"></a>比對

1. 請前往 **比對** 索引標籤並選取 **設定訂單**。

1. 在 **主要** 下拉式清單中，選擇 **eCommerceContacts : eCommerce** 作為主要來源，並包含所有記錄。

1. 在 **實體 2** 下拉清單中，選擇 **loyCustomers : LoyaltyScheme** 並包含所有記錄。

   :::image type="content" source="media/unify-match-order.PNG" alt-text="統整比對電子商務與忠誠度。":::

1. 選取 **建立新規則**

1. 使用 FullName 新增您的第一個條件。

   * 在 eCommerceContacts ，請在下拉式清單中選擇 **全名**。
   * 在 loyCustomers，請在下拉式清單中選擇 **全名**。
   * 選取 **正規化** 下拉式清單並選擇 **類型 (電話、名稱、地址、...)**。
   * 設定 **精密等級**：**基本** 與 **值**：**高**。

1. 輸入新規則名稱 **FullName、電子郵件**。

   * 選取 **新增條件** 來新增電子郵件地址的第二個條件
   * 在 eCommerceContacts 實體，請在下拉式清單中選擇 **電子郵件**。
   * 在loyCustomers 實體，請在下拉式清單中選擇 **電子郵件**。 
   * 保留正規化空白。 
   * 設定 **精密等級**：**基本** 與 **值**：**高**。

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="統整比對規則的名稱和電子郵件。":::

7. 選取 **儲存** 和 **執行**。

### <a name="merge"></a>執行合併​​

1. 請前往 **合併** 索引標籤。

1. 在 **loyCustomers** 實體的 **ContactId** 上，將顯示名稱變更為 **ContactIdLOYALTY**，以便將它與其他內嵌的識別碼區分開來。

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="從忠誠度識別碼重新命名 contactid。":::

1. 選取 **儲存** 並 **執行** 以便開始合併流程。


## <a name="task-3---configure-the-subscription-churn-prediction"></a>任務 3 - 組態訂閱流失預測

現在我們可以使用統整的客戶設定檔執行訂閱流失預測。 如需詳細步驟，請參閱[訂閱流失預測](predict-subscription-churn.md)的文章。 

1. 前往 **智慧** > **發現** 並選取使用 **客戶流失模型**。

1. 選取 **訂閱** 選項和 **開始使用**。

1. 將模型 **OOB 訂閱流失預測** 和輸出實體命名為 **OOBSubscriptionChurnPrediction**。

1. 定義流失模型的兩個條件：

   * **訂閱結束後的天數**：**至少 60** 天。 如果客戶在訂閱結束後這段期間未續訂訂閱動作，則視同已流失。 

   * **流失定義**：**至少 93** 天。 模型預測可能流失客戶的持續時間。 未來您看的愈仔細，結果就愈不精確。

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="選取模型槓桿預測視窗和流失定義。":::

1. 選取訂閱歷史資料的 **新增必要資料** 和 **新增資料**。

1. 新增 **訂閱：SubscriptionHistory** 實體並將電子商務欄位對應到模型所需的對應欄位。

1. 加入 **訂閱：SubscriptionHistory** 實體和 **eCommerceContacts：電子商務**，命名 **eCommerceSubscription** 關係。

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="加入電子商務實體。":::

1. 請在客戶活動下方新增 **webReviews：網站** 實體並將 webReviews 欄位對應到模型所需的對應欄位。 
   - 主索引鍵：ReviewId
   - 時間戳記：ReviewDate
   - 事件：ReviewRating

1. 組態用於網站評論的活動。 選取活動 **評論**，並加入 **webReviews：網站** 實體和 **eCommerceContacts：電子商務**。

1. 選取 **下一步** 以設定模型排程。

   當內嵌新資料時，模型必須定期定型以便瞭解新樣式。 本範例中，請選取 **按月**。

1. 評論所有詳細資料後，請選取 **儲存和執行**。

## <a name="task-4---review-model-results-and-explanations"></a>任務 4 - 評論模型結果和解釋

讓模型完成資料的定型與計分。 您現在可以評論訂閱流失模型解釋。 如需更多資訊，請見 [評論預測狀態和結果](predict-subscription-churn.md#review-a-prediction-status-and-results)。

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>任務 5 - 建立高流失風險客戶的區段

執行生產模型會一併建立您可以在 **資料** > **實體** 中看見的新實體。   

您可以根據模型建立的實體基礎建立新區段。

1.  前往 **區段**。 選取 **新增** 並選擇 **從** > **智慧** 建立。 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="使用模型輸出建立區段。":::

1. 選取 **OOBSubscriptionChurnPrediction** 端點並定義區段： 
   - 欄位：ChurnScore
   - 運算子：大於
   - 值：0.6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="設定訂閱流失區段。":::

您現在有動態更新的區段，其找出對此訂閱業務而言屬於高流失風險的客戶。

如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。


[!INCLUDE [footer-include](includes/footer-banner.md)]