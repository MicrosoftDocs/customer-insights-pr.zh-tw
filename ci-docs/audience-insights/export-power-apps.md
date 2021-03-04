---
title: Power Apps 連接器
description: 連接 Power Apps 和 Power Automate。
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268906"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps 連接器 (預覽)

透過 Power Apps 將統整的客戶設定檔帶入您的個人化應用程式。

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>連接 Power Apps 和 Dynamics 365 Customer Insights

Customer Insights 是 [Power Apps 中許多可用資料來源](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources)之一。

請參閱 Power Apps 文件，了解如何[將資料連線新增至應用程式](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection)。 建議您另外檢閱 [Power Apps 如何使用委派來處理畫布應用程式中的大型資料集](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview)。

## <a name="available-entities"></a>可用的實體

將 Customer Insights 新增為資料連線之後，您可以在 Power Apps 中選擇下列實體：

- 客戶：使用[統整客戶設定檔](customer-profiles.md)中的資料。
- 統整的活動：在應用程式上顯示[活動時間表](activities.md)。

## <a name="limitations"></a>限制

### <a name="retrievable-entities"></a>可擷取的實體

您只能透過 Power Apps 連接器擷取 **客戶**、**UnifiedActivity** 和 **客戶細分** 實體。 顯示其他實體，因為基礎連接器會透過 Power Automate 中的觸發程序支援這些實體。  

### <a name="delegation"></a>委派

委派適用於客戶實體和 UnifiedActivity 實體。 

- **客戶** 實體的委派：若要使用此實體的委派，必須在 [搜尋 & 篩選條件索引](search-filter-index.md) 中編製欄位索引。  

- **UnifiedActivity** 的委派：此實體的委派僅適用於 **ActivityId** 和 **CustomerId** 欄位。  

- 如需委派的詳細資訊，請參閱 [Power Apps 可委派的函數和作業](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps)。 

## <a name="example-gallery-control"></a>範例庫控制項

例如，您將客戶設定檔新增到 [資源庫控制項](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery)。

1. 將 **資源庫** 控制項新增至您要建立的應用程式。

> [!div class="mx-imgBorder"]
> ![新增資源庫元素](media/connector-powerapps9.png "新增資源庫元素")

1. 選取 **客戶** 做為項目的資料來源。

    > [!div class="mx-imgBorder"]
    > ![選取資料來源](media/choose-datasource-powerapps.png "選取資料來源")

1. 您可以在右邊變更資料面板，以選取要在資源庫上顯示之客戶實體欄位。

1. 如果您想要在資源庫中顯示所選客戶的任何欄位，請填入標籤的 Text 屬性：**{Name_of_the_gallery}.Selected.{property_name}**

    範例：Gallery1.Selected.address1_city

1. 若要顯示客戶的統整時間表，請新增資源庫元素，並新增 Items 屬性：**Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    範例：Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]