---
title: 產品建議預測範例指南
description: 使用此範例指南嘗試立即可用的產品建議預測模型。
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762676"
---
# <a name="product-recommendation-prediction-sample-guide"></a>產品建議預測範例指南

我們將使用的下方範例資料，逐步介紹完整的產品建議預測範例。

## <a name="scenario"></a>案例

Contoso 是一家公司，生產高品質咖啡和咖啡機，透過 Contoso 咖啡網站銷售。 他們的目標是瞭解他們應該建議哪些產品給他們的重複客戶。 知道客戶 **很可能購買** 哪些產品，可協助他們專注在特定項目並精簡行銷工作。

## <a name="prerequisites"></a>先決條件

- 至少有 Customer Insights 中的[參與者權限](permissions.md)。
- 我們建議您 [在新環境中](manage-environments.md) 執行下列步驟。

## <a name="task-1---ingest-data"></a>任務 1 - 內嵌資料

請特別檢閱關於[資料擷取](data-sources.md)和[使用 Power Query 連接器匯入資料來源](connect-power-query.md)的文章。 下列資訊假定您大體上已熟悉內嵌資料。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>從電子商務平台內嵌客戶資料

1. 建立稱為 **電子商務** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人 URL：[https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts)。

1. 編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **DateOfBirth**：日期
   - **CreatedOn**：日期/時間/時區

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="將出生日期轉換為日期。":::

1. 請在右側窗格的 '名稱' 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommerceContacts**

1. **儲存** 資料來源。

### <a name="ingest-online-purchase-data"></a>內嵌線上購買資料

1. 將另一個資料集新增到同一個 **電子商務** 資料來源。 再選擇一次 **文字/CSV** 連接器。

1. 為 **線上購買** 資料 [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline) 輸入 URL。

1. 編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **PurchasedOn**：日期/時間
   - **TotalPrice**：貨幣

1. 請在側邊窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommercePurchases**。

1. **儲存** 資料來源。

### <a name="ingest-customer-data-from-loyalty-schema"></a>從忠實結構描述內嵌客戶資料

1. 建立稱為 **LoyaltyScheme** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。

1. 為電子商務連絡人[https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty) 輸入URL。

1. 編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **DateOfBirth**：日期
   - **RewardsPoints**: 整數
   - **CreatedOn**：日期/時間

1. 請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **loyCustomers**。

1. **儲存** 資料來源。

## <a name="task-2---data-unification"></a>任務 2 - 資料統整

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>工作 3 - 設定產品建議預測

透過整合的客戶個人資料，現在可以執行產品建議預測。

1. 移至 **智慧** > **預測** 選擇 **產品建議**。

1. 請然後選取 **開始使用**。

1. 模型命名為 **OOB 產品建議模型預測** 並將輸出實體命名為 **OOBProductRecommendationModelPrediction**。

1. 為模型定義三個條件：

   - **產品數目**：將此值設定為 **5**。 這個設定為定義您想要向客戶建議多少產品。

   - **重複購買預期**：選取 **是** 表示您想要在建議中包括客戶在之前先購買的產品。

   - **回顧視窗：** 至少要選取 **365 天**。 此設定是定義模型要回顧客戶活動的天數，用來作為其建議的輸入值。

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="產品建議模型的模型喜好設定。":::

1. 在 **新增必要資料** 步驟中，選取 **新增資料**。

1. 在 **新增資料** 窗格中，選取 **SalesOrderLine** 作為購買歷史記錄實體。 此刻，這可能尚未設定。 在窗格中打開連結，使用下列步驟來建立活動：
   1. 輸入 **活動名稱**，然後選擇 *eCommercePurchases:eCommerce* 作為 **活動實體**。 **主索引鍵** 為 *PurchaseId*。
   1. 定義並命名 *eCommerceContacts:eCommerce entity* 關聯性，然後選擇 **ContactId** 作為外部索引鍵。
   1. 為活動整合，請將 **事件活動** 設為 *TotalPrice* 且時間戳記設為 *PurchasedOn*。 您可以指定 [客戶活動](activities.md) 中列出的更多欄位。
   1. 在 **活動類型** 中，選擇 *SalesOrderLine*。 對應以下活動欄位:
      - 訂單明細識別碼：PurchaseId
      - 訂單識別碼：PurchaseId
      - 訂單日期：PurchasedOn
      - 產品識別碼：ProductId
      - 總金額：TotalPrice
   1. 在回到模型設定之前，先審查並完成活動。

1. 回到 **選取活動** 步驟中，在 **活動** 區段中選取新建立的活動。 選取 **下一步**，且屬性對應已填入。選取 **儲存**。

1. 在本範例指南中，將略過 **新增產品資訊** 和 **產品篩選**，因為沒有產品資訊資料。

1. 在 **資料更新** 步驟中，設定模型排程。

   當內嵌新資料時，模型必須定期定型以便瞭解新樣式。 本範例中，請選取 **按月**。

1. 評論所有詳細資料後，請選取 **儲存和執行**。 第一次執行模型時會花費幾分鐘的時間。

## <a name="task-4---review-model-results-and-explanations"></a>任務 4 - 評論模型結果和解釋

讓模型完成資料的定型與計分。 您現在可以審閱產品建議模型說明。 如需更多資訊，請見 [評論預測狀態和結果](predict-transactional-churn.md#review-a-prediction-status-and-results)。

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>工作 5 - 建立高購買量產品區段

執行生產模型會一併建立您可以在 **資料** > **實體** 中看見的新實體。

您可以根據模型建立的實體基礎建立新區段。

1. 前往 **區段**。 選取 **新增** 並選擇 **從智慧建立**。

   ![使用模型輸出建立區段。](media/segment-intelligence.png)

1. 選取 **OOBProductRecommendationModelPrediction** 端點並定義區段：

   - 欄位：ProductID
   - 值：選取前三個產品識別碼

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="從模型結果建立區段。":::

您現在有一個動態更新的客戶細分，可用來找出可能有興趣購買這三種最建議產品的客戶。

如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
