---
title: 匯出 Customer Insights 資料到 Mailchimp
description: 瞭解如何組態到 Mailchimp 的連接。
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267163"
---
# <a name="connector-for-mailchimp-preview"></a>適用 Mailchimp 的連接器 (預覽版)

將統一客戶設定檔區段匯出到 Mailchimp，建立電子報和電子郵件行銷活動。

## <a name="prerequisites"></a>先決條件

-   您具有 [Mailchimp 帳戶](https://mailchimp.com/) 及對應的系統管理員認證。
-   Mailchimp 和對應的識別碼中有現有的對象。 如需詳細資訊，請參閱 [Mailchimp 對象](https://mailchimp.com/help/create-audience/)。
-   您有 [組態的區段](segments.md)
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="connect-to-mailchimp"></a>連線至 Mailchimp

1. 移至 **管理員** > **匯出目的地**。

1. 請在 **Mailchimp** 下方選取 **設定**。

1. 在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 輸入您的 **[Mailchimp 對象識別碼](https://mailchimp.com/help/find-audience-id/)** 然後選取 **連接** 初始化到 Mailchimp 的連接。

1. 選取 **使用 Mailchimp 驗證** 並提供您的 Mailchimp 認證。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="匯出 Mailchimp 連接的螢幕截取畫面":::

1. 選取 **下一步** 以設定匯出。

## <a name="configure-the-connector"></a>設定連接器

1. 在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。 

1. 或者將 **名字** 和 **姓氏** 匯出為其他欄位，以建立更多個人化電子郵件。 選取 **新增屬性** 對應這些欄位。

1. 選取您要匯出的客戶細分。 您總共最多可匯出 1 百萬個客戶設定檔到 Mailchimp。

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="選取要匯出到 Mailchimp 的欄位和區段":::

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。 在 Mailchimp 中，您現在可以在 [Mailchimp 對象](https://mailchimp.com/help/create-audience/) 下方找到您的區段。

## <a name="known-limitations"></a>已知限制

- 每個到 Mailchimp 的匯出最多可達 1 百萬個設定檔。
- 匯出到 Mailchimp 被限制為區段。
- 因供應商端的限制，匯出總計 1 百萬個設定檔的區段最長耗時 3 小時。 
- 您可以匯出到 Mailchimp 的設定檔數量端賴且受限於您與 Mailchimp 的合約。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Mailchimp 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Mailchimp 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]