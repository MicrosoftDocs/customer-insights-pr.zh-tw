---
title: 開始使用 iOS SDK
description: 了解如何個人化並執行 iOS SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226205"
---
# <a name="get-started-with-the-ios-sdk"></a>開始使用 iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

本教學課程可引導您逐步完成以 Dynamics 365 Customer Insights 參與度見解 SDK 檢測 iOS 應用程式的流程。 在五分鐘或更短的時間內，您就能開始看到您的入口網站中的事件。

## <a name="configuration-options"></a>設定選項

下列組態選項可透過提供的 `EIConfig.plist` 檔案傳遞至 SDK：

- **ingestionKey**：擷取金鑰用來將事件傳送至專案。
- **autocollectAction**：對動作事件啟用或停用自動檢測的布林值。
- **autocollectView**：對動作事件啟用或停用檢視的布林值。
- **endpointUrl**：將引導事件的端點 URL。

## <a name="prerequisites"></a>先決條件

- Xcode 版本 9+
- iOS 版本 8.2+
- 擷取金鑰 (請參閱下方的指示來取得)

## <a name="integrate-the-sdk-into-your-application"></a>將 SDK 整合至應用程式

選取作業進行的工作區、選取 iOS 行動平台以及下載 SDK，您可以開始程序。

- 使用左導覽窗格中的工作區切換器來選取您的工作區。

- 如果沒有已存在的工作區，請選取 **新增工作區**，然後依照步驟建立[新的工作區](create-workspace.md)。

- 建立工作區之後，請移至 **管理** > **工作區**，然後選取 **安裝指南**。

## <a name="configure-the-sdk"></a>設定 SDK

下載 SDK 之後，您可以在 Xcode 中使用它來啟用和定義事件。 有兩種方式可以做到

### <a name="option-1-using-cocoapods-recommended"></a>選項 1：使用 CocoaPods (建議使用)
CocoaPods 是 Swift 和 Objective-C Cocoa 專案的相依性管理程式。 使用此程式可讓您更容易整合 iOS 的參與見解 SDK。 CocoaPods 也讓您能將參與見解 SDK 升級到最新版本。 以下是如何使用 CocoaPods，將參與見解 SDK 整合至您的 Xcode 專案中。 

1. 安裝 CocoaPods。 

1. 在專案的根目錄中建立名為 Podfile 的新檔案，並將下列陳述式新增至該檔案中。以您的 Xcode 專案名稱取代 YOUR_TARGET_PROJECT_NAME。 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
上述的 pod 設定包含 SDK 的偵錯版本和發行版本。 選擇最適合您專案的。

1. 執行以下命令，安裝 pod： `pod install --repo-update `

### <a name="option-2-using-download-link"></a>選項 2：使用下載連結

1. 下載[參與度見解 iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip)，並將 `EIObjC.xcframework` 檔案放在`Frameworks` 資料夾中。

1. 如果 `Frameworks` 資料夾不存在，請在專案資料夾中建立。

## <a name="enable-auto-instrumentation"></a>啟用自動檢測
 
不需編寫任何程式碼，您就可以輕鬆啟用自動分析。 當專案執行時，會使用設定好的擷取金鑰自動追蹤 `view` 和 `action` 事件。 

1. 在專案目錄資料夾中，對提供的 `EIConfig.plist` 檔案中更新並加入下列欄位：
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = YES
    - autocollectAction = YES

2. 然後在 Xcode 中，將 `EIConfig.plist` 檔案新增至您的專案。 



要停用自動檢測，請在專案目錄資料夾中，對已包含的 `EIConfig.plist` 檔案，更新下列欄位。 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>實作自訂事件

1. 在 Xcode 開啟專案，並瀏覽至 **一般** 設定。 
1. 新增 `EIObjC.xcframework`至專案的「架構、程式庫及嵌入的內容」區段下。

1. 以下列程式碼片段將 Framework 標頭檔案匯入 AppDelegate.m:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. 從 application: didFinishLaunchingWithOptions 初始化參與度見解 SDK。
1. 從 **安裝指南** 複製 XML 程式碼片段。

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. 追蹤事件：

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>設定活動的使用者詳細資料

SDK 可讓您隨每個事件定義能傳送的使用者資訊。 您可以在 SDK 呼叫 `setUser:(nonnull EIUser *)user` API 來指定使用者資訊。

在 `Analytics` 層級指定使用者詳細資料，表示所有的遙測都將包含此資訊。 不過，如果透過在 EIEvent 物件上呼叫 `setUser:(nonnull EIUser *)user` API 來指定在事件層級上，則只有該指定事件會包含該資訊。

`EIUser` 資料類包含下列 NSString 屬性：

- **localId**：使用者的本機 ID。
- **authId**：已驗證的使用者 ID。
- **authType**：用來取得已驗證使用者 ID 的驗證類型。
- **name**：使用者的名稱。
- **email**：使用者的電子郵件地址。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
