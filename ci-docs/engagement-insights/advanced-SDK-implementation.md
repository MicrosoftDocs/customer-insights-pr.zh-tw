---
title: 進階 web SDK 案例
description: 使用 SDK 來規範您的網站時，要考慮的進階案例。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036318"
---
# <a name="advanced-web-sdk-instrumentation"></a>進階網站 SDK 檢測工具

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

這篇文章將引導您在使用 Dynamics 365 Customer Insights 業務開發見解功能 SDK [規範您的網站](instrument-website.md) 時，需考慮的進階案例。

## <a name="setting-user-details-for-your-event"></a>設定事件的使用者詳細資料

SDK 可讓您隨每個事件定義能傳送的使用者資訊。 您可以在稱為 `user` 的屬性（此屬性的預期資料為 `IUser` 物件）中指定使用者詳細資料，這類似於 `src`、`name` 和 `cfg` 在程式碼片段中的設定。

`IUser` 物件包含下列字串屬性：

- **localId**：使用者的本機 ID。
- **authId**：已驗證的使用者 ID。
- **authType**：用來取得已驗證使用者 ID 的驗證類型。
- **name**：使用者的名稱。
- **email**：使用者的電子郵件地址。
    
下列範例顯示一段傳送使用者資訊的程式碼片段。 在您看到以 * 表示的函數中，請將它替換為您執行呼叫的那些值：  

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
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

您也可以在 SDK 上呼叫 `setUser(user: IUser)` API 來指定使用者資訊。 在呼叫 `setUser API` 後傳送的遙測將包含使用者資訊。

## <a name="adding-custom-properties-for-each-event"></a>為每個事件新增自訂屬性

SDK 可讓您隨每個事件傳送指定的自訂屬性。 您可以將自訂屬性指定為包含鍵值配對的物件（值可以是 `string | number | boolean` 類型）。 該物件可以新增至名為 `props` 的屬性，這類似於程式碼片段設定中的 `src`、`name` 和 `cfg` 屬性。 

下列範例顯示一段傳送自訂屬性的程式碼片段：

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
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

您也可以在 SDK 上呼叫 `setProperty(name: string, value: string | number | boolean)` API，個別指定自訂屬性。

## <a name="sending-custom-events"></a>傳送自訂事件

您可以使用 SDK 傳送自訂事件。 您必須指定事件的名稱，以及要隨事件傳送的屬性。

下列範例顯示一段追蹤自訂事件的程式碼片段。 「名稱」是程式碼片段設定中的 `name` 鍵中的值。 它也是 SDK 載入處視窗物件中的變數名稱。

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]