---
title: 管理工作區和環境
description: 如何建立、重新命名及刪除工作區和環境。
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486025"
---
# <a name="manage-environments-and-workspaces"></a>管理環境和工作區

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>概觀

工作區是用來儲存和管理事件與報表的空間。 您可以在這裡即時查看使用者活動。 當您建立一個工作區時，請選取要傳送到工作區的資料類型。 目前，支援 Web 資料和行動裝置應用程式。

環境是用來管理您的工作區和連接的空間。 您如何使用環境，視組織和使用案例而定。 例如，您可以建立：

-   單一環境。
-   各自獨立的環境以進行測試和生產。
-   組織中特定團隊或部門各自獨立的環境，其中包含每個對象的相關事件。
-   為貴公司全球各地的分公司建立各自獨立的環境。
-   連線到 Customer Insights 對象見解功能。

## <a name="choose-an-environment-and-create-a-workspace"></a>選擇一個環境並建立工作區 

每個工作區都必須位於環境中。 您可以選取先前就存在的環境，或在建立工作區時建立新的環境。 然後您可以選擇新增工作區成員並開始收集資料。

**要建立您的第一個工作區**

1. 在業務開發見解中，從工作區切換器中選取 **新增**。 

   :::image type="content" source="media/New-workspace.png" alt-text="Customer Insights 頁面工作區選取器。":::

1. 從清單中選擇環境，或選取 **建立新環境**。

1. 在 **工作區名稱** 中輸入一個名字。 

1. 依照您要測量網站或行動裝置應用程式中的什麼變化，選取要建立的環境類型。 

1. 您可以從 **角色** 清單中新增成員並指派其使用權限等級。 然後選取 **完成** 來建立工作區，或 **下一步** 以安裝程式碼。 

1. 安裝程式碼片段以開始接收資料，然後選取 **完成**。 

## <a name="manage-a-workspace"></a>管理工作區

您可以在一個環境中同時保有多個工作區。 您的[角色](user-roles.md)會決定您可以使用的程度。 

 - 您必須是環境管理員或工作區管理員，才能管理工作區。
 - 做為工作區管理員，您可以重新命名現有的工作區或將它們刪除。 

### <a name="edit-a-workspace-name"></a>編輯工作區名稱

1. 移至 **系統管理員** > **工作區**，然後選取 **設定**。

1. 在 **工作區名稱** 方塊中輸入新的名稱。

1. 選取 **儲存** 套用變更。

### <a name="delete-a-workspace"></a>刪除工作區

刪除工作區將永久移除其所有內容、資料、設定和權限。 此動作無法復原。

1. 移至 **系統管理員** > **工作區**，然後選取 **設定**。

1. 選取 **刪除工作區**。 

1. 在 **刪除工作區** 對話方塊中，輸入 **確認刪除**。 

1. 選取 **刪除** 以永久刪除該工作區。

### <a name="manage-workspace-members"></a>管理工作區成員

1. 移至 **系統管理員** > **工作區**，然後選取 **成員**。

1. 選取 **新增成員** 以提供存取並[指派角色](user-roles.md)。 目前只有 **工作區系統管理員** 可以選用。

1. 選取 **新增成員**，將它們新增至您的工作區。

## <a name="manage-an-environment"></a>管理環境

做為環境管理員，您可以從左導覽窗格存取環境。 您可以進行環境設定、以及設定其他環境管理員及工作區。 選取要在系統管理中心不同區域之間移動的索引標籤。

:::image type="content" source="media/New-environment.png" alt-text="環境系統管理中心。":::

### <a name="create-an-environment"></a>建立環境

1. 在工作區選取器，選擇 **+新建**。

1. 在引導式體驗中，打開 **環境** 下拉式清單，然後選取 **建立新環境**。 

1. 提供 **環境名稱**。

   :::image type="content" source="media/create-environment.png" alt-text="引導式體驗中的步驟，指定環境詳細資料。":::

1. 選擇 **地區** 並選取 **下一步**。 

1. 提供工作區名稱，並選擇您要建立的工作區類型。 

1.  或者，新增成員並複製程式碼片段完成建立程序。

### <a name="rename-an-environment"></a>重新命名環境

1. 移至 **系統管理員** > **環境**，然後選取 **設定**。

1. 更新 **環境名稱**，然後選取 **儲存** 來套用變更。

### <a name="manage-environment-members"></a>管理環境成員

1. 移至 **系統管理員** > **環境**，然後選取 **成員**。

1. 選取 **新增成員** 以更新成員並[指派角色](user-roles.md)。 目前只有 **環境管理員** 可以選用。

1. 選取 **新增成員**，將它們新增至您的環境。

### <a name="delete-an-environment"></a>刪除環境

環境管理員可以刪除環境。 在您可以刪除環境之前，您必須移除其中的所有工作區。

1. 移至 **系統管理員** > **環境**，然後選取 **設定**。

1. 選取 **刪除環境**。 

1. 在 **刪除工作區** 對話方塊中，輸入 **確認刪除**。 

1. 選取 **刪除** 永久刪除環境。

## <a name="manage-connections"></a>管理連線

建立連接至對象見解，可讓您根據統一的客戶設定檔來查看業務開發見解中的報表。 

如需更多資訊，請參見[建立對象見解與參與見解之間的連結](integrate-audience-insights-engagement-insights.md)。

## <a name="manage-personal-data"></a>管理個人資料

若要保護您的客戶個人資料，您可以刪除或匯出終端使用者的可識別資料。

如需詳細資訊，請參閱[刪除和匯出包含個人資訊的事件資料](delete-export-personal-data.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
