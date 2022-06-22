---
title: 將 Customer Insights 資料匯出至 Snapchat
description: 了解如何設定連接並匯出至 Snapchat。
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d64b482c322af8632e29ec41d6e34c390c5e646c
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947266"
---
# <a name="export-segments-to-snapchat-preview"></a>將客戶細分匯出至 Snapchat (預覽版)

將整合客戶個人資料的客戶細分匯出至 Snapchat，並用於廣告。 

## <a name="prerequisites-for-a-connection"></a>連接的先決條件

-   您擁有 [Snapchat 商務帳號](https://business.snapchat.com/)、[Snapchat 廣告帳號](https://ads.snapchat.com/)以及對應的系統管理員認證。 您必須至少是組織帳戶的成員，以及指定 AD 帳戶的資料管理員。 
-   在 Snapchat 對象管理者中，至少有一個類型為 SAM (Snap 對象對比) 的對象。 
-   在 Customer Insights 中，您具有[已設定的客戶細分](segments.md)。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 匯出到 Snapchat 時，會被限制為客戶細分。
- 匯出多達 1 百萬個客戶設定檔到 Snapchat 最長花費 15 分鐘完成。 

## <a name="set-up-connection-to-snapchat"></a>設定與 Snapchat 的連接

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Snapchat** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 來初始化與 Snapchat 的連接。

1. 選取 **與 Snapchat 驗證**，並提供系統管理員認證給 Snapchat。 

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 Snapchat 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 輸入 [**Snapchat 客戶細分/對象識別碼**](https://businesshelp.snapchat.com/s/article/custom-audiences)。 在 Snapchat 觀眾管理者中選取對象之後，即可在 URL 中找到對象的識別碼。 

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。 這必須匯出客戶細分到 Snapchat。

1. 選取您要匯出的客戶細分。 

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸至 Snapchat 時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。 Microsoft 將會在您的指示下傳送這類資料，但是您必須負責確保 Snapchat 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。
