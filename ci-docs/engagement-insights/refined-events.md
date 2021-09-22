---
title: 建立及修改精簡事件
description: 如何建立及修改精簡事件。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034764"
---
# <a name="create-and-modify-refined-events"></a>建立及修改精簡事件

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


事件是代表使用者行為的資料，類似於網站上的活動。

- *基礎* 事件會在使用者查看頁面（查看事件）或與內容互動（動作事件）時進行記錄。
- *精簡* 事件是基礎事件的虛擬視圖。 您可以藉由移除和新增屬性，或根據屬性值篩選事件，來定義精簡事件。

使用精簡事件來減少要[匯出](export-events.md) 的基礎事件範圍，或移除不需要曝光的屬性。

## <a name="create-refined-events"></a>建立精修的事件

有三種方法可以從基礎事件建立精簡事件。 

1. 移至 **資料**> **事件**，然後選擇下列其中一個選項：
    - 選取 **新增事件**，然後選取 **建立精簡事件**。
    - 選取一個基礎事件以打開詳細的視圖，並從頂端功能表選取 **建立精簡事件**。
    - 選取 **其他 [...]** 以打開基礎事件的捷徑功能表。 然後選取 **建立精簡事件**。
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="建立精簡事件的選項。":::

1. 在 **建立精簡事件** 對話方塊中，輸入下列資訊：

- 若要建立新的活動，請從 **基礎事件** 下拉式選單中選取一個事件。
- 在 **精簡事件顯示名稱** 方塊中輸入名稱。
- （可選）更新建議的 **實際名稱** 而非使用空格。

3. 選取 **建立** 以套用您的設定。

1. 在精簡事件的詳細視圖中，選取 **新增和移除屬性** 來打開 **編輯屬性** 窗格。 

1. 使用核取方塊來選取想要顯示和隱藏的屬性。 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="編輯精簡事件的屬性。":::

1. 選取 **確認** 以套用您的選取。

1. 選取 **儲存** 以儲存設定。

## <a name="edit-refined-events"></a>編輯精簡事件

您可以變更精簡事件的名稱與屬性。

### <a name="edit-event-name"></a>編輯事件名稱

1. 移至 **資料** > **事件**。 
1. 選取事件的 **其他 [...]**，然後選取 **編輯名稱**。
1. 更新事件名稱，然後選取 **重新命名**。

### <a name="edit-selected-properties"></a>編輯已選取的屬性

1. 移至 **資料** > **事件**，並選取精簡事件，以打開詳細的視圖。
1. 選取 **新增和移除屬性**。 
1. 編輯選取的核取方塊。
1. 選取 **確認**，然後按一下 **儲存** 來套用變更。

如需有關匯出事件的詳細資訊，請參閱[匯出事件](export-events.md)。
[!INCLUDE[footer-include](../includes/footer-banner.md)]
