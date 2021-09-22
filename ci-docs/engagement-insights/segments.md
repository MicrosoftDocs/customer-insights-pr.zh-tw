---
title: 檢視和建立客戶細分
description: 如何建立、編輯及刪除客戶細分，以及在何處使用它們。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036138"
---
# <a name="view-and-create-segments"></a>檢視和建立客戶細分

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

客戶細分可讓您依據特徵或網站互動來找出訪客的子集。 客戶細分可讓您套用篩選並分析這些子集。 這項分析可協助您檢查並回應業務趨勢。 

:::image type="content" source="media/segments-page.png" alt-text="參與見解應用程式的螢幕擷取畫面，圖上顯示工作區中現有的客戶細分清單。":::

## <a name="view-segments"></a>查看客戶細分

1. 在左導覽窗格中，移至 **資料**。 

1. 選取 **客戶細分** 索引標籤，以查看工作區中所有客戶細分的清單。 

## <a name="create-a-segment"></a>建立客戶細分

客戶細分是由規則和條件以邏輯運算子連接所組成。 條件會將篩選套用至選取的維度。 每個客戶細分最多可以使用五個維度。

下列範例顯示一條規則中有兩個條件的客戶細分。 它會篩選出瀏覽器是 Chrome 和作業系統為 iOS 或 Android 的所有網站事件。

:::image type="content" source="media/segment-sample.png" alt-text="一個規則中有兩個條件的範例客戶細分，可篩選網站事件。":::

本節說明如何從頭開始建立 *空白客戶細分*。

1. 移至 **資料** > **客戶細分**。

1. 選取 **新增區段**。

1. 在 **資源庫** 中，選擇想要作為篩選的屬性。 目前，您只能依據維度來建立客戶細分。

1. 為選取的屬性選擇運算子與值。 下列的作業都被支援。
   - **是**：需要完全相符才能包含值。 對單一值中使用 **等於**，或以 **任何** 包含多個值。
   - **不是**：需要完全相符才能排除值。 對單一值中使用 **等於**，或以 **任何** 包含多個值。
   - **起始為**：相符值起始的字串。
   - **結尾為**：相符值結尾的字串。
   - **包含**：相符值中要包含的字串。

1. 若要將更多條件新增至群組，您可以使用兩個邏輯運算子。 使用集合運算子時，映射屬性會被計入。
   - **AND** 運算子：在區段程序中兩個條件都必須符合。 當您跨不同實體定義條件時，此選項非常有用。
   - **OR** 運算子：在區段程序中，需要符合其中一項條件。 當您為相同實體定義多個條件時，此選項非常有用。

1. 選取 **儲存**，然後命名客戶細分。 

該客戶細分會列在客戶細分頁面上，您可以將它套用至工作區中的所有報表和漏斗圖上。

## <a name="use-a-segment-in-a-report-or-funnel"></a>在報表或漏斗圖使用客戶細分

您可以將客戶細分套用至報表或漏斗圖，以客戶細分中的條件來篩選它們。 但是，您無法將客戶細分套用至即時使用報表。

:::image type="content" source="media/segment-reports-filter.png" alt-text="網頁查看報表，包含展開的下拉式清單，可讓您選擇要套用哪些客戶細分。":::

若要套用客戶細分，請打開報表或漏斗圖。 選取 **新增條件**，然後選擇 **依客戶細分篩選**。 從清單上選擇您想要套用客戶細分。 該客戶細分會套用至報表。 如果圖表不支援該客戶細分，則會顯示錯誤。
 
您可以 *最多將三個客戶細分* 套用至報表或漏斗。

## <a name="edit-a-segment"></a>編輯客戶細分

1. 移至 **資料** > **客戶細分**。
1. 請在清單中選取客戶細分來開啟它。 
1. 視需要變更或新增值。
1. 選取 **儲存** 套用變更。

## <a name="change-the-name-of-a-segment"></a>變更客戶細分的名稱

1. 移至 **資料** > **客戶細分**。
1. 在客戶細分清單中，選取 **更多 [...]**。 
1. 在下拉式清單中，選擇 **編輯名稱**。
1. 輸入新的名稱，然後選取 **重新命名**。

## <a name="delete-a-segment"></a>刪除客戶細分

1. 移至 **資料** > **客戶細分**。
1. 在客戶細分清單中，選取 **更多 [...]**。 
1. 在下拉式清單中，選擇 **刪除**。
1. 請選取 **刪除**，確認刪除。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
