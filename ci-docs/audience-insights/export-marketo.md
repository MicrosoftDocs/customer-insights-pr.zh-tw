---
title: 匯出 Customer Insights 資料到 Marketo
description: 了解如何設定連接並匯出至 Marketo。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759811"
---
# <a name="export-segments-to-marketo-preview"></a>將客戶細分匯出至 Marketo (預覽版)

匯出統一的客戶設定檔區段以便產生行銷活動，提供電子郵件行銷及使用含 Marketo 的特定族群客戶。

## <a name="prerequisites-for-connection"></a>連接的先決條件

-   您具有 [Marketo 帳戶](https://login.marketo.com/) 及對應的系統管理員認證。
-   Marketo 和對應的識別碼中有現有的清單。 如需詳細資訊，請參閱 [ Marketo 清單](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)。
-   您有 [組態的區段](segments.md)。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 每個到 Marketo 的匯出最多可達 1 百萬個設定檔。
- 匯出到 Marketo 被限制為區段。
- 匯出總計為 1 百萬個設定檔的分段可能需要 3 小時的時間。 
- 您可以匯出到 Marketo 的設定檔數量端賴且受限於您與 Marketo 的合約。

## <a name="set-up-connection-to-marketo"></a>設定對 Marketo 的連接

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Marketo** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 輸入您的 **[Marketo 用戶端識別碼、用戶端秘密和 REST 端點主機名稱](https://developers.marketo.com/rest-api/authentication/)**。

1. 選取 **我同意** 以便確認 **資料隱私權與合規性** 和選取 **連線** 初始化到 Marketo 的連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 Marketo 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 輸入您的 **[Marketo 清單識別碼](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. 在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。 

1. 或者，您可以匯出 **名**、**姓**、**市/鎮**、**縣/市** 和 **國家/地區**，以建立更多的個人化電子郵件。 選取 **新增屬性** 對應這些欄位。

1. 選取您要匯出的客戶細分。 您總共最多可匯出 1 百萬個客戶設定檔到 Marketo。

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 在 Marketo 中，您現在可以在 [Marketo 清單](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) 下方找到您的區段。


## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Marketo 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Marketo 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]