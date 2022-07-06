---
title: 將客戶細分匯出至 Campaign Monitor (預覽版)
description: 了解如何設定連接並匯出至 Campaign Monitor。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ea7431d4df5143724b5ecf2a2d747ed164fe2c29
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080938"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>將客戶細分匯出至 Campaign Monitor (預覽版)

將整合客戶個人資料的客戶細分匯出至 Campaign Monitor，並用於行銷活動。

## <a name="prerequisites"></a>先決條件

-   您擁有一個 [Campaign Monitor 帳戶](https://www.campaignmonitor.com/)及對應的系統管理員認證。
-   在 Customer Insights 中，您具有[已設定的客戶細分](segments.md)。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 每次匯出，您最多可以匯出 1 百萬個客戶設定檔到 Campaign Monitor。
- 僅限於客戶細分可被匯出至 Campaign Monitor。
- 匯出多達 1 百萬個客戶設定檔到 Campaign Monitor 最長花費 20 分鐘完成。 
- 您可以匯出到 Campaign Monitor 的客戶設定檔數目取決於並受限於您和 Campaign Monitor 簽訂的契約。

## <a name="set-up-connection-to-campaign-monitor"></a>設定到 Campaign Monitor 的連接

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Campaign Monitor** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 來初始化與 Campaign Monitor 的連接。

1. 選取 **與 Campaign Monitor 驗證**，並提供管理認證給 Campaign Monitor。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 Campaign Monitor 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. [**Campaign Monitor 清單識別碼**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   在 Campaign Monitor 的 **帳戶設定** 中[生成 API 金鑰](https://www.campaignmonitor.com/api/getting-started/)，然後再查看 API 清單識別碼。  

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。 這必須匯出客戶細分到 Campaign Monitor。

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸至 Campaign Monitor 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。 Microsoft 將會在您的指示下傳送這類資料，但是您必須負責確保 Campaign Monitor 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。
