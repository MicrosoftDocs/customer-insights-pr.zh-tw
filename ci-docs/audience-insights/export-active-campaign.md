---
title: 將 Customer Insights 資料匯出到 ActiveCampaign
description: 了解如何設定連接並匯出到 ActiveCampaign。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 089b9b0d76437e695f797f941ed384734d8f772e
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227799"
---
# <a name="export-segments-to-activecampaign-preview"></a>匯出客戶細分到 ActiveCampaign (預覽版)

將整合客戶個人資料的客戶細分匯出到 ActiveCampaign ，並將其用在行銷活動上。

## <a name="prerequisites"></a>先決條件

-   您有一個 [ActiveCampaign 帳戶](https://www.activecampaign.com/)和相應的系統管理員認證。
-   您在對象見解中具有 [組態區域](segments.md) 權限。
-   在匯出的客戶細分中，整合的客戶個人資料包含有電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 您最多可以匯出 1 百萬個客戶設定檔到 ActiveCampaign，它需要長達 90 分鐘完成。
- 匯出到 ActiveCampaign 僅限於客戶細分。
- 您可以匯出到 ActiveCampaign 的客戶設定檔數目取決於您和 ActiveCampaign 簽訂的契約。

## <a name="set-up-connection-to-activecampaign"></a>設定到 ActiveCampaign 的連接

1. 移至 **管理** > **連接**。

1. 選擇 **新增連接** 並選擇 **ActiveCampaign** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 輸入您的 [ActiveCampaign API 金鑰與 REST 端點主機名稱](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key)。 REST 端點主機名稱僅是主機名稱，沒有 https://。 

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 來初始化 ActiveCampaign 連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出連接** 欄位中，從 ActiveCampaign 區段選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 輸入您的 [**ActiveCampaign 清單識別碼**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign)。    

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。 這需要匯出客戶細分到 ActiveCampaign。 或者，您可以匯出名字、姓氏和電話來建立更個人化的電子郵件。 選取 新增屬性 對應這些欄位。

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸到 ActiveCampaign 時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在的敏感性資料 (例如個人資料)。 Microsoft 將會依您的指示傳送這類資料，但是您必須負責確保 ActiveCampaign 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，不再繼續使用此功能。
