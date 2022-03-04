---
title: 開始使用業務開發見解功能
description: 協助資源概述能幫您快速開始使用。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225534"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>開始使用 Dynamics 365 Customer Insights 業務開發見解功能（公開預覽版）

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

業務開發見解功能可讓您收集並評估您網站上的客戶行為。 它整合了對象見解功能，因此您可以透過客戶設定檔報表來查看豐富的即時行為分析。 本文中的連結可協助您快速配置和設定您的環境。

## <a name="step-1-review-prerequisites"></a>步驟 1：檢閱先決條件

首先，您必須要有一個有效的 Microsoft Azure Active Directory (AAD) 使用者帳戶。 然後，在設定業務開發見解工作區之前，請先閱讀下列文章。

- 檢閱並同意 Microsoft 的[服務條款](terms-of-service.md)。  
- 閱讀[管理 cookie 和使用者同意](user-consent-storage.md) 文章。 接著，評估您是否需要更新您的使用者同意通知。 如果您先前沒有「非必要」cookie，您可能需要更新網站原則。
- 請檢閱[詞彙表](glossary.md)，以取得關鍵術語和概念的快速介紹。

## <a name="step-2-explore-engagement-insights"></a>步驟 2：探索業務開發見解

第一次登入參與見解時，您可以進行設定、檢閱原則，並探索功能。

1. 使用您的 Microsoft AAD 使用者 (學校或工作) 帳戶[登入參與見解功能入口網站](https://home.ci.ai.dynamics.com/app/engagement-insights)。

1. 選取您的地區，如果您想加入接收電子郵件更新和優惠，請核取方塊。

1. 審閱業務開發見解(預覽版) **使用條款** 和 **隱私權聲明**，然後選取 **探索示範** 以接受這些設定。

1. 使用一組範例資料來探索產品。

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>步驟 3：設定工作區並建立報表

工作區可讓您即時查看使用者活動，並儲存和管理報表。 將程式碼新增至您的網站，以開始收集 *事件*（來自使用者的活動資料）。

1. [建立工作區](create-workspace.md) 並新增成員。

1. 將程式碼新增到您的[網站](instrument-website.md)或[行動裝置 App](developer-resources.md#capture-events-from-mobile-apps) 查看使用者進入工作區的活動。

1. 查看[即時報表](view-reports.md)，根據瀏覽器、裝置、作業系統、位置和語言顯示活動中的使用者。 您也可以建立[自訂報表](custom-reports.md)，以建立您自己的視覺效果。

1. 建立[維度](dimensions.md)並按照新使用者和傳回使用者排序訪客，[計量](metrics.md)有助於更瞭解使用者行為，而[區段](segments.md)可依據特徵或網站互動情況辨識訪客的子集。
    
## <a name="step-4-export-data-to-other-channels"></a>步驟 4：將資料匯出至其他通道

您可以建立網站分析資料的 *精簡事件*（一個虛擬視圖）。 然後篩選並將資料匯出至 Azure Data Lake Storage。 您可以將匯出的資料內嵌為資料來源。

1. [建立精簡事件](refined-events.md) 以匯出。

1. [匯出資料](export-events.md)到 Azure Data Lake Storage。

1. [建立觀眾見解與參與見解之間的連結](integrate-audience-insights-engagement-insights.md)，以在兩個功能之間共用資料。

1. 使用 **未知到已知** 功能[從先前驗證的使用者認出 Ｗeb 事件](unknown-to-known.md)。

1. 瞭解如何[刪除和匯出包含個人資訊的事件資料](delete-export-personal-data.md)。

## <a name="step-5-create-and-manage-funnel-reports"></a>步驟 5：建立和管理漏斗圖報表

漏斗報表會從您的網站或行動應用程式收集客戶旅程期間的步驟資訊。 除了建立隨開即用設定檔報表和自訂報表以外，您可以建立漏斗圖報表找出您的客戶購買前的路徑。 

1. [建立漏斗圖報表](funnel-reports.md)通知決策並找出最佳化與流程改善的部份。

1. 一旦您已經使用業務開發見解 [Android SDK](get-started-android.md) 或 [iOS sdk](get-started-ios.md) 裝備您的行動裝置應用程式，即可建立交叉漏斗圖報表。

1. 請使用 [Funnel Insights](funnel-reports.md#funnel-insights) 在漏斗圖報表中獲取客戶對各步驟行為的更深入見解。
 
## <a name="step-6-stay-connected"></a>步驟 6：保持聯繫

我們非常感激您的積極參與，且會在開發未來版本時仔細斟酌所有相關意見。 您可以透過下列其中一種管道分享您的意見反應並舉報問題：
- [社群](https://go.microsoft.com/fwlink/?linkid=2141648)
- [提供意見反應](https://go.microsoft.com/fwlink/?linkid=2143222)
- [要求支援](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
