---
title: 開始使用 Android SDK
description: 了解如何個人化並執行 Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036908"
---
# <a name="get-started-with-the-android-sdk"></a>開始使用 Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

本教學課程可引導您逐步完成以 Dynamics 365 Customer Insights 參與度見解 SDK 檢測 Android 應用程式的流程。 在五分鐘或更短的時間內，您就能開始看到您的入口網站中的事件。

## <a name="configuration-options"></a>設定選項
下列配置選項可傳遞至 SDK：

- **ingestionKey**：擷取金鑰用來將事件傳送至工作區。

## <a name="prerequisites"></a>先決條件

- Android Studio

- 最小 Android API 等級：16 (Jelly Bean)

- 擷取金鑰 (請參閱下方有關如何取得的指示)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>步驟 1。 將 SDK 整合至應用程式
選取工作區、選取 Android 行動平台以及下載 Android SDK，您可以開始程序。

- 使用左導覽窗格中的工作區切換器來選取您的工作區。

- 如果沒有已存在的工作區，請選取 **新增工作區**，然後依照步驟建立[新的工作區](create-workspace.md)。

## <a name="step-2-configure-the-sdk"></a>步驟 2。 設定 SDK

1. 建立工作區之後，請移至 **管理** > **工作區**，然後選取 **安裝指南**。 

1. 下載[參與度見解 Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip)，並將 `eiandroidsdk-debug.aar` 檔案放在 `libs` 資料夾中。

1. 開啟您的專案層級 `build.gradle` 檔案，新增下列程式碼片段：
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. 在位於 `manifests` 資料夾底下的 `AndroidManifest.xml` 檔案，設定參與度見解 SDK 設定。 
1. 從 **安裝指南** 複製 XML 程式碼片段。 `Your-Ingestion-Key`應該自動填入。

   > [!NOTE]
   > 您不需要更換 `${applicationId}`區段。 它應該自動填入。
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. 將上述 `autoCapture` 欄位設定為 `true` 或 `false`，以啟用或停用 `View` 事件的自動擷取。

1. (可選) 包括設定端點收集器 URL 的其他設定。 它們可以新增在 `AndroidManifest.xml` 中的擷取金鑰中繼資料下：
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>步驟 3。 從 MainActivity 初始化 SDK 

初始化 SDK 之後，您可以使用 MainActivity 環境中的事件及其屬性。

    
Java：
```java
Analytics analytics = new Analytics();
```

Kotlin：
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>對所有事件設定屬性 (可選)
    
Java：
```java
analytics.setProperty("year", 2021);
```

Kotlin：
```kotlin
analytics.setProperty("year", 2021)
```

內容事件屬性支援下列類型：
- String
- 日期
- 雙重
- Long
- Boolean
- UUID

### <a name="track-an-event"></a>追蹤事件

Java：
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin：
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>設定活動的使用者詳細資料 (可選)

SDK 可讓您隨每個事件定義能傳送的使用者資訊。 您可以在 `Analytics` 層級呼叫 `setUser(user: User)` API 來指定使用者資訊。

Java：
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin：
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

`User` 資料類包含下列字串屬性：

- **localId**：使用者的本機 ID。
- **authId**：已驗證的使用者 ID。
- **authType**：驗證類型是用來取得驗證的使用者識別碼。
- **name**：使用者的名稱。
- **email**：使用者的電子郵件地址。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
