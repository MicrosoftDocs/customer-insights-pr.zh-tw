---
title: 將 Customer Insights 資料匯出到 Microsoft Advertising
description: 了解如何設定連接並匯出至 Microsoft Advertising。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f009ed0258ded424340061e5320dd7df68c199f
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226881"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>將客戶細分匯出至 Microsoft Advertising (預覽版)

將 Customer Insights 客戶細分匯出至 Microsoft Advertising，以建立客戶相符的對象。 將在您的廣告行銷活動使用這些對象。

## <a name="prerequisites"></a>先決條件

-   一個 [Microsoft Advertising 帳戶](https://ads.microsoft.com/)及對應的系統管理員認證。
-   您接受了客戶比對的使用條款。 
-   讚對象見解中[設定客戶細分](segments.md)。
-   在匯出的客戶細分中，整合的客戶個人資料包含有電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 每次匯出最多可以匯出 500,000 個客戶設定檔到 Microsoft Advertising。
- 匯出到 Microsoft Advertising 會被限制為客戶細分。
- 匯出多達 500,000 個客戶設定檔到 Microsoft Advertising 最長花費 10 分鐘完成。 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>設定連線至 Microsoft Advertising

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Microsoft Advertising** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 預設為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 來初始化與 Microsoft Advertising 的連接。

1. 選取 **驗證 Microsoft Advertising**，並提供您的 Microsoft Advertising 管理認證。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 Microsoft Advertising 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 選取要匯出的客戶細分。 會以選取要匯出的客戶細分名稱自動建立 Microsoft Advertising 中客戶比對的對象。 每一個客戶細分都會造成不同的客戶比對對象。 

1. 輸入您的 **Microsoft Advertising 客戶識別碼和帳戶識別碼**。 當您登入 Microsoft Advertising 時，您可以在 URL 的參數中找到客戶識別碼 (`cid`) 和帳戶識別碼 (`aid`)。

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取含客戶電子郵件地址的欄位。 這必須匯出客戶細分到 Microsoft Advertising。

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸至 Microsoft Advertising 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。 Microsoft 將會在您的指示下傳送這類資料，但是您必須負責確保 Microsoft Advertising符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，停止使用此功能。
