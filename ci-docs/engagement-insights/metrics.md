---
title: 檢視和建立計量
description: 如何建立和編輯和刪除計量。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 79600a14bc7e98dfd066270f19c353fd007e1341
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623712"
---
# <a name="view-and-create-metrics"></a>檢視和建立計量

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

計量可協助您了解訪客的行為。 它們會彙總事件屬性，並測量 web 屬性的統計資料與效能。  

假設您正在您的網站上執行行銷宣傳活動。 您可以使用計量來追蹤在促銷期間來訪的不重複訪客或使用者數量。 分析計量可協助您更好地了解網站的受眾。 在[自訂報表](custom-reports.md)上將計量與[維度](dimensions.md)相結合，可讓您測量行為，瞭解您的使用者。 例如，您可以將訪客分隔成新的和返回的類別，以找出族群在興趣和意圖的差異。

## <a name="view-metrics"></a>檢視計量

參與見解包括常用事件屬性彙整作為系統計量： 

- 訪客
- 瀏覽次數
- 頁面檢視數
- 點選數

這些系統計量是根據基本事件中的現有事件屬性而定。

1. 在左導覽窗格中，移至 **資料**。 
1. 選取 **計量** 索引標籤，以查看工作區中所有計量的清單。 
   > [!NOTE]
   > 系統生成的計量是唯讀的。 您無法編輯或刪除它們。 您只能建立及編輯自訂計量。

## <a name="create-a-metric"></a>建立計量

環境和工作區系統管理員可以建立計量。 在建立計量之前，必須將事件屬性傳送至工作區。 根據基本事件傳送的事件屬性或使用 web SDK [傳送自訂事件屬性](advanced-SDK-implementation.md)，您可以建立計量。

1. 移至 **資料** > **計量**。
1. 請選取 **新計量** 打開 **資源庫** 和 **未命名的新計量** 對話方塊。

   :::image type="content" source="media/new-metric.png" alt-text="新增計量到事件中。":::

1. 請在 **未命名的新計量** 對話方塊中選取 **格式** 下拉式清單，並選擇 **整數** 或 **倍精度浮點數** 資料類型。 整數即為無小數點整數。 倍精度浮點數方面，您可以選擇小數點後一位和三位。

   :::image type="content" source="media/create-new-metric.png" alt-text="建立新計量。":::
   
5. 請在 **資源庫** 窗格中尋找計量要依據的事件屬性。
6. 選取屬性旁邊的 **加號 (+)**，以在公式中使用它。 您只能依據一個屬性來建立公式。 
7. 選擇下列其中一組彙整函數。 

   - 總和：所有值的算術總計 
   - 平均值：所有值的平均值
   - 計數：值的總數
   - 相異計數：相異值的總數

   在定義計量之後，您會看到計量在最近一小時的活動預覽。

1. 選取 **儲存**。 
1. 輸入計量的名稱，然後選取 **儲存**。

在您用它來[建立自訂報表之前](custom-reports.md)，最多需要一分鐘的時間。

## <a name="edit-a-metric"></a>編輯計量

您只能編輯自訂的計量。

1. 移至 **資料** > **計量**。
1. 選取清單中的計量。
1. 變更計量的定義
1. 選取 **儲存**。

## <a name="change-the-name-of-a-metric"></a>變更計量的名稱

您只能變更自訂計量的名稱。

1. 移至 **資料** > **計量**。
1. 對計量選取 **更多 [...]**，然後選擇 **編輯名稱**。
1. 變更名稱。 
1. 選取 **重新命名**。

## <a name="delete-a-metric"></a>刪除計量

您只能刪除自訂的計量。

1. 移至 **資料** > **計量**。
1. 對計量選取 **更多 [...]**，然後選擇 **刪除**。

   :::image type="content" source="media/delete-metric.png" alt-text="刪除事件中的計量。":::

1. 請選取 **刪除**，以確認刪除。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
