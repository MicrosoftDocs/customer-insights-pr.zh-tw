---
title: 檢視和建立維度
description: 如何建立、編輯及刪除維度。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623622"
---
# <a name="view-and-create-dimensions"></a>檢視和建立維度

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

維度是事件的屬性，可以描述、篩選或分組資料。 如果您正在網站上執行行銷宣傳，您可以使用維度，依據新的和回訪的使用者來分類訪客。  

Engagement見解包括對事件屬性的開箱即用 (OOB) 維度。 例如：

- 瀏覽器名稱
- 頁面名稱
- 裝置模型
- 作業系統
- 國家/地區

## <a name="view-dimensions"></a>查看維度

維度是根據現有的事件屬性而定。 使用參與見解的追蹤程式碼時，會自動建立系統維度。

1. 在左導覽窗格中，移至 **資料**。 
1. 選取 **維度** 以查看工作區中所有維度的清單。 
   > [!NOTE]
   > 系統生成的維度是唯讀的。 您無法進行編輯。 您只能建立和編輯自訂維度。

## <a name="create-a-dimension"></a>建立維度

除了系統生成的維度之外，環境和工作區系統管理員也可以建立自訂維度。 根據基準事件的預設屬性，或是它們可以使用[事件的自訂屬性](advanced-SDK-implementation.md)來自訂維度。

1. 移至 **資料** > **維度**。
1. 選取 **新增維度**。

   :::image type="content" source="media/add-dimension.png" alt-text="新增事件的維度。":::

1. 在 **建立維度** 窗格中，選取維度要依據的屬性。 屬性清單將顯示在工作區中所有尚未指派至維度的屬性。
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="建立新維度。":::
      
3. 在 **函數名稱** 方塊中輸入函數名稱。 或者您可以選擇新增 **說明**。
4. 選取 **建立流程** 以儲存維度。 在[自訂報表](custom-reports.md)或[客戶細分](segments.md)中使用此維度之前，可能需要一分鐘的時間。 

## <a name="edit-a-dimension"></a>編輯維度

您可以變更維度的名稱與說明。 您只能編輯使用者建立的維度，但不可以編輯系統維度。


1. 移至 **資料** > **維度**。
1. 選取您要刪除的維度。
1. 在 **編輯維度** 窗格中，更新維度。
1. 選取 **套用** 儲存變更。

## <a name="delete-a-dimension"></a>刪除維度

您只能刪除使用者建立的維度，但是不可以移除系統維度。

刪除維度是永久性的。 使用已刪除維度的報表和段落將無法運作。 

1. 移至 **資料** > **維度**。
1. 選取您要刪除的維度。
1. 在 **編輯維度** 窗格中，選取 **刪除維度**。

   :::image type="content" source="media/delete-dimension.png" alt-text="刪除事件的維度。":::

1. 輸入 **CONFIRM DELETE** (全部大寫) 以確認刪除。 
1. 選取 **刪除**。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
