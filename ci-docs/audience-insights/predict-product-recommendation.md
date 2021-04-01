---
title: 產品建議預測
description: 預測一個客戶可能購買或互動的產品。
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598053"
---
# <a name="product-recommendation-prediction-preview"></a>產品建議預測 (預覽版)

產品建議模型會建立一組預測的產品建議。 建議是基於先前的購買行為和具有類似購買模式的客戶而建立的。 您可以在 **智慧** > **預測** 頁面上建立新的產品建議預測。 選取 **我的預測** 以查看您所建立的其他預測。

產品建議應取決於當地法律和法規以及客戶的期望，但此模型不是組建來專門考量這些項目。  作為此預測能力的使用者，**您必須先審查建議，再傳送給您的客戶**，以確保您有遵守所有適用的法律或法規，以及客戶對建議的期待。 

此外，此模型的輸出將依據產品識別碼提供給您建議。 您的傳送機制將需要取得預測的產品識別碼，並將它們對應至提供客戶的適當內容，來說明當地語系化、影像內容以及其他特定業務的內容或行為。

## <a name="sample-guide"></a>範例指南

如果您想要試用此功能，但沒有能完成下面的需求的資料，您可以[建立範例實施](sample-guide-predict-product-recommendation.md)。

## <a name="prerequisites"></a>先決條件

- 至少有 Customer Insights 中的[參與者權限](permissions.md)。
- 商務知識，瞭解與您企業相關的各種類型產品，以及客戶如何與它們互動。 我們的支援可建議您的客戶已購買過的產品或建議新的產品。
- 關於交易/購買及其歷史記錄的資料：
    - 區分購買或交易的交易識別碼。
    - 將客戶對應到交易的客戶識別碼。
    - 交易事件日期指定交易發生的日期。
    - (可選) 交易的產品識別碼資訊。
    - (可選) 交易是否為退貨。
    - 語意資料結構描述需要下列資訊：
        - **交易識別碼：** 購買或交易的唯一識別碼。
        - **交易日期**：購買或交易的日期。
        - **交易值**：購買或交易的數字值。
        - **唯一的產品識別碼：** 產品識別碼，或者如果您的資料是明細項目層級，則為已購買服務的識別碼。
        - (可選) **購買或退貨：** 標識交易是否為退貨的是/否欄位。 如果 **交易值** 是負值，我們也會使用此項資訊推論是否退還。


## <a name="create-a-product-recommendation-prediction"></a>建立產品建議預測

1. 在 Customer Insights 中，移至 **智慧** > **預測**。

1. 選取 **產品建議模型 (預覽版)** 圖格和 **使用此模型**。
   > [!div class="mx-imgBorder"]
   > ![使用此模型按鈕的產品建議模型圖格](media/product-recommendation-usethismodel.PNG "使用此模型按鈕的產品建議模型圖格")

1. 查看有關模型需求的資訊。 如果您有必要的資料，請選取 **開始使用**。

### <a name="name-model"></a>命名模型

1. 提供模型的名稱，以便與其他模型有所區分。

1. 輸入輸出實體的名稱，名稱由字母和數位，而不需有任何空格。 這是模型實體將會使用的名稱。 然後選取 **下一步**。

### <a name="define-product-recommendation-configuration"></a>定義產品建議設定

1. 設定想要向客戶建議的 **產品數目**。 依照傳送方式此值填充資料。 如果您可以建議三種產品，請依此設定此值。
   
   >[!TIP]
   > 您隨時都可以選取 **儲存後關閉**，將預測儲存為草稿。 您可以在 **我的預測** 索引標籤中找到預測草稿。

1. 如果您想 **建議客戶最近購買過的產品**，請選擇。

1. 如果您已選取 *不要* 建議最近購買過的產品，請設定 **回顧視窗**。 此設定指定模型向使用者再次推薦產品前，考量的時間範圍。 例如，標示客戶每 2 年就會購買筆記本電腦。 此視窗將查看過去 2 年的購買歷史記錄，如果他們找到項目，則會將該項目從建議篩選掉。

1. 選取 **下一個**

### <a name="add-required-data"></a>新增必要資料

1. 對 **客戶交易歷史記錄** 選取 **新增資料** 接著選擇實體以提供[先決條件](#prerequisites) 中描述的交易/購買歷史記錄資訊。

1. 將語義欄位對應到您的購買歷史記錄實體中的屬性，並選取 **下一步**。 如需欄位的描述，請查看[先決條件](#prerequisites)。
   > [!div class="mx-imgBorder"]
   > ![定義實體關聯](media/product-recommendation-purchasehistorymapping.PNG "購買歷史記錄頁面，顯示的語意屬性可對應至選取的購買歷史記錄實體中欄位")

1. 如果欄位未填寫，請設定購買歷史記錄實體到 *客戶* 實體的關聯。
    1. 請選取 **購買歷史記錄實體**。
    1. 請在購買歷史記錄實體中選取找出客戶的 **欄位**。 必須關聯到 *客戶* 實體的主要客戶識別碼。
    1. 選取與主要客戶實體相配的 **客戶實體**。
    1. 輸入描述此關聯的名稱。
       > [!div class="mx-imgBorder"]
       > ![購買歷史記錄頁面顯示建立對客戶的關聯](media/model-purchase-join.png "購買歷史記錄頁面顯示建立對客戶的關聯")

1. 選取 **儲存**。

1. 選取 **下一步**。

### <a name="set-schedule-and-review-configuration"></a>設定排程並檢閱設定

1. 設定保留模型的頻率。 將新資料匯入至 Customer Insights 時，此設定對於更新預測準確度很重要。 大部分企業都可以每月重新定型一次，讓他們的預測取得良好的準確度。

1. 選取 **下一步**。

1. 檢閱設定。 您可以選取顯示值底下的 **編輯**，返回預測設定的任何一部分。 或者，也可以從進度指示器中選取設定步驟。

1. 如果所有的值都已正確設定，請選取 **儲存並執行** 以開始預測程序。 在 **我的預測** 索引標籤 中，您可以看到預測狀態。 視預測中使用的資料量而定，此程序可能需要數個小時才能完成。

## <a name="review-a-prediction-status-and-results"></a>檢閱預測狀態與結果

1. 移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。
   > [!div class="mx-imgBorder"]
   > ![我的預測頁面的檢視表](media/product-recommendation-mypredictions.PNG "我的預測頁面的檢視表")

1. 選取您要檢閱的預測。
   - **預測名稱：** 建立預測時提供的預測名稱。
   - **預測類型：** 預測使用的模型類型
   - **輸出實體：** 用於儲存預測輸出之實體的名稱。 您可以在 **資料** > **實體** 中找到具有此名稱的實體。
   - **預測欄位：** 此欄位只填入某些類型的預測，並不用在流失預測中。
   - **狀態：** 預測的執行的目前狀態。
        - **已排入佇列：** 預測目前正在等待其他要執行的程序。
        - **重新整理：** 預測目前正在執行「分數」處理階段，以產生流入輸出實體的結果。
        - **失敗：** 預測失敗。 選取 **記錄檔** 以取得更多詳細資料。
        - **成功：** 預測已成功。 選取垂直省略符號下方的 **檢視** 來檢閱預測
   - **已編輯：** 變更預測設定的日期。
   - **上次重新整理：** 預測重新整理輸出實體中結果的日期。

1. 選取您要檢閱結果的預測旁邊的垂直省略符號，並選取 **檢視**。
   > [!div class="mx-imgBorder"]
   > ![預測的垂直省略符號功能表的 [檢視] 選項包括編輯、重新整理、檢視、記錄和刪除](media/product-recommendation-verticalellipses.PNG "預測的垂直省略符號功能表的 [檢視] 選項包括編輯、重新整理、檢視、記錄和刪除")

1. 結果頁面中有三個主要的資料區段：
    1. **定型模型效能：** A、B 或 C 是可能的分數。 此分數表示預測的效能，可協助您做出決定以使用輸出實體中儲存的結果。
        - 分數是根據下列規則所決定：
            - **A** 如果 "Success @ K" 指標比基準模型至少高 10%，則該模型被視為品質 **A**。 
            - **B** 如果 "Success @ K" 指標比基準模型高 0 到 10%，則該模型被視為品質 **B**。
            - **C** 如果 "Success @ K" 指標比基準模型低，則該模型被視為品質 **C**。
               
               > [!div class="mx-imgBorder"]
               > ![模型效能結果的檢視](media/product-recommendation-modelperformance.PNG "模型效能結果的檢視")
            - **基準**：模型會透過所有客戶的購買總數來採用最常推薦的產品，並使用模型辨識出並習得的規則為客戶建立一組建議。 然後，會將預測與前排名最高產品 (以購買該產品的客戶數目計算) 進行比較。 如果客戶的建議產品中至少有一個產品也能高購買量產品中看到，則會將他們視為基準的一部分。 如果這樣的客戶每 100 位有 10 位曾購買建議的產品，則基準衡量為 10%。
            - **Success @ K**：使用交易記錄時段的驗證集為所有客戶建立建議，並以此建議與交易的驗證集進行比較。 例如，在 12 個月的時段中，可能會將第 12 個月保留為資料的驗證集。 如果此模型根據先前的 11 個月所學到的時間，可預測第 12 個月您所購買的至少一樣物品，則此客戶將會增加 "Success @ K" 的衡量標準。
    
    1. **最建議的產品 (含計數)：** 為客戶預測的前 5 種產品。
       > [!div class="mx-imgBorder"]
       > ![最建議的 5 個產品的圖表](media/product-recommendation-topproducts.PNG "最建議的 5 個產品的圖表")
    
    1. **高信賴度的產品建議：** 提供給您的客戶建議範例，這些是模型認為客戶最有可能購買的。
       > [!div class="mx-imgBorder"]
       > ![清單上是受選個別客戶組的高信賴度建議](media/product-recommendation-highconfidence.PNG "清單上是受選個別客戶組的高信賴度建議")

## <a name="fix-a-failed-prediction"></a>修正失敗的預測

1. 移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。

1. 選取您要檢視其錯誤記錄檔的預測，並選取 **記錄檔**。

1. 檢閱所有錯誤。 可能發生的錯誤有數種類型，這些類型描述造成錯誤的狀況。 例如，沒有足夠資料而無法準確預測的錯誤，通常是透過載入額外資料到 Customer Insights 中來解決。

## <a name="refresh-a-prediction"></a>重新整理預測

根據在設定中與[資料重新整理排程](system.md#schedule-tab)相同的設定，預測會自動重新整理。

1. 移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。

1. 選取您要重新整理之預測旁邊的垂直省略符號。

1. 選取 **重新整理**。

## <a name="delete-a-prediction"></a>刪除預測

刪除預測也會移除其輸出實體。

1. 移至 **智慧** > **預測** 上的 **我的預測** 索引標籤。

1. 選取您要刪除之預測旁邊的垂直省略符號。

1. 選取 **刪除**。


[!INCLUDE[footer-include](../includes/footer-banner.md)]