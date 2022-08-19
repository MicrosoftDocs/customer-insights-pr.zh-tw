---
title: 透過 SFTP 自訂匯入來擴充客戶設定檔 (預覽版)
description: 有關SFTP 自訂匯入富集的一般資訊。
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237756"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>透過 SFTP 自訂匯入來擴充客戶設定檔 (預覽版)

安全檔案傳輸通訊協定 (SFTP) 自訂匯入功能可讓您匯入不需要透過資料統一處理的資料。 那是一種靈活、安全且容易帶入您的資料的方式。 SFTP 自訂匯入功能可以和 [SFTP 匯出](export-sftp.md) 功能搭配使用，讓您匯出富集所需的客戶設定檔資料。 然後可以處理和擴充資料，而 SFTP 自訂匯入可以用來將已擴充資料傳回 Dynamics 365 Customer Insights。

## <a name="prerequisites"></a>先決條件

- 要匯入到 SFTP 主機上的檔案，其名稱與位置 (路徑) 是已知的。

- 指定匯入資料的 Common Data Model 結構描述的 *model. json* 檔案可以使用。 此檔案必須和將匯入的檔案在同一個目錄中。

- SFTP[連接](connections.md)已[設定](#configure-the-connection-for-sftp-custom-import)。

## <a name="file-schema-example"></a>檔案結構描述範例

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>為 SFTP 自訂匯入設定連接

您必須是 Customer Insights 的[系統管理員](permissions.md#admin)，且在資料匯入起點的 SFTP 位置擁有其使用者認證、URL 及連接埠號碼。

1. 在設定擴充時，請選取 **新增連接** 或前往 **管理** > **連接** 並在自訂匯入磚上選取 **設定**。

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="自訂匯入的連接設定頁面":::

1. 輸入連接的名稱

1. 輸入匯入的資料駐留的 SFTP 伺服器其有效的使用者名、密碼及主機 URL。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **驗證** 來驗證設定，然後選取 **儲存**。

## <a name="configure-the-import"></a>設定匯入

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 **SFTP 自訂匯入** 磚中，選取 **擴充我的資料**。

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP 自訂匯入圖格。":::

1. 檢閱概覽，然後選擇 **下一步**。

1. 選取連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. **選取顧客資料集**，然後選擇要擴充的個人資料或客戶細分。 *Customer* 實體可擴充所有客戶個人資料，然而客戶細分實體僅擴充位於該客戶細分的客戶個人資料。

1. 選取 **下一步**。

1. 輸入您要匯入的資料檔案的 **路徑** 和 **檔案名稱**。

1. 選取 **下一步**。

1. 請提供擴充的 **名稱** 與 **輸出實體名稱**。

1. 檢閱選擇之後，請選取 **儲存擴充**。

1. 選取 **執行** 以開始擴充程序，或者直接關閉返回至 **擴充** 頁面。

## <a name="view-enrichment-results"></a>查看擴充結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
