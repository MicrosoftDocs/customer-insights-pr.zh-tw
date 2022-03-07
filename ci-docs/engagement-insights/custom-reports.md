---
title: 關於自訂報表
description: 學習如何建立自訂報表。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2540221710786dc1c84b231fbb23b9749b601cc6a2aeb78614e16002302a80a9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036953"
---
# <a name="create-and-edit-custom-reports"></a>建立與編輯自訂報表

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

除了隨拆即用的報表外，您還可以建立含有圖表和表格視覺效果的自訂報表，以協助您瞭解使用者行為。 本文解釋如何使用表格和圖表視覺效果，建立包含所需資料的報表。 

## <a name="create-a-custom-report"></a>建立一個自訂報表

1. 移至 **分析** > **自訂** 以存取自訂報表清單。

1. 選取 **新報表** 來開始建立自訂報表。

   :::image type="content" source="media/new-custom-report.png" alt-text="新的自訂報表。":::

1. 決定您想要建立的報表類型：

    - 在命令列中選取 **新增視覺效果**，以建立預設的表格視覺效果。
    - 或者，從 **報表編輯器** 窗格中選取柱狀圖、條形圖、折線圖、區域、圓形圖、環形或表格視覺效果。

1. 在 **資料** 窗格中，選擇其中一個可用的 **計量**（例如，網頁查看）來顯示。 然後新增要在視覺效果中顯示的 **維度**（例如，國家）。 如需新增其他選項以進行選擇的詳細資訊，請參閱[查看和建立計量](metrics.md)並[查看和建立維度](dimensions.md)。

1. 在 **視覺效果編輯器** 窗格中選取 **設計**，以新增 **標題文字**，並設定 **位置**、**資料標籤** 和 **軸**。  您也可以藉由選取另一種圖表類型來變更視覺效果。

1. 您可以變更視覺效果的大小與位置：
   - 選取視覺效果，然後拖曳其中一角或邊框來調整其大小。
   - 選取視覺效果，並將它移至新的位置。 您也可以使用方向鍵來變更位置。
1. 若要新增另一個視覺效果，請選取命令列中的 **新增視覺效果**。
1. 在新增好您想要放在報表上的視覺效果後，請選取命令列中的 **儲存**。

1. 提供一個名稱給自訂報表，並選取 **儲存** 以建立該報表。
 
## <a name="edit-a-custom-report"></a>編輯自訂報表

1. 移至 **分析** > **自訂** 以存取自訂報表清單。

1. 在自訂報表清單中，選取 **其他 [...]** 

1. 選擇 **編輯詳細資料** 來變更報表的名稱。

1. 選取報表的名稱，並使用 **新增視覺效果** 和 **編輯** 選項來新增、移除、重新置放或調整視覺效果的大小。

1. 若要變更視覺效果的屬性，請選取 **...**，然後選取 **編輯視覺效果**。

   :::image type="content" source="media/edit-visual-control.png" alt-text="編輯自訂報表的圖表屬性。":::

1. 報表編輯完成後，選取 **儲存** 以套用您的變更。 

## <a name="delete-a-custom-report"></a>刪除一個自訂報表

1. 移至 **分析** > **自訂** 以存取自訂報表清單。

1. 在自訂報表清單中，選取 **...**

1. 選擇 **刪除** 來移除報表。

1. 確認您的刪除以永久移除該報表。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
