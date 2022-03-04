---
title: 管理工作區和環境
description: 如何建立、重新命名及刪除工作區和環境。
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ded9e98f06109b7cdc27f449455b7f58d633722f
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350627"
---
# <a name="manage-environments-and-workspaces"></a>管理環境和工作區

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>概觀

本主題討論如何管理建立後的工作區和環境。 

- *工作區* 是儲存和管理事件及報表的空間。 您可以在這裡即時查看使用者活動。 當您建立一個工作區時，請選取要傳送到工作區的資料類型。 目前，支援 Web 資料和行動裝置應用程式。 如需詳細資訊，請參閱[建立新工作區與新增成員](create-workspace.md)。

- *環境* 是管理您的工作區和連線的空間。 如需詳細資訊，請參閱[建立新環境](create-new-environment.md)。

## <a name="manage-an-existing-workspace"></a>管理現有的工作區

您可以在一個環境中同時保有多個工作區。 您的[角色](user-roles.md)會決定您可以使用的程度。 

 - 您必須是環境管理員或工作區管理員，才能管理工作區。
 - 做為工作區管理員，您可以重新命名現有的工作區或將它們刪除。 

:::image type="content" source="media/workspace-edit.png" alt-text="工作區管理員中心。":::

### <a name="edit-a-workspace-name"></a>編輯工作區名稱

1. 移至 **系統管理員** > **工作區**，然後選取 **設定**。

1. 在 **工作區名稱** 方塊中輸入新的名稱。

1. 選取 **儲存** 套用變更。

### <a name="delete-a-workspace"></a>刪除工作區

刪除工作區會永久移除其所有內容、資料、設定和權限。 此動作無法復原。

1. 移至 **系統管理員** > **工作區**，然後選取 **設定**。

1. 選取 **刪除工作區**。 

1. 請在 **刪除工作區** 對話方塊中以全大寫字母輸入 **確認刪除**。 

1. 選取 **刪除** 以永久刪除該工作區。

### <a name="manage-workspace-members"></a>管理工作區成員

1. 移至 **系統管理員** > **工作區**，然後選取 **成員**。

1. 選取 **新增成員** 以提供存取並[指派角色](user-roles.md)。 目前只有 **工作區系統管理員** 可以選用。

1. 選取 **新增成員**，將它們新增至您的工作區。

## <a name="manage-an-existing-environment"></a>管理現有環境

身為環境管理員，您可以從左導覽窗格存取環境。 您可以進行環境設定、以及設定其他環境管理員及工作區。 選取要在系統管理中心不同區域之間移動的索引標籤。

:::image type="content" source="media/environment-edit.png" alt-text="環境系統管理中心。":::

### <a name="edit-an-environment-name"></a>編輯環境名稱

1. 移至 **系統管理員** > **環境**，然後選取 **設定**。

1. 更新 **環境名稱**，然後選取 **儲存** 來套用變更。

### <a name="delete-an-environment"></a>刪除環境

環境管理員可以刪除環境。 在您可以刪除環境之前，您必須移除其中的所有工作區。

1. 移至 **系統管理員** > **環境**，然後選取 **設定**。

1. 選取 **刪除環境**。 

1. 請在 **刪除工作區** 對話方塊中以全大寫字母輸入 **確認刪除**。 

1. 選取 **刪除** 永久刪除環境。

### <a name="manage-environment-members"></a>管理環境成員

1. 移至 **系統管理員** > **環境**，然後選取 **成員**。

1. 選取 **新增成員** 以更新成員並[指派角色](user-roles.md)。 目前只有 **環境管理員** 可以選用。

1. 選取 **新增成員**，將它們新增至您的環境。

## <a name="manage-connections"></a>管理連線

建立連接至對象見解，可讓您根據統一的客戶設定檔來查看業務開發見解中的報表。 

如需更多資訊，請參見[建立對象見解與參與見解之間的連結](integrate-audience-insights-engagement-insights.md)。

## <a name="manage-personal-data"></a>管理個人資料

若要保護您的客戶個人資料，您可以刪除或匯出終端使用者的可識別資料。

如需詳細資訊，請參閱[刪除和匯出包含個人資訊的事件資料](../dsr-rights-requests.md)。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
