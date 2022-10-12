---
title: 交易性流失預測範例指南
description: 使用此範例指南試用交易性流失創意預測模型。
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609674"
---
# <a name="transactional-churn-prediction-sample-guide"></a>交易性流失預測範例指南

本指南將從頭到尾向您說明使用範例資料的交易性流失預測範例。 我們建議您[在新環境中](manage-environments.md)嘗試這項預測。

## <a name="scenario"></a>案例

Contoso 是一家公司，生產高品質的咖啡及咖啡機。 透過 Contoso Coffee 網站銷售產品。 他們的目標是了解典型上定期購買他們產品的客戶在未來 60 天將不再是有效客戶。 知道哪一位客戶 **很有可能流失** 可協助他們持續聚焦行銷力量。

## <a name="prerequisites"></a>先決條件

- 至少 [參與者權限](permissions.md)。

## <a name="task-1---ingest-data"></a>任務 1 - 內嵌資料

檢視[關於資料擷取](data-sources.md)和[連接至 Power Query 資料來源](connect-power-query.md)的文章。 下列資訊假定您大致上已熟悉擷取資料。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>從電子商務平台內嵌客戶資料

1. 建立名為 **電子商務** 的資料來源，並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人 URL https://aka.ms/ciadclasscontacts。

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：

   - **DateOfBirth**：日期
   - **CreatedOn**：日期/時間/時區

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="轉換出生日期到日期。":::

1. 請在右側窗格的 **名稱** 欄位中，將您的資料來源重新命名為 **eCommerceContacts**

1. 儲存資料來源。

### <a name="ingest-online-purchase-data"></a>內嵌線上購買資料

1. 將另一個資料集新增到同一個 **電子商務** 資料來源。 再選擇一次 **文字/CSV** 連接器。

1. 輸入線上購買資料的 URL https://aka.ms/ciadclassonline。

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：

   - **PurchasedOn**：日期/時間
   - **TotalPrice**：貨幣

1. 在右側窗格的 **名稱** 欄位中，將您的資料來源重新命名為 **eCommercePurchases**。

1. 儲存資料來源。

### <a name="ingest-customer-data-from-loyalty-schema"></a>從忠實結構描述內嵌客戶資料

1. 建立名為 **LoyaltyScheme** 的資料來源，並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人 URL https://aka.ms/ciadclasscustomerloyalty。

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：

   - **DateOfBirth**：日期
   - **RewardsPoints**: 整數
   - **CreatedOn**：日期/時間

1. 請在右側窗格的 **名稱** 欄位中，將您的資料來源重新命名為 **loyCustomers**。

1. 儲存資料來源。

## <a name="task-2---data-unification"></a>任務 2 - 資料統整

檢閱[關於資料統整](data-unification.md)的文章。 下列資訊假定您大致上已熟悉資料統整。

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>工作 3 - 建立交易歷程記錄活動

檢閱[有關客戶活動](activities.md)的文章。 下列資訊假定您大致上已熟悉建立活動。

1. 建立名為 **eCommercePurchases** 的活動，並使用 *eCommercePurchases:eCommerce* 實體與其主索引鍵，**PurchaseId**。

1. 建立 *eCommercePurchases* 和 *eCommerceContacts:eCommerce* 之間的關係，並使用 **ContactID** 做為外部索引鍵來連接兩個實體。

1. 選取 **EventActivity** 的 **TotalPrice**，和 **時間戳記** 的 **PurchasedOn**。

1. 選取 **活動類型** 的 **SalesOrderLine** ，並語義對應活動資料。

1. 執行活動。

## <a name="task-4---configure-transaction-churn-prediction"></a>任務 4 - 組態交易流失預測

使用適當的統一客戶設定檔和活動，執行交易流失預測。

1. 請移至 **智慧** > **預測**。

1. 在 **建立** 索引標籤上，選取 **客戶流失模型** 上的 **使用模型**。

1. 流失類型請選取 **交易性**，然後選取 **開始**。

1. 將模型 **OOB 電子商務交易流失預測** 和輸出實體命名為 **OOBeCommerceChurnPrediction**。

1. 選取 **下一步**。

1. 定義模型偏好：

   - **預測視窗**：**60** 天以定義我們要預測客戶流失所需觀察的未來時間長度。

   - **流失定義**：**60** 天，表示在此期間內未進行購買，即視同客戶已流失。

     :::image type="content" source="media/model-levers.PNG" alt-text="選取模型偏好預測視窗和流失定義。":::

1. 選取 **下一步**。

1. 選取 **購買歷史記錄 (必要項目)** 和 **新增** 購買歷史資料。

1. 選取 **SalesOrderLine** 及 eCommercePurchases 實體，然後選取 **下一步**。 所需資料會從活動自動填入。 選取 **儲存**，然後選取 **下一步**。

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="加入電子商務實體。":::

1. 略過 **其他資料 (選用)** 步驟。

1. 在 **資料更新** 步驟中，設定模型排程為 **每月**。

1. 評論所有詳細資料後，請選取 **儲存和執行**。

## <a name="task-5---review-model-results-and-explanations"></a>任務 5 - 評論模型結果和解釋

讓模型完成資料的定型與計分。 檢閱流失模型說明。 如需詳細資訊，請參閱[查看預測結果](predict-transactional-churn.md#view-prediction-results)。

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>任務 6 - 建立高流失風險客戶的區段

執行生產模型會建立新的實體，會列在 **資料** > **實體** 上。 您可以根據模型建立的實體基礎建立新區段。

1. 在結果頁面上，選取 **建立客戶細分**。

1. 建立使用 **OOBeCommerceChurnPrediction** 實體的規則並定義客戶細分：
   - **欄位**：ChurnScore
   - **運算子**：大於
   - **值**：0.6

1. 選取 **儲存** 並 **執行** 客戶細分。

您現在有一個動態更新的客戶細分，用來識別高流失風險的客戶。 如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。

> [!TIP]
> 您也可以選取 **新** 並選擇 **從** > **智慧建立**，以從 **客戶細分** 頁面，建立預測模型的客戶細分。 如需詳細資訊，請參閱[使用快速客戶細分建立客戶細分](segment-quick.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
