---
title: 將實體合併到資料統整中
description: 合併實體以建立統整的客戶設定檔。
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597823"
---
# <a name="merge-entities"></a>合併實體

合併階段是資料統整程序的最後一個階段。 其目的在於協調衝突的資料。 衝突資料的範例包括位於兩個資料集中的客戶名稱，但在各資料集中略有不同 (例如「Grant Marshall」與「Grant Marshal」)，或是格式不同的電話號碼 (617-803-091X 與 617803091X)。 合併這些相互衝突的資料點，是依屬性逐一進行。

完成 [比對階段](match-entities.md)之後，您可以透過在 **統整** 頁面上選取 **合併** 圖標來開始合併階段。

## <a name="review-system-recommendations"></a>檢閱系統建議

在 **合併** 頁面上，您可以選擇並排除要在您的統整客戶設定檔實體 (設定程序的結果) 中合併的屬性。 某些屬性會由系統自動合併。

### <a name="view-merged-attributes"></a>檢視合併的屬性

若要查看其中一個自動合併屬性所包含的屬性，請選取該合併屬性。 構成該合併屬性的兩個屬性會顯示在合併屬性下方的兩個新列中。

> [!div class="mx-imgBorder"]
> ![選取合併的屬性](media/configure-data-merge-profile-attributes.png "選取合併的屬性")

### <a name="separate-merged-attributes"></a>分割合併的屬性

若要分割或取消合併任何自動合併的屬性，請在 **設定檔屬性** 表格中尋找屬性。

1. 選取省略符號 (...) 按鈕。
  
2. 在下拉式清單中，選取 **分割欄位**。

### <a name="remove-merged-attributes"></a>移除合併的屬性

若要從最終的客戶設定檔實體中排除屬性，請在 **設定檔屬性** 表格中找到它。

1. 選取省略符號 (...) 按鈕。
  
2. 在下拉式清單中，選取 **不合併**。

   屬性會移至 **已從客戶記錄中移除** 區段。

## <a name="manually-add-a-merged-attribute"></a>手動新增合併的屬性

若要新增合併的屬性，請移至 **合併** 頁面。

1. 選取 **新增合併的屬性**。

2. 提供 **名稱** 以供稍後在 **合併** 頁面上識別它。

3. 或者，提供 **顯示名稱**，將顯示在統整客戶設定檔實體中。

4. 設定 **選取重複的屬性**，以選取您要從相符的實體合併的屬性。 您也可以搜尋屬性。

5. 設定 **依重要性排名**，以優先處理某個屬性。 例如，如果 *WebAccountCSV* 實體包含有關 *全名* 屬性的最準確資料，您可以選取 *WebAccountCSV*，將此實體的優先順序設定高於 *ContactCSV*。 因此，在提取 *全名* 屬性的值時，*WebAccountCSV* 會移至第一優先順序，而 *ContactCSV* 則移至第二優先順序。

## <a name="run-your-merge"></a>執行合併

不論您手動合併屬性或讓系統合併，您都可以執行合併。 在 **合併** 頁面上，選取 **執行** 來開始處理。

> [!div class="mx-imgBorder"]
> ![資料合併儲存與執行](media/configure-data-merge-save-run.png "資料合併儲存與執行")

若要進行其他變更並重新執行步驟，您可以取消進行中的合併。 選取 **重新整理中...**，然後在出現的側面窗格中選取 **取消工作**。

在 **重新整理中** 文字變更為 **成功** 後，已根據您定義的原則完成合併並解決資料中的衝突。 合併和未併入的屬性會包含在統整設定檔實體中。 排除的屬性不會包含在統整設定檔實體中。

如果這不是您第一次成功地進行合併，所有下游程序（包括擴充、區段化和量值）都會自動重新執行。 在所有下游程序重新執行之後，客戶設定檔會反映您所做的任何變更。

> [!TIP]
> 任務/流程目前有 [六種類型的狀態](system.md#status-types)。 此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。 您可以選取程序的狀態，以查看整個工作的進度詳細資料。 針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。

## <a name="next-step"></a>後續步驟

設定[活動](activities.md)、[擴充](enrichment-microsoft-graph.md)或[關聯](relationships.md)，以進一步了解您的客戶。

如果您已設定活動、擴充或關聯，或者您已定義區段時，系統會自動加以處理來使用最新的客戶資料。




[!INCLUDE[footer-include](../includes/footer-banner.md)]