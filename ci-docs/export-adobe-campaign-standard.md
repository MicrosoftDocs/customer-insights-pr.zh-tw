---
title: 了解如何匯出 Customer Insights 客戶細分到 Adobe Campaign Standard (預覽版)
description: 了解如何在 Adobe Campaign Standard中使用 Customer Insights 客戶細分。
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080866"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>了解如何匯出 Customer Insights 客戶細分到 Adobe Campaign Standard (預覽版)

作為 Dynamics 365 Customer Insights 使用者，您可能會建立一些客戶細分，鎖定相關的對象，讓您的行銷廣告活動更有效率。 若要在 Adobe Experience Platform 及類似 Adobe Campaign Standard 的應用程式中使用來自 Customer Insights 的客戶細分，您需要執行本文中說明的幾個步驟。

:::image type="content" source="media/ACS-flow.png" alt-text="本文概述步驟的流程圖。":::

## <a name="prerequisites"></a>先決條件

- Dynamics 365 Customer Insights 授權
- Adobe Campaign Standard 授權
- Azure Blob 儲存體帳戶

## <a name="campaign-overview"></a>行銷活動概觀

為了更好地了解如何在 Adobe Experience Platform 中使用 Customer Insights，我們來看一下虛構的範例行銷活動。

假設貴公司在美國為客戶提供每月訂閱型的服務。 您希望找出哪些客戶的訂閱是需要在未來八天內續訂但尚未續訂的。 為了留住這些客戶，您希望使用 Adobe Campaign Standard 以電子郵件對他們發送促銷優惠。

在此範例中，我們希望執行一次促銷電子郵件的行銷活動。 本文不涵蓋多次執行行銷活動的使用案例。 不過，Customer Insights 和  Adobe Campaign Standard，也能設定成適合定期行銷活動情境。

## <a name="identify-your-target-audience"></a>找出目標對象

在我們的案例中，我們假設客戶的電子郵件地址可以使用，且分析他們的促銷喜好以確認客戶細分成員。

在 [Customer Insights 中定義的客戶細分](segments.md)被稱為 **ChurnProneCustomers**，您計畫傳送電子郵件促銷給這些客戶。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="建立了 ChurnProneCustomers 客戶細分頁面的螢幕擷取畫面。":::

您要發送的優惠電子郵件將包含客戶的姓、名和訂閱結束日期。 此信件通知客戶，如果他們在訂閱結束前續訂訂閱，他們將獲得折扣。

## <a name="export-your-target-audience"></a>匯出目標對象

### <a name="configure-a-connection"></a>設定連接

辨識完目標對象，我們可以設定匯出至 Azure Blob 儲存體帳戶。

1. 在 Customer Insights 中，移至 **系統管理員** > **連接**。

1. 選取 **新增連接**，然後選擇 **Adobe Campaign** 來設定此連接，或在 **Adobe Campaign** 圖格中選取 **設定**。

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="用於 Adobe Campaign Standard 的設定圖格。":::

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 輸入要將客戶細分匯出到的 Azure Blob 儲存體帳戶其 **帳戶名稱**、**帳戶金鑰** 和 **容器**。  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="儲存體帳戶設定的螢幕擷取畫面。"::: 

   - 若要進一步了解如何尋找 Azure Blob 儲存體帳戶名稱及帳戶金鑰，請參閱 [管理 Azure 入口網站中的儲存體帳戶設定](/azure/storage/common/storage-account-manage)。

   - 若要了解如何建立容器，請參閱[建立容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

1. 選取 **儲存** 來完成連接。

### <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新匯出，請選取 **新增匯出**。

1. 在 **匯出連接** 欄位中，從 Adobe Campaign 區段選擇連接。 如果您沒有看到此區段名稱，則代表此類型中的連接沒有您可以使用的。

1. 選擇您要匯出的客戶細分。 在這個例子中，它是 **ChurnProneCustomers**。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="客戶細分選擇使用者介面中已選擇 ChurnProneCustomers 客戶細分的螢幕擷取畫面。":::

1. 選取 **下一步**。

1. 現在，我們會將 Customer Insights 客戶細分中的 **來源** 欄位對應至 Adobe Campaign Standard 結構中的 **目標** 欄位名稱。

   :::image type="content" source="media/ACS-field-mapping.png" alt-text=" Adobe Campaign Standard 連接器的欄位對應。":::

   若要新增更多屬性，請選擇 **新增屬性**。 目標名稱可以不同於來源欄位，這樣如果兩個系統中的欄位名稱不同，就可以將 Customer Insights 中的客戶細分輸出對應至 Adobe Campaign Standard。

   > [!NOTE]
   > 電子郵件地址作為為識別欄位，但是您可以使用來自客戶個人資料的任何其他識別碼將資料對應至 Adobe Campaign Standard。

1. 選取 **儲存**。

儲存匯出目的地之後，您會在 **資料** > **匯出** 中找到它 。

現在，您能[依需求匯出客戶細分](export-destinations.md#run-exports-on-demand)。 匯出也會與每個[排定的重新整理](system.md)一起執行。

> [!NOTE]
> 確保匯出的客戶細分中的記錄數量在 Adobe Campaign Standard 授權的允許範圍內。

匯出的資料儲存在前面設定的 Azure Blob 儲存體容器中。 在您的容器中將自動建立下列資料夾路徑：

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>設定 Adobe Campaign Standard

匯出的客戶細分，包含上一個步驟中定義匯出目的地時選定的欄。 此資料可用於 [建立 Adobe Campaign Standard 中的個人資料](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)。

要在 Adobe Campaign Standard 中使用客戶細分，需要擴展 Adobe Campaign Standard 中的個人資料結構描述，以包括另外兩個欄位。 了解如何在 Adobe Campaign Standard [擴充個人資料資源](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing)的新欄位。

在我們的範例中，這些欄位是 *客戶細分名稱和客戶細分日期 (可選)*。

在 Adobe Campaign Standard 中，我們將使用這些欄位來識別此行銷活動中的目標個人資料。

如果 Adobe Campaign Standard 中只有要匯入記錄，沒有其他記錄，您可以跳過此步驟。

## <a name="import-data-into-adobe-campaign-standard"></a>匯入資料到 Adobe Campaign Standard

現在一切都已到位，我們必須將準備好的對象資料從 Customer Insights 匯入 Adobe Campaign Standard，才能建立個人資料。 了解 [如何在 Adobe Campaign Standard 匯入個人資料](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)。

下方圖片中的匯入工作流程已設定為每隔 8 小時執行一次，將尋找匯出的 Customer Insights 客戶細分 (Azure Blob 儲存體中的 csv 檔案)。 工作流程以指定的資料行順序擷取 csv 檔案內容。 此工作流程是為了執行基本錯誤處理，確保每個記錄在將資料進入到 Adobe Campaign Standard 中之前都有電子郵件位址。 工作流程也會在 upsert 至 Adobe Campaign Standard 個人資料之前，先從檔案名中 擷取客戶細分名稱。

:::image type="content" source="media/ACS-import-workflow.png" alt-text=" Adobe Campaign Standard 使用者介面中匯入工作流程的螢幕擷取畫面。":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>在 Adobe Campaign Standard 中擷取對象

只要資料匯入 Adobe Campaign Standard 中，您可以 [建立一個工作流程](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data)，並根據 *客戶細分名稱* 和 *客戶細分日期*[查詢](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data)客戶，來選擇為我們的範例行銷活動識別的個人資料。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>使用 Adobe Campaign Standard 建立和發送電子郵件

建立電子郵件內容，接著[測試並發送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)電子郵件。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text=" Adobe Campaign Standard 續訂優惠的範例電子郵件。":::
