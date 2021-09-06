---
title: Machine Learning Studio (經典版) 實驗
description: 在 Dynamics 365 Customer Insights 中使用 Azure Machine Learning Studio (經典版) 模型。
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b979dd177b7c6de1971c02a69748006d041e4d2c3e49a3639dba03212bd7acf9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033713"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>根據 Azure Machine Learning Studio (經典版) 基礎使用各模型

Dynamics 365 Customer Insights 中的統一資料是組建可產生額外業務見解的機器學習模型來源。 整合 Customer Insights 和 Machine Learning Studio (經典版) 使用您自己的自訂模型。 若要瞭解 Azure Machine 中開發的模型如何整合 Customer Insights，請見 [Azure Machine Learning 實驗](azure-machine-learning-experiments.md)。

## <a name="prerequisites"></a>先決條件

- 存取 Customer Insights
- 有效的 Azure 企業版訂用帳戶
- [統整的客戶設定檔](data-unification.md)
- [對 Azure Blob 儲存體的實體匯出](export-azure-blob-storage.md)設定

## <a name="set-up-machine-learning-studio-classic"></a>設定 Machine Learning Studio 經典版

在步驟一中，我們必須建立 Machine Learning Studio (經典版) 工作區並打開它。

1. 前往 [https://www.portal.azure.com](https://www.portal.azure.com/) 並登入。

1. 選取 **建立資源**。

1. 搜尋 **Machine Learning Studio 工作區** 並選取 **建立**。

1. 輸入[建立工作區](/azure/machine-learning/studio/create-workspace)所需的詳細資料。 根據您計畫匯入的資料量選擇 **Web 服務計畫價格層級**。 為了取得最佳效能，請選取地理上距離您最近的 **位置**。

1. 建立資源之後，Machine Learning Studio 工作區儀表板會出現。 選取 **啟動 Machine Learning Studio**。

   ![Azure Machine Learning Studio 使用者介面。](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>使用 Azure Machine Learning Studio

您現在可以建立新實驗，或從範例庫匯入現有的實驗範本。 目前三種標準案例均有實驗範例：

- [流失預測](#churn-analysis)

- [客戶存留期數值](#customer-lifetime-value-prediction)

- [產品建議或下一步最佳動作](#productrecommendation-or-next-best-action)

1. 如果您建立新實驗，或使用資料庫中的實驗範本，則必須設定 **匯入資料** 屬性。 請使用引導式體驗或直接提供詳細資料存取包含資料的 Azure Blob 儲存體。  

   ![Azure Machine Learning Studio 實驗。](media/azure-machine-learning-studio-experiment.png)

1. 現在您可以建置自訂處理管線，以清理並預先處理資料、擷取功能，以及定型適當模型。

1. 測試和最佳化模型效能。

1. 當您滿意模型的品質時，選取 **設定 Web 服務** > **預測型 Web 服務**。 此選項會將已定型模型與特徵化管線從定型實驗匯入至預測服務。 預測服務可以透過定型實驗中使用的結構描述，接受另一組輸入資料。

   ![設定預測型 Web 服務。](media/predictive-webservice-control.png)

1. 預測型 Web 服務實驗成功完成後，就可以將其部署作自動排程之用。 若要讓 Web 服務與 Customer Insights 搭配使用，請選取 **部署 Web 服務** > **部署 Web 服務 [新增] 預覽**。 [進一步了解部署 Web 服務](/azure/machine-learning/studio/deploy-a-machine-learning-web-service)。

   ![部署預測型 Web 服務。](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>資源庫中的範例模型

此文章中，我們將使用虛構的 Contoso飯店案例來製作模型。 Contoso 飯店收集下列資料：

- 包含飯店住宿活動的 CRM 資料。 資料集包含每個已登記客戶的住宿日期資訊。 其中也包含預訂、房間類型、消費明細等方面的相關資訊。 資料涵蓋從 2014 年 1 月至 2018 年 1 月的四年期間。
- 飯店房客的客戶設定檔。 這些設定檔包含每個客戶的相關資訊，包括其姓名、生日、郵寄地址、性別和電話號碼。
- 飯店提供的服務使用項目，例如温泉、洗衣房、WiFi 或快遞。 每個已登記客戶的這些資訊都記錄下來。 服務的使用通常連結著住宿。 在某些情況下，客戶未在飯館住宿也能使用服務。

## <a name="churn-analysis"></a>流失分析

流失分析會套用至不同的業務領域。 在本範例中，我們準備針對上述飯店服務情境查看服務流失情況。 它提供端對端模型管道的實用範例，可用做其他任何流失模型類型的起點。

### <a name="definition-of-churn"></a>流失的定義

根據案例而定，流失的定義可能會有所不同。 在本範例中，過去一年內尚未親訪飯店的房客應標註為已流失。  

實驗範本可從資源庫匯入。 首先，請確保從 Azure Blob 儲存體匯入 **飯店留宿活動**、**客戶資料** 和 **服務使用方式資料** 的資料。

   ![匯入流失模型的資料。](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>特徵化

根據流失定義，我們先找出將影響標籤的原始特色。 然後，將這些原始特徵處理成可用於機器學習模型的數值特徵。 資料整合發生於 Customer Insights，因此我們可以使用 *顧客識別碼* 加入這些表格。

   ![加入匯入的資料。](media/join-imported-data.png)

組建流失分析模型的特徵化動作會有一點難以應付。 資料是每天所記錄的新飯店活動的時間函數。 進行特徵化時，我們需要從動態資料產生靜態特徵。 在本案例中，我們使用一年的滑動視窗從飯店活動產生多個特徵。 我們還會將房間類型或預訂類型等分類特徵擴展成使用一位有效編碼的個別特徵。  

最終特徵清單：

| **數字**  | **原始資料行**          | **衍生特徵**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | 房間類型                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | 預約類型                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | 旅遊類別              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | 消費金額                | TotalDollarSpent                                                                                                                          |
| 5           | 入住和退房日期  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015、StayCount2014                |
| 6           | 服務使用項目                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>模型選取

現在我們必須選擇要使用的最佳演算法。 在此案例中，大部分特徵都是以分類特徵為依據。 決策樹模型效果往往不錯。 如果只有數字特徵，神經網路應該是比較好的選擇。 支援向量機器 (SVM) 在此類情形中也是不錯的候選模型，但這需要進行大量調整才能取得最佳效能。 我們選擇 **二元促進式決策樹** 做為首選模型，接著再將 **二元 SVM** 用做第二種模型。 Azure Machine Learning Studio 讓您進行 A/B 測試，因此最好一開始就使用兩種模型 (而非一種)。

下圖顯示 Azure Machine Learning Studio 提供的模型定型和評估管線：

![Azure Machine Learning Studio 中的流失模型。](media/azure-machine-learning-model.png)

我們也套用一種稱為 **排列特徵重要性** 的技術，這是模型最佳化的重要層面。 內建模型對最終預測從任何特定特徵所受的影響知之甚微。 特徵重要性計算機使用的是自訂演算法，可運算個別特徵對特定模型結果產生的影響。 特徵重要性已標準化為介於 + 1 到 -1 之間。 負值影響代表對應的特徵對結果有違反常理的影響，應該從模型移除。 正值影響表示此特徵對預測造成很大的影響。 因為是不同的計量，這些值並非相關係數。 如需詳細資訊，請見 [排列特徵重要性](/azure/machine-learning/studio-module-reference/permutation-feature-importance)。

整個 [流失實驗可查詢 Azure AI 資源庫](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp)。

## <a name="customer-lifetime-value-prediction"></a>客戶存留期值預測

顧客終身價值 (CLTV) 計算是企業可用來評估與區隔客戶的其中一項關鍵指標。 飯店業務方面，了解自己的客戶是關鍵要素。 例如，了解構成優良客戶的因素是決定性資訊。 這有助於飯店管理部門評估他們需要強調的特徵，並著手改善以滿足高消費型客戶。 這些決策可能會對銷售和收益產生直接影響。  

### <a name="definition-of-cltv"></a>CLTV 的定義

本範例中，我們將客戶的 CLTV 值定義為客戶在未來 365 天預計花費的總金額。 我們預計使用所有客戶過去整整三年的資料來預測此數值。

### <a name="featurization"></a>特徵化

在此案例中，特徵化也將很像流失案例那樣。 不過標籤和預測值與上方定義值不同。

### <a name="model-selection"></a>模型選取

預測 CLTV 是一項迴歸問題，因為預測值是正值連續變數。 我們根據特徵屬性將 **促進式決策樹迴歸** 選取為一種演算法，**神經網路迴歸** 則選取為另一種訓練模型演算法。

## <a name="product-recommendation-or-next-best-action"></a>產品推薦或下一步最佳動作

飯店案例中的產品建議會解釋為推薦飯店提供的服務給客戶。 目標式是為客戶選擇適當的服務，讓他們的使用量最大化。 這類似於對視訊串流服務使用者的影片建議。

### <a name="definition-of-product-recommendation-or-next-best-action"></a>產品建議或下一步最佳動作的定義

我們將目標定義為根據飯店客戶的興趣提供最適配的服務給他們，讓服務消費金額最大化。

### <a name="featurization"></a>特徵化

如同流失模型，我們正加入含有 CustomerID 的 ServiceCustomerID，以便按照各 CustomerID 一致性組建推薦產品。

![建議模型特徵化。](media/azure-machine-learning-model-featurization.png)

資料源自三種不同實體，特徵則由其衍生。 與流失及 CLTV 案例相比，建議問題的特徵化有所不同。 推薦模型需要以三組特徵為資料的輸入格式。

### <a name="model-selection"></a>模型選取

我們使用稱為 **訓練 Matchbox 推薦程式** 的演算法預測產品或服務，藉此訓練推薦模型。

![產品建議演算法。](media/azure-machine-learning-model-recommendation-algorithm.png)

**訓練 Matchbox 推薦程式** 模型的三個輸入埠納入訓練服務使用方式資料、客戶描述 (非必要) 和服務描述使用。 目前有三種不同的模型評分方式。 其中一種適用模型評估，其間標準化折現累積增益 (Normalized Discounted Cumulative Gain，NDCG) 分數經算出後排列評級項目名次。 在此實驗中，我們的 NDCG 分數設定為 0.97。 另外兩個選項是針對整個可推薦服務目錄上的模型評分，或只針對使用者未曾使用過的項目評分。

進一步端詳整個服務目錄的推薦分佈情況，我們注意到電話、WiFi 和快遞是預計推薦的前幾項服務。 這與我們從服務消費資料的分佈所發現的情況一致：

![建議模型輸出。](media/azure-machine-learning-model-output.png)

整個 [產品推薦實驗可在 Azure AI 資源庫存取。](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>整合自訂模型

若要在 Customer Insights 中使用這些預測，您必須連同客戶識別碼一起 **匯出** 預測。 [將它們匯出到您預計匯出](/azure/storage/common/storage-import-export-data-from-blobs) 來源資料的同一個 Azure Blob 儲存體位置。 您可以將預測型 Web 服務排定為定期執行，並更新分數。

自訂模型產生的資料可用來進一步富集您的客戶資料。 如需詳細資訊，請參閱[自訂機器學習模型](custom-models.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]