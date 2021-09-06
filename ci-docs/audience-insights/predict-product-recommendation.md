---
title: 產品建議預測
description: 預測一個客戶可能購買或互動的產品。
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: bcbafa513c2c61b0280c91aa7ed71e211c32c35c
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556114"
---
# <a name="product-recommendation-prediction-preview"></a>產品建議預測 (預覽版)

產品建議模型會建立一組預測的產品建議。 建議是基於先前的購買行為和具有類似購買模式的客戶而建立的。 您可以在 **智慧** > **預測** 頁面上建立新的產品建議預測。 選取 **我的預測** 以查看您所建立的其他預測。

產品建議可能受到當地法律、法規及客戶期望等限制，而模型並未特別納入考慮。  使用者使用這種預測能力的時候，**必須先檢閱建議，再傳遞給您的客戶**，才能確保建議的內容符合任何適用的法律或規定以及客戶期望。 

此外，此模型的輸出將依據產品識別碼提供給您建議。 您的傳遞機制必須將預測出的產品識別碼對應至適當的內容，讓您的客戶可以取得當地語系化、影像內容以及其他業務特定的內容或行為。

## <a name="sample-guide"></a>範例指南

如果您想要試用此功能，但沒有能完成下面的需求的資料，您可以[建立範例實施](sample-guide-predict-product-recommendation.md)。

## <a name="prerequisites"></a>先決條件

- 至少有 Customer Insights 中的[參與者權限](permissions.md)。

- 商務知識，瞭解與您企業相關的各種類型產品，以及客戶如何與它們互動。 我們的支援可建議您的客戶已購買過的產品或建議新的產品。

- 關於交易/購買及其歷史記錄的資料：
    - 區分購買或交易的交易識別碼。
    - 將客戶對應到交易的客戶識別碼。
    - 交易事件日期指定交易發生的日期。
    - 交易記錄的產品識別碼資訊。
    - (可選)用來篩選產品的產品類別目錄資料實體。
    - (可選) 交易是否為退貨。
    - 語意資料結構描述需要下列資訊：
        - **交易識別碼：** 購買或交易的唯一識別碼。
        - **交易日期：** 購買或交易的日期。
        - **交易值**：購買或交易的數字值。
        - **唯一的產品識別碼：** 產品識別碼，或者如果您的資料是明細項目層級，則為已購買服務的識別碼。
        - (可選)**購買或退貨：** 布林值欄位，其中值 *true* 表示交易是退貨。 如果未提供採購或退貨資料，然而 **交易記錄的值** 是負值，我們也會使用此資訊來推斷是退貨。
- 建議的資料特性：
    - 足夠的歷史資料：至少一年的交易資料，要涵蓋一些季節性最好是 2 到 3 年。
    - 每個客戶有多個購買：每個客戶識別碼有三個或更多交易記錄
    - 客戶數量：至少 100 個客戶，最好超過 10,000 個客戶。 少於 100 個客戶模型會發生錯誤。

> [!NOTE]
> - 模型需要客戶的交易歷史記錄。 交易的定義非常靈活。 任何描述使用者-產品互動的資料都可以當作輸入。 例如，購買產品、上課或參加活動。
> - 目前只能設定一個交易記錄歷史記錄實體。 如果有多個購買實體，請在資料內嵌之前，在 Power Query 將它們聯集。
> - 如果訂單和訂單詳細資料是不同的實體，請於用在模型之前，先連結它們。 在實體中只有訂單識別碼或收據識別碼時，模型無法運作。


## <a name="create-a-product-recommendation-prediction"></a>建立產品建議預測

1. 在 Customer Insights 中，移至 **智慧** > **預測**。

1. 選取 **產品建議模型 (預覽版)** 圖格和 **使用此模型**。
   > [!div class="mx-imgBorder"]
   > ![具有「使用此模型」按鈕的產品建議模型圖標。](media/product-recommendation-usethismodel.PNG "使用此模型按鈕的產品建議模型圖格")

1. 查看有關模型需求的資訊。 如果您有必要的資料，請選取 **開始使用**。

### <a name="name-model"></a>命名模型

1. 提供模型的名稱，以便與其他模型有所區分。

1. 輸入輸出實體的名稱，名稱由字母和數位，而不需有任何空格。 這是模型實體將會使用的名稱。 然後選取 **下一步**。

### <a name="define-product-recommendation-configuration"></a>定義產品建議設定

1. 設定想要向客戶建議的 **產品數目**。 依照傳送方式此值填充資料。 如果您可以建議三種產品，請依此設定此值。
   
   >[!TIP]
   > 您隨時都可以選取 **儲存後關閉**，將預測儲存為草稿。 您可以在 **我的預測** 索引標籤中找到預測草稿。

1. 如果您想 **建議客戶最近購買過的產品**，請選擇。

1. 如果您已選取 *不要* 建議最近購買過的產品，請設定 **回顧視窗**。 此設定指定模型向使用者再次推薦產品前，考量的時間範圍。 例如，指定客戶每兩年購買一台筆記本電腦。 此視窗將查看過去兩年的購買歷史記錄，如果找到項目，則將該項目從建議中篩選掉。

1. 選取 **下一個**

### <a name="add-required-data"></a>新增必要資料

1. 對 **客戶交易歷史記錄** 選取 **新增資料** 接著選擇實體以提供[先決條件](#prerequisites) 中描述的交易/購買歷史記錄資訊。

1. 將語義欄位對應到您的購買歷史記錄實體中的屬性，並選取 **下一步**。 如需欄位的描述，請查看[先決條件](#prerequisites)。
   > [!div class="mx-imgBorder"]
   > ![定義實體關聯。](media/product-recommendation-purchasehistorymapping.PNG "購買歷史記錄頁面，顯示的語意屬性可對應至選取的購買歷史記錄實體中欄位")

1. 如果欄位未填寫，請設定購買歷史記錄實體到 *客戶* 實體的關聯。
    1. 請選取 **購買歷史記錄實體**。
    1. 請在購買歷史記錄實體中選取找出客戶的 **欄位**。 必須關聯到 *客戶* 實體的主要客戶識別碼。
    1. 選取與主要客戶實體相配的 **客戶實體**。
    1. 輸入描述此關聯的名稱。
       > [!div class="mx-imgBorder"]
       > ![購買歷史記錄頁面顯示對客戶關係的建立。](media/model-purchase-join.png "購買歷史記錄頁面顯示建立對客戶的關聯")

1. 選取 **儲存**。

1. 選取 **下一步**。

### <a name="configure-product-filters"></a>設定產品篩選

有些時候，您建立的預測類型只對特定產品有好處或只適用於特定產品。 產品篩選可讓您找出有特定特徵的產品子集，來建議給客戶。 模型將使用所有可用的產品來學習模式，但只使用符合產品篩選輸出的產品。

1. 在 **新增產品資訊** 步驟中，將每一種產品的資訊新增至產品目錄。 選取 **下一步** 對應必須的資訊。

3. 在 **產品篩選** 步驟中，選擇下列選項。

   * **無篩選**：使用產品建議預測中的全部產品。

   * **定義特定的產品篩選**：使用產品建議預測中的特定產品。

1. 選取 **下一步**。

1. 如果您選擇定義產品篩選，則需要立刻定義它。 在 **產品類別目錄屬性** 窗格中，從 *產品類別目錄實體* 中選取要包含在篩選中的屬性。

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="側邊窗格顯示產品類別目錄實體中的屬性，可選取到產品篩選中。":::

1. 您可以選擇產品篩選是否要使用 **and** 或 **or** 連接子，以邏輯將選取的屬性與產品類別目錄合併。
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="產品篩選結合邏輯「AND」連接子的設定範例。":::

1. 選取 **下一步**。

### <a name="set-update-schedule-and-review-configuration"></a>設定更新排程並檢閱設定

1. 設定保留模型的頻率。 將新資料匯入至 Customer Insights 時，此設定對於更新預測準確度很重要。 大部分企業都可以每月重新定型一次，讓他們的預測取得良好的準確度。

1. 選取 **下一步**。

1. 檢閱設定。 您可以選取顯示值底下的 **編輯**，返回預測設定的任何一部分。 或者，也可以從進度指示器中選取設定步驟。

1. 如果所有的值都已正確設定，請選取 **儲存並執行** 以開始預測程序。 在 **我的預測** 索引標籤 中，您可以看到預測狀態。 視預測中使用的資料量而定，此程序可能需要數個小時才能完成。

## <a name="review-a-prediction-status-and-results"></a>檢閱預測狀態與結果

1. 移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。
   > [!div class="mx-imgBorder"]
   > ![我的預測頁面的檢視表。](media/product-recommendation-mypredictions.PNG "我的預測頁面的檢視表")

1. 選取您要檢閱的預測。
   - **預測名稱：** 建立預測時提供的預測名稱。
   - **預測類型：** 預測使用的模型類型
   - **輸出實體：** 用於儲存預測輸出之實體的名稱。 您可以在 **資料** > **實體** 中找到具有此名稱的實體。    
      產出實體中的 *分數* 是此建議的量值。 對比分數低的產品，此模型會建議分數較高的產品。
   - **預測欄位：** 僅某些類型的預測需填入此欄位，並不用於產品建議預測。
   - **狀態：** 預測的執行的目前狀態。
        - **已排入佇列：** 預測目前正在等待其他要執行的程序。
        - **重新整理：** 預測目前正在執行「分數」處理階段，以產生流入輸出實體的結果。
        - **失敗：** 預測失敗。 選取 **記錄檔** 以取得更多詳細資料。
        - **成功：** 預測已成功。 選取垂直省略符號下方的 **檢視** 來檢閱預測
   - **已編輯：** 變更預測設定的日期。
   - **上次重新整理：** 預測重新整理輸出實體中結果的日期。

1. 選取您要檢閱結果的預測旁邊的垂直省略符號，並選取 **檢視**。
   > [!div class="mx-imgBorder"]
   > ![檢視垂直省略符號功能表中與預測有關的選項，包括編輯、重新整理、檢視、記錄和刪除。](media/product-recommendation-verticalellipses.PNG "預測的垂直省略符號功能表的 [檢視] 選項包括編輯、重新整理、檢視、記錄和刪除")

1. 結果頁面中有五個主要資料區段：
    1. **定型模型效能：** A、B 或 C 是可能的分數。 此分數表示預測的效能，可協助您做出決定以使用輸出實體中儲存的結果。
        - 分數是根據下列規則所決定：
            - **A** 如果 "Success @ K" 指標比基準模型至少高 10%，則該模型被視為品質 **A**。 
            - **B** 如果 "Success @ K" 指標比基準高 0% 到 10%，則該模型被視為品質 **B**。
            - **C** 如果 "Success @ K" 指標比基準低，則該模型被視為品質 **C**。
               
               > [!div class="mx-imgBorder"]
               > ![模型效能結果的檢視。](media/product-recommendation-modelperformance.PNG "模型效能結果的檢視")
            - **基準**：模型會透過所有客戶的購買總數來採用最常推薦的產品，並使用模型辨識出並習得的規則為客戶建立一組建議。 然後，會將預測與前排名最高產品 (以購買該產品的客戶數目計算) 進行比較。 如果客戶的建議產品中至少有一個產品也能高購買量產品中看到，則會將他們視為基準的一部分。 如果這樣的客戶每 100 位有 10 位曾購買建議的產品，則基準衡量為 10%。
            - **Success @ K**：使用交易記錄時段的驗證集為所有客戶建立建議，並以此建議與交易的驗證集進行比較。 例如，在 12 個月的時段中，可能會將第 12 個月保留為資料的驗證集。 如果此模型根據先前的 11 個月所學到的時間，可預測第 12 個月您所購買的至少一樣物品，則此客戶將會增加 "Success @ K" 的衡量標準。
    
    1. **最建議的產品 (含計數)：** 為客戶預測的五種最佳的產品。
       > [!div class="mx-imgBorder"]
       > ![最建議的 5 個產品的圖表。](media/product-recommendation-topproducts.PNG "最建議的 5 個產品的圖表")
    
    1. **主要建議因素：** 模型會使用客戶的交易歷史記錄，來製作產品建議。 它會根據過去的購買內容學習模式，並尋找客戶與產品之間的相似處。 然後使用這些相似處來生成產品建議。
    以下是可能會影響模型生成產品建議的因素。 
        - **過去交易**：過去的購買模式會被模型用來生成產品建議。 例如，如果某個人最近購買了 _Surface Book 3_ 和 _Surface Pen_，則模型會建議 _Surface Arc 滑鼠_。 此模型瞭解到過去有許多客戶在購買 _Surface Book 3_ 和 _Surface Pen_ 後，就購買 _Surface Arc 滑鼠_。
        - **客戶相似性**：建議的產品在過去由表現出類似購買模式的其他客戶購買。 例如，因為 Jennifer 和 Brad 最近購買 _Surface 耳機 2_，John 被建議了 _Surface 耳機 2_。 因為他們過去都有類似的購買模式，模型相信 John 跟 Jennifer 與 Brad 相似。
        - **產品相似性**：建議的產品與客戶先前購買的其他產品類似。 如果產品過去會被同時購買或被類似的客戶購買，此模型會將兩種它們視為相似。 例如，有些人會取得 _USB 儲存裝置_ 建議，是因為他們先前購買了 _USB-C to USB 轉接器_，而且基於歷史購買模式，模型認為 _USB 儲存裝置_ 與 _USB-C to USB 轉接器_ 類似。

        每個產品建議都會受到一個或多個因素的影響。 在圖表中，會視覺化每個影響因素對建議造成影響的百分比。 在下列範例中，100% 的建議受到過去交易的影響，60% 為客戶相似性，以及 22% 為產品相似性。 將滑鼠停留在圖表上的方塊，可查看影響因素所提供的確切百分比。

        > [!div class="mx-imgBorder"]
        > ![關鍵建議因素。](media/product-recommendation-keyrecommendationfactors.png "為生成產品建議，模型學習到的主要建議因素")
       
     
   1. **資料統計資料**：提供模型所考慮的交易、客戶及產品數量的概覽。 這是根據用來學習模式和生成產品建議的輸入資料而定。

      > [!div class="mx-imgBorder"]
      > ![資料統計資料。](media/product-recommendation-datastatistics.png "資料統計資訊關於模型使用來學習模式的 inout 資料")

      此區段顯示的統計資料是關於模型使用來學習模式並生成產品建議的資料點。 在模型設定中設定好的篩選，會套用在模型生成的輸出上。 但是，模型會使用所有可用的資料來學習模式。 因此，如果您在模型設定中使用產品篩選，此區段會顯示模型分析來學習各種模式的產品總數量，這可能與符合篩選準則定義的產品數量不同。

   1. **高信賴度的產品建議：** 提供給您的客戶建議範例，這些是模型認為客戶最有可能購買的。    
      如果新增了產品類別目錄，則產品產品識別碼會被取代為產品名稱。 產品名稱對預測提供更具備可操作性和最直觀的資訊。
       > [!div class="mx-imgBorder"]
       > ![清單上是受選個別客戶組的高信賴度建議。](media/product-recommendation-highconfidence.PNG "清單上是受選個別客戶組的高信賴度建議")

## <a name="manage-predictions"></a>管理預測

最佳化、疑難排解、重新整理或刪除預測都能夠做到。 檢閱輸入資料可用性報表，找出如何讓預測更快捷和更可靠。 如需詳細資訊，請參閱[管理預測](manage-predictions.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]