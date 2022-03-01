---
title: 匯出 Customer Insights 資料到 SendGrid
description: 了解如何設定連接並匯出至 SendGrid。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759755"
---
# <a name="export-segments-to-sendgrid-preview"></a>將客戶細分匯出至 SendGrid (預覽版)

將整合客戶設定檔的客戶細分匯出至 SendGrid 聯絡人清單，並在 SendGrid 中用來進行行銷活動和電子郵件行銷。 

## <a name="prerequisites-for-a-connection"></a>連接的先決條件

-   您具有 [SendGrid 帳戶](https://sendgrid.com/) 及對應的系統管理員認證。
-   有對應的識別碼且在 SendGrid 中有現有的聯絡人清單。 如需詳細資訊，請參閱 [SendGrid - 管理連絡人](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)。
-   您在對象見解中具有 [組態區域](segments.md) 權限。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 對 SendGrid 總計最多 100'000 份設定檔。
- 匯出到 SendGrid 被限制在客戶細分。
- 匯出多達 100'000 份設定檔到 SendGrid 需要花費幾個小時。 
- 您可以匯出到 SendGrid 的設定檔數量是根據且受限於您與 SendGrid 的合約。

## <a name="set-up-connection-to-sendgrid"></a>設定與 SendGrid 的連接

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **SendGrid** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 輸入您的 **SendGrid API 金鑰** [SendGrid API 金鑰 ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 初始化與 SendGrid 的連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 SendGrid 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 輸入您的 **[SendGrid 清單識別碼](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**。

1. 在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。 對其他可選欄位 (如 **名**、**姓**、**國家/地區**、**縣/市**、**市/鎮** 和 **郵遞區號**) 重複相同步驟。

1. 選取您要匯出的客戶細分。 我們強烈 **建議您不要匯出總計超過 100'000 份客戶設定檔** 至 SendGrid。 

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 傳輸資料給 SendGrid 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感資料 (如個人資料)。 Microsoft 將依據您的指示傳輸此資料，但您有責任確保 SendGrid 符合任何您承擔的隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]