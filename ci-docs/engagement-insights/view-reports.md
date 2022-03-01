---
title: 檢視資料報表
description: 使用可用的報表，以查看您網站上的即時活動。
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036638"
---
# <a name="view-reports"></a>查看報告

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

報表是資料視覺效果的集合，使用由 SDK 收集的資料來協助您測量和瞭解使用者行為。 Dynamics 365 Customer Insights 參與度見解包括 Web 和行動專案的立即可用 (OOB) 報表。  

## <a name="web-reports"></a>Web 報表

您可以在左導覽窗格中的 **探索** 下，存取 Web 報表。

:::image type="content" source="media/report-menu.png" alt-text="顯示可用報表清單的導覽。":::

### <a name="real-time-usage-report"></a>即時使用報表

**即時使用** 報表提供網站上每分鐘自動刷新的目前活動概述。 使用即時使用來監控行銷廣告活動、新聞事件以及其他案例對您的網站流量的影響。

### <a name="key-metrics-reports"></a>關鍵計量報表

- **頁面查看** 列出各個頁面的頁面查看數量，以及所選取時間範圍的總頁面查看數量。

- **瀏覽數** 顯示瀏覽數和瀏覽期間的資訊。

- **訪客數** 顯示您的網站中新的和回訪的不重複訪客數。

### <a name="content-reports"></a>內容報表

- **連結** 顯示有關點擊次數和類型的資訊。

- **離開頁面** 列出訪客離開您的網站時點擊的連結。

### <a name="traffic-sources-reports"></a>流量來源報表

- **來源** 列出將訪客帶到您的網站的網域和 URL。

- **追蹤程式碼** 提供追蹤程式碼的詳細資料，此程式碼位於讓使用者可以進入您的網站的連結中。

### <a name="visitor-profiles-reports"></a>造訪者設定檔報表

- **裝置** 列出用來存取您的網站的實體裝置。

- **OS & 瀏覽器** 深入解析存取您的網站時執行的作業系統和瀏覽器。

- **位置** 以國家/地區和市/鎮顯示訪客的相關資訊。

- **語言** 依據訪客的慣用語言來列出頁面查看。

## <a name="mobile-reports"></a>行動報表

行動報表是依即時使用方式、應用程式和使用者類別分組。 您可以在左導覽窗格中的 **探索** 下，存取行動報表。   

:::image type="content" source="media/mobile-reports.png" alt-text="參與度見解的使用者介面，圖上為以圖表和清單呈現資料的即時使用方式報表。":::   

### <a name="real-time-usage"></a>即時使用方式

**即時使用** 提供目前在您的行動裝置應用程式中的活動概述，每分鐘都會自動重新整理。 使用即時使用方式報表來監控應用程式中目前使用中的使用者和工作階段數量，以及最高的畫面查看。

### <a name="app-reports"></a>應用程式報表

- **畫面查看** 列出應用程式中各個畫面的畫面查看數量，以及選取的時間範圍中的畫面查看總數。 您可以依據畫面名稱或畫面標題來查看畫面查看數。

- **工作階段** 顯示工作階段和工作階段期間的資訊。

- **返回頻率** 根據上次工作階段後的天數，分組工作階段計數。

- **使用者** 顯示在行動裝置應用程式中新的和返回的使用者。

- **事件** 列出從應用程式收集的所有事件，以及每個事件的總計數。

### <a name="user-reports"></a>使用者報表

- **應用程式版本** 列出大多數使用者使用的行動裝置應用程式版本。

- **裝置 & OS 版本** 深入解析執行行動裝置應用程式的裝置和作業系統。

- **位置** 以國家/地區和市/鎮顯示應用程式的相關資訊。

## <a name="filter-by-time-or-value"></a>依時間或值篩選

在 Web 或行動報表中，您可以選取時間範圍或值，以將聚焦在放在一個值或時間間隔。 

- 若要選取時間範圍，請從報表的下拉式清單中選取 **更多 [...]**。 即時使用報表無法啟用時間範圍選取；即時使用報表所使用的時間範圍為「現在」。

- 在大部分的報表中，可選取圖表或清單中的值，以用此選定值篩選報表。

[!INCLUDE[footer-include](../includes/footer-banner.md)]