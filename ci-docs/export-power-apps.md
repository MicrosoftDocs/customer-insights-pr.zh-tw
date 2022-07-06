---
title: Power Apps 連接器 (預覽)
description: 連接 Power Apps 和 Power Automate。
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 0b71f723d1e491d422d24b1be6616d2f33c95d40
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055250"
---
# <a name="power-apps-connector-preview"></a>Power Apps 連接器 (預覽)

透過 Microsoft Power Apps 將統整的客戶設定檔帶入您的個人化應用程式。

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>連接 Power Apps 和 Dynamics 365 Customer Insights

Customer Insights 是 [Power Apps 中許多可用資料來源](/powerapps/maker/canvas-apps/working-with-data-sources)之一。

請參閱 Power Apps 文件，了解如何[將資料連線新增至應用程式](/powerapps/maker/canvas-apps/add-data-connection)。 建議您另外檢閱 [Power Apps 如何使用委派來處理畫布應用程式中的大型資料集](/powerapps/maker/canvas-apps/delegation-overview)。

## <a name="available-entities"></a>可用的實體

將 Customer Insights 新增為資料連線之後，您可以在 Power Apps 中選擇下列實體：

- **客戶**：使用來自[統一客戶設定檔](customer-profiles.md)的資料。
- **UnifiedActivity**：在 App 裡顯示[活動時間表](activities.md)。
- **ContactProfile**：顯示客戶的連絡人。 此實體只能用在 Customer Insights 環境的公司客戶。

## <a name="limitations"></a>限制

### <a name="retrievable-entities"></a>可擷取的實體

您只能透過 Power Apps 連接器檢索 **客戶**、**UnifiedActivity**、**區段** 和 **ContactProfile**。 ContactProfile 只能用在 Customer Insights 執行個體的公司客戶。 顯示其他實體，因為基礎連接器會透過 Power Automate 中的觸發程序支援這些實體。

60 秒最多可以執行 100 個呼叫。 您可以使用 $skip 參數，多次呼叫 API 端點。 [了解 $skip 參數的詳細資訊](/connectors/customerinsights/#get-items-from-an-entity)。

### <a name="delegation"></a>委派

委派適用 **客戶** 實體和 **UnifiedActivity** 實體。 

- **客戶** 實體的委派：若要使用此實體的委派，必須在 [搜尋 & 篩選條件索引](search-filter-index.md) 中編製欄位索引。  
- **UnifiedActivity** 的委派：此實體的委派僅適用於 **ActivityId** 和 **CustomerId** 欄位。  
- ContactProfile 的 **委派**：此實體的委派只適用 **ContactId** 和 **CustomerId** 欄位。 ContactProfile 只能用在Customer Insights 環境的公司客戶。

如需委派的詳細資訊，請前往 [Power Apps 委派功能和作業](/powerapps/maker/canvas-apps/delegation-overview)。 

## <a name="example-gallery-control"></a>範例庫控制項

您可以將客戶設定檔新增到[資源庫控制項](/powerapps/maker/canvas-apps/add-gallery)。

1. 將 **資源庫** 控制項新增到您正在建構的應用程式。

    > [!div class="mx-imgBorder"]
    > ![新增資源庫元素。](media/connector-powerapps9.png "新增資源庫元素。")

2. 選取 **客戶** 做為項目的資料來源。

    > [!div class="mx-imgBorder"]
    > ![選取資料來源。](media/choose-datasource-powerapps.png "選取資料來源。")

3. 您可以在右邊變更資料面板，以選取要在資源庫上顯示之客戶實體欄位。

4. 如果您想要在資源庫顯示選取客戶的任何欄位，請使用 **{Name_of_the_gallery}{property_name}**.Selected. 填入標籤的 **文字** 屬性  
    - 例如：_Gallery1.Selected.address1_city_

5. 若要顯示客戶的統一時間表，請新增資源庫元素和使用 **篩選條件 ('UnifiedActivity', CustomerId = {Customer_Id})** 新增 **項目** 屬性  
    - 例如：_Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
