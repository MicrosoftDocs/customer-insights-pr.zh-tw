---
title: 使用未知到已知功能，辨識 web 事件是來自先前驗證的訪客
description: 未知到已知的功能可讓您將網站上的事件與先前驗證的訪客關聯。
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036773"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>辨識 web 事件是來自先前驗證的訪客

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

參與見解功能中的 **未知到已知** 功能能夠關聯網站上的事件與先前驗證的訪客。 如果停用該功能，無法識別在之前的瀏覽中驗證後離開的訪客，要再次進行驗證，才會被識別。 

例如，在上週進入網站的人員，在網站上登入使用者帳戶，之後瀏覽產品類別目錄。 此人次週返回，瀏覽更多的產品，但沒有登入帳戶。 網站擁有者使用 **未知到已知** 功能，便可以知道該人員返回並且在網站上做了什麼事情。 這讓網站活動的報告和分析能夠更精確。

## <a name="enable-unknown-to-known"></a>啟用未知到已知

您需要是[工作區管理員](user-roles.md)才能啟用此功能。 

1. 在參與見解中，移至 **管理** > **工作區**。 
2. 選取 **設定** 索引標籤。
3. 在 **未知到已知** 區段中，將切換為 **啟用**。

![啟用未知到已知](media/U2Ktoggle.png "啟用未知到已知")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>將 JavaScript 程式碼新增至網站的追縱程式碼片段

網站可以使用 [參與見解 Web SDK](advanced-SDK-implementation.md)，透過下列 JavaScript 範例來擷取使用者 **user authId**。 為了讓 **未知到已知** 功能成功運作，您需要擷取 authId *並* 在程式碼片段 JavaScript 中啟用 userMapping:True，如下列範例所示。

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
