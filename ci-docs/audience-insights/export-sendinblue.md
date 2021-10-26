---
title: 將 Customer Insights 資料匯出到 Sendinblue
description: 了解如何設定連接並匯出到 Sendinblue。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5924b2d4e7f0b11ce6478a31015fcbaaf44ff93
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617775"
---
# <a name="export-segments-to-sendinblue-preview"></a>匯出客戶細分到 Sendinblue (預覽版)

匯出整合個人資料的客戶細分，以使用 Sendinblue 建立行銷活動、提供電子郵件行銷，並使用特定客戶群組。

## <a name="prerequisites-for-connection"></a>連接的先決條件

-   您有一個 [Sendinblue 帳戶](https://www.sendinblue.com/)和相應的系統管理員認證。
-   Sendinblue 中存在現有清單和相應的識別碼。
-   您有 [組態的區段](segments.md)。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 每次可匯出多達 1 百萬個客戶設定檔到 Sendinblue。
- 匯出到 Sendinblue 僅限於客戶細分。
- 總計匯出 1 百萬個客戶設定檔的區段最久會花費 90 分鐘。 
- 您可以匯出到 Sendinblue 的客戶設定檔數目取決於並受限於您和 Sendinblue 簽訂的契約。

## <a name="set-up-connection-to-sendinblue"></a>設定到 Sendinblue 連接

1. 移至 **管理** > **連接**。

1. 選擇 **新增連接** 並選擇 **Sendinblue** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 請輸入 **[SendinBlue API 金鑰](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**。

1. 選擇 **我同意** 確認 **資料隱私和合規性**，並選擇 **連接** 以初始化 Sendinblue 的連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出連接** 欄位中，從 Sendinblue 區段選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 輸入您的 **Sendinblue 清單識別碼** 

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。 

1. 或者，您可以匯出 **名字**、**姓氏** 和 **電話** 建立更個人化的電子郵件。 選取 **新增屬性** 對應這些欄位。

1. 選取您要匯出的客戶細分。 

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸到 Sendinblue 時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在的敏感性資料 (例如個人資料)。 Microsoft 將會依您的指示傳送這類資料，但是您必須負責確保 Sendinblue 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
