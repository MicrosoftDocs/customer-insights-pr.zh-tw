---
title: 將 Customer Insights 資料匯出到 Klaviyo
description: 了解如何設定連接並匯出到 Klaviyo。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5f7c91afed8eeb1f767f1efc58dceb7782c37bb4
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619063"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>匯出客戶細分清單到 Klaviyo (預覽)

將整合客戶個人資料的客戶細分匯出到 Klaviyo ，並將其用在行銷活動上。

## <a name="prerequisites"></a>先決條件

-   您有一個 [Klaviyo 帳戶](https://www.klaviyo.com/)和相應的系統管理員認證。
-   您在對象見解中具有 [組態區域](segments.md) 權限。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 每次匯出最多可以匯出 100,000 個客戶設定檔到 Klaviyo。
- 匯出到 Klaviyo 僅限於客戶細分。
- 匯出多達 1 百萬個客戶設定檔到 Klaviyo 最長花費 20 分鐘完成。 
- 您可以匯出到 Klaviyo 的客戶設定檔數目取決於並受限於您和 Klaviyo 簽訂的契約。

## <a name="set-up-connection-to-klaviyo"></a>設定連線至 Klaviyo

1. 移至 **管理** > **連接**。

1. 選擇 **新增連接** 並選擇 **Klaviyo** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供您的 [Klaviyo API 金鑰](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys)，以繼續進行登入。 

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 來初始化 Klaviyo 連接。

1. 選取 **驗證 Klaviyo**，並提供您的 Klaviyo 管理認證。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出連接** 欄位中，從 Klaviyo 區段選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 輸入您的 [**Klaviyo 清單識別碼**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID)。     

3. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。 這需要匯出客戶細分到 Klaviyo。

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸到 Klaviyo 時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在的敏感性資料 (例如個人資料)。 Microsoft 將會依您的指示傳送這類資料，但是您必須負責確保 Klaviyo 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。
