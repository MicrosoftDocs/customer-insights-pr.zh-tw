---
title: 在 Microsoft Dataverse 中連線至資料表
description: 從 Microsoft Dataverse 受管理的資料湖匯入資料。
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: fecf3e33b5bc1eec17006fc196004be902c03b40
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900141"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>連線至 Microsoft Dataverse 受管理資料湖中的資料

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

本文說明 Dataverse 使用者如何快速連接至位於 Microsoft Dataverse 受管理的 Lake 的分析實體。 

> [!NOTE]
> 您必須是 Dataverse 組織的系統管理員才能繼續進行並查看受管理的 Lake 可用的實體清單。

## <a name="important-considerations"></a>重要考量

儲存在線上服務 (例如 Azure Data Lake Storage) 的資料可能會儲存在與處理資料所在位置不同的位置或儲存在 Dynamics 365 Customer Insights 中。 匯入或連接至儲存在線上服務的資料，即表示您同意可以將資料傳輸或儲存至 Dynamics 365 Customer Insights。 [在 Microsoft 信任中心深入了解](https://www.microsoft.com/trust-center)。

## <a name="connect-to-a-dataverse-managed-lake"></a>連接至 Dataverse 受管理的資料湖

1. 在對象見解中，前往 **資料** > **資料來源**。

2. 選取 **新增資料來源**。

3. 選取 **Microsoft Dataverse**，然後選取 **下一步**。

4. 輸入資料來源的 **名稱**，然後選取 **下一步**。 

5. 提供 Dataverse 組織的 **伺服器位址**，並選取 **登入**。

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="在資料擷取步驟中，使用者可輸入 Dataverse 環境 URL 的畫面。":::

6. 從可用清單中選取要作為實體擷取至對象見解的資料表。    

   > [!NOTE]
   > 如果已選取某些資料表，則其他 Dynamics 365 應用程式可能會使用這些資料表 (例如 Dynamics 365 Sales Insights 或 Customer Service Insights)。 您無法變更此選取項目。 建立資料來源之後，這些資料表便能以實體的方式使用。

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="顯示 Dataverse 環境中實體清單的對話方塊。":::

7. 儲存您的選擇，開始從Dataverse同步選取的資料表。 您會在 **資料來源** 頁面上找到最近新增的連接。 它將會排入佇列進行重新整理，並在所有選取的資料表同步之前，實體計數顯示為 0。

只有一個環境的資料來源可同時使用同一個 Dataverse 管理湖。

## <a name="edit-a-dataverse-managed-lake-data-source"></a>編輯 Dataverse 受管理的資料湖資料來源

只有在建立資料來源之後，才可以編輯實體選取項目。 例如，如果已將其他實體新增至 Dataverse，但您也想要將這些實體匯入時。    
若要連接不同的 Dataverse Data Lake，請[建立新的資料來源](#connect-to-a-dataverse-managed-lake)。

1. 在對象見解中，前往 **資料** > **資料來源**。

2. 在您想要更新的資料來源旁邊，選取省略符號。

3. 從清單中選取 **編輯** 選項。

4. 從可用實體清單選取額外實體，然後選取 **儲存**。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
