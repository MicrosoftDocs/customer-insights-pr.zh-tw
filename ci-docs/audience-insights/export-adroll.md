---
title: 匯出 Customer Insights 資料到 AdRoll
description: 了解如何設定連接並匯出至 AdRoll。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f9373ea18e77723c988392a5a2959baa66d8eae9
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617321"
---
# <a name="export-segments-to-adroll-preview"></a>將客戶細分匯出至 AdRoll (預覽版)

將統整客戶個人資料的客戶細分匯出至 AdRoll，並用來進行廣告。 

## <a name="prerequisites-for-a-connection"></a>連接的先決條件

-   您具有 [AdRoll 帳戶](https://www.adroll.com/) 及對應的系統管理員認證。
-   您在對象見解中具有 [組態區域](segments.md) 權限。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 您一次最多可以匯出 250,000 個客戶設定檔到 AdRoll。
- 您不能匯出少於 100 個客戶設定檔的區段到 AdRoll。 
- 對 AdRoll 的匯出被限制為客戶細分。
- 將最多 250,000 個客戶設定檔匯出到 AdRoll 最長會花費 10 分鐘完成。 
- 您可以匯出 AdRoll 的客戶設定檔數目取決於您和 AdRoll 簽訂的契約。

## <a name="set-up-connection-to-adroll"></a>設定到 AdRoll 的連接

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **AdRoll** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 初始化與 AdRoll 的連接。

1. 選取 **使用 AdRoll 驗證** 並提供您的 AdRoll 管理員認證。 

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 AdRoll 區段中選擇連接。 如果您沒有看到此區段名稱，則代表此類型中的連接沒有您可以使用的。

1. 輸入您的 **AdRoll 廣告客戶識別碼**。 如需詳細資訊，請參閱 [AdRoll 廣告客戶個人資料](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)。

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。 必需將客戶細分匯出至 AdRoll。

1. 選取您要匯出的客戶細分。 選取一個包含最少 100 個成員的客戶細分。 您無法匯出更小的客戶細分。 此外，匯出一個客戶細分的最大數量為每個匯出 250,000 個成員。 

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 

您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 AdRoll 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 AdRoll 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，不再繼續使用此功能。
