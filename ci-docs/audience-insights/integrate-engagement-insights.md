---
title: 將參與度見解的網頁數據和對象見解的整合
description: 將參與度見解中有關客戶的網站資訊匯入對象見解中。
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2789a7d1379e0cf56511b272a763c904d8a3d347058ea9e029aaff0f723a028
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033759"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>將參與度見解的網頁數據和對象見解的整合

客戶通常會使用網站來線上進行日常交易。 Dynamics 365 Customer Insights 中的參與度見解 (預覽版) 功能是將 Web 資料整合為來源的便捷解決方案。 除了交易、人口統計或行為資料之外，我們還可以在整合客戶設定檔中查看網頁上的活動。 我們可以使用這些個人資料來取得對象啟用的其他見解，例如分客戶細分、量值或預測。

本文說明將客戶網路活動資料從參與度見解移至現有對象見解環境的步驟。

在此範例中，我們假設有一個包含整合客戶設定檔的環境。 設定檔已經與調查、零售和票證系統的來源進行整合。 它也會顯示客戶的相關活動。 

我們現在希望知道客戶是否拜訪我們的 web 資源並瞭解他們的活動。 活動包括如訪問網站或在電子郵件中從收到的連結查看的產品頁面。

## <a name="prerequisites"></a>先決條件

若要整合參與度見解的資料，則需要符合幾個必要的先決條件： 

- 整合參與度見解 SDK 與您的網站。 如需詳細資訊，請參閱[開發人員資源概觀](../engagement-insights/developer-resources.md)。
- 從參與度見解匯出 Web 事件需要存取 Azure Data Lake Storage 帳戶，該帳戶可以將 Web 事件資料擷取至對象見解。 如需詳細資訊，請參閱 [匯出事件](../engagement-insights/export-events.md)。

## <a name="configure-refined-events-in-engagement-insights"></a>在參與度見解中設定精簡事件

系統管理員使用參與度見解 SDK 檢測網站之後，當使用者查看網頁或按一下其中一個地方時，就會收集 *基準事件*。 基本事件往往包含許多詳細資料。 根據您的使用案例，您只需要基本事件中的一部分資料。 參與度見解可讓您建立 *精簡事件*，其中僅包含選取的基準事件屬性。     

如需詳細資訊，請參閱[建立和修改精簡事件](../engagement-insights/refined-events.md)。

建立精簡事件時的考量： 

- 為精簡事件提供有意義的名稱。 在對象見解中，它會被用作活動名稱。
- 至少選取下列屬性，建立對象見解中的活動： 
    - Signal.Action.Name –表示活動詳細資料。
    - Signal.User.Id – 用於對應客戶識別碼。
    - Signal.View.Uri – 當成網址使用，作為客戶細分或量值的基礎。
    - Signal.Export.Id – 當作事件的主索引鍵。
    - Signal.Timestamp – 辨識活動的日期與時間。

選取篩選，專注在對使用案例重要的事件和頁面上。 在此範例中，我們將使用「電子郵件促銷」動作名稱。

## <a name="export-the-refined-web-events"></a>匯出精簡 Web 事件 

定義精簡事件之後，您必須設定將事件資料匯出至 Azure Data Lake Storage，並在對象見解中將其設定為資料來源進行擷取。 作為事件流程，來自 web 屬性的匯出持續發生。

如需詳細資訊，請參閱 [匯出事件](../engagement-insights/export-events.md)。

## <a name="ingest-event-data-to-audience-insights"></a>內嵌事件資料到觀眾見解中

現在您已定義好精簡事件並設定其匯出，我們開始內嵌資料到觀眾見解。 您需要依照 Common Data Model 資料夾建立新的資料來源。 輸入有關事件匯進的儲存體帳戶的詳細資料。 在 *default.cdm.json* 檔案中，選取要內嵌的精簡事件並在對象見解中建立實體。

如需詳細資訊，請參閱[使用 Azure Data Lake 帳戶連接至 Common Data Model 資料夾](connect-common-data-model.md)。


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>將精簡事件資料關聯成客戶設定檔的活動

完成實體內嵌之後，您可以為客戶設定檔設定活動。

如需詳細資訊，請參閱[客戶活動](activities.md)。

:::image type="content" source="media/web-event-activity.png" alt-text="已展開編輯活動窗格並完成欄位填入的活動頁面。":::

使用下列對應設定新活動： 

- **主索引鍵**：Signal.Export.Id，即參與度見解中每個事件記錄可用的唯一識別碼。 此屬性是自動生成的。

- **時間戳記**：事件屬性中的 Signal.Timestamp。

- **事件**：Signal.Name，您想要追蹤的事件名稱。

- **網址**：Signal.View.Uri，參照建立事件的頁面的 URI。

- **詳細資料**：Signal.Action.Name，顯示與事件有關的資訊。 在此案例中，選取的屬性標示這是電子郵件促銷的事件。

- **活動類型**：在此範例中，我們選擇現有的活動類型 Weblog。 要依據此活動類型執行預測模型或建立客戶細分，這是一項非常實用的篩選選項。

- **設定關聯**：這項重要設定會將活動與現有的客戶個人資料繫結。 **Signal.User.Id** 是在 SDK 中設定好用來收集的識別碼，且與對象見解中設定的其他資料來源其使用者識別碼相關。 在此範例中，我們會設定 Signal.User.Id 與 RetailCustomers:CustomerRetailId 之間的關聯，這是資料整合程序的對應步驟中識別的主索引鍵。

處理活動後，您可以查看客戶記錄並打開客戶卡，便能在時間表中查看參與度見解的活動。 

> [!TIP]
> 若要尋找具有參與度見解活動的客戶識別碼，請移至 **實體**，並預覽 UnifiedActivity 實體的資料。 ActivityTypeDisplay = WebLog 包含上述範例中設定的參與度見解活動。 複製其中一個記錄客戶的識別碼並在 **客戶** 頁面上給出該識別碼。

## <a name="next-steps"></a>後續步驟

您現在可以建立[客戶細分](segments.md)、[量值](measures.md)和 [預測](predictions.md)，讓與您的客戶有意義的連結。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
