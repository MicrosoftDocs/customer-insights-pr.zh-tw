---
title: 訂閱流失預測範例指南
description: 使用此範例指南試用訂閱流失創意預測模型。
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609996"
---
# <a name="subscription-churn-prediction-sample-guide"></a>訂閱流失預測範例指南

本指南將從頭到尾向您說明使用範例資料的訂閱流失預測範例。 我們建議您[在新環境中](manage-environments.md)嘗試這項預測。

## <a name="scenario"></a>案例

Contoso 是一家公司，生產高品質的咖啡及咖啡機。 透過 Contoso Coffee 網站銷售產品。 他們最近開始客戶的訂閱業務，讓客戶定期取用咖啡。 他們的目標是瞭解哪些已訂閱的客戶可能在接下來的幾個月取消訂閱。 知道 **有可能流失** 的客戶，可協助他們將注意力集中在留住客戶，省下行銷心力。

## <a name="prerequisites"></a>先決條件

- 至少有 Customer Insights 中的[參與者權限](permissions.md)。

## <a name="task-1---ingest-data"></a>任務 1 - 內嵌資料

檢視[關於資料擷取](data-sources.md)和[連接至 Power Query 資料來源](connect-power-query.md)的文章。 下列資訊假定您大致上已熟悉擷取資料。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>從電子商務平台內嵌客戶資料

1. 建立名為 **電子商務** 的 Power query 資料來源，並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人 URL https://aka.ms/ciadclasscontacts。

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **DateOfBirth**：日期
   - **CreatedOn**：日期/時間/時區

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="將出生日期轉換為日期。":::

1. 請在右側窗格的 **名稱** 欄位中，將您的資料來源重新命名為 **eCommerceContacts**

1. 儲存資料來源。

### <a name="ingest-customer-data-from-loyalty-schema"></a>從忠實結構描述內嵌客戶資料

1. 建立名為 **LoyaltyScheme** 的資料來源，並選取 **文字/CSV** 連接器。

1. 輸入忠實客戶的 URL https://aka.ms/ciadclasscustomerloyalty。

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **DateOfBirth**：日期
   - **RewardsPoints**: 整數
   - **CreatedOn**：日期/時間

1. 請在右側窗格的 **名稱** 欄位中，將您的資料來源重新命名為 **loyCustomers**。

1. 儲存資料來源。

### <a name="ingest-subscription-information"></a>內嵌訂閱資訊

1. 建立名為 **SubscriptionHistory** 的資料來源，並選取 **文字/CSV** 連接器。

1. 輸入訂閱的 URL https://aka.ms/ciadchurnsubscriptionhistory

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **SubscriptioID**: 整數
   - **SubscriptionAmount**：貨幣
   - **SubscriptionEndDate**：日期/時間
   - **SubscriptionStartDate**：日期/時間
   - **TransactionDate**：日期/時間
   - **IsRecurring**：真/偽
   - **Is_auto_renew**：真/偽
   - **RecurringFrequencyInMonths**：整數

1. 在右側窗格的 **名稱** 欄位中，將您的資料來源重新命名為 **SubscriptionHistory**。

1. 儲存資料來源。

### <a name="ingest-customer-data-from-website-reviews"></a>從網站審查中內嵌客戶資料

1. 建立名為 **網站** 的資料來源，並選取 **文字/CSV** 連接器。

1. 輸入網站檢視的 URL https://aka.ms/ciadclasswebsite。

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **ReviewRating**：整數
   - **ReviewDate**：日期

1. 在右側窗格的 **名稱** 欄位中，將您的資料來源重新命名為 **webReviews**。

## <a name="task-2---data-unification"></a>任務 2 - 資料統整

檢閱[關於資料統整](data-unification.md)的文章。 下列資訊假定您大致上已熟悉資料統整。

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>工作 3 - 建立交易歷程記錄活動

檢閱[有關客戶活動](activities.md)的文章。 下列資訊假定您大致上已熟悉建立活動。

1. 建立名為 **SubscriptionHistory** 的活動，並使用 *Subscription* 實體與其主索引鍵，**CustomerId**。

1. 建立 *SubscriptionHistory:Subscription* 和 *eCommerceContacts:eCommerce* 之間的關係，並使用 **CustomerID** 做為外部索引鍵來連接兩個實體。

1. 選取 **EventActivity** 的 **SubscriptionType**，和 **時間戳記** 的 **SubscriptionEndDate**。

1. 選取 **活動類型** 的 **訂閱** ，並語義對應活動資料。

1. 執行活動。

1. 新增另一個活動，並將其欄位名稱對應至相應的欄位：
   - 客戶活動實體：Reviews:Website
   - 主索引鍵：Website.Reviews.ReviewId
   - 時間戳記：Website.Reviews.ReviewDate
   - 事件 (活動名稱)：Website.Reviews.ActivityTypeDisplay
   - 詳細資料 (金額或值)：Website.Reviews.ReviewRating

1. 執行活動。

## <a name="task-4---configure-the-subscription-churn-prediction"></a>任務 4 - 組態訂閱流失預測

使用適當的統一客戶設定檔和建立的活動，執行訂閱流失預測。 如需詳細步驟，請參閱[訂閱流失預測](predict-subscription-churn.md)。

1. 請移至 **智慧** > **預測**。

1. 在 **建立** 索引標籤上，選取 **客戶流失模型** 圖標上的 **使用模型**。

1. 選取流失類型的 **訂閱**，然後選取 **開始**。

1. 將模型 **OOB 訂閱流失預測** 和輸出實體命名為 **OOBSubscriptionChurnPrediction**。

1. 定義模型偏好：
   - **訂閱已結束的天數**：**60** 天，是指使用者在其訂閱結束後，未於此期間續約訂閱，就會被視為已流失。
   - **要預測流失需要觀察的未來天數**：**93** 天是模型要預測哪些客戶可能流失所需觀察的期間。 未來您看的愈仔細，結果就愈不精確。

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="選取模型偏好和流失定義。":::

1. 選取 **下一步**。

1. 在 **必要資料** 步驟，選取 **新增資料** 以提供訂閱歷史資料。

1. 選取 **訂閱** 及 SubscriptionHistory 實體，然後選取 **下一步**。 所需資料會從活動自動填入。 選取 **儲存**。

1. 在客戶活動下方，選取 **新增資料**。

1. 在這個範例中，新增網頁檢視活動。

1. 選取 **下一步**。

1. 在 **資料更新** 步驟中，設定模型排程為 **每月**。

1. 評論所有詳細資料後，請選取 **儲存和執行**。

## <a name="task-5---review-model-results-and-explanations"></a>任務 5 - 評論模型結果和解釋

讓模型完成資料的定型與計分。 檢閱訂閱流失模型說明。 如需詳細資訊，請參閱[查看預測結果](predict-subscription-churn.md#view-prediction-results)。

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>任務 6 - 建立高流失風險客戶的區段

執行模型會建立新的實體，列在 **資料** > **實體** 中。 您可以根據模型建立的實體基礎建立新區段。

1. 在結果頁面上，選取 **建立客戶細分**。

1. 建立使用 **OOBSubscriptionChurnPrediction** 實體的規則並定義客戶細分：
   - **欄位**：ChurnScore
   - **運算子**：大於
   - **值**：0.6

1. 選取 **儲存** 並 **執行** 客戶細分。

您現在有動態更新的區段，其找出對此訂閱業務而言屬於高流失風險的客戶。 如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。

> [!TIP]
> 您也可以選取 **新** 並選擇 **從** > **智慧建立**，以從 **客戶細分** 頁面，建立預測模型的客戶細分。 如需詳細資訊，請參閱[使用快速客戶細分建立客戶細分](segment-quick.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
