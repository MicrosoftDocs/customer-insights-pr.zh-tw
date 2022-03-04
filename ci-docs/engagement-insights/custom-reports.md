---
title: 關於自訂報表
description: 學習如何建立自訂報表。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232138"
---
# <a name="create-and-edit-custom-reports"></a>建立與編輯自訂報表

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

除了隨開即用 (OOB) 報表以外，您可以使用圖表和表格視覺效果組建自訂報表，協助您了解使用者行為。 本文解釋如何使用表格和圖表視覺效果，建立包含所需資料的報表。 如需 OOB 報表資訊，請參閱[查看報表](view-reports.md)。

## <a name="create-a-custom-report"></a>建立一個自訂報表

1. 移至 **分析** > **自訂** 以存取自訂報表清單。

1. 選取 **新報表** 來開始建立自訂報表。

   :::image type="content" source="media/new-custom-report.png" alt-text="新的自訂報表。":::

1. 決定您想要建立的報表類型：

    - 在命令列中選取 **新增視覺效果**，以建立預設的表格視覺效果。
    - 或者，從 **報表編輯器** 窗格中選取柱狀圖、條形圖、折線圖、區域、圓形圖、環形或表格視覺效果。

1. 請在 **視覺化編輯器** 窗格的 **資料** 區段中的 **計量** 下拉式選單選擇其中一個可用的選項 (例如，頁面檢視)。 您也可以新增要在視覺效果顯示的 **維度** (例如國家/地區)。 如需詳細資訊，請參閱[查看和建立計量](metrics.md)並[查看和建立維度](dimensions.md)。

   :::image type="content" source="media/page-views.png" alt-text="選擇您的報表計量。":::

1. 請選取 **視覺效果編輯器** 窗格的 **設計** 區段新增 **標題文字** 並切換 **標題** 開啟或關閉。  您也可以選取另一張圖表變更視覺效果類型，例如 **圓形圖**。

1. 若要變更視覺化效果的大小與位置：
   - 選取視覺效果，然後拖曳其中一角或邊框來調整其大小。
   - 選取視覺效果，並將它移至新的位置。 您也可以使用方向鍵來變更位置。
1. 若要新增另一個視覺效果，請選取命令列中的 **新增視覺效果**。
1. 在新增好您想要放在報表上的視覺效果後，請選取命令列中的 **儲存**。

1. 提供一個名稱給自訂報表，並選取 **儲存** 以建立該報表。
 
## <a name="filter-a-custom-report"></a>篩選自訂報表

您可以選取自訂報表中的時間範圍或日期範圍，將焦點放在值或時段。

若要選取時間框，請在報表檢視的右上角從報表的下拉式清單選取值。 您也可以選擇**固定日期範圍*。

:::image type="content" source="media/filter-time-date-range.png" alt-text="依時間或日期範圍篩選。":::

如果是大部分報表，請選取 **+ 新增條件**，以便選擇要篩選報表的維度或區段。 如需詳細資訊，請參閱[查看和建立區段](segments.md)。

## <a name="edit-a-custom-report"></a>編輯自訂報表

1. 移至 **分析** > **自訂** 以存取自訂報表清單。

1. 在自訂報表清單中，選取 **其他 [...]** 

1. 選擇 **編輯名稱** 變更報表的名稱。

1. 選取報表的名稱，並使用 **+ 新增視覺效果** 和 **編輯** 選項來新增、移除、重新放置或調整視覺效果的大小。

1. 若要變更視覺化效果屬性，請選取視覺物件，選取 **...**，然後 **編輯視覺效果**。

   :::image type="content" source="media/edit-visual-control.png" alt-text="編輯自訂報表的圖表屬性。":::

1. 報表編輯完成後，選取 **儲存** 以套用您的變更。 

## <a name="delete-a-custom-report"></a>刪除一個自訂報表

1. 移至 **分析** > **自訂** 以存取自訂報表清單。

1. 在自訂報表清單中，選取 **...**

1. 選擇 **刪除** 來移除報表。

1. 確認您的刪除以永久移除該報表。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
