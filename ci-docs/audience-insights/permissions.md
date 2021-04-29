---
title: 管理使用者權限
description: 了解有關權限和使用者角色。
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760363"
---
# <a name="user-permissions"></a>使用者權限

**權限** 頁面是您可以設定觀眾見解的使用角色和權限的地方。

您必須有系統管理員權限，才能查看此頁面。 若要在觀眾見解中存取權限頁面，請前往 **管理員** > **權限**。

目前共有三種類型角色：

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
- 完成 *資料統整* 區 (**對應**、**比對** 和 **合併**) 打造統整的客戶設定檔實體。
- 定義 **關聯** 和 **活動**。
- 使用 **區段** 頁面建立區段。
- 使用 **量值** 頁面建立量值。
- 從 **擴充** 頁面管理設定並擴充客戶設定檔 (僅適用於第一方擴充內容)。
- 以與參與者共用的連接來管理和建立匯出。 [進一步了解系統管理員如何讓參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

## <a name="administrator"></a>管理員

- 參與者可用的所有權限。
- 在 **系統** 頁面上變更設定，包括工作語言和系統流程的重新整理排程。
- 使用 **權限** 頁面查看和新增權限。
- 使用 **搜尋和篩選索引** 頁面 (透過 **客戶** 頁面存取) 設定客戶頁面的搜尋和篩選條件定義。
- 管理連接，並在 **連接** 頁面上允許其他使用者角色使用。
- 從 **擴充** 頁面管理設定並擴充客戶設定檔 (適用於所有擴充內容)。
- 在 **匯出** 頁面上管理和建立匯出。
- 安裝和使用 **客戶卡片增益集**。
- 新增和使用 **Power Apps 連接器**。
- 啟用 [Customer Insights API](apis.md) 的使用方式。

## <a name="assign-roles-and-permissions"></a>指派角色和權限

1. 在對象見解中，前往 **管理員** > **權限**。

1. 選取 **新增使用者** 打開 **新增/編輯權限** 窗格。

1. 使用 **搜尋** 欄位，尋找您要調整其權限的 Azure Active Directory 使用者或群組。 選取 **角色** 以指派給該使用者或群組。

1. 選取 **儲存**。 目前的環境將自動與您已變更權限的使用者或群組成員共用。 使用者可以存取 Customer Insights 應用程式，並根據他們指定的角色進行工作。

## <a name="view-current-permissions"></a>檢視目前的權限

請在觀眾見解中前往 **管理員** > **權限** 查看目前有效的角色指派。

- **類型** 欄指定單一使用者、群組或應用程式。 系統支援個別使用者和群組。
- 角色是在 **角色** 欄底下指定。
- 選取任何欄標題以依據該欄的值來排序結果。
- 使用頁面頂端的 **搜尋** 欄位尋找特定使用者。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
