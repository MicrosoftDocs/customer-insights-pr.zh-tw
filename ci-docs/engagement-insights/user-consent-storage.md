---
title: 在 Dynamics 365 Customer Insights 管理 cookie 和使用者同意來儲存使用者資料
description: 瞭解如何使用 cookie 和使用者同意來識別網站的來訪者。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558794"
---
# <a name="manage-cookies-and-user-consent"></a>管理 cookie 和使用者同意

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights 參與見解功能會使用 cookie 和 (`localStorage`) 金鑰來找出網站訪客。

Cookie 是一些小檔案，可儲存使用者與網站互動時的相關資訊。 它們儲存在網頁瀏覽器中。 當使用者造訪存有其 cookie 的網站時，瀏覽器會將該資訊傳送至伺服器，該伺服器會傳回該使用者特有的資訊。 就是這項技術允許如線上購物的購物車即使在使用者離開網站後，仍可保留其所選物件。

## <a name="user-consent"></a>使用者同意

[一般資料保護規定（GDPR）](/dynamics365/get-started/gdpr/) 是一種歐盟（EU）的規章，規定組織應如何處理其使用者的隱私權和安全性。 Cookie 通常會儲存或收集「個人資料」，例如線上識別碼，而這方面是 GDPR 所允許的。 假如您的業務涉及使用和/或販售到歐盟資料主體，則將受 GDPR 影響。 [深入瞭解 Microsoft 如何協助您符合 GDPR 規範](https://www.microsoft.com/trust-center/privacy/gdpr-faqs)。

若要讓業務開發見解 SDK 儲存 cookie 或其他敏感資訊，您必須指明使用者是否已同意。 這會發生在進入設定中設定 `userConsent` 欄位來初始化 SDK 的時候。

如果您指出此處並無任何使用者同意，則 SDK 將不會儲存任何資料，也不會傳送可用於追蹤使用者行為的事件。 先前儲存的任何資料都會從瀏覽器中移除。

如果未指定任何使用者同意值，SDK 將假設使用者已同意。 這表示如果您（做為我們的客戶）不指定 SDK 中使用者同意的值，資料就會被收集。 不過，如果您指定使用者同意的值必須是「true」，則當使用者拒絕或不願意表達明確同意時，就不會收集資料。

以下是以使用者同意初始化網頁 SDK 的程式碼片段：
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>業務開發見解功能中的造訪者資料儲存區

### <a name="cookies"></a>餅乾

- _msei
    - 儲存匿名使用者 ID。 此 cookie 是在自訂網域中設定的，並於 365 天後到期。

### <a name="local-storage"></a>本機儲存空間

參與見解功能也可用 (`localStorage`) 金鑰追蹤不敏感的資料。 此資料會完整儲存在瀏覽器中，與您的伺服器間不會有任何交流。

- *EISession.Id*
    - 儲存有關正在進行中的使用者工作階段資訊，例如工作階段 ID、開始時間和到期時間。
- *EISession.Previous*
    - 在當前工作階段中儲存先前所造訪頁面的 URL。

本機儲存區中的金鑰不會自動過期，而且它們會在下一個 SDK 工作階段重設。

## <a name="deleting-cookies"></a>刪除 cookie

您的客戶能隨時透過他們的瀏覽器設定手動刪除 cookies 和本機儲存體金鑰。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
