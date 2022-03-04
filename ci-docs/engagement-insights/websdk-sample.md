---
title: 執行網頁 SDK 範例
description: 瞭解如何個人化和執行網頁 SDK 範例。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225321"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>執行 Dynamics 365 Customer Insights 業務開發見解功能的網頁 SDK 範例

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

業務開發見解功能網頁 SDK 程式庫是一個 JavaScript 程式庫，其中包含可在您的網站上使用的範例程式碼。

## <a name="prerequisites"></a>先決條件

- 安裝 [Visual Studio 程式碼](https://code.visualstudio.com/)。
- 在 Visual Studio 程式碼中[安裝 Live Server 擴充功能](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)，並熟悉如何執行 Live Server。
- 您必須要有 [Engagement見解工作區](create-workspace.md)。

## <a name="run-sample"></a>執行範例

1. [下載網頁 SDK 範例](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip)。

1. 解壓縮 `ei_websdk_sample.zip` 檔案。

1. 在 Visual Studio 程式碼中打開解壓縮的資料夾。

1. 請前往您的工作區的業務開發見解入口網站。 請選取 **系統管理員** > **工作區**，然後按一下 **安裝指引**。 請遵照第一個選項，選取 **複製程式碼**，以複製 JavaScript 程式碼片段。

1. 請在 `ei_websdk_sample.html`檔案中將剛才複製的程式碼片段貼到此列下方：

   - <--將 JAVASCRIPT 程式碼片段從 ENGAGMENT見解入口網站貼到此行下方 -->

1. 從狀態列中選取 **啟用 Live** 以使用 Visual Studio 程式碼中的 Live Server 打開`ei_websdk_sample.html` 檔案。

1. 打開頁面時，應該會自動傳送查看事件。 按一下頁面上的任何按鈕，就會傳送動作事件。 **追蹤事件** 按鈕也會傳送自訂事件。 選取 **移至 Bing** 按鈕時，會在瀏覽至 Bing 網站之前，傳送動作事件。

1. 當您瀏覽至您的工作區時，查看事件流。 此工作區與步驟 4 輸入的擷取鍵有關。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
