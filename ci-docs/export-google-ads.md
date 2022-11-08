---
title: 將客戶細分匯出至 Google Ads (預覽版)
description: 了解如何設定連接並匯出至 Google Ads。
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725068"
---
# <a name="export-segments-to-google-ads-preview"></a>將客戶細分匯出至 Google Ads (預覽版)

將整合客戶個人資料的客戶細分匯出到 Google Ads 對象清單中，並在 Google 搜尋、Gmail、YouTube和 Google Display Network 上使用它們進行廣告宣傳。

## <a name="prerequisites"></a>先決條件

- [Google Ads 帳戶](https://ads.google.com/) 及對應的系統管理員認證。
- [Google Ads 客戶識別碼](https://support.google.com/google-ads/answer/1704344)。
- 滿足 [Customer Match 原則](https://support.google.com/adspolicy/answer/6299717)的要求。
- 滿足[再行銷清單大小](https://support.google.com/google-ads/answer/7558048)的要求。
- [已設定的客戶細分](segments.md)。
- 匯出的客戶細分中的整合客戶個人資料包含著代表電子郵件地址、電話、行動裝置廣告識別碼、協力廠商使用者識別碼或地址的欄位。

## <a name="known-limitations"></a>已知限制

- 不支援與自備儲存體 (BYOS) 搭配使用的私人連結。
- 每次最多可匯出 100 萬個客戶資料至 Google Ads，由於提供者方面的限制，這可能需要 30 分鐘才能完成。
- 僅客戶細分。
- Google Ads 中的比對最長耗時 48 小時。

## <a name="set-up-connection-to-google-ads"></a>設定與 Google Ads 的連接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Google Ads**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 輸入您的 Google Ads 客戶識別碼。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **使用 Google Ads 驗證** 並提供您的 Google Ads 認證。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 Google Ads 區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 選擇是使用現有對象還是建立新對象：
   - 若要更新現有的 Google Ads 對象，請輸入您的 [Google Ads 對象識別碼](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns)。
   - 若要建立新的對象，請將 Google Audience 識別碼欄位保留空白。 Customer Insights 會在 Google Ads 帳戶中自動建立新的對象，並使用匯出的客戶細分名稱。

1. 在 **資料比對** 區段中，請選取一或多個要匯出的資料欄位，並且選取與 Customer Insights 資料欄位對應的代表欄位。

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
