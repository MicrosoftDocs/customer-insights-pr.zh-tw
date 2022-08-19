---
title: 指派使用者權限
description: 了解有關權限和使用者角色。
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245409"
---
# <a name="assign-user-permissions"></a>指派使用者權限

 Customer Insights 的存取權被限制在由系統管理員新增至應用程式的組織內使用者。系統管理員可以新增、編輯或移除使用者。 使用者可以是單一使用者、群組或應用程式。 使用者可以擁有三種類型的角色：

## <a name="viewer"></a>檢視者

- 在 **首頁** 和 **區段** 頁面中探索見解和區段。
- 使用 **客戶** 頁面搜尋和篩選客戶設定檔。 欄位必須是可搜尋。
- 檢視並探索 **擴充** 頁面。
- 使用 **實體** 頁面探索和匯出實體。
- 使用 **系統** 頁面檢視系統程序的狀態。
- 在 **匯出** 頁面中查看匯出。
- 安裝和使用 **Power BI Customer Insights** 儀表板。

## <a name="contributor"></a>參與者

- 檢視者可用的所有權限。
- 使用 **資料來源** 頁面載入和轉換資料。
- 完成 **資料統一**，會產生統一客戶設定檔實體。
- 定義 **關聯** 和 **活動**。
- 使用 **區段** 頁面建立區段。
- 使用 **量值** 頁面建立量值。
- 從 **擴充** 頁面管理設定並擴充客戶設定檔 (僅適用於第一方擴充內容)。
- 以 [與參與者共用的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)來管理和建立匯出。

## <a name="admin"></a>管理

- 參與者可用的所有權限。
- 在 **系統** 頁面上變更設定，包括工作語言、系統流程的重新整理排程，以及匯出診斷記錄。
- 在 **安全性** 頁面上變更設定，包括使用者、API 金鑰、私人連結和金鑰存儲庫。
- 使用 **搜尋和篩選索引** 頁面 (透過 **客戶** 頁面存取) 設定客戶頁面的搜尋和篩選條件定義。
- 管理連接，並在 **連接** 頁面上允許其他使用者角色使用。
- 從 **擴充** 頁面管理設定並擴充客戶設定檔 (適用於所有擴充內容)。
- 在 **匯出** 頁面上管理和建立匯出。
- 安裝和使用 **客戶卡片增益集**。
- 新增和使用 **Power Apps 連接器**。
- 啟用 [Customer Insights API](apis.md) 的使用方式。
- [指派環境擁有權](manage-environments.md#change-the-owner-of-an-environment)給另一位系統管理員。

## <a name="admin-owner"></a>系統管理員 (負責人)

- 系統管理員可以使用所有權限。
- [重設或刪除](manage-environments.md#reset-an-existing-environment-preview)環境。

## <a name="add-users"></a>新增使用者

1. 請前往 **系統管理員** > **安全性**，然後選取 **使用者** 索引標籤。

1. 選取 **新增使用者** 打開 **新增/編輯權限** 窗格。

1. 使用 **搜尋** 欄位，尋找您要新增的 Azure Active Directory 使用者或群組。 選取 **角色** 以指派給該使用者或群組。

1. 選取 **儲存**。 目前的環境將自動與使用者或群組成員共用。 使用者可以存取 Customer Insights 應用程式，並根據他們指定的角色進行工作。

## <a name="view-current-permissions"></a>檢視目前的權限

移至 **系統管理** > **安全性**，然後選取 **使用者** 索引標籤，便能查看使用中使用者的清單及其角色指派。 您可以用任何欄來排序使用者清單，或是使用搜尋方塊尋找特定使用者。

## <a name="manage-current-users"></a>管理目前的使用者

前往 **系統管理員** > **安全性** 接著選取 **使用者** 索引標籤，您可以用任何欄來排序使用者清單，或是使用搜尋方塊尋找您要管理的使用者。

選取使用者來查看可用的動作。

- **編輯** 可編輯 Customer Insights 中的使用者角色。 選取 **儲存** 確認變更。
- **移除** 可移除使用者對 Customer Insights 的存取權。 請選取 **刪除**，以確認刪除。

[!INCLUDE [footer-include](includes/footer-banner.md)]
