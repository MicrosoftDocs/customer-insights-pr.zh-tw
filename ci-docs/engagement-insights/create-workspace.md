---
title: 建立新工作區
description: 工作區用途及建立新環境的方式。
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f8922703af506974c8b5b24086b61f05a83609d
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673372"
---
# <a name="create-a-new-workspace-and-add-members"></a>建立新工作區和新增成員

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

工作區是指您如何即時查看使用者活動，以便更瞭解您的對象。 您可以在其中儲存和管理事件與報表。

當您建立一個工作區時，請選取您想聚焦的資料類型。 您可以隨時將其他使用者或成員新增至現有的工作區。 

## <a name="create-a-new-workspace"></a>建立新工作區

建立工作區的程序包括設定用來管理工作區的 *環境*。 環境是可以包含一或多個工作區的空間。 您可以使用環境來管理您的工作區和與對象見解功能的連接。

1. 從工作區切換器中選取 **+新增**。

   :::image type="content" source="media/new-workspace.png" alt-text="在導覽窗格及說明中帶有標注的 Customer Insights 頁面。":::

1. 請在 **工作區** 窗格輸入 **工作區名稱**。

   :::image type="content" source="media/workspace-name.png" alt-text="請鍵入工作區名稱。":::

1. 請選擇您要測量的平台類型 (Web 或 Mobile)。

1. 請選取 **顯示進階設定** 啟用或停用這些非必要設定：

   - 請將 **未知到已知** 切換成「已啟用」，以便將 Web 事件與先前驗證的使用者產生關聯。 如需詳細資訊，請參閱[從先前驗證的訪客識別 Web 事件](unknown-to-known.md)
   - 請將 **篩選條件 bot 流量** 切換成「已啟用」，以便藉由 bot 為此工作區移除 web 流量。 

1. 完成時請選取 **完成**。 

1. 安裝程式碼片段以開始收取資料，然後選取 **完成** 建立工作區。 如需詳細資訊，請參閱[開發人員資源概觀](developer-resources.md)。

> [!NOTE]
> 您現在可以新增成員並從 **角色** 清單指派權限等級 。 如需詳細資訊，請參閱[角色與權限](user-roles.md)。 

如需詳細資訊，請參閱[管理環境和工作區](manage-environments-workspaces.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
