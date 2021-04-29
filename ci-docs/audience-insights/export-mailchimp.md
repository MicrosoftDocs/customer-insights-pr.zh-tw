---
title: 匯出 Customer Insights 資料到 Mailchimp
description: 了解如何設定連接並匯出至 Mailchimp。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759868"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a>將客戶細分清單匯出至 Mailchimp (預覽版)

將統一客戶設定檔區段匯出到 Mailchimp，建立電子報和電子郵件行銷活動。

## <a name="prerequisites-for-connection"></a>連接的先決條件

-   您具有 [Mailchimp 帳戶](https://mailchimp.com/) 及對應的系統管理員認證。
-   Mailchimp 和對應的識別碼中有現有的對象。 如需詳細資訊，請參閱 [Mailchimp 對象](https://mailchimp.com/help/create-audience/)。
-   您有 [組態的區段](segments.md)
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 每個到 Mailchimp 的匯出最多可達 1 百萬個設定檔。
- 匯出到 Mailchimp 被限制為區段。
- 匯出含 1 百萬份個人資料的客戶細分可能需要花費三個小時的時間。 
- 您可以匯出到 Mailchimp 的設定檔數量端賴且受限於您與 Mailchimp 的合約。

## <a name="set-up-connection-to-mailchimp"></a>設定對 Mailchimp 的連接

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Autopilot** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 來初始化與 Mailchimp 的連接。

1. 選取 **使用 Mailchimp 驗證** 並提供您的 Mailchimp 認證。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。 

## <a name="configure-the-connector"></a>設定連接器

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料**> **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 Mailchimp 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 輸入 **[Mailchimp 對象識別碼](https://mailchimp.com/help/find-audience-id/)**

3. 在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。 

1. 或者，您可以匯出 **名** 和 **姓** 以建立更多的個人化電子郵件。 選取 **新增屬性** 對應這些欄位。

1. 選取您要匯出的客戶細分。 您總共最多可匯出 1 百萬個客戶設定檔到 Mailchimp。

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Mailchimp 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Mailchimp 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
