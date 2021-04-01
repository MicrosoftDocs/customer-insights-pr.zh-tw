---
title: 將 Customer Insights 資料匯出到 Adobe Campaign Standard
description: 瞭解如何在 Adobe Campaign Standard 中使用對象見解客戶細分。
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596305"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>在 Adobe Campaign Standard 中使用 Customer Insights 客戶細分 (預覽)

作為 Dynamics 365 Customer Insights 對象見解的使用者，您可能創建了多個客戶細分，鎖定相關對象來提高行銷廣告活動的效益。 在 Adobe Experience Platform 和 Adobe Campaign Standard 之類的應用程式中使用對象見解的客戶細分，您需要遵循本文中概述的幾個步驟。

:::image type="content" source="media/ACS-flow.png" alt-text="本文概述步驟的流程圖。":::

## <a name="prerequisites"></a>先決條件

-   Dynamics 365 Customer Insights 授權
-   Adobe Campaign Standard 授權
-   Azure Blob 儲存體帳戶

## <a name="campaign-overview"></a>行銷活動概觀

為了更好地了解如何使用 Adobe Experience Platform 中對象見解的客戶細分，先來看看一個虛構的行銷活動。

假設貴公司在美國為客戶提供每月訂閱型的服務。 您希望找出哪些客戶的訂閱是需要在未來八天內續訂但尚未續訂的。 為了保留這些客戶，您希望使用 Adobe Campaign Standard 向他們發送電子郵件提供促銷優惠。

在此範例中，我們希望執行一次促銷電子郵件的行銷活動。 本文不涵蓋多次執行行銷活動的使用案例。 但是，對象見解和 Adobe Campaign Standard 也可以設定為定期行銷活動案例運作。

## <a name="identify-your-target-audience"></a>找出目標對象

在我們的案例中，我們假設客戶的電子郵件位址包含在對象見解中，而他們的促銷偏好也已經完成分析，能找出該客戶細分的成員。

[在對象見解中定義的客戶細分](segments.md)名稱為 **ChurnProneCustomers**，且您計畫向這些客戶發送電子郵件促銷。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="建立了 ChurnProneCustomers 客戶細分頁面的螢幕擷取畫面。":::

您要發送的優惠電子郵件將包含客戶的姓、名和訂閱結束日期。 此信件通知客戶，如果他們在訂閱結束前續訂訂閱，他們將獲得折扣。

## <a name="export-your-target-audience"></a>匯出目標對象

找出目標對象後，我們可以設定從對象見解到 Azure Blob 儲存體帳戶的匯出。

1. 在對象見解中，前往 **系統管理員** > **匯出目的地**。

1. 在 **Adobe Campaign** 圖格中選取 **設定**。

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard 的設定圖格。":::

1. 為這個新的匯出目的地提供 **顯示名稱**，然後輸入您希望客戶細分匯出到的 Azure Blob 儲存體帳戶其 **帳戶名稱**、**帳戶金鑰**、和 **容器**。  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="儲存體帳戶設定的螢幕擷取畫面。"::: 

   - 若要進一步了解如何尋找 Azure Blob 儲存體帳戶名稱及帳戶金鑰，請參閱 [管理 Azure 入口網站中的儲存體帳戶設定](/azure/storage/common/storage-account-manage)。

   - 若要了解如何建立容器，請參閱[建立容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

1. 選取 **下一步**。

1. 選擇您要匯出的客戶細分。 在這個例子中，它是 **ChurnProneCustomers**。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="客戶細分選擇使用者介面中已選擇 ChurnProneCustomers 客戶細分的螢幕擷取畫面。":::

1. 選取 **下一步**。

1. 現在，我們將對象見解客戶細分的 **來源** 欄位對應到 Adobe Campaign Standard 個人資料結構描述中的 **目標** 欄位名稱。

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard 連接器的欄位對應。":::

   若要新增更多屬性，請選擇 **新增屬性**。 目標名稱可以與來源欄位名稱不同，因此，如果兩個系統中的欄位名稱不相同，您仍可以對應對象見解的客戶細分輸出到 Adobe Campaign Standard。

   > [!NOTE]
   > 電子郵件地址被當成識別欄位，但您可以使用對象見解客戶個人資料中的任何其他識別碼來對應資料到 Adobe Campaign Standard。

1. 選取 **儲存**。

儲存匯出目的地後，您可以在 **管理** > **匯出** > **我的匯出目的地** 找到。

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="醒目提示匯出清單和範例客戶細分的螢幕擷取畫面。":::

現在，您能[依需求匯出客戶細分](export-destinations.md#export-data-on-demand)。 匯出也會與每個[排定的重新整理](system.md)一起執行。

> [!NOTE]
> 確認客戶細分記錄的匯出數量在 Adobe Campaign Standard 授權限制內。

匯出的資料儲存在前面設定的 Azure Blob 儲存體容器中。 在您的容器中將自動建立下列資料夾路徑：

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>設定 Adobe Campaign Standard

匯出對象見解的客戶細分時，它包含您在上個步驟定義匯出目的地時選擇的資料行。 此資料可用於[建立 Adobe Campaign Standard 中的個人資料](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)。

要使用 Adobe Campaign Standard 中的客戶細分，我們需要擴充 Adobe Campaign Standard 中的個人資料結構描述，容納兩個額外的欄位。 瞭解在 Adobe Campaign Standard 中如何使用新欄位[擴充個人資料資源](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing)。

在我們的範例中，這些欄位是 *客戶細分名稱和客戶細分日期 (可選)。*

我們將使用這些欄位在 Adobe Campaign Standard 中找出我們想要用在此活動的個人資料。

如果除了要匯入的內容，Adobe Campaign Standard 中沒有其他記錄，您可以跳過此步驟。

## <a name="import-data-into-adobe-campaign-standard"></a>將資料匯入 Adobe Campaign Standard

現在一切都準備好了，我們需要從對象見解匯入準備好的對象資料到 Adobe Campaign Standard，以建立個人資料。 瞭解使用工作流程，[如何在 Adobe Campaign Standard 匯入個人資料](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)。

下圖中的匯入工作流程已設定為每 8 小時執行一次，並找出已匯出的對象見解客戶細分 (Azure Blob 儲存體中的 csv 檔案)。 工作流程以指定的資料行順序擷取 csv 檔案內容。 此工作流程已組建為能執行基本錯誤處理，及確保每個記錄有一個電子郵寄地址之後才在 Adobe Campaign Standard 將資料序列化。 工作流程還能從檔名中擷取資料細分名稱，再更新插入 ACS 個人資料。

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard 使用者介面中匯入工作流程的螢幕擷取畫面。":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>在 Adobe Campaign Standard 中擷取對象

當資料匯入 Adobe Campaign Standard，您可以 [建立工作流程](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data)以及根據 *客戶細分名稱* 和 *客戶細分日期* 對客戶[查詢](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data)，來選取為範例活動確認完成的個人資料。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>使用 Adobe Campaign Standard 建立和發送電子郵件

建立電子郵件內容，接著[測試並發送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)電子郵件。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text=" Adobe Campaign Standard 中包含續訂優惠的電子郵件範例。":::