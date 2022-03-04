---
title: 匯出 Customer Insights 資料到 Google Ads
description: 了解如何設定連接並匯出至 Google Ads。
ms.date: 09/27/2021
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28e2b35c5a47a025b8cdcccdb3f61c79878bf056
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227000"
---
# <a name="export-segments-to-google-ads-preview"></a>將客戶細分匯出至 Google Ads (預覽版)

將整合客戶個人資料的客戶細分匯出到 Google Ads 對象清單中，並在 Google 搜尋、Gmail、YouTube和 Google Display Network 上使用它們進行廣告宣傳。 

> [!IMPORTANT]
> 目前，您只能建立新的連接，並將資料匯出至 Google Ads (如果您已經擁有受核准的 Google Ads 開發人員權杖)。 由於原則變更，我們將稍後更新 Google Ads 匯出，並提供不需要開發人員權杖的匯出選項，來確保您的體驗連續性並簡化匯出至 Google Ads 的過程。 我們建議您不要設定更多的 Google Ads 連接，以便更輕鬆地切換至新的匯出選項。

## <a name="prerequisites-for-connection"></a>連接的先決條件

-   您具有 [Google Ads 帳戶](https://ads.google.com/) 及對應的系統管理員認證。
-   您擁有[受核准的 Google Ads 開發人員權杖](https://developers.google.com/google-ads/api/docs/first-call/dev-token)。 
-   您滿足[客戶比對原則](https://support.google.com/adspolicy/answer/6299717)的要求。
-   您滿足[再行銷清單大小](https://support.google.com/google-ads/answer/7558048)的要求。
-   Google Ads 和對應的識別碼中有現有的對象。 如需詳細資訊，請參閱 [Google Ads 對象](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)。
-   您有 [組態的區段](segments.md)。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址、名字和姓氏的欄位。

## <a name="known-limitations"></a>已知限制

- 每次可匯出多達 1 百萬個客戶設定檔到 Google Ads。
- 匯出到 Google Ads 被限制為區段。
- 匯出總計 1 百萬個客戶設定檔的區段會因為供應商端的限制而花費 5 分鐘完成。 
- Google Ads 中的相符最長耗時 48 小時。

## <a name="set-up-connection-to-google-ads"></a>設定與 Google Ads 的連接

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Google Ads** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 輸入您的 **[Google Ads 客戶識別碼](https://support.google.com/google-ads/answer/1704344)**。

1. 輸入您的 **[Google Ads 核准的開發人員權杖](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **使用 Google Ads 驗證** 並提供您的 Google Ads 認證。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。 

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 Google Ads 區段中選擇連接。 如果您沒有看到此區段名稱，則代表此類型中的連接沒有您可以使用的。

1. 輸入您的 **[Google Ads 對象識別碼](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** 然後選取 **連接** 初始化到 Google Ads 的連接。

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。

1. 選取您要匯出的客戶細分。 您總共最多可匯出 1 百萬個客戶設定檔到 Google Ads。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 

您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Google Ads 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Google Ads 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
