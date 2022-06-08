---
title: 將 Customer Insights 資料匯出至 Criteo
description: 了解如何設定 Criteo 的連線和匯出。
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 854f5f0c53f053fc5d742d69a045db1926fec00c
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808761"
---
# <a name="export-segments-to-criteo-preview"></a>將客戶細分匯出至 Criteo (預覽版)

匯出統一客戶設定檔的客戶細分以產生廣告活動、提供電子郵件行銷，並且搭配 Criteo 使用特定的客戶群組。

## <a name="prerequisites-for-connection"></a>連接的先決條件

-   您擁有 [Criteo Dynamics Retargeting 帳戶](https://www.criteo.com/login/)及對應的系統管理員認證。
-   您有 [組態的區段](segments.md)。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 每次匯出到 Criteo 的客戶設定檔多達 1 百萬。
- 對 Criteo 的匯出限制為客戶細分。
- 總計匯出 1 百萬個客戶設定檔的區段最久會花費 30 分鐘。 
- 您可以匯出到 Criteo 的客戶個人資料數量取決於並受限於您和 Criteo 簽訂的合約。

## <a name="set-up-connection-to-criteo"></a>設定至 Criteo 的連線

1. 移至 **管理** > **連接**。

1. 選取 **新增連線**，然後選擇 **Criteo** 來設定連線。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 選取 **我同意** 確認 **資料隱私權與合規性**，並選取 **連接** 來初始化與 Criteo 的連線。

1. 選取 **使用 Criteo 進行驗證**，並提供 Criteo 的系統管理員使用者名稱和認證。 

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出用的連線** 欄位，從 Criteo 區段中選擇連線。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。 

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。 

1. 或者，您可以匯出 **廣告客戶識別碼** 及 **名稱**

1. 選取您要匯出的客戶細分。 

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 對 Criteo 的資料傳輸時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，其中包括潛在敏感性資料，如個人資料。 Microsoft 將會在您指示時傳送這類資料，但是您必須負責確保 Criteo 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。


[!INCLUDE[footer-include](includes/footer-banner.md)]
