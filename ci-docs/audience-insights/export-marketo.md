---
title: 匯出 Customer Insights 資料到 Marketo
description: 瞭解如何組態到 Marketo 的連接。
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597961"
---
# <a name="connector-for-marketo-preview"></a>適用 Marketo 的連接器 (預覽版)

匯出統一的客戶設定檔區段以便產生行銷活動，提供電子郵件行銷及使用含 Marketo 的特定族群客戶。

## <a name="prerequisites"></a>先決條件

-   您具有 [Marketo 帳戶](https://login.marketo.com/) 及對應的系統管理員認證。
-   Marketo 和對應的識別碼中有現有的清單。 如需詳細資訊，請參閱 [ Marketo 清單](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)。
-   您有 [組態的區段](segments.md)。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="connect-to-marketo"></a>連線到 Marketo

1. 移至 **管理員** > **匯出目的地**。

1. 請在 **Marketo** 下方選取 **設定**。

1. 在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。

1. 輸入您的 **[Marketo 用戶端識別碼、用戶端秘密和 REST 端點主機名稱](https://developers.marketo.com/rest-api/authentication/)**。

1. 輸入您的 **[Marketo 清單識別碼](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. 選取 **我同意** 以便確認 **資料隱私權與合規性** 和選取 **連線** 初始化到 Marketo 的連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

   :::image type="content" source="media/export-connect-marketo.png" alt-text="匯出 Marketo 連接的螢幕截取畫面":::

1. 選取 **下一步** 以設定匯出。

## <a name="configure-the-connector"></a>設定連接器

1. 在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。 

1. 或者將 **名字**、**姓氏**、**城市**、**州** 和 **國家/區域** 匯出為其他欄位，以建立更多個人化電子郵件。 選取 **新增屬性** 對應這些欄位。

1. 選取您要匯出的客戶細分。 您總共最多可匯出 1 百萬個客戶設定檔到 Marketo。

   :::image type="content" source="media/export-segment-marketo.png" alt-text="選取要匯出到 Marketo 的欄位和區段":::

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。 在 Marketo 中，您現在可以在 [Marketo 清單](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) 下方找到您的區段。

## <a name="known-limitations"></a>已知限制

- 每個到 Marketo 的匯出最多可達 1 百萬個設定檔。
- 匯出到 Marketo 被限制為區段。
- 匯出總計為 1 百萬個設定檔的分段可能需要 3 小時的時間。 
- 您可以匯出到 Marketo 的設定檔數量端賴且受限於您與 Marketo 的合約。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Marketo 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Marketo 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]