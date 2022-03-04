---
title: 建立和修改事件
description: 建立及修改事件的方式。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228193"
---
# <a name="create-and-modify-events"></a>建立和修改事件

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

事件是代表使用者行為的資料，類似於網站上的活動。

- *基礎* 事件會在使用者查看頁面（查看事件）或與內容互動（動作事件）時進行記錄。
- *精簡* 事件是基礎事件的虛擬視圖。 您可以藉由移除和新增屬性，或根據屬性值篩選事件，來定義精簡事件。

## <a name="prerequisites"></a>先決條件

若要取得事件，您必須先使用程式碼片段將您的網站資料連接業務開發見解。 如需更多資訊，請參閱[在網站上安裝網頁 SDK](instrument-website.md)。

 :::image type="content" source="media/new-events-connect-data.png" alt-text="先連接您的資料。":::

## <a name="create-refined-events"></a>建立精簡事件

使用精簡事件來減少要[匯出](export-events.md) 的基礎事件範圍，或移除不需要曝光的屬性。

> [!NOTE]
> 一旦您將 Web SDK 新增到您的網站，您就能檢視基準事件並建立細緻事件。 

若要檢視您的基準事件：

1. 在左導覽窗格中，移至 **資料**。

1. 請選取 **事件** 查看工作區中所有事件的清單。

    :::image type="content" source="media/data-events.png" alt-text="檢視事件。":::

若要從基準事件建立精緻事件： 

1. 請前往 **資料** > **事件**，並在畫面頂端選取 **+ 新事件**。

1. 請在 **新事件** 對話方塊中選取 **建立精緻事件** 和 **下一步**。
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="新事件精靈。":::
     
1. 請在 **新事件** 對話方塊輸入下列資訊：

   - 請從 **基準事件** 下拉式清單選取某事件。
   - 在 **精簡事件顯示名稱** 方塊中輸入名稱。
   - （可選）更新建議的 **實際名稱** 而非使用空格。

1. 選取 **建立** 以套用您的設定。

精緻事件現在會出現在您的 **事件** 清單。

### <a name="edit-event-name"></a>編輯事件名稱

您可以變更基準或精緻事件的名稱與屬性。

1. 移至 **資料** > **事件**。 

1. 選取事件的 **其他 [...]**，然後選取 **編輯名稱**。
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="建立精簡事件的選項。":::

3. 更新事件名稱，然後選取 **重新命名**。

### <a name="view-the-details-of-a-refined-event"></a>檢視精緻事件的詳細資料：

1. 請在 **事件** 清單中選取您的基準或精緻事件。 

1. 請選取畫面上方的 **新增和移除屬性** 打開 **編輯屬性** 窗格。 

     :::image type="content" source="media/add-remove-properties.png" alt-text="新增和移除屬性。":::

1. 使用核取方塊來選取想要顯示和隱藏的屬性。 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="編輯精簡事件的屬性。":::

1. 請選取 **確認** 套用您的選取，接著選取 **儲存**。


### <a name="edit-selected-properties-for-a-refined-event"></a>編輯精緻事件的選取屬性

1. 移至 **資料** > **事件**，並選取精簡事件，以打開詳細的視圖。
1. 選取 **新增和移除屬性**。 
1. 編輯選取的核取方塊。
1. 選取 **確認**，然後按一下 **儲存** 來套用變更。

如需有關匯出事件的詳細資訊，請參閱[匯出事件](export-events.md)。
[!INCLUDE[footer-include](../includes/footer-banner.md)]
