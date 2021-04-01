---
title: 將 Customer Insights 資料匯出到 Adobe Experience Platform
description: 了解如何在 Adobe Experience Platform 中使用對象見解客戶細分。
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596259"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>在 Adobe Experience Platform 中使用 Customer Insights 客戶細分 (預覽)

作為 Dynamics 365 Customer Insights 對象見解的使用者，您可能創建了多個客戶細分，鎖定相關對象來提高行銷廣告活動的效益。 在 Adobe Experience Platform 和 Adobe Campaign Standard 之類的應用程式中使用對象見解的客戶細分，您需要遵循本文中概述的幾個步驟。

:::image type="content" source="media/AEP-flow.png" alt-text="本文概述步驟的流程圖。":::

## <a name="prerequisites"></a>先決條件

-   Dynamics 365 Customer Insights 授權
-   Adobe Experience Platform 權限
-   Adobe Campaign Standard 授權
-   Azure Blob 儲存體帳戶

## <a name="campaign-overview"></a>行銷活動概觀

為了更好地了解如何使用 Adobe Experience Platform 中對象見解的客戶細分，先來看看一個虛構的行銷活動。

假設貴公司在美國為客戶提供每月訂閱型的服務。 您希望找出哪些客戶的訂閱是需要在未來八天內續訂但尚未續訂的。 為了保留這些客戶，您希望使用 Adobe Experience Platform 向他們發送電子郵件提供促銷優惠。

在此範例中，我們希望執行一次促銷電子郵件的行銷活動。 本文不涵蓋多次執行行銷活動的使用案例。

## <a name="identify-your-target-audience"></a>找出目標對象

在我們的案例中，我們假設客戶的電子郵件位址包含在對象見解中，而他們的促銷偏好也已經完成分析，能找出該客戶細分的成員。

[在對象見解中定義的客戶細分](segments.md)名稱為 **ChurnProneCustomers**，且您計畫向這些客戶發送電子郵件促銷。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="建立了 ChurnProneCustomers 客戶細分頁面的螢幕擷取畫面。":::

您要發送的優惠電子郵件將包含客戶的姓、名和訂閱結束日期。 此信件通知客戶，如果他們在訂閱結束前續訂訂閱，他們將獲得折扣。

## <a name="export-your-target-audience"></a>匯出目標對象

找出目標對象後，我們可以設定從對象見解到 Azure Blob 儲存體帳戶的匯出。

1. 在對象見解中，前往 **系統管理員** > **匯出目的地**。

1. 在 **Azure Blob 儲存體** 圖格中，選擇 **設定**。

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob 儲存體的設定圖格。":::

1. 為這個新的匯出目的地提供 **顯示名稱**，然後輸入您希望客戶細分匯出到的 Azure Blob 儲存體帳戶其 **帳戶名稱**、**帳戶金鑰**、和 **容器**。  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="儲存體帳戶設定的螢幕擷取畫面。"::: 

   - 若要進一步了解如何尋找 Azure Blob 儲存體帳戶名稱及帳戶金鑰，請參閱 [管理 Azure 入口網站中的儲存體帳戶設定](/azure/storage/common/storage-account-manage)。

   - 若要了解如何建立容器，請參閱[建立容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

1. 選取 **下一步**。

1. 選擇您要匯出的客戶細分。 在這個例子中，它是 **ChurnProneCustomers**。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="客戶細分選擇使用者介面中已選擇 ChurnProneCustomers 客戶細分的螢幕擷取畫面。":::

1. 選取 **儲存**。

儲存匯出目的地後，您可以在 **管理** > **匯出** > **我的匯出目的地** 找到。

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="醒目提示匯出清單和範例客戶細分的螢幕擷取畫面。":::

現在，您能[依需求匯出客戶細分](export-destinations.md#export-data-on-demand)。 匯出也會與每個[排定的重新整理](system.md)一起執行。

> [!NOTE]
> 確認客戶細分記錄的匯出數量在 Adobe Campaign Standard 授權限制內。

匯出的資料儲存在前面設定的 Azure Blob 儲存體容器中。 在您的容器中將自動建立下列資料夾路徑：

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

匯出實體的 *model.json* 位於 *%ExportDestinationName%* 層級。

範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>在 Adobe Experience Platform 中定義體驗資料模型 (XDM)

在 Adobe Experience Platform 中使用對象見解的匯出資料之前，我們需要定義體驗資料模型結構描述，並[為即時客戶個人資料設定資料](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)。

了解 [XDM 是什麼](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)，並了解[結構描述組成的基本知識](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema)。

## <a name="import-data-into-adobe-experience-platform"></a>匯入資料到 Adobe Experience Platform

現在一切都準備好了，我們需要從對象見解匯入準備好的對象資料到 Adobe Experience Platform，以建立個人資料。

首先，[建立 Azure Blob 儲存體來源連接 ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)。    

定義來源連接後，為雲端儲存空間批次連接[設定資料流程](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials)，從對象見解客戶細分輸出匯入 Adobe Experience Platform。

## <a name="create-an-audience-in-adobe-campaign-standard"></a>在 Adobe Campaign Standard 建立對象

發送此行銷活動的電子郵件，我們將使用 Adobe Campaign Standard。 將資料匯入 Adobe Experience Platform 後，我們需要使用 Adobe Experience Platform 中的資料在 Adobe Campaign Standard 中[建立對象](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)。

了解在 Adobe Campaign Standard 中如何[使用客戶細分建立工具](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment)以 Adobe Experience Platform 的資料定義對象。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>使用 Adobe Campaign Standard 建立和發送電子郵件

建立電子郵件內容，接著[測試並發送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)電子郵件。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text=" Adobe Campaign Standard 中包含續訂優惠的電子郵件範例。":::