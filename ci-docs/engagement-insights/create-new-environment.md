---
title: 建立新環境
description: 環境的用途及建立新環境的方式。
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f82ff588c2ffbe82c3ee7df2498ac2cca2bad31
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225413"
---
# <a name="create-a-new-environment"></a>建立新環境 

## <a name="overview"></a>概觀

環境是用來管理您的工作區和連接的空間。 您如何使用環境，視組織和使用案例而定。 例如，您可以建立：

- 單一環境。
- 各自獨立的環境以進行測試和生產。
- 組織中特定團隊或部門各自獨立的環境，其中包含每個對象的相關事件。
- 為貴公司全球各地的分公司建立各自獨立的環境。
- 連線到 Customer Insights 對象見解功能。

## <a name="create-a-new-environment"></a>建立新環境

1. 請在主橫幅右邊選取環境選擇器和 **+ New**。

   :::image type="content" source="media/environment-picker.png" alt-text="選取環境選擇器。":::

1. 請在 **設定** 窗格鍵入 **環境名稱**。

1. 請根據您的計畫類型選擇帳戶的 **類型**。

1. 選擇 **地區** 並選取 **下一步**。 

1. 請鍵入 **工作區名稱**，讓您收集特定網站或應用程式的資料。 如需詳細資訊，請參閱[建立工作區](create-workspace.md)。

1. 請選擇 **您要建立的工作區類型** (Web 或 Mobile)。 

1. 請選取 **顯示進階設定** 啟用或停用這些非必要設定：

   - 請將 **未知到已知** 切換成「已啟用」，以便將 Web 事件與先前驗證的使用者產生關聯。 如需詳細資訊，請參閱[從先前驗證的訪客識別 Web 事件](unknown-to-known.md)。
   - 請將 **篩選條件 bot 流量** 切換成「已啟用」，以便藉由 bot 為此工作區移除 web 流量。 

1. 完成時請選取 **完成**。 

1. 安裝程式碼片段以開始收取資料，然後選取 **完成** 建立工作區。 如需詳細資訊，請參閱[開發人員資源概觀](developer-resources.md)。

> [!NOTE]
> 您現在可以新增成員並從 **角色** 清單指派權限等級 。 如需詳細資訊，請參閱[角色與權限](user-roles.md)。 

如需詳細資訊，請參閱[管理環境和工作區](manage-environments-workspaces.md)。

## <a name="work-with-your-new-environment"></a>搭配您的新環境使用

- [建立工作區](../engagement-insights/create-workspace.md) 並新增成員。
- [將程式碼新增到您的網站](../engagement-insights/instrument-website.md)或[行動應用程式](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps)。
- 查看[即時報表](../engagement-insights/view-reports.md)或建立[自訂報表](../engagement-insights/custom-reports.md)。
- [建立精簡事件](../engagement-insights/refined-events.md) 以匯出。
- [將資料匯出](../engagement-insights/export-events.md) 至 Data Lake Storage。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
