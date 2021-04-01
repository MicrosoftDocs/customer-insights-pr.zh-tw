---
title: SFTP 自訂匯入的富集
description: 有關SFTP 自訂匯入富集的一般資訊。
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595845"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>使用自訂資料富集客戶設定檔 (預覽版)

安全檔案傳輸通訊協定 (SFTP) 自訂匯入功能可讓您匯入不需要透過資料統一處理的資料。 那是一種靈活、安全且容易帶入您的資料的方式。 SFTP 自訂匯入功能可以和 [SFTP 匯出](export-sftp.md) 功能搭配使用，讓您匯出富集所需的客戶設定檔資料。 接著資料可以處理、富集和 SFTP 自訂匯入，將富集後的資料帶回 Dynamics 365 Customer Insights 的對象見解功能。

## <a name="prerequisites"></a>先決條件

若要組態 SFTP 自訂匯入，您務必符合下列先決條件：

- 您具備準備匯入資料的 SFTP 位置使用者憑證 (使用者名稱與密碼)。
- 您具有 STFP 主機的 URL 和連接埠號碼 (通常是 22)。
- 您具有將匯入 SFTP 主機的檔案名稱和位置。
- 目前有一個指定將匯入資料的結構描述 *model.json* 檔案。 此檔案必須和將匯入的檔案在同一個目錄中。
- 您具有 [系統管理員](permissions.md#administrator) 權限。

## <a name="configuration"></a>組態

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 請在 **SFTP 自訂匯入圖格** 上選取 **富集我的資料**。

   > [!div class="mx-imgBorder"]
   > ![SFTP 自訂匯入圖格](media/SFTP_Custom_Import_tile.png "SFTP 自訂匯入圖格")

1. 選取 **開始使用** 並提供 SFTP 伺服器的憑證和位址。 例如，sftp://mysftpserver.com:22。

1. 輸入包含不在根資料夾時，SFTP 伺服器上檔案資料和路徑的檔案名稱。

1. 選取 **連接到自訂匯入** 確認所有輸入資料。

   > [!div class="mx-imgBorder"]
   > ![SFTP 自訂匯入組態飛出視窗](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP 自訂匯入組態飛出視窗")

## <a name="defining-field-mappings"></a>定義欄位對應 

包含將在 SFTP 伺服器上匯入檔案的目錄也必須包含 *model.json* 檔案。 此檔案定義用來匯入資料的結構描述。 結構描述必須使用 [Common Data Model](/common-data-model/) 指定欄位對應。 model.json 檔案的簡易範例如下：

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

建立在您擴充的客戶資料之上。 建立 [區段](segments.md)、[量值](measures.md) 和 [匯出資料](export-destinations.md) 以便將個人化的經驗傳遞給您的客戶。




[!INCLUDE[footer-include](../includes/footer-banner.md)]