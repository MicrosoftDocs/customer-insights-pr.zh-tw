---
title: 將 Customer Insights 資料匯出至 Constant Contact
description: 了解如何設定連接並匯出至 Constant Contact。
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124263"
---
# <a name="export-segments-to-constant-contact-preview"></a>將客戶細分匯出至 Constant Contact (預覽版)

將整合客戶個人資料的客戶細分匯出至 Constant Contact，並用於行銷活動。 

## <a name="prerequisites-for-a-connection"></a>連接的先決條件

-   您擁有一個 [Constant Contact 帳戶](https://www.constantcontact.com/account-home)及對應的系統管理員認證。
-   您在對象見解中具有 [組態區域](segments.md) 權限。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 每筆匯出中您最多可以將 1 百萬筆個人資料匯出至 Constant Contact。
- 匯出到 Constant Contact 時，會被限制為客戶細分。
- 將最多 1 百萬筆個人資料匯出至 Constant Contact 可能需要花費 1 小時的時間才能完成。 
- 您可以匯出至 Constant Contact 的個人資料數量與 Constant Contact 的合約有關且受到其限制。

## <a name="set-up-connection-to-constant-contact"></a>設定與 Constant Contact 的連結

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Constant Contact** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 來初始化與 Constant Contact 的連接。

1. 選取 **與 AdRoll 驗證**，並提供系統管理員認證給 Constant Contact。 

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 Constant Contact 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 輸入您的 [**Constant Contact 清單識別碼**](https://app.constantcontact.com/pages/contacts/ui#lists)。 在 Constant Contact 中打開清單，以尋找 URL 中的清單識別碼。

1. 在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。 這必須匯出客戶細分到 Constant Contact。

1. 或者將 名字 和 姓氏 匯出為其他欄位，以建立更多個人化電子郵件。 選取 **新增屬性** 對應這些欄位。

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸至 Constant Contact 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。 Microsoft 將會在您的指示下傳送這類資料，但是您必須負責確保 Constant Contact 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。
