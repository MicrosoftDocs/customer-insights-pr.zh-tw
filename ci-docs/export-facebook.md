---
title: 將客戶細分匯出至 Facebook 廣告管理員 (預覽版) (含影片)
description: 了解如何設定連接並匯出至 Facebook 廣告管理員。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724574"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>將客戶細分匯出至 Facebook Ads 管理員 (預覽版)

將統一客戶設定檔的區段匯出至 Facebook 廣告管理員，以建立 Facebook 和 Instagram 上的行銷活動。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>先決條件

- [Facebook 廣告帳戶](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) 且其中包含 [Facebook 商務帳戶](https://business.facebook.com/)。
- [Facebook 廣告帳戶](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)上的管理員權限。
- 要在 Customer Insights 中設定關係的使用者必須接受「自訂受眾條款」。

## <a name="known-limitations"></a>已知限制

- 最多可以匯出 10 百萬個客戶設定檔到 Facebook 廣告管理員，最長需要 90 分鐘才能完成。
- 僅客戶細分。
- Facebook Ads 整合不支援擁有超過 25 個廣告帳戶的使用者。
- 僅 [客戶對象](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)中的 Facebook *客戶清單*。
  > [!NOTE]
  > 在某些案例中，您可能會在下拉式清單中看到不同類型的自訂對象。 如果選擇 *客戶清單* 以外的類型，則匯出失敗。

## <a name="set-up-connection-to-facebook-ads-manager"></a>設定與 Facebook 廣告管理員的連接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Facebook 廣告管理員**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. [允許參與者使用匯出連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 進行 Facebook 廣告驗證：

   1. 選取 **繼續使用 Facebook**，登入您的 Facebook Ads 帳戶。

   1. 使用 Facebook 驗證之後，允許 **ads_management** 權限。

   1. 選取您要使用的 **Facebook 廣告帳戶**。

   1. 從下拉式清單中選取 **現有的自訂觀眾**，或建立 **新的自訂觀眾**。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 Facebook 廣告管理員區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 在 **連接資料** 欄位中，選取要傳送給 Facebook 廣告管理員的 **電子郵件**、**姓名和地址** 或 **電話**。

1. 從您的統一客戶實體中對應所選金鑰識別元的相應屬性。
   > [!TIP]
   > 如果您選取 **電子郵件** 做為金鑰識別元，則最有可能找到有相符項目。 新增其他識別元可能會改善比對情況。

1. 選取 **新增屬性** 對應更多屬性，以傳送至 Facebook 廣告管理員。 Facebook 廣告管理員中的屬性將會對應至下列友善使用者的名稱：**FN** = **名**、**LN** = **姓氏**、**FI** = **名字字首**、**PHONE** = **電話**、**GEN** = **性別**、**DOB** = **出生日期**、**ST** = **縣/市**、**CT** = **市/鎮**、**ZIP** = **郵遞區號**、**COUNTRY** = **國家/地區**

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
