---
title: 將資料匯出至 Salesforce Marketing Cloud 中 (預覽版)
description: 了解如何設定連接並匯出到 Salesforce Marketing Cloud。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197028"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>將資料匯出至 Salesforce Marketing Cloud 中 (預覽版)

通過安全檔案傳輸協定 (SFTP) 位置匯出客戶資料，在 Salesforce Marketing Cloud 中使用它們。

## <a name="prerequisites"></a>先決條件

- [Salesforce Marketing Cloud 的 SFTP 主機](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5)及對應的管理員認證。

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>設置與 Salesforce Marketing Cloud 的連接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選擇 **新增連接**，然後選擇 **Salesforce Marketing Cloud**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供 **使用者名稱**、**密碼**、 **主機名稱** 和 **匯出資料夾** 給您的 SFTP 帳戶。

1. 選取 **驗證** 以測試連接。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 SFTP 區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 選擇是否要以 **Gzipped** 或 **解壓縮** 方式匯出您的資料，以及匯出檔案的 **欄位分隔符號**。

1. 選取您要匯出的實體 (例如客戶細分)。

   > [!NOTE]
   > 匯出時，每個選取的實體會分割成最多五個輸出檔案。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>將 Customer Insights 資料從 SFTP 位置匯入到 Salesforce Marketing Cloud

1. 建立 [Salesforce Marketing Cloud 中的資料擴充](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)，以便從 SFTP 位置匯入 Customer Insights 資料檔案。

2. [將來自 SFTP 位置的資料匯入 ](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) 到 Salesforce Marketing Cloud 資料擴充。

3. 設定自動化，將資料匯入資料擴充。 了解有關[檔案卸除自動化和排程自動化](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)。

   定義 [檔案卸除自動化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5)或[排程自動化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)。

這是 [SFTP 自動化](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)的範例。

[!INCLUDE [footer-include](includes/footer-banner.md)]
