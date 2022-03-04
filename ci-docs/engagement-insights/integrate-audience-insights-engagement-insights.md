---
title: 建立對象見解與參與見解之間的連結
description: 在對象見解與參與見解之間建立有效連結，啟用雙向共用資料。
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229862"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>建立對象見解與參與見解之間的連結

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

參與見解與對象見解之間的整合連結兩項功能的環境，並在它們之間雙向共用資料。

請使用對象見解中的整合個人資料和客戶細分，在參與見解中取得更多分析選項。 從參與見解中匯出有高商務價值的事件。 您可以使用這些事件，在對象見解中將資料新增至整合個人資料。

## <a name="prerequisites"></a>先決條件

- 對象見解個人資料必須儲存您在 Azure Data Lake Storage的帳戶或儲存在 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash;受管理的 Data Lake 中。 
- 此外，您的對象見解環境應具有關聯的 Dataverse 環境。 此外，如果該環境也是用 Dataverse 儲存資料，請確認您已在對象見解中核取 **啟用資料共用** 選項。 如需詳細資訊，請參閱[在對象見解中建立與組態環境](../audience-insights/create-environment.md)。
- 您需要參與見解和對象見解所在環境的系統管理員權限。
- 連結的環境必須位於相同的地理區域。

> [!NOTE]
> - 如果您的對象見解訂閱是使用對象見解內受管理的 Data Lake 的試用版，請與取得 [pirequest@microsoft.com](mailto:pirequest@microsoft.com)協助。 
> - 如果您的對象見解環境使用您自己的 Azure Data Lake Storage 來儲存資料，您需要將參與見解 Azure 服務主體新增至您的儲存帳戶。 如需詳細資訊，請移至[以 Azure 服務主體建立 Azure Data Lake Storage帳戶來使用對象見解](../audience-insights/connect-service-principal.md)。 


## <a name="create-an-environment-link"></a>建立環境連結

您可以透過更新參與見解中的 **管理** > **環境** 設定，建立環境連結。

**建立對象見解與參與見解之間的有效連結**

1. 在 **環境管理** 頁面上，選取 **連結環境** 索引標籤。

    :::image type="content" source="media/integrate1.png" alt-text="設定環境。":::

1. 在畫面左上角或畫面底部選取 **設定環境**。

     :::image type="content" source="media/integrate2.png" alt-text="選取一個對象見解環境。":::

1. 選取對象見解環境，然後選取 **下一步** 來完成。 現在您可以選取連結環境的選擇性功能。
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>啟用對象見解整合個人資料屬性和客戶細分

在連結環境後，您可以選取連結環境的選擇性功能。 這些功能讓對象見解中的整合個人資料屬性和客戶細分，可以在客戶資料進行互動式分析。

> [!IMPORTANT]
> 若要讓對象見解客戶細分顯示在參與見解中，您必須先[執行合併和下游處理](../audience-insights/merge-entities.md)。 下游程序很重要，因為它們會生成唯一的資料表，以準備要與參與見解共用的對象見解客戶細分。 (如果已排程系統重新整理，則會自動包括下游程序。)

**分析參與見解中的 Web 資料**

1. 在 **環境管理** 頁面上，打開 **對參與見解共用來自觀眾見解的資料**，然後選取 **下一步**。

    :::image type="content" source="media/integrate4.png" alt-text="選取功能。":::

1. 選取將在參與見解中成為維度的整合個人資料屬性。 (並非所有屬性都是有用的維度。 例如，您不太可能需要 **名字** 或 **姓氏** 做為用來分析您的網站事件的屬性。)

    :::image type="content" source="media/integrate5.png" alt-text="策劃維度。":::

   >[!NOTE]
   > 所有對象見解中代表識別碼的個人資料屬性 (如 **識別碼** 和 **替代識別碼**) 都會從可用屬性中篩選出，並成為參與見解中的維度。

1. 當您完成選取屬性後，請選取 **下一步**。
1. 新增可在參與見解中查看對象見解個人資料維度和客戶細分的使用者。

    :::image type="content" source="media/integrate6.png" alt-text="管理對客戶資料的存取權。":::

   > [!IMPORTANT]
   > 如果在此步驟中未明確新增使用者，則參與見解中的使用者將無法看見資料。
   > 若要讓對象見解客戶細分顯示在參與見解中，您必須先[執行合併和下游處理](../audience-insights/merge-entities.md)。 下游程序很重要，因為它們會生成唯一的資料表，以準備要與參與見解共用的對象見解客戶細分。 (如果已排程系統重新整理，則會自動包括下游程序。)

1. 檢閱選取的項目，然後按一下 **完成**。

    :::image type="content" source="media/integrate7.png" alt-text="檢閱客戶資料設定。":::

## <a name="export-refined-events-to-audience-insights"></a>匯出精簡事件到對象見解

在環境間建立連結之後，您可以將精簡事件從參與見解匯出到對象見解，並當作新的資料來源進行內嵌。 

如需詳細資訊，請移至[整合參與見解的 web 資料到對象見解](../audience-insights/integrate-engagement-insights.md)。

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
