---
title: 使用預測完成部分資料
description: 使用預測填滿未完成的客戶資料。
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: e2cace3547a0b584dbf26ae5eecf86f3b256649f
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740709"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>透過預測完成部分資料 (已取代)

> [!IMPORTANT]
> 此功能將自 **2021 年 11 月 5 日** 起 **被取代**。 在移除功能之前，目前的實作將繼續運作，但是您將無法使用下列指示建立新的整合。

預測可讓您輕鬆建立預測值，以增強您對客戶的了解。 在 **智慧** > **預測** 頁面上，您可以選取 **我的預測** 來查看您已在 Customer Insights 的其他組件中設定的預測，並允許您進一步加以自訂。

> [!NOTE]
> 如果您的環境使用 Azure Data Lake Gen 2 儲存體，您無法使用此功能。
>
> 預測功能使用自動方法來評估資料，並根據該資料進行預測，因此具有用作剖析方法的能力，因為這個術語是由一般資料保護規定 (「GDPR」) 所定義。 若客戶使用此功能來處理資料，可能會受到 GDPR 或其他法律或法規的制約。 您負責確保您對 Dynamics 365 Customer Insights 的使用，包括預測、符合所有適用法律和規定，包括隱私權、個人資料、生物資料、資料保護和通訊機密性相關法律。

## <a name="prerequisites"></a>先決條件

在您的組織可以使用預測功能之前，必須符合下列先決條件：

1. 您的組織擁有[在 Microsoft Dataverse 中設定](/ai-builder/build-model#prerequisites)的執行個體，而且與 Customer Insights 位於相同的組織中。

2. 您的 Customer Insights 環境已附加至您的 Dataverse 執行個體。

如需詳細資訊，請參閱[建立新環境](create-environment.md)。

## <a name="create-a-prediction-in-the-customer-entity"></a>在客戶實體中建立預測

1. 請前往 **資料** > **實體**。

2. 選取 **客戶** 實體。

3. 在 **Customer: CustomerInsights** 實體中，選取 **欄位** 索引標籤。

4. 尋找想要預測值的屬性名稱，然後在 **摘要** 欄中選取 **概觀** 圖示。
   > [!div class="mx-imgBorder"]
   > ![概觀圖示。](media/intelligence-overviewicon.png "概觀圖示")

5. 如果您的屬性缺少很多值，請選取 **預測遺失值**，繼續預測。
   > [!div class="mx-imgBorder"]
   > ![顯示預測遺失值按鈕的概觀狀態。](media/intelligence-overviewpredictmissingvalues.png "顯示預測遺失值按鈕的概觀狀態")

6. 提供預測結果的 **顯示名稱** 和 **輸出實體名稱**。

7. 預先填入的選項清單將顯示可將值對應至預測類別的位置。 在此案例中，您的類別選項只有 0 或 1，因為這些選項對應至預測的 true/false 或二進位性質。 在 [類別] 欄中，將您想要在最終預測中分類為 "0" 的欄位值對應至 "0"，然後將您想要在最終預測中分類為 "1" 的項目對應至 "1"。
   > [!div class="mx-imgBorder"]
   > ![範例中顯示對應至類別的欄位值。](media/intelligence-categorymapping.png "顯示對應的欄位值至類別的範例")

8. 選取 **完成**，預測將會得到處理。 處理工作需要花費一些時間，視資料的大小和複雜度而定。 根據您所建立之預測的 **輸出實體名稱**，在新實體中提供結果。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>建立區段時建立預測

建立區段時，也可以預測特定屬性的遺失值。 特別是，當您根據統整的客戶實體或 Customer_Measure 實體快速建立區段時。

在此流程中，您可以選擇要據以建立區段的特定屬性，例如客戶滿意度或購買金額。 建立區段時，系統會建議針對此屬性預測任何遺失值的方法。

1. 請前往 **客戶細分** 並選取 **個人資料** 磚。

2. 選擇要在上建立區段的 **欄位**，並選取 **運算子**，然後選取 **檢閱**。

3. 提供區段的 **名稱** 和 **顯示名稱**。

4. 選取 **儲存**。

5. 如果您建立的區段在來源欄位中有不完整的資料，您可以選擇預測遺失的值。
   > [!div class="mx-imgBorder"]
   > ![預測按鈕。](media/segments-predictoption.png "預測按鈕")

6. 提供預測結果的 **顯示名稱** 和 **輸出實體名稱**。

7. 選取 **完成**。 您的預測很快會在新的實體中產生，此實體具有您為 **輸出實體名稱** 所提供的名稱。

## <a name="view-a-prediction"></a>檢視預測

1. 請移至 **智慧** > **預測** > **我的預測**。

2. 選取您要檢閱的預測。

3. 在 **動作** 欄中選取省略符號，然後選擇 **檢視**。

4. 您將會在預測的檢視表中看到數個資料點。
   > [!div class="mx-imgBorder"]
   > ![預測頁面。](media/intelligence-predictionsviewpage.png "預測頁面")

   - **預測值** 顯示您在欄位值對應至類別階段所建立的對應。 這些值是資料集中已對應至特定類別的值。
   -**主要影響因素** 是資料集中的因素，最有可能影響對應至特定類別之欄位值的預測信賴度。
   - **效能** 表示預測的效果。 選取連結以了解詳細資訊。
   - **預覽** 會顯示您預測的輸出資料集樣本，以及預測值的可能性或信賴度，其中 0 是不確定，1 則是確定。

## <a name="update-a-prediction"></a>更新預測

1. 請移至 **智慧** > **預測** > **我的預測**。

2. 選取要更新的預測，然後選取 **更新** 圖示。

3. 預測將會排程進行處理。 您可以在 **預測** 頁面的 **已更新** 欄中查看其上次更新的時間。

## <a name="edit-a-prediction"></a>編輯預測

建立預測之後，您可以在 AI Builder 中自訂模型，提高模型的效能。  

1. 請移至 **智慧** > **預測** > **我的預測**。

2. 選取您想編輯的預測。

3. 在 **動作** 欄中選取省略符號，然後選擇 **檢視**。

4. 選取 **自訂 AI Builder**。

5. 在 AI Builder 中更新您的模型。 [深入了解如何在 AI Builder 中管理模型](/ai-builder/manage-model#retrain-and-republish-existing-models)。

下次執行預測時，會使用您所建立的更新模型。

> [!NOTE]
> 在 AI Builder 中建立的新模型不會顯示在 Customer Insights 中，除非該模型是從上述體驗中建立的。

## <a name="remove-a-prediction"></a>移除預測

1. 請移至 **智慧** > **預測** > **我的預測**。

2. 選取您要刪除的預測。

3. 在 **動作** 欄中選取省略符號，然後選擇 **刪除**。

4. 確認刪除。

## <a name="troubleshooting"></a>疑難排解​​

如果由於發生錯誤而無法完成附加 Dataverse 程序，則可以嘗試手動完成程序。 在附加程序中有兩個已知問題：

- Customer 卡片增益集解決方案並未安裝。
    1. 完成 [安裝和設定解決方案](customer-card-add-in.md)的指示。

- 應用程式權限並未授予。
    1. 移至 [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com)。
    1. 選取 **環境**。
    1. 選取您要新增權限的環境旁邊的省略符號，並選取 **設定**。
    1. 展開 **使用者 + 權限**，然後選取 **使用者**。
    1. 選取 **+ 新增**，然後選取 **使用者**。
    1. 選取 **應用程式使用者**（如果尚未選取），並輸入下列資訊：
        - **使用者名稱：**cihelp@microsoft.com
        - **應用程式識別碼：** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **名字：** Customer
        - **姓氏**：Insights
        - **主要電子郵件：**cihelp@microsoft.com
    1. 選取 **儲存後關閉**。
    1. 選取您剛建立的使用者。
    1. 在上方功能表列中選取 **管理角色**。
    1. 選取 **系統系統管理員**，然後選取 **確定**。


[!INCLUDE [footer-include](includes/footer-banner.md)]
