---
title: 開始使用業務開發見解功能
description: 協助資源概述能幫您快速開始使用。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405348"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>開始使用 Dynamics 365 Customer Insights 業務開發見解功能（公開預覽版）

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

業務開發見解功能可讓您收集並評估您網站上的客戶行為。 它整合了對象見解功能，因此您可以透過客戶設定檔報表來查看豐富的即時行為分析。 本文中的連結可協助您快速配置和設定您的環境。

## <a name="step-1-review-prerequisites"></a>步驟 1：檢閱先決條件

首先，您必須要有一個有效的 Microsoft Azure Active Directory 使用者帳戶。 然後，在設定業務開發見解工作區之前，請先閱讀下列文章。

- 檢閱並同意 Microsoft 的[服務條款](terms-of-service.md)。  
- 閱讀[管理 cookie 和使用者同意](user-consent-storage.md) 文章。 檢閱此文章之後，請評估您是否需要更新您的使用者同意通知。 如果您先前沒有「非必要」cookie，您可能需要更新網站原則。
- 請檢閱[詞彙表](glossary.md)，以取得關鍵術語和概念的快速介紹。

## <a name="step-2-explore-engagement-insights"></a>步驟 2：探索業務開發見解

第一次造訪業務開發見解時，您可以配置設定、檢閱原則以及探索產品。

1. 使用您的 Microsoft Azure Active Directory 使用者帳戶登入[業務開發見解功能入口網站](https://pi.dynamics.com)。 （這可以是您的學校或工作帳戶。）

1. 選取您的地區，然後使用核取方塊，指出您是否想要透過電子郵件來接收最新消息和優惠。

1. 檢閱 **業務開發見解（預覽版）使用條款** 和 **隱私權聲明**，然後選取 **探索示範** 來接受它們。

1. 使用一組範例資料來探索產品。

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>步驟 3：設定工作區並將程式碼新增至您的網站

工作區可讓您即時查看使用者活動，並儲存和管理報表。 將程式碼新增至您的網站，以開始收集 *事件*（來自使用者的活動資料）。

1. [建立工作區](create-workspace.md) 並新增成員。

1. [將程式碼新增至您的網站](instrument-website.md)或[行動裝置應用程式 ](developer-resources.md#capture-events-from-mobile-apps)，以查看使用者活動進入工作區。

1. 查看依瀏覽器、裝置、作業系統、位置和語言所顯示的線上使用者[即時報表](view-reports.md)。 您也可以建立[自訂報表](custom-reports.md)，以建立您自己的視覺效果。
    
## <a name="step-4-export-data-to-other-channels"></a>步驟 4：將資料匯出至其他通道

您可以建立網站分析資料的 *精簡事件*（一個虛擬視圖）。 然後篩選並將資料匯出至 Azure Data Lake Storage。 您可以將匯出的資料內嵌為資料來源。 如需更多資訊，請參見[建立對象見解與參與見解之間的連結](integrate-audience-insights-engagement-insights.md)。

1. [建立精簡事件](refined-events.md) 以匯出。

1. [將資料匯出](export-events.md) 至 Data Lake Storage。

1. 瞭解如何[刪除和匯出包含個人資訊的事件資料](delete-export-personal-data.md)。
 
## <a name="step-5-stay-connected"></a>步驟 5：保持聯繫

我們非常感激您的積極參與，並計畫在未來發行的版本中將所有相關意見反饋納入考慮。 您可以透過下列其中一種管道分享您的意見反應並舉報問題：
- [社群](https://go.microsoft.com/fwlink/?linkid=2141648)
- [提供意見反應](https://go.microsoft.com/fwlink/?linkid=2143222)
- [要求支援](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
