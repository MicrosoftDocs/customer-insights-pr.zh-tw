---
title: 新增程式碼至您的網站
description: 如何新增程式碼片段來擷取您網站上的事件。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035084"
---
# <a name="install-the-code-snippet-on-a-website"></a>在網站上安裝程式碼片段

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

本文描述系統管理員如何在網站上安裝程式碼片段。 在您將指令碼新增至您的網站不久後，您將會開始看到工作區中的事件。 如需詳細資訊，請參閱[管理工作區和環境](manage-environments-workspaces.md)。 若要在行動裝置應用程式中擷取事件，請參閱[開發人員資源概述](developer-resources.md)。


### <a name="prerequisites"></a>先決條件

* 您必須有工作區系統管理員的權限，才能儲存資料。
* 您的網站或專案必須線上託管才能傳送活動資料。 伺服器將不會接受本機檔案所傳送的資料。


## <a name="add-code-to-your-website"></a>新增程式碼至您的網站
1.  移至 **管理員** > **工作區**，然後選取 **安裝指南**。
1. 選取 **複製程式碼**，以複製程式碼片段。 根據預設，您工作區的擷取鍵會嵌入在程式碼片段中。
:::image type="content" source="media/copy-code.png" alt-text="程式碼片段頁面的螢幕擷取畫面。":::
3. 將複製的程式碼片段新增至您的網站，靠近 <head> 標記及在其他任何指令碼或 CSS 標記之前。
4.  發佈您更新過的網站，並等待幾分鐘以擷取進入的網路流量。
5.  若要查看您的資料，請從導覽窗格的工作區切換器中選取您的工作區。 然後，在 **探索** 區段中選取其中一個報表。

## <a name="configuration-options"></a>設定選項

您可以變更下列的程式碼片段設定選項：

- **ingestionKey**：用於將事件傳送至工作區的擷取鍵。 您可以變更擷取金鑰，將事件傳送至不同的工作區。 每個工作區的擷取金鑰都是唯一的。 
- **autoCapture**：指定是否擷取頁面查看以及與網站的互動。 它有兩個選項：
    - **查看**：設定為 *true* 以擷取網頁查看。 網頁查看會被擷取為 *查看*[事件](glossary.md#event)（屬於一種 [基礎事件](glossary.md#base-event)）。
    - **點擊**：設定為 *true* 以擷取訪客與網站的互動。 互動會被擷取為 *動作*[事件](glossary.md#event)，屬於一種 [基礎事件](glossary.md#base-event)。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
