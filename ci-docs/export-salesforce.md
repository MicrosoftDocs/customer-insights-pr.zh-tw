---
title: 將資料匯出至 Salesforce Marketing Cloud 中 (預覽版)
description: 了解如何設定連接並匯出到 Salesforce Marketing Cloud。
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080899"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>將資料匯出至 Salesforce Marketing Cloud 中 (預覽版)

通過安全檔案傳輸協定 (SFTP) 位置匯出客戶資料，在 Salesforce Marketing Cloud 中使用它們。

## <a name="prerequisites-for-connection"></a>連接的先決條件

- 可用的 SFTP 主機和相應的系統管理員認證。 [如何為 Salesforce Marketing Cloud 設定 SFTP 位置](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>設置與 Salesforce Marketing Cloud 的連接

1. 移至 **管理** > **連接**。

1. 選擇 **新增連接** 並選擇 **Salesforce Marketing Cloud** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供 **使用者名稱**、**密碼**、 **主機名稱** 和 **匯出資料夾** 給您的 SFTP 帳戶。

1. 選取 **驗證** 以測試連接。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 SFTP 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 選擇是否要以 **Gzipped** 或 **解壓縮** 方式匯出您的資料，以及匯出檔案的 **欄位分隔符號**。

1. 選取您要匯出的實體 (例如客戶細分)。

   > [!NOTE]
   > 匯出時，每個選取的實體會分割成最多五個輸出檔。 

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>將 Customer Insights 資料從 SFTP 位置匯入到 Salesforce Marketing Cloud

1. 建立 [Salesforce Marketing Cloud 中的資料擴充](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)，以便從 SFTP 位置匯入 Customer Insights 資料檔案。

2. [將來自 SFTP 位置的資料匯入 ](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) 到 Salesforce Marketing Cloud 資料擴充。 

3. 設定自動化，將資料匯入資料擴充。 了解有關[檔案卸除自動化和排程自動化](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)。

   定義 [檔案卸除自動化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5)或[排程自動化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)。 

這是 [SFTP 自動化](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)的範例。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料透過 SFTP 傳輸時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保匯出目的地符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，不再繼續使用此功能。

[!INCLUDE [footer-include](includes/footer-banner.md)]
