---
title: SFTP 自訂匯入的富集
description: 有關SFTP 自訂匯入富集的一般資訊。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 9331cf8057850e2fbe03622831f388e73056d938
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555389"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>使用自訂資料富集客戶設定檔 (預覽版)

安全檔案傳輸通訊協定 (SFTP) 自訂匯入功能可讓您匯入不需要透過資料統一處理的資料。 那是一種靈活、安全且容易帶入您的資料的方式。 SFTP 自訂匯入功能可以和 [SFTP 匯出](export-sftp.md) 功能搭配使用，讓您匯出富集所需的客戶設定檔資料。 然後可以處理和擴充資料，並使用 SFTP 自訂匯入將擴充後的資料帶回 Dynamics 365 Customer Insights 的對象見解功能。

## <a name="prerequisites"></a>先決條件

若要組態 SFTP 自訂匯入，您務必符合下列先決條件：

- 您擁有將在 SFTP 主機上匯入的檔案名稱和位置 (路徑)。
- 檔案 *model.json*，會為要匯入的資料指定 [Common Data Model 結構描述](/common-data-model/)。 此檔案必須和將匯入的檔案在同一個目錄中。
- SFTP 連接已由系統管理員設定，*或* 您擁有[系統管理員](permissions.md#administrator)權限。 您會需要 SFTP 位置的使用者認證、URL 及連接埠號碼，該 SFTP 位置是匯入資料的所在處。


## <a name="configure-the-import"></a>設定匯入

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 **SFTP 自訂匯入圖格** 上選取 **擴充我的資料**，然後選取 **開始使用**。

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP 自訂匯入圖格。":::

1. 從下拉式清單選取一個[連結](connections.md)。 如果沒有可用的連接，請與系統管理員聯繫。 如果您是系統管理員，則可以選取 **新增連接**，然從下拉式清單中選擇 **SFTP 自訂匯入**，來建立連接。

1. 選取 **連接至自訂匯入** 以確認選取的連接。

1.  選取 **下一步**，然後輸入您要匯入的資料檔案的 **路徑** 和 **檔案名**。

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="輸入資料位置時的螢幕擷取畫面。":::

1. 選取 **下一步** 並提供擴充的名稱以及輸出實體的名稱。 

1. 檢閱選擇之後，請選取 **儲存擴充**。

## <a name="configure-the-connection-for-sftp-custom-import"></a>為 SFTP 自訂匯入設定連接 

您必須是系統管理員才能設定連接。 在設定擴充時，請選取 **新增連接***或* 在自訂匯入圖格上移至 **管理** > **連接** 並選取 **設定**。

1. 在 **顯示名稱** 方塊中輸入連接的名稱。

1. 輸入匯入的資料駐留的 SFTP 伺服器其有效的使用者名、密碼及主機 URL。

1. 選取 **我同意** 核取方塊，以檢閱 **資料隱私權和合規性** 並表示同意。

1. 選取 **驗證** 來驗證設定。

1. 驗證完成後，您可以選取 **儲存** 來儲存連接。

   > [!div class="mx-imgBorder"]
   > ![Experian 連接設定頁面。](media/enrichment-SFTP-connection.png "Experian 連接設定頁面")


## <a name="defining-field-mappings"></a>定義欄位對應 

包含將在 SFTP 伺服器上匯入檔案的目錄也必須包含 *model.json* 檔案。 此檔案定義用來匯入資料的結構描述。 結構描述必須使用 [Common Data Model](/common-data-model/) 來指定欄位對應。 model.json 檔案的簡易範例如下：

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>擴充結果

若要開始擴充程序，請從命令列中選取 **執行**。 您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。 處理時間將視要匯入資料的大小和 SFTP 伺服器的連接而定。

富集流程完成後，您可以在 **我的富集群** 下方評論新匯入的自訂富集資料。 此外，您還會找到上次更新時間以及已擴充的設定檔數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

## <a name="next-steps"></a>後續步驟

建立在您擴充的客戶資料之上。 建立[客戶細分](segments.md)和[量值](measures.md)，和[匯出資料](export-destinations.md)，為您的客戶提供個人化的體驗。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
