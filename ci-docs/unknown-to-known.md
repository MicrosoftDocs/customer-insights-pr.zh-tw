---
title: 使用已知和未知使用者的資料個人化您的體驗
description: 當您知道他們的身份時，合併有關以前未知使用者的資訊。
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224285"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>使用已知和未知使用者的資料個人化您的體驗

管理客戶資料並不是一項新挑戰，但隨著使用者瀏覽品牌提供的各種數字管道，變得越來越困難。 如果未登錄，則在一個頻道中已知 (已驗證) 的使用者在另一個頻道中將變為未知 (未驗證)。 問題通常是未經身份驗證 (未知) 的使用者沒有共同的 ID。 這可用於關聯有意義的設定檔文件屬性，並生成統一的客戶設定檔。 Customer Insights 能透過從源系統上的追蹤方法中擷取資料，協助解決此問題。 整合未知和已知設定檔，可為組織提供最新設定檔及其歷史交易、行為和人口統計資料的完整檢視。 甚至更進一步提供身份解析，允許您跨多個管道統一客戶活動，包括您的網站、店內購買、忠誠度計劃等。

## <a name="sample-scenario"></a>範例案例

讓我們想想一間咖啡連鎖店，它擁有廣泛的客戶群，他們會在商店購買咖啡和食品並在線上訂購產品。 通常，線上訪客在瀏覽產品時沒有經過身份驗證，使他們成為「未知使用者」。 如果使用者未知，咖啡連鎖店很難提供個人化的優惠和體驗。 另一方面，客戶可以通過加入忠誠度系統登入他們的帳戶並成為公司的「知名使用者」，從而提供更個人化的體驗。 Customer Insights 可以幫助咖啡連鎖店了解已知和以前未知的使用者。

透過 Customer Insights，公司可以在使用者登入並為人所知後，將客戶檔案與來自未經身份驗證 (未知) 工作階段的活動資料相結合。 咖啡連鎖店可以使用內建連接器將來自其他資料來源的資料引入 Customer Insights，以合併來自各種管道的客戶身份。

## <a name="prerequisites"></a>先決條件

- 收集 Web 資料並包含所有訪客的「訪客 ID」。
- Web 資料包含已登入訪客的「經過身份驗證的使用者 ID」。 這些 ID 與忠誠度系統相關聯。
- 例如「產品檢視」和「結帳」之類的高價值事件資料與事件的時間戳記和事件 ID 一起定義並包含在源資料中。

下表顯示如何擷取高價值 Web 事件的簡化範例。

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|7|07-23-2022 10:00:00|abc123|--|產品檢視|
|2|07-23-2022 10:05:00|abc123|707|Loyalty 登入|
|3|07-23-2022 10:10:00|abc123|707|結帳|
|4|07-23-2022 10:20:00|xyz789|--|產品檢視|

## <a name="data-ingestion"></a>資料擷取

有關客戶的資料可以來自您的網站作為事件資料，並且可以儲存在您自己的內部或第三方資料分析服務中。 如果網站具有與身份驗證服務整合的身份驗證流程，則 Web 資料包含已知和未知使用者。 例如，要求使用者提供完整詳細資訊以完成購買交易的電子商務系統。 或者需要驗證以確認獎勵折扣的有效接收者的忠誠度系統。

上方範例中的事件資料包含已知和未知使用者的不同設定檔 ID。 在事件 1 和 4 中使用者未知，而在事件 2 和 3 中，ID 為 abc123 的使用者註冊了忠誠度計劃。

:::image type="content" source="media/website-data-source.png" alt-text="包括 Contoso 網站在內的資料源。":::

關於資料擷取的可用選項更多資訊，請參閱[資料來源概述](data-sources.md)。

## <a name="data-unification"></a>資料統整

依已知的標識彙聚未知的標識，可協助根據使用者行為啟用個人化功能，不管其設定檔狀態 (已知或未知)。 所有使用者的個人化內容可協助客戶快速取得他們目前感興趣的最相關的產品或服務。

因為我們資料中的部分使用者是已知的，所以我們可以使用 Customer Insights，將這些資料與使用者的設定檔相結合。 如需整合客戶設定檔的詳細資訊，請參閱[資料整合概述](data-unification.md)。

1. 從 Web 資料實體中選擇來源欄位。 使用儲存在 Web 資料中的設定檔資料，並選取代表含人口統計資料之 Ids 的欄位。

   :::image type="content" source="media/website-source-fields.png" alt-text="Web 資料來源的來源欄位。":::

1. 新增規則以合併重複的記錄。 如果是 web 資料，請選擇最完整的資料。

1. 設定比對規則和條件。 此範例中的 web 設定檔事件資料，會與包含客戶資訊之其他資料來源的設定檔在 ID 上進行匹配。 將 IDs 上的完全相符規則設定為不同的規則，以及每個具有對應主鍵或 ID 的其他設定檔實體。 在此範例中，web 事件設定檔資料是用做為最後一個相符的實體，這樣就會先合併其他設定檔資料。
   1. 不檢查 **包括所有記錄** 會建立已知使用者的統一設定檔，並包含其對應的未知使用者 id。 當您想要查看已知使用者仍然未知的先前行為活動時，這是個非常實用的方案。
   1. 勾選 **包括所有記錄** 會為未知使用者建立不同的設定檔記錄。 未知的使用者會取得唯一的客戶 ID。 將來，當已知的個人資料與網路事件個人資料相關聯時，也可以根據過去的未知行為資料查看和使用新知道的使用者旅程進行個人化。

:::image type="content" source="media/website-match-rule.png" alt-text="網站資料來源實體的匹配規則。":::

## <a name="get-insights"></a>取得見解

如果為未知和已知的使用者建立客戶設定檔，則可以使用高價值的 web 事件資料做為 [活動](activities.md)。 這些活動可以用來建立更深入的見解。 例如，六個月前訪問過網站的客戶 (當時他們還不為人所知) 或沒有忠誠度 ID 的客戶從未完成結帳。

:::image type="content" source="media/website-known-unknown.png" alt-text="具有已知和未知客戶的客戶頁面螢幕擷取畫面。":::

[擴充](enrichment-hub.md)您的資料、構建[測量](measures.md)並建立用於進一步啟動的[區段](segments.md)。

例如，您可以建立有查看某些產品但尚未完成簽出的已知使用者區段。

如需詳細資訊，請查看[區段總覽](segments.md)。

## <a name="activate-insights"></a>啟用見解

您可以使用多種方法來匯出資料，並根據基礎見解進行動作。

如需詳細資訊，請參閱[匯出概觀](export-destinations.md)。
