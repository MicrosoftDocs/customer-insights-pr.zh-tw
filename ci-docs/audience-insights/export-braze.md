---
title: 將 Customer Insights 資料匯出至 Braze
description: 了解如何設定 Braze 的連線和匯出。
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8d7cf95c1f157c771b2d655346464e5af03d73b9
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524144"
---
# <a name="export-segment-lists-to-braze-preview"></a>將客戶細分清單匯出至 Braze (預覽版)

將整合客戶個人資料客戶細分匯出至 Braze，並在行銷活動使用。

## <a name="prerequisites"></a>先決條件

-   您擁有 [Braze 帳戶](https://www.braze.com/)及對應的系統管理員認證。
-   您在對象見解中具有 [組態區域](segments.md) 權限。
-   在匯出客戶細分中的整合客戶個人資料，包含表示電子郵件地址和 Braze 客戶識別碼的欄位。 

## <a name="known-limitations"></a>已知限制

- 對 Braze 的匯出限制為客戶細分。
- 匯出達 1 百萬個客戶個人資料到 Braze 需要花費最多 40 分鐘完成。 
- 您可以匯出到 Braze 的客戶個人資料數量取決於並受限於您和 Braze 簽訂的合約。

## <a name="set-up-connection-to-braze"></a>設定至 Braze 的連線

1. 移至 **管理** > **連接**。

1. 選取 **新增連線**，然後選擇 **Braze** 來設定連線。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供您的 [BRAZE API 金鑰](https://www.braze.com/docs/api/basics/)以繼續登入。 

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連線**，初始化 Braze 的連線。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出用的連線** 欄位，到 Braze 區段中選擇連線。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。  

3. 在 **資料比對** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的欄位，並在「客戶識別碼」欄位中，選取代表客戶 Braze 識別碼的欄位。 這對匯出至 Braze 的資料客戶細分是必要的。 Braze 中建立的客戶細分將與 Dynamics 365 Customer Insights 的客戶細分名稱相同。 您可以為匹配資料選擇其他的可選欄位。 

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 對 Braze 的資料傳輸時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，其中包括潛在敏感性資料，如個人資料。 Microsoft 將會在您指示時傳送這類資料，但是您必須負責確保 Braze 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。
