---
title: 匯出 Customer Insights 資料到 Autopilot
description: 了解如何設定連接並匯出至 Autopilot。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7a7a67a52fcf39da8d50bd95817d25470fc90b6f
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227656"
---
# <a name="export-segments-to-autopilot-preview"></a>將客戶細分匯出至 Autopilot (預覽版)

將統整客戶設定檔的客戶細分匯出至 Autopilot，並在 Autopilot 中用來進行電子郵件行銷。 

## <a name="prerequisites-for-a-connection"></a>連接的先決條件

-   您具有 [Autopilot 帳戶](https://www.autopilothq.com/) 及對應的系統管理員認證。
-   您在對象見解中具有 [組態區域](segments.md) 權限。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 您總共可以匯出 100,000 個客戶設定檔到 Autopilot。
- 匯出到 Autopilot 被限制在客戶細分。
- 匯出高達 100,000 個客戶設定檔到 Autopilot 最長花費數小時完成。 
- 您可以匯出到 Autopilot 的客戶設定檔數目取決於並受限於您和 Autopilot 簽訂的契約。

## <a name="set-up-connection-to-autopilot"></a>設定對 Autopilot 的連接

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Autopilot** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 請輸入 [Autopilot API 金鑰](https://autopilot.docs.apiary.io/#)。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 初始化與 Autopilot 的連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 Autopilot 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。 對其他可選欄位 (如 **名**、**姓**) 重複相同步驟。

1. 選取您要匯出的客戶細分。 我們強烈 **建議您不要匯出總計超過 100'000 份客戶設定檔** 到 Autopilot。 

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 來傳輸資料給 Autopilot，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，其中包括潛在敏感資料 (如個人資料)。 Microsoft 將依據您的指示傳輸此資料，但您有責任確保 Autopilot 符合任何您承擔的隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
