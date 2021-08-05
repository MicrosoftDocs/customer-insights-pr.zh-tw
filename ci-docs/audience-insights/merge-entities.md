---
title: 將實體合併到資料統整中
description: 合併實體以建立統整的客戶設定檔。
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 24b523786158ff36c314601846ee25ea64cfabbe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650124"
---
# <a name="merge-entities"></a>合併實體

合併階段是資料統整程序的最後一個階段。 其目的在於協調衝突的資料。 衝突資料的範例包括位於兩個資料集中的客戶名稱，但在各資料集中略有不同 (例如「Grant Marshall」與「Grant Marshal」)，或是格式不同的電話號碼 (617-803-091X 與 617803091X)。 合併這些相互衝突的資料點，是依屬性逐一進行。

:::image type="content" source="media/merge-fields-page.png" alt-text="資料統整處理中的合併頁面，顯示定義整合客戶個人資料且具有合併欄位的表格。":::

完成 [比對階段](match-entities.md)之後，您可以透過在 **統整** 頁面上選取 **合併** 圖標來開始合併階段。

## <a name="review-system-recommendations"></a>檢閱系統建議

在 **資料** > **統整** > **合併** 中，您可以選擇並排除一些屬性，不要合併到整合客戶個人資料實體中。 整合客戶個人資料是資料統整處理的結果。 某些屬性會由系統自動合併。

若要查看包含在自動合併屬性中的任一種屬性，請在表格的 **客戶欄位** 索引標籤中，選取該合併屬性。 構成該合併屬性的屬性會顯示在合併屬性下方的兩個新列中。

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>分割、重新命名、排除及編輯合併欄位

您可以變更系統處理合併屬性的方式，生成整合客戶個人資料。 選取 **顯示詳細資訊**，然後選擇要變更的內容。

:::image type="content" source="media/manage-merged-attributes.png" alt-text="顯示更多的下拉式功能表中的選項，可管理合併屬性。":::

如需詳細資訊，請參閱下節。

## <a name="separate-merged-fields"></a>分割合併欄位

若要分割合併欄位，請在表格中尋找屬性。 分割欄位會以個別資料點顯示在整合的客戶個人資料上。 

1. 選取合併欄位。
  
1. 選取 **顯示更多**，然後選擇 **分割欄位**。
 
1. 確認分割。

1. 選取 **儲存** 並 **執行** 來處理變更。

## <a name="rename-merged-fields"></a>重新命名合併欄位

變更合併屬性的顯示名稱。 您無法變更輸出實體的名稱。

1. 選取合併欄位。
  
1. 選取 **顯示更多**，然後選擇 **重新命名**。

1. 確認變更顯示名稱。 

1. 選取 **儲存** 並 **執行** 來處理變更。

## <a name="exclude-merged-fields"></a>排除合併欄位

從整合的客戶個人資料中排除屬性。 如果欄位是用於其他程序中 (例如，客戶細分)，則請先從這些程序中移除該欄位，然後再從客戶個人資料中排除它。 

1. 選取合併欄位。
  
1. 選取 **顯示更多**，然後選擇 **排除**。

1. 確認排除。

1. 選取 **儲存** 並 **執行** 來處理變更。 

在 **合併** 頁面上，選取 **排除欄位** 以查看所有排除欄位的清單。 此窗格可新增排除欄位。

## <a name="manually-combine-fields"></a>手動結合欄位

手動指定合併屬性。 

1. 在 **合併** 頁面上，選取 **結合欄位**。

1. 提供 **名稱** 和 **輸出欄位名稱**。

1. 選擇欄位以新增。 選擇 **新增欄位** 結合更多欄位。

1. 確認排除。

1. 選取 **儲存** 並 **執行** 來處理變更。 

## <a name="change-the-order-of-fields"></a>變更欄位順序

某些實體比其他實體包含更多詳細資料。 如果實體包含欄位的最新資料，您可以在合併值時，設定它優先於其他實體。

1. 選取合併欄位。
  
1. 選取 **顯示更多**，然後選擇 **編輯**。

1. 在 **合併欄位** 窗格中，選取 **上移/下移** 來設定順序，或將它們拖放至想要的位置。

1. 確認變更。

1. 選取 **儲存** 並 **執行** 來處理變更。

## <a name="run-your-merge"></a>執行合併

不論您手動合併屬性或讓系統合併，您都可以執行合併。 在 **合併** 頁面上，選取 **執行** 來開始處理。

> [!div class="mx-imgBorder"]
> ![資料合併儲存與執行。](media/configure-data-merge-save-run.png "資料合併儲存與執行")

若只想要查看反映在整合客戶實體中的輸出，請選取 **只執行合併**。 下游程序將會按照[排程中定義的重新整理](system.md#schedule-tab)來重新整理。

選擇 **執行合併及下游程序** 以變更來重新整理系統。 所有程序 (包括擴充、客戶細分和量值) 都會自動重新執行。 在所有下游程序完成後，客戶個人資料會反映出您做的所有變更。

若要進行更多變更並重新執行步驟，您可以取消進行中的合併。 選取 **重新整理中...**，然後在出現的側面窗格中選取 **取消工作**。

> [!TIP]
> 執行合併程序後，請選取程序狀態以打開 **工作詳細資料** 窗格。 它提供處理時間、上次處理日期以及與工作相關的所有錯誤與警告的概覽。 選取 **查看詳細資料**，以查看參與比對程序的實體、解決衝突流程是否成功，以及更新是否已順利發布。  
> 任務/流程目前有 [六種類型的狀態](system.md#status-types)。 此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。  
> :::image type="content" source="media/process-detail-path.png" alt-text="從工作狀態連結取得程序詳細資料的逐層探究路徑。":::

## <a name="next-step"></a>後續步驟

設定[活動](activities.md)、[擴充](enrichment-hub.md)或[關聯](relationships.md)，以進一步了解您的客戶。

如果您已設定活動、擴充或客戶細分，則會自動處理它們，以使用最新的客戶資料。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
