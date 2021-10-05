---
title: 漏斗圖報表
description: 如何使用漏斗圖報表來瞭解對象如何進行決策。
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: efb10f2664630a5851d9582ff09c378c01777b96
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558803"
---
# <a name="create-and-manage-funnel-reports"></a>建立及管理漏斗圖報表

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

漏斗報表會從您的網站或行動應用程式收集客戶旅程期間的步驟資訊。 它可協助您透過程式瞭解對象的進程，並找出落點。 例如，您可以使用漏斗圖報表，找出客戶在購買之前經過的路徑。 漏斗圖報表提供要通知決策者的資料，並找出要優化和改善程式的區域。

## <a name="create-a-funnel-report"></a>建立漏斗圖報表

若要建立漏斗圖報表，請指定要包括在內的所有步驟以及每一步要進行的活動。 活動是代表使用者行為的[事件](glossary.md)。 漏斗圖報表會顯示完成每個已定義步驟的使用者數目。 

1. 移至 **漏斗圖**，選取 **新漏斗圖** 以開始建立新的漏斗圖報表。

1. 在 **漏斗圖編輯器** 中，在 **步驟** 底下，選取 **新增步驟**。 

1. 在 **步驟標題** 中輸入名稱。

   :::image type="content" source="media/new-funnel-report.png" alt-text="新增漏斗圖報表。":::

1. 選取 **活動**。 活動會在使用者查看頁面（**查看** 活動）或與內容互動時（**動作** 活動）進行記錄。

1. 使用 **步驟準則** 來指定活動的維度。 [維度](dimensions.md)是指可以描述、篩選或歸類資料的屬性。

1. 或者，您可以設定多條件漏斗步驟。 選取 **新增條件** 在步驟中指定更多維度。 其他準則必須使用相同的活動類型。 您可以選擇是否有多個條件以 AND 或 OR 運算子相連。

   :::image type="content" source="media/funnel-add-condition.png" alt-text="漏斗編輯器，顯示步驟設定中包含的多個條件步驟。":::

1. 選取 **新增步驟**，直到完成所有您想加在報表中的步驟。

1. 選取 **儲存**，命名該報表，然後重新 **儲存**。 

### <a name="example-fourth-coffee-company-funnel-report"></a>範例：「第四個咖啡店」的公司漏斗報表

下列案例演示使用漏斗圖報表的一種方式。 「第四個咖啡店」公司的分析員想要瞭解最新訂用費率促銷所造成的影響。 分析員會建立漏斗圖報表來識別客戶的活動。 從客戶進入公司首頁開始，到他們使用訂閱促銷程式碼為止。 分析員會依照下列步驟建立漏斗圖報表：

步驟 1：進入首頁的客戶   
步驟 2：進行購買的客戶   
步驟 3：使用促銷程式碼來取得訂用折扣的使用者   
步驟 4：註冊訂用   

:::image type="content" source="media/funnel-report-example.png" alt-text="漏斗圖報表範例。":::
  
這張漏斗圖可讓您看到在單次購買後，使用促銷程式碼註冊訂用程式的使用者數目。

### <a name="configure-advanced-settings"></a>設定進階設定 

漏斗報表可讓您定義完成漏斗的時間限制。 例如，您可以設定完成漏斗的時間為四天。 此設定只會統計在使用者造訪首頁後四天內發生的成功訂閱註冊。

1. 移至 **漏斗圖**，以打開 **漏斗圖程式庫**。

1. 選取一個報表名稱以開啟。 

1. 在 **漏斗編輯器** 窗格中，選取 **進階設定**。 

1. 設定限制漏斗圖完成時間為 **啟動**。

   :::image type="content" source="media/funnel-limit-time.png" alt-text="漏斗編輯器顯示限制完成漏斗時間的進階設定和選項。":::

1. 在 **將限制設定為** 下拉式清單中，選擇必須完成漏斗的時間。

1. 選取 **儲存** 套用變更。


## <a name="cross-channel-funnel-reports"></a>交叉通道漏斗報表 

參與度見解也可收集行動裝置應用程式的客戶行為資料。 在您使用參與度見解 [Android SDK](get-started-android.md) 或[ iOS SDK](get-started-ios.md) 為您的行動裝置應用程式完成檢測之後，您就可以建立交叉通道漏斗報表。 

### <a name="create-a-cross-channel-funnel-report"></a>建立交叉通道漏斗報表 

1. 依照這些步驟來[建立漏斗報表](#create-a-funnel-report)。    

1. 若要追蹤您的客戶如何透過您的網站和行動裝置應用程式或多個網站與您的品牌互動，請使用工作區切換器，從其他工作區中的資料建立漏斗步驟。 在 **漏斗編輯器** 的 **步驟** 底下，選取漏斗步驟的資料來自哪個工作區。

## <a name="manage-funnel-reports"></a>管理漏斗圖報表

您可以檢閱漏斗圖報表，以分析資料、追蹤效能以及蒐集見解。

> [!NOTE]
> - 業務開發見解漏斗圖報表目前支援這樣的案例：漏斗圖中的所有使用者都是匿名的，或所有使用者均已通過驗證。 
> - 漏斗圖報表中的歷史資料在 30 天皆可進行查閱。

### <a name="view-funnel-reports"></a>檢視漏斗圖報表

1. 移至 **漏斗圖**，以打開 **漏斗圖程式庫**。
1. 選取一個報表名稱以開啟。    

### <a name="see-the-data-collected-for-a-report"></a>查看報表所收集的資料   

若要查看有關階段的資訊

- 請指向報表中的步驟。

:::image type="content" source="media/funnel-step-data.png" alt-text="漏斗圖資料。":::

### <a name="change-the-date-range-for-the-funnel-report"></a>變更漏斗圖報表的日期範圍

1. 移至 **漏斗圖**，以打開 **漏斗圖程式庫**。

1. 選取一個報表名稱以開啟。

1. 打開 **時間範圍**，並從清單或 **固定日期範圍** 中選取新的時段，以指定日期範圍。

## <a name="edit-or-delete-funnel-reports"></a>編輯或刪除漏斗圖報表

您可以變更漏斗圖報表的名稱、刪除漏斗圖或修改報表中的步驟。

### <a name="rename-or-delete-a-funnel-report"></a>重新命名或刪除漏斗圖報表

1. 移至 **漏斗圖**，以打開 **漏斗圖程式庫**。 

1. 在您想要變更的報表旁邊選取 **更多**，然後選擇 **編輯名稱** 或 **刪除**。

### <a name="edit-a-funnel-step"></a>編輯漏斗圖步驟  

1. 移至 **漏斗圖**，以打開 **漏斗圖程式庫**。 

1. 選取一個報表名稱以開啟。

1. 選取您要編輯的步驟。

1. 選取 **編輯**。

1. 在 **漏斗圖編輯器** 中，更新想要變更的資訊。  

1. 選取 **儲存**。

### <a name="reorder-a-funnel-step"></a>重新排列漏斗圖步驟的順序

1. 移至 **漏斗圖**，以打開 **漏斗圖程式庫**。 

1. 選取一個報表名稱以開啟。

1. 選取您要重新排序的步驟。

1. 選取 **移動**，然後選 **向上**、**向下**、**置頂** 或 **移到底端** 來移動步驟。

### <a name="delete-a-funnel-step"></a>刪除漏斗圖步驟

1. 移至 **漏斗圖**，以打開 **漏斗圖程式庫**。 

1. 選取一個報表名稱以開啟。

1. 選取您要移除的步驟，然後選取 **移除**。

## <a name="funnel-insights"></a>漏斗圖見解 

參與見解現在提供客戶的漏斗圖見解。 使用漏斗圖見解，深入瞭解客戶在漏斗圖報表中各步驟的行為。 當您建立並儲存新的漏斗圖報表時，會為您的報表自動生成漏斗圖見解。 

:::image type="content" source="media/funnel-insights.png" alt-text="漏斗圖見解。":::

> [!NOTE]
> 只能為 **不** 包括自訂維度的漏斗圖步驟生成漏斗圖見解。 若要為漏斗圖中的所有步驟建立漏斗圖見解，請使用參與見解的現成維度來建立您的漏斗圖步驟。 

您可以從下列類別，從主要等級和步驟等級查看漏斗圖見解： 

 - 轉換率
 -    結帳和購買間的轉換率為 22%。
 - 轉換時間 
 -    購物車和結帳處之間的平均轉換時間為 23 分鐘。 
 - 完成時間 
 -    客戶完成漏斗圖所花費的平均時間量為 47 分鐘。 

您可以使用這些見解深入探索客戶行為，並更清楚地瞭解漏斗圖報表的暫時擱置點和轉換。 

若要比較不同步驟的見解，請從見解卡片選取 **查看步驟明細** 或 **比較其他步驟**。 這些將顯示柱狀圖來比對漏斗各步驟的計量。 

每隔 24 小時漏斗圖見解會重新計算一次，以及在您 **儲存** 漏斗圖報表時進行重新計算。 

> [!NOTE]
> 若要查看漏斗圖的見解，必須在每次變更報表時，儲存報表。 

