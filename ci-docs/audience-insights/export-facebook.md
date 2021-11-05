---
title: 匯出 Customer Insights 資料到 Facebook Ads Manager
description: 了解如何設定連接並匯出至 Facebook 廣告管理員。
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bb74e35799410b92b64e48e065b45efda82490ca
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "7672943"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>將客戶細分清單匯出至 Facebook 廣告管理員 (預覽版)

將統一客戶設定檔的區段匯出至 Facebook 廣告管理員，以建立 Facebook 和 Instagram 上的行銷活動。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>連接的先決條件

- 您必須擁有 [**Facebook 廣告帳戶**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) 且其中包含 [**Facebook 商務帳戶**](https://business.facebook.com/)。
- 您必須是 [**Facebook Ads 帳戶**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)上的系統管理員。

## <a name="known-limitations"></a>已知限制

- 匯出至 Facebook Ads 管理員的客戶個人資料每筆最多可達 1 千萬。
- 僅客戶細分可以匯出到 Facebook 廣告管理員。
- 僅能在 Facebook 建立或更新 *客戶清單* 類型中的自訂對象。
- 總計匯出 1 千萬個客戶設定檔區段會花費 90 分鐘完成。

## <a name="set-up-connection-to-facebook-ads-manager"></a>設定與 Facebook 廣告管理員的連接

系統管理員必須設定與服務的連接，並允許參與者使用該連接，使用者才能建立匯出。

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Facebook 廣告管理員** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 進行 Facebook 廣告驗證： 

   1. 選取 **繼續使用 Facebook**，登入您的 Facebook Ads 帳戶。

   1. 使用 Facebook 驗證之後，允許 **ads_management** 權限。

   1. 選取您要使用的 **Facebook 廣告帳戶**。

   1. 從下拉式清單中選取 **現有的自訂觀眾**，或建立 **新的自訂觀眾**。 如需詳細資訊，請參閱 [**Facebook 廣告管理員中的對象**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)。
      > [!NOTE]
      > 使用此匯出，您只能在 Facebook 建立或更新 *客戶清單* 類型中的自訂對象。 在某些案例中，您會在下拉式清單中看到不同類型的自訂對象。 選取與 *客戶清單* 不同的類型會導致匯出失敗。 

1. 請檢查 **資料隱私權和合規性**，並選取 **我同意**。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。 

1. 在 **匯出的連接** 欄位中，在 **Facebook 廣告管理員** 區段中選擇連接。 如果您沒有看到此區段名稱，則代表此類型中的連接沒有您可以使用的。

1. 在 **選擇金鑰識別元欄位** 中，選取要傳送給 Facebook 廣告管理員的 **電子郵件**、**姓名和地址** 或 **電話**。 

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。

1. 從您的統一客戶實體中對應所選金鑰識別元的相應屬性。
   > [!TIP]
   > 如果您選取 **電子郵件** 做為金鑰識別元，則最有可能找到有相符項目。 新增其他識別元可能會改善比對情況。

1. 選取 **新增屬性** 對應更多屬性，以傳送至 Facebook 廣告管理員。 Facebook 廣告管理員中的屬性將會對應至下列友善使用者的名稱：**FN** = **名**、**LN** = **姓氏**、**FI** = **名字字首**、**PHONE** = **電話**、**GEN** = **性別**、**DOB** = **出生日期**、**ST** = **縣/市**、**CT** = **市/鎮**、**ZIP** = **郵遞區號**、**COUNTRY** = **國家/地區**

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 

您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Facebook Ads Manager 時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Facebook 廣告符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
