---
title: 匯出 Customer Insights 資料到 Facebook Ads Manager
description: 了解如何設定與 Facebook 廣告管理員的連接。
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596669"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>適用於 Facebook 廣告管理員的連接器 (預覽)

將統一客戶設定檔的區段匯出至 Facebook 廣告管理員，以建立 Facebook 和 Instagram 上的行銷活動。

## <a name="prerequisites"></a>先決條件

- 您必須具有包括 [**Facebook 商業帳戶**](https://business.facebook.com/) 的 [**Facebook 廣告帳戶**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)。
- 您在 [**Facebook 廣告帳戶**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) 上必須是管理員身份。

## <a name="connect-to-facebook-ads-manager"></a>連接至 Facebook 廣告管理員

1. 移至 **管理員** > **匯出目的地**。

1. 在 **Facebook 廣告管理員** 底下，選取 **設定**。

1. 在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。

1. 選取 **繼續使用 Facebook** 登入您的 Facebook 廣告帳戶。

1. 使用 Facebook 驗證之後，允許 **ads_management** 權限。

1. 選取您要使用的 **Facebook 廣告帳戶**。

1. 從下拉式清單選取 **現有的自訂對象**，或建立 **新的自訂對象**。 如需詳細資訊，請參閱 [**Facebook 廣告管理員中的對象**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **下一步** 以設定匯出。

## <a name="configure-the-connector"></a>設定連接器

1. 在 **選擇金鑰識別元欄位** 中，選取要傳送給 Facebook 廣告管理員的 **電子郵件**、**姓名和地址** 或 **電話**。

1. 從您的統一客戶實體中對應所選金鑰識別元的相應屬性。
   > [提示] 如果您選取 **電子郵件** 做為金鑰識別元，則最有可能找到有相符項目。 新增其他識別元可能會改善比對情況。

1. 選取 **新增屬性** 以對應要傳送至 Facebook 廣告管理員的其他屬性。 Facebook 廣告管理員中的屬性將會對應至下列使用者易記的名稱：**FN** = **名字**、**LN** = **姓氏**、**FI** = **名字首字母**、**PHONE** = **電話**、**GEN** = **性別**、**DOB** = **出生日期**、**ST** = **縣/市**、**CT** = **市/鎮**、**ZIP** = **郵遞區號**、**COUNTRY** = **國家/地區**

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。

## <a name="known-limitations"></a>已知限制

- 每次最多可匯出 1 千萬份客戶設定檔至 Facebook 廣告管理員 
- 匯出到 Facebook 廣告管理員被限制在資料細分
- 以總計為 1 千萬份的設定檔匯出客戶細分可能需要 90 分鐘完成

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Facebook Ads Manager 時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Facebook 廣告符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]