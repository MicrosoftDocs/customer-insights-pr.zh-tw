---
title: 客戶存留期值預測範例指南
description: 您可以依循此範例指南來嘗試客戶存留期值預測的模型。
ms.date: 05/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: c130e5f699f7eb921b69a20bc6d4ba9eab5b2779
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354821"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>客戶存留期值 (CLV) 預測範例指南

本指南以範例逐步說明如何在 Customer Insights 中使用範例資料預測使用者存留期值 (CLV)。

## <a name="scenario"></a>案例

Contoso 是一家公司，生產高品質的咖啡及咖啡機。 透過 Contoso Coffee 網站銷售產品。 公司想要了解他們的客戶在未來 12 個月所能生成的價值 (營收)。 知道客戶在接下來的 12 個月中的預期價值，將可讓他們將行銷活動導向價值最高的客戶。

## <a name="prerequisites"></a>先決條件

- 在對象見解中至少是[投稿人參與者權限](permissions.md)。
- 我們建議您 [在新環境中](manage-environments.md) 執行下列步驟。

## <a name="task-1---ingest-data"></a>任務 1 - 內嵌資料

檢閱關於[資料擷取](data-sources.md)和[使用 Power Query 連接器匯入資料來源](connect-power-query.md)的文章。 下列資訊假定您大體上已熟悉內嵌資料。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>從電子商務平台內嵌客戶資料

1. 建立名為 **電子商務** 的資料來源，選擇匯入選項並選取 **Text/CSV** 連接器。

1. 在電子商務連絡人輸入 URL [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts)。

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **DateOfBirth**：日期
   - **CreatedOn**：日期/時間/時區

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="將出生日期轉換為日期。":::

1. 請在右側窗格的 '名稱' 欄位中將您的資料來源從 **查詢** 重新命名為 **eCommerceContacts**

1. **儲存** 資料來源。

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

### <a name="ingest-customer-data-from-website-reviews"></a>從網站審查中內嵌客戶資料

1. 建立稱為 **網站** 的資料來源，選擇匯入選項並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人 URL https://aka.ms/CI-ILT/WebReviews。

1. 編輯資料時選取 **轉換**，然後 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：

   - **ReviewRating**：十進位數字
   - **ReviewDate**：日期

1. 在右窗格的'名稱'欄位中，將您的資料來源從 **查詢** 重新命名為 **檢閱**。

1. **儲存** 資料來源。

## <a name="task-2---data-unification"></a>任務 2 - 資料統整

擷取資料之後，我們會開始進行資料整合處理，以建立整合的客戶個人資料。 如需更多資訊，請見 [資料統整](data-unification.md)。

### <a name="map"></a>對應

1. 內嵌資料後，將電子商務的聯絡人與忠誠度資料對應到常用資料類型。 請前往 **資料** > **統整** > **對應**。

1. 選取代表客戶設定檔的實體 – **eCommerceContacts** 和 **loyCustomers**。 然後，選取 **套用**。

   ![統整電子商務與忠誠度資料來源。](media/unify-ecommerce-loyalty.png)

1. 選取 **ContactId** 做為 **eCommerceContacts** 主鍵，而 **LoyaltyID** 做為 **loyCustomers** 主鍵。

   ![統整 LoyaltyId 為主鍵。](media/unify-loyaltyid.png)

1. 選取 **儲存**。

### <a name="match"></a>比對

1. 請前往 **比對** 索引標籤並選取 **設定訂單**。

1. 在 **主要** 下拉式清單中，選擇 **eCommerceContacts : eCommerce** 作為主要來源，並包含所有記錄。

1. 在 **實體 2** 下拉清單中，選擇 **loyCustomers : LoyaltyScheme** 並包含所有記錄。

   ![統整比對電子商務與忠誠度。](media/unify-match-order.png)

1. 選取 **新增規則**

1. 使用 FullName 新增您的第一個條件。

   - 在 eCommerceContacts ，請在下拉式清單中選擇 **全名**。
   - 在 loyCustomers，請在下拉式清單中選擇 **全名**。
   - 選取 **標準化** 下拉式功能表，然後選擇 **類型 (電話、名稱、地址、...)**。
   - 設定 **精密等級**：**基本** 與 **值**：**高**。

1. 輸入新規則名稱 **FullName、電子郵件**。

   - 選取 **新增條件** 來新增電子郵件地址的第二個條件
   - 在 eCommerceContacts 實體，請在下拉式清單中選擇 **電子郵件**。
   - 在loyCustomers 實體，請在下拉式清單中選擇 **電子郵件**。
   - 保留正規化空白。
   - 設定 **精密等級**：**基本** 與 **值**：**高**。

   ![統整比對規則的名稱和電子郵件。](media/unify-match-rule.png)

1. 選取 **完成**。

1. 選取 **儲存** 和 **執行**。

### <a name="merge"></a>執行合併​​

1. 請前往 **合併** 索引標籤。

1. 在 **loyCustomers** 實體的 **ContactId** 上，將顯示名稱變更為 **ContactIdLOYALTY**，以便將它與其他內嵌的識別碼區分開來。

   ![從忠誠度識別碼重新命名 contactid。](media/unify-merge-contactid.png)

1. 選取 **儲存** 和 **執行合併與下游程序**。

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>工作 3 - 設定客戶存留期值預測

透過整合客戶個人資料，我們現在可以執行客戶存留期值預測。 如需詳細步驟，請參閱 [客戶存留期值預測](predict-customer-lifetime-value.md)。

1. 移至 **智慧**  > **預測**，然後選取 **客戶存留期值模型**。

1. 瀏覽側邊窗格中的資訊，然後選取 **開始使用**。

1. 將模型命名為 **OOB 電子商務 CLV 預測** 和輸出實體 **OOBeCommerceCLVPrediction**。

1. 為 CLV 模型定義模型喜好設定：
   - **預測時間間隔**：**12 個月或 1 年**。 這個設定定義要預測客戶存留期值到未來多遠。
   - **活躍客戶**：指定業務活躍客戶的平均。 設定歷史時間範圍，其中客戶必須至少有一個交易被視為有效。 此模型只能預測活躍的客戶 CLV。 選擇讓模型根據歷史交易記錄資料計算時間間隔，或選擇提供指定的時間範圍。 在本範例指南中，我們 **讓模型計算採購間隔**，這是預設選項。
   - **高價值客戶**：定義高價值的客戶是前百分之幾的付費客戶。 模型使用此輸入，以您商務定義上的高價值客戶提供結果。 您可以選擇讓模型定義高價值客戶。 它使用能產生百分位數的啟發性規則。 您可以定義定義高價值的客戶是前百分之幾的未來付費客戶。 在本範例指南中，我們手動將高價值的客戶定義為 **前 30% 的活躍付費客戶**，並選取 **下一步**。

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV 模型的引導式體驗中的喜好設定步驟。":::

1. 在 **必要的資料** 步驟，選取 **新增資料** 以提供交易歷史資料。

1. 新增 **eCommercePurchases : eCommerce** 實體，並對應模型所需的屬性：
   - 交易識別碼：eCommerce.eCommercePurchases.PurchaseId
   - 交易日期：eCommerce.eCommercePurchases.PurchasedOn
   - 交易金額：eCommerce.eCommercePurchases.TotalPrice
   - 產品識別碼：eCommerce.eCommercePurchases.ProductId

1. 選取 **下一步**。

1. 設定 **eCommercePurchases : eCommerce** 實體和 **eCommerceContacts : eCommerce** 之間的關聯。

1. **其他資料 (可選)** 步驟可讓您新增更多的客戶活動資料。 這項資料可協助您深入解析客戶與您的業務間的互動，這可能會對 CLV 有貢獻。 新增關鍵的客戶互動 (例如 web 日誌、客戶服務記錄或獎勵計劃歷史記錄) 可以改善預測的準確性。 選取 **新增資料** 以包括更多客戶活動資料。

1. 新增客戶活動實體，並將其欄位名稱對應至模型所需的對應欄位：
   - 客戶活動實體：Reviews:Website
   - 主索引鍵：Website.Reviews.ReviewId
   - 時間戳記：Website.Reviews.ReviewDate
   - 事件 (活動名稱)：Website.Reviews.ActivityTypeDisplay
   - 詳細資料 (金額或值)：Website.Reviews.ReviewRating

1. 選取 **下一步**，然後設定交易資料與客戶資料間的活動與關聯：  
   - 活動類型：選擇現有
   - 活動標籤：檢閱
   - 對應的標籤：Website.Reviews.UserId
   - 客戶實體：eCommerceContacts:eCommerce
   - 關聯：WebsiteReviews

1. 選取 **下一步** 以設定模型排程。

   模型需要定期進行定型，在擷取到新的資料時，學習新的模式。 在這個範例中，請選擇 **每月**。

1. 檢閱所有詳細資料後，請選取 **儲存和執行**。

## <a name="task-4---review-model-results-and-explanations"></a>任務 4 - 評論模型結果和解釋

讓模型完成資料的定型與計分。 接下來，您可以檢閱 CLV 模型結果和解釋。 如需更多資訊，請見 [評論預測狀態和結果](predict-customer-lifetime-value.md#review-prediction-status-and-results)。

## <a name="task-5---create-a-segment-of-high-value-customers"></a>工作 5 - 建立高價值客戶的客戶細分

執行模型會建立新的實體，列在 **資料** > **實體** 中。 您可以依據模型所建立的實體來建立新的客戶細分。

1. 前往 **區段**。 

1. 選取 **新增** 並選擇 **從...建立** > **智慧**。

   ![使用模型輸出建立區段。](media/segment-intelligence.png)

1. 選取 **OOBeCommerceCLVPrediction** 實體並定義客戶細分：
  - 欄位：CLVScore
  - 運算子：大於
  - 值：1500

1. 選取 **檢閱** 並 **儲存** 客戶細分。

您現在有一個客戶細分，能識別出接下來的 12 個月中，預計生成超過 $1500 營收的客戶。 若擷取更多的資料，則會動態更新此分段。

如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。
