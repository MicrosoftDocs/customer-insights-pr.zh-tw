---
title: 匯出 Customer Insights 資料到 Google Ads
description: 瞭解如何組態到 Google Ads 的連接。
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568412"
---
# <a name="connector-for-google-ads-preview"></a>Google Ads 的連接器 (預覽版)

將統一客戶設定檔區段匯出到 Google Ads 對象清單，並用它們在 Google Search、Gmail、YouTube 和 Google Display Network 上刊登廣告。 

## <a name="prerequisites"></a>先決條件

-   您具有 [Google Ads 帳戶](https://ads.google.com/) 及對應的系統管理員認證。
-   Google Ads 和對應的識別碼中有現有的對象。 如需詳細資訊，請參閱 [Google Ads 對象](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)。
-   您有 [組態的區段](segments.md)
-   匯出區段的統一客戶設定檔包含代表電子郵件地址、名字和姓氏的欄位

## <a name="connect-to-google-ads"></a>連線至 Google Ads

1. 移至 **管理員** > **匯出目的地**。

1. 請在 **Google Ads** 下方選取 **設定**。

1. 在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。

1. 輸入您的 **[Google Ads 客戶識別碼](https://support.google.com/google-ads/answer/1704344)**。

1. 輸入您的 **[Google Ads 核准的開發人員權杖](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 輸入您的 **[Google Ads 對象識別碼](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** 然後選取 **連接** 初始化到 Google Ads 的連接。

1. 選取 **使用 Google Ads 驗證** 並提供您的 Google Ads 認證。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="匯出 Google Ads 連接的螢幕截取畫面":::

1. 選取 **下一步** 以設定匯出。

## <a name="configure-the-connector"></a>設定連接器

1. 在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。 針對 **名字** 和 **姓氏** 欄位重複相同步驟。

1. 選取您要匯出的客戶細分。 您總共最多可匯出 1 百萬個客戶設定檔到 Google Ads。

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。 在 Google Ads 中，您現在可以在 [Google Ads 對象](https://support.google.com/google-ads/answer/7558048?hl=en/) 下方找到您的區段。

## <a name="known-limitations"></a>已知限制

- 每個到 Google Ads 的匯出最多可達 1 百萬個設定檔。
- 匯出到 Google Ads 被限制為區段。
- 因供應商端的限制，匯出總計 1 百萬個設定檔的區段最長耗時 5 分鐘。 
- Google Ads 中的相符最長耗時 48 小時。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Google Ads 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Google Ads 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。
