---
title: 產品建議預測範例指南
description: 使用此範例指南嘗試立即可用的產品建議預測模型。
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610134"
---
# <a name="product-recommendation-prediction-sample-guide"></a>產品建議預測範例指南

本指南會從頭到尾向您說明使用範例資料的產品建議預測範例。 我們建議您[在新環境中](manage-environments.md)嘗試這項預測。

## <a name="scenario"></a>案例

Contoso 是一家公司，生產高品質的咖啡及咖啡機。 透過 Contoso Coffee 網站銷售產品。 他們的目標是瞭解他們應該建議哪些產品給他們的重複客戶。 知道客戶 **可能購買** 的產品，可協助他們將注意力集中放在特定項目上，省下行銷心力。

## <a name="prerequisites"></a>先決條件

- 至少有 Customer Insights 中的[參與者權限](permissions.md)。

## <a name="task-1---ingest-data"></a>任務 1 - 內嵌資料

檢視[關於資料擷取](data-sources.md)和[連接至 Power Query 資料來源](connect-power-query.md)的文章。 下列資訊假定您大致上已熟悉擷取資料。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>從電子商務平台內嵌客戶資料

1. 建立名為 **電子商務** 的 Power query 資料來源，並選取 **文字/CSV** 連接器。

1. 輸入電子商務連絡人的 URL：https://aka.ms/ciadclasscontacts。

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **DateOfBirth**：日期
   - **CreatedOn**：日期/時間/時區

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="將出生日期轉換為日期。":::

1. 請在右側窗格的 **名稱** 欄位中，將您的資料來源重新命名為 **eCommerceContacts**。

1. **儲存** 資料來源。

### <a name="ingest-online-purchase-data"></a>內嵌線上購買資料

1. 將另一個資料集新增到同一個 **電子商務** 資料來源。 再選擇一次 **文字/CSV** 連接器。

1. 輸入線上購買資料的 URL https://aka.ms/ciadclassonline。

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **PurchasedOn**：日期/時間
   - **TotalPrice**：貨幣

1. 請在側窗格的 **名稱** 欄位中，將您的資料來源重新命名為 **eCommercePurchases**。

1. **儲存** 資料來源。

### <a name="ingest-customer-data-from-loyalty-schema"></a>從忠實結構描述內嵌客戶資料

1. 建立名為 **LoyaltyScheme** 的資料來源，並選取 **文字/CSV** 連接器。

1. 輸入忠實客戶的 URL https://aka.ms/ciadclasscustomerloyalty。

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **DateOfBirth**：日期
   - **RewardsPoints**: 整數
   - **CreatedOn**：日期/時間

1. 請在右側窗格的 **名稱** 欄位中，將您的資料來源重新命名為 **loyCustomers**。

1. **儲存** 資料來源。

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

## <a name="task-4---configure-product-recommendation-prediction"></a>工作 4 - 設定產品建議預測

透過適當的統一客戶設定檔和建立的活動，執行產品建議預測。

1. 請移至 **智慧** > **預測**。

1. 在 **建立** 索引標籤上，選取 **產品建議 (預覽版)** 圖標上的 **使用模型**。

1. 請然後選取 **開始使用**。

1. 模型命名為 **OOB 產品建議模型預測** 並將輸出實體命名為 **OOBProductRecommendationModelPrediction**。

1. 選取 **下一步**。

1. 定義模型偏好：
   - **產品數量**：**5** 來定義您想要向客戶建議多少產品。
   - **重複預期的購買**：**是** 以在建議中包含先前購買過的產品。
   - **回顧視窗：** **365 天** 以定義模型在再次建議產品之前將回顧至多久以前。

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="產品建議模型的模型喜好設定。":::

1. 選取 **下一步**。

1. 在 **新增購買歷史紀錄** 步驟中，選取 **新增資料**。

1. 選取 **SalesOrderLine** 及 eCommercePurchases 實體，然後選取 **下一步**。 所需資料會從活動自動填入。 選取 **儲存**，然後選取 **下一步**。

1. 略過 **新增產品資訊** 和 **產品篩選條件** 步驟，因為我們沒有產品資訊資料。

1. 在 **資料更新** 步驟中，設定模型排程為 **每月**。

1. 選取 **下一步**。

1. 評論所有詳細資料後，請選取 **儲存和執行**。

## <a name="task-5---review-model-results-and-explanations"></a>任務 5 - 評論模型結果和解釋

讓模型完成資料的定型與計分。 檢閱[產品建議模型說明](predict-transactional-churn.md#view-prediction-results)。

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>工作 6 - 建立高購買量產品區段

執行模型會建立新的實體，列在 **資料** > **實體** 中。 您可以根據模型建立的實體基礎建立新區段。

1. 在結果頁面上，選取 **建立客戶細分**。

1. 使用 **OOBProductRecommendationModelPrediction** 實體建立規則並定義客戶細分：
   - **欄位**：ProductID
   - **值**：選取前三個產品識別碼

1. 選取 **儲存** 並 **執行** 客戶細分。

您現在有一個動態更新的客戶細分，會找出可能有興趣購買五大建議產品的客戶。 如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。

> [!TIP]
> 您也可以選取 **新** 並選擇 **從** > **智慧建立**，以從 **客戶細分** 頁面，建立預測模型的客戶細分。 如需詳細資訊，請參閱[使用快速客戶細分建立客戶細分](segment-quick.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
