---
title: 客戶存留期值 (CLV) 預測範例指南
description: 您可以依循此範例指南來嘗試客戶存留期值預測的模型。
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609628"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>客戶存留期值 (CLV) 預測範例指南

本指南會從頭到尾向您說明在 Customer Insights 中使用範例資料預測客戶終身價值 (CLV) 的範例。 我們建議您[在新環境中](manage-environments.md)嘗試這項預測。

## <a name="scenario"></a>案例

Contoso 是一家公司，生產高品質的咖啡及咖啡機。 透過 Contoso Coffee 網站銷售產品。 公司想要了解他們的客戶在未來 12 個月所能生成的價值 (營收)。 知道客戶在接下來的 12 個月中的預期價值，將可讓他們將行銷活動導向價值最高的客戶。

## <a name="prerequisites"></a>先決條件

- 至少 [參與者權限](permissions.md)。

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

1. **儲存** 資料來源。

### <a name="ingest-online-purchase-data"></a>內嵌線上購買資料

1. 將另一個資料集新增到同一個 **電子商務** 資料來源。 再選擇一次 **文字/CSV** 連接器。

1. 輸入 **線上購買** 資料 URL https://aka.ms/ciadclassonline。

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

### <a name="ingest-customer-data-from-website-reviews"></a>從網站審查中內嵌客戶資料

1. 建立名為 **網站** 的資料來源，並選取 **文字/CSV** 連接器。

1. 輸入網站檢視的 URL https://aka.ms/CI-ILT/WebReviews。

1. 編輯資料時選取 **轉換**，接著 **使用第一行做為標頭**。

1. 更新下列欄位的資料類型：
   - **ReviewRating**：十進位數字
   - **ReviewDate**：日期

1. 請在右側窗格的 **名稱** 欄位中，將您的資料來源重新命名為 **檢視**。

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

1. 新增另一個活動，並將其欄位名稱對應至相應的欄位：
   - **活動實體**：Reviews:Website
   - **主索引鍵**：ReviewId
   - **時間戳記**：ReviewDate
   - **事件活動**：ActivityTypeDisplay
   - **其他詳細資料**：ReviewRating
   - **活動類型**：檢視

1. 執行活動。

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>工作 4 - 設定客戶存留期值預測

透過適當的統一客戶設定檔和建立的活動，執行客戶終身價值 (CLV) 預測。 如需詳細步驟，請參閱 [客戶存留期值預測](predict-customer-lifetime-value.md)。

1. 請移至 **智慧** > **預測**。

1. 在 **建立** 索引標籤上，選取 **客戶終身價值** 圖標上的 **使用模型**。

1. 請然後選取 **開始使用**。

1. 將模型命名為 **OOB 電子商務 CLV 預測** 和輸出實體 **OOBeCommerceCLVPrediction**。

1. 定義模型偏好：
   - **預測時間區段**：**12 個月或 1 年** 以定義您要預測多久以後的 CLV。
   - **活躍客戶**：'**讓模型計算購買間隔**，其中客戶在此時間範圍內必須至少有一筆交易才會被視為活躍。
   - **高價值客戶**：手動定義高價值的客戶是 **活躍客戶的前 30%** 。

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV 模型的引導式體驗中的喜好設定步驟。":::

1. 選取 **下一步**。

1. 在 **必要的資料** 步驟，選取 **新增資料** 以提供交易歷史資料。

    :::image type="content" source="media/clv-model-required.png" alt-text="在 CLV 模型的引導式體驗中新增所需資料步驟。":::

1. 選取 **SalesOrderLine** 及 eCommercePurchases 實體，然後選取 **下一步**。 所需資料會從活動自動填入。 選取 **儲存**，然後選取 **下一步**。

1. **其他資料 (選用)** 步驟可讓您新增更多客戶活動資料來取得更多客戶互動的深入解析。 在這個範例中，選取 **新增資料**，然後新增網頁檢視活動。

1. 選取 **下一步**。

1. 在 **資料更新** 步驟中，設定模型排程為 **每月**。

1. 選取 **下一步**。

1. 評論所有詳細資料後，請選取 **儲存和執行**。

## <a name="task-5---review-model-results-and-explanations"></a>任務 5 - 評論模型結果和解釋

讓模型完成資料的定型與計分。 檢視 [CLV 模型結果和說明](predict-customer-lifetime-value.md#view-prediction-results)。

## <a name="task-6---create-a-segment-of-high-value-customers"></a>工作 6 - 建立高價值客戶的客戶細分

執行模型會建立新的實體，列在 **資料** > **實體** 中。 您可以依據模型所建立的實體來建立新的客戶細分。

1. 在結果頁面上，選取 **建立客戶細分**。

1. 使用 **OOBeCommerceCLVPrediction** 實體建立規則並定義客戶細分：
   - **欄位**：CLVScore
   - **運算子**：大於
   - **值**：1500

1. 選取 **儲存** 並 **執行** 客戶細分。

您現在有一個客戶細分，能識別出接下來的 12 個月中，預計生成超過 $1500 營收的客戶。 若擷取更多的資料，則會動態更新此分段。 如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。

> [!TIP]
> 您也可以選取 **新** 並選擇 **從** > **智慧建立**，以從 **客戶細分** 頁面，建立預測模型的客戶細分。 如需詳細資訊，請參閱[使用快速客戶細分建立客戶細分](segment-quick.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
