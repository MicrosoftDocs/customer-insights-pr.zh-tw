---
title: 使用 Customer Insights 管理未知設定檔
description: 使用在 Dynamics 365 Customer Insights 中建立和管理的未知客戶設定檔。
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776811"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>使用 Customer Insights 管理未知設定檔

網際網路使用者通常是身分不明或匿名的線上使用者。 即使是最忠誠的客戶在不同的裝置中登入，也可能會顯示為「未知」。 對於許多品牌來說，儘管客戶對個人化的期望越來越高，但已知或經過驗證的使用者還是少數。 隨著第三方 Cookie 的未來發展受到質疑，改以第一方資料為根據來管理使用者喜好設定，對實現個人化體驗至關重要。

令人難忘的個人化依賴於您對客戶的了解程度，而 Customer Insights 可追蹤所有客戶來協助您做到這一點。  您不必限制或停止使用在客戶旅程開始時收集的資料。 Customer Insights 可讓您匯入自己的資料，以建立未知使用者的客戶設定檔。 然後，儘管缺少連絡人資訊，您仍可以使用該設定檔進行進一步的動作。 將來自 Web、移動或 CRM 系統等來源的第一方資料匯入 Customer Insights，以不斷豐富客戶資料。 當您統一更多互動時，就會將 [*未知* 客戶變成 *已知* 客戶](unknown-to-known.md)。

## <a name="sample-scenario"></a>範例案例

假設使用者使用他們的行動裝置來瀏覽您的電子商務網站。 網站會將訪客「mobile_guest123」指派為唯一的識別碼，並根據其線上活動開始收集行為活動。 例如，他們訪問了哪些頁面、他們在這些頁面上花費了多少時間，或是他們點擊了哪些連結。 您不知道他們的姓名或電子郵件地址，但是這些資料有助於為品牌提供有關此特定使用者的有意義深入解析。 反過來，您可以在使用者下次造訪該網站時將這些深入解析付諸實踐。 查詢「mobile_guest123」的 Customer Insights，以擷取使用者的客戶細分清單，例如「有機」、「行動預訂客戶」、「高價值的客戶」等等，或擷取設定檔以建立個人化 Web 體驗。 您也可以將資料匯出至任何啟動系統來執行相同的作業。

## <a name="prerequisites"></a>先決條件

- 將第一方資料內嵌到 Customer Insights
- 每個實體都有一個設定為主索引鍵的唯一識別碼
- 每個具有個人化主索引鍵的實體都是統一的
- 網站的內容管理系統可以使用 API (用於根據與 Customer Insights 直接通訊的 Web 個人化)

下表顯示如何擷取高價值 Web 事件的簡化範例。

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|7|09-15-2022 9:00:00|abc123|CookieID1|產品檢視|
|2|09-18-2022 10:05:00|abc123|CookieID1|產品檢視|
|3|09-18-2022 10:10:00|abc123|CookieID1|新增至購物車|
|4|09-21-2022 09:05:00|abc123|CookieID1|產品檢視|

## <a name="data-ingestion"></a>資料擷取

關於資料擷取的可用選項更多資訊，請參閱[資料來源概述](data-sources.md)。

## <a name="data-unification"></a>資料統整

如需整合客戶設定檔的詳細資訊，請參閱[資料整合概述](data-unification.md)。

## <a name="get-insights"></a>取得見解

[擴充](enrichment-hub.md)您的資料、構建[測量](measures.md)並建立用於進一步啟動的[區段](segments.md)。

例如，您可以建立未知使用者的客戶細分，這些使用者瀏覽了相同的產品頁面，但是尚未完成結帳。

## <a name="activation"></a>啟用

隨著您在 Customer Insights 中的資料和深入解析準備就緒，您可以使用 Customer Insights 進行個人化：

1. 使用 [OData API](apis.md) 來擷取客戶細分成員資格或客戶設定檔。如需更多範例，請參閱 [Customer Insights API 的 OData 查詢範例](odata-examples.md)。

1. 將您的資料[匯出](export-destinations.md)至您的啟動系統。

範例：未知使用者多次造訪網站，並瀏覽各種型號的皮鞋的產品頁面。 透過 Customer Insights 中提供的資料，您可以將未知使用者納入對皮鞋感興趣的客戶細分。 使用此客戶細分來告知您的網站為回訪者建立個人化設定。 在下一次造訪時，該網站會識別出未知使用者，並可以為他們提供 10% 的皮鞋優惠券。

[!INCLUDE [footer-include](includes/footer-banner.md)]
