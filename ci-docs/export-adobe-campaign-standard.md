---
title: 了解如何匯出 Customer Insights 客戶細分到 Adobe Campaign Standard (預覽版)
description: 了解如何在 Adobe Campaign Standard中使用 Customer Insights 客戶細分。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195510"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>了解如何匯出 Customer Insights 客戶細分到 Adobe Campaign Standard (預覽版)

將針對相關對象的客戶細分匯出到 Adobe Campaign Standard。

:::image type="content" source="media/ACS-flow.png" alt-text="本文概述步驟的流程圖。":::

## <a name="prerequisites"></a>先決條件

- Adobe Campaign Standard 授權。
- [Azure Blob 儲存體帳戶](/azure/storage/blobs/create-data-lake-storage-account)名稱和帳戶金鑰。 若要尋找名稱和金鑰，請參閱 [Azure 入口網站中的「管理儲存體帳戶設定」](/azure/storage/common/storage-account-manage)。
- [Azure Blob 儲存體容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

## <a name="campaign-overview"></a>行銷活動概觀

為了更好地了解如何在 Adobe Experience Platform 中使用 Customer Insights，我們來看一下虛構的範例行銷活動。

假設貴公司在美國為客戶提供每月訂閱型的服務。 您希望找出哪些客戶的訂閱是需要在未來八天內續訂但尚未續訂的。 為了留住這些客戶，您希望使用 Adobe Campaign Standard 以電子郵件對他們發送促銷優惠。

在此範例中，我們希望執行一次促銷電子郵件的行銷活動。 本文不涵蓋多次執行行銷活動的使用案例。 不過，Customer Insights 和  Adobe Campaign Standard，也能設定成適合定期行銷活動情境。

## <a name="identify-your-target-audience"></a>找出目標對象

在我們的案例中，我們假設客戶的電子郵件地址在 Customer Insights 可以使用，且分析他們的促銷喜好以確認客戶細分的成員。

在 [Customer Insights 中定義的客戶細分](segments.md)被稱為 **ChurnProneCustomers**，您計畫傳送電子郵件促銷給這些客戶。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="建立了 ChurnProneCustomers 客戶細分頁面的螢幕擷取畫面。":::

您要發送的優惠電子郵件將包含客戶的姓、名和訂閱結束日期。 此信件通知客戶，如果他們在訂閱結束前續訂訂閱，他們將獲得折扣。

## <a name="export-your-target-audience"></a>匯出目標對象

### <a name="set-up-connection-to-adobe-campaign"></a>設定與 Adobe Campaign 的連接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Adobe Campaign**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 輸入您的 Blob 儲存體帳戶的 **帳戶名稱**、**帳戶金鑰** 和 **容器**。  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="儲存體帳戶設定的螢幕擷取畫面。":::

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **儲存** 來完成連接。

### <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出連接** 欄位中，從 Adobe Campaign 區段選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 選擇您要匯出的客戶細分。 在這個例子中，它是 **ChurnProneCustomers**。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="客戶細分選擇使用者介面中已選擇 ChurnProneCustomers 客戶細分的螢幕擷取畫面。":::

1. 選取 **下一步**。

1. 將 Customer Insights 客戶細分中的 **來源** 欄位對應至 Adobe Campaign Standard 結構中的 **目標** 欄位名稱。

   :::image type="content" source="media/ACS-field-mapping.png" alt-text=" Adobe Campaign Standard 連接器的欄位對應。":::

   若要新增更多屬性，請選擇 **新增屬性**。 目標名稱可以不同於來源欄位，這樣如果兩個系統中的欄位名稱不同，就可以將 Customer Insights 中的客戶細分輸出對應至 Adobe Campaign Standard。

   > [!NOTE]
   > 電子郵件地址作為為識別欄位，但是您可以使用來自客戶個人資料的任何其他識別碼將資料對應至 Adobe Campaign Standard。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> 確保匯出的客戶細分中的記錄數量在 Adobe Campaign Standard 授權的允許範圍內。

匯出的資料儲存在前面設定的 Azure Blob 儲存體容器中。 下列資料夾路徑會在您的容器中自動建立：*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>設定 Adobe Campaign Standard

匯出的客戶細分會包含您在設定匯出時選取的資料行。 此資料可用於 [建立 Adobe Campaign Standard 中的個人資料](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)。

若要在 Adobe Campaign Standard 中使用客戶細分，請擴展 Adobe Campaign Standard 中的[個人資料結構描述](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing)，以包括另外兩個欄位。

在我們的範例中，這些欄位是客戶細分名稱和客戶細分日期。 在 Adobe Campaign Standard 中，我們將使用這些欄位來識別此行銷活動中的目標個人資料。

如果 Adobe Campaign Standard 中只有要匯入記錄，沒有其他記錄，則可以跳過此步驟。

## <a name="import-data-into-adobe-campaign-standard"></a>匯入資料到 Adobe Campaign Standard

將準備好的對象資料從 Customer Insights 匯入 Adobe Campaign Standard，以[使用工作流程建立個人資料](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)。

下方圖片中的匯入工作流程已設定為每隔 8 小時執行一次，將尋找匯出的 Customer Insights 客戶細分 (Azure Blob 儲存體中的 csv 檔案)。 工作流程以指定的資料行順序擷取 csv 檔案內容。 此工作流程是為了執行基本錯誤處理，確保每個記錄在將資料進入到 Adobe Campaign Standard 中之前都有電子郵件位址。 工作流程也會在 upsert 至 Adobe Campaign Standard 個人資料之前，先從檔案名中 擷取客戶細分名稱。

:::image type="content" source="media/ACS-import-workflow.png" alt-text=" Adobe Campaign Standard 使用者介面中匯入工作流程的螢幕擷取畫面。":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>在 Adobe Campaign Standard 中擷取對象

只要資料匯入 Adobe Campaign Standard 中，您可以[建立一個工作流程](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data)，並根據客戶細分名稱和客戶細分日期[查詢](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data)客戶，來選擇為我們的範例行銷活動識別的個人資料。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>使用 Adobe Campaign Standard 建立和發送電子郵件

建立電子郵件內容，接著[測試並發送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)電子郵件。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text=" Adobe Campaign Standard 續訂優惠的範例電子郵件。":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
