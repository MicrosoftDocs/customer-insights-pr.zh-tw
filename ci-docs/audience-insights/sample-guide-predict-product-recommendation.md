---
title: 產品建議預測範例指南
description: 使用此範例指南嘗試立即可用的產品建議預測模型。
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b136084316da5ae17a8428236381f69e5c21f9ea
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129889"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>產品建議預測 (預覽版) 範例指南

我們將使用的下方範例資料，逐步介紹完整的產品建議預測範例。

## <a name="scenario"></a>案例

Contoso 是生產高品質咖啡和咖啡機的一家公司，並透過其 Contoso 咖啡網站進行銷售。 他們的目標是瞭解他們應該建議哪些產品給他們的重複客戶。 知道客戶 **很可能購買** 哪些產品，可協助他們專注在特定項目並精簡行銷工作。

## <a name="prerequisites"></a>先決條件

- 至少有 Customer Insights 中的[參與者權限](permissions.md)。
- 我們建議您 [在新環境中](manage-environments.md) 執行下列步驟。

## <a name="task-1---ingest-data"></a>任務 1 - 內嵌資料

具體回顧這些文章 [關於資料內嵌](data-sources.md) 和 [使用 Power Query 連接器匯入資料來源](connect-power-query.md)。 下列資訊假定您大體上已熟悉內嵌資料。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>從電子商務平台內嵌客戶資料

1. 建立稱為 **電子商務** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人 URL https://aka.ms/ciadclasscontacts。

1. 編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **DateOfBirth**：日期
   - **CreatedOn**：日期/時間/時區

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="將出生日期轉換為日期。":::

5. 請在右側窗格的 '名稱' 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommerceContacts**

6. **儲存** 資料來源。

### <a name="ingest-online-purchase-data"></a>內嵌線上購買資料

1. 將另一個資料集新增到同一個 **電子商務** 資料來源。 再選擇一次 **文字/CSV** 連接器。

1. 輸入 **線上購買** 資料 URL https://aka.ms/ciadclassonline。

1. 編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **PurchasedOn**：日期/時間
   - **TotalPrice**：貨幣

1. 請在側邊窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommercePurchases**。

1. **儲存** 資料來源。


### <a name="ingest-customer-data-from-loyalty-schema"></a>從忠實結構描述內嵌客戶資料

1. 建立稱為 **LoyaltyScheme** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人 URL https://aka.ms/ciadclasscustomerloyalty。

1. 編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **DateOfBirth**：日期
   - **RewardsPoints**: 整數
   - **CreatedOn**：日期/時間

1. 請在右側窗格的 **名稱** 欄位中將您的資料來源從 **查詢** 重新命名為 **loyCustomers**。

1. **儲存** 資料來源。

## <a name="task-2---data-unification"></a>任務 2 - 資料統整

擷取資料之後，我們會開始進行資料整合處理，以建立整合的客戶個人資料。 如需更多資訊，請見 [資料統整](data-unification.md)。

### <a name="map"></a>對應

1. 內嵌資料後，將電子商務的聯絡人與忠誠度資料對應到常用資料類型。 請前往 **資料** > **統整** > **對應**。

2. 選取代表客戶設定檔的實體 – **eCommerceContacts** 和 **loyCustomers**。

   ![統整電子商務與忠誠度資料來源。](media/unify-ecommerce-loyalty.png)

3. 選取 **ContactId** 做為 **eCommerceContacts** 主鍵，而 **LoyaltyID** 做為 **loyCustomers** 主鍵。

   ![統整 LoyaltyId 為主鍵。](media/unify-loyaltyid.png)

### <a name="match"></a>相符項目

1. 請前往 **比對** 索引標籤並選取 **設定訂單**。

2. 請在 **主要** 下拉式清單中選擇 **eCommerceContacts：電子商務** 為主要來源並包括所有記錄。

3. 請在 **實體 2** 下拉式清單中選擇 **loyCustomers：LoyaltyScheme** 並包括所有記錄。

   ![統整比對電子商務與忠誠度。](media/unify-match-order.png)

4. 選取 **建立新規則**

5. 使用 FullName 新增您的第一個條件。

   - eCommerceContacts 方面，請在下拉式清單中選取 **FullName**。
   - loyCustomers 方面，請在下拉式清單中選取 **FullName**。
   - 選取 **正規化** 下拉式清單並選擇 **類型 (電話、名稱、地址、...)**。
   - 設定 **精密等級**：**基本** 與 **值**：**高**。

6. 輸入新規則名稱 **FullName、電子郵件**。

   - 選取 **新增條件** 來新增電子郵件地址的第二個條件
   - 實體 eCommerceContacts 方面，請在下拉式清單中選擇 **電子郵件**。
   - 實體 loyCustomers 方面，請在下拉式清單中選擇 **電子郵件**。
   - 保留正規化空白。
   - 設定 **精密等級**：**基本** 與 **值**：**高**。

   ![統整比對規則的名稱和電子郵件。](media/unify-match-rule.png)

7. 選取 **儲存** 和 **執行**。

### <a name="merge"></a>執行合併​​

1. 請前往 **合併** 索引標籤。

1. 在 **loyCustomers** 實體的 **ContactId** 上，將顯示名稱變更為 **ContactIdLOYALTY**，以便將它與其他內嵌的識別碼區分開來。

   ![從忠誠度識別碼重新命名 contactid。](media/unify-merge-contactid.png)

1. 選取 **儲存** 並 **執行** 以便開始合併流程。

## <a name="task-3---configure-product-recommendation-prediction"></a>工作 3 - 設定產品建議預測

現在我們可以使用統整的客戶設定檔執行訂閱流失預測。

1. 移至 **智慧** > **預測** 選擇 **產品建議**。

1. 請然後選取 **開始使用**。

1. 模型命名為 **OOB 產品建議模型預測** 並將輸出實體命名為 **OOBProductRecommendationModelPrediction**。

1. 為模型定義三個條件：

   - **產品數目**：將此值設定為 **5**。 這個設定為定義您想要向客戶建議多少產品。

   - **重複購買預期**：選取 **是** 表示您想要在建議中包括客戶在之前先購買的產品。

   - **回顧視窗：** 至少要選取 **365 天**。 此設定是定義模型要回顧客戶活動的天數，用來作為其建議的輸入值。
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="產品建議模型的模型喜好設定。":::

1. 選取購買歷史資料的 **必要資料** 和 **新增資料**。

1. 新增 **eCommercePurchases：電子商務** 實體並將電子商務欄位對應到模型所需的對應欄位。

1. 加入 **eCommercePurchases：電子商務** 實體和 **eCommerceContacts：電子商務**。

   ![加入電子商務實體。](media/model-purchase-join.png)

1. 選取 **下一步** 以設定模型排程。

   當內嵌新資料時，模型必須定期定型以便瞭解新樣式。 本範例中，請選取 **按月**。

1. 評論所有詳細資料後，請選取 **儲存和執行**。


## <a name="task-4---review-model-results-and-explanations"></a>任務 4 - 評論模型結果和解釋

讓模型完成資料的定型與計分。 您現在可以審閱產品建議模型說明。 如需更多資訊，請見 [評論預測狀態和結果](predict-subscription-churn.md#review-a-prediction-status-and-results)。

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>工作 5 - 建立高購買量產品區段

執行生產模型會一併建立您可以在 **資料** > **實體** 中看見的新實體。

您可以根據模型建立的實體基礎建立新區段。

1. 前往 **區段**。 選取 **新增** 並選擇 **從** > **智慧** 建立。

   ![使用模型輸出建立區段。](media/segment-intelligence.png)

1. 選取 **OOBProductRecommendationModelPrediction** 端點並定義區段：

   - 欄位：ProductID
   - 運算子：值
   - 值：選取前三個產品識別碼

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="從模型結果建立區段。":::

您現在有一個動態更新的區段，能找出最可能購買三種最建議產品的客戶 

如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
