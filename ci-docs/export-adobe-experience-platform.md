---
title: 匯出客戶細分至 Adobe Experience Platform (預覽版)
description: 了解如何在 Adobe Experience Platform 使用 Customer Insights 客戶細分。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195280"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>匯出客戶細分至 Adobe Experience Platform (預覽版)

將針對相關對象的客戶細分匯出到 Adobe Experience Platform。

:::image type="content" source="media/AEP-flow.png" alt-text="本文概述步驟的流程圖。":::

## <a name="prerequisites"></a>先決條件

- Adobe Experience Platform 授權。
- Adobe Campaign Standard 授權。
- [Azure Blob 儲存體帳戶](/azure/storage/blobs/create-data-lake-storage-account)名稱和帳戶金鑰。 若要尋找名稱和金鑰，請參閱 [Azure 入口網站中的「管理儲存體帳戶設定」](/azure/storage/common/storage-account-manage)。
- [Azure Blob 儲存體容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

## <a name="campaign-overview"></a>行銷活動概觀

為了更好地了解如何在 Adobe Experience Platform 中使用 Customer Insights，我們來看一下虛構的範例行銷活動。

假設貴公司在美國為客戶提供每月訂閱型的服務。 您希望找出哪些客戶的訂閱是需要在未來八天內續訂但尚未續訂的。 為了留住這些客戶，您希望使用 Adobe Experience Platform 以電子郵件對他們發送促銷優惠。

在此範例中，我們希望執行一次促銷電子郵件的行銷活動。 本文不涵蓋多次執行行銷活動的使用案例。

## <a name="identify-your-target-audience"></a>找出目標對象

在我們的案例中，我們假設客戶的電子郵件地址在 Customer Insights 可以使用，且分析他們的促銷喜好以確認客戶細分的成員。

在 [Customer Insights 中定義的客戶細分](segments.md)被稱為 **ChurnProneCustomers**，您計畫傳送電子郵件促銷給這些客戶。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="建立了 ChurnProneCustomers 客戶細分頁面的螢幕擷取畫面。":::

您要發送的優惠電子郵件將包含客戶的姓、名和訂閱結束日期。 此信件通知客戶，如果他們在訂閱結束前續訂訂閱，他們將獲得折扣。

## <a name="export-your-target-audience"></a>匯出目標對象

我們會設定從 Customer Insights 匯出至 Azure Blob 儲存體帳戶。

### <a name="set-up-connection-to-azure-blob-storage"></a>設定與 Azure Blob 儲存體的連接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Azure Blob 儲存體**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 對客戶細分要匯出到的 Azure Blob 儲存體帳戶，輸入其 **帳戶名稱**、**帳戶金鑰** 和 **容器**。  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="儲存體帳戶設定的螢幕擷取畫面。":::

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **儲存** 來完成連接。

### <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 Azure Blob 儲存體區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 選擇您要匯出的客戶細分。 在這個例子中，它是 **ChurnProneCustomers**。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="客戶細分選擇使用者介面中已選擇 ChurnProneCustomers 客戶細分的螢幕擷取畫面。":::

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> 確保匯出的客戶細分中的記錄數量在 Adobe Campaign Standard 授權的允許範圍內。

匯出的資料會儲存在您設定的 Azure Blob 儲存體容器中。 容器中會自動建立下列資料夾路徑：

- 關於系統產生的來源實體和實體： 

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- 匯出實體的 *model.json* 位於 *%ExportDestinationName%* 層級。

  範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>在 Adobe Experience Platform 中定義經驗資料模型 (XDM)

在 Adobe Experience Platform 中可使用從 Customer Insights 匯出的資料之前，請先定義體驗資料模型架構，並[為即時客戶個人資料設定資料](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)。

了解 [XDM 是什麼](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)，並了解[結構描述組成的基本知識](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema)。

## <a name="import-data-into-adobe-experience-platform"></a>將資料匯入至 Adobe Experience Platform

將準備好的對象資料從 Customer Insights 匯入 Adobe Experience Platform。

1. [建立 Azure Blob 儲存體來源連接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)。

1. 為雲端儲存體批次連接[設定資料流程](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials)將 Customer Insights 客戶細分輸出匯入到 Adobe Experience Platform。

## <a name="create-an-audience-in-adobe-campaign-standard"></a>在 Adobe Campaign Standard 中建立對象

若要傳送此行銷活動的電子郵件，我們將使用 Adobe Campaign Standard。

1. 使用 Adobe Experience Platform 中的資料在 Adobe Campaign Standard 中[建立對象](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)。

1. 在 Adobe Campaign Standard 中[使用客戶細分建立器](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html)依照 Adobe Experience Platform 中的資料定義對象。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>使用 Adobe Campaign Standard 建立和發送電子郵件

建立電子郵件內容，接著[測試並發送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)電子郵件。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text=" Adobe Campaign Standard 續訂優惠的範例電子郵件。":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
