---
title: 連接到 Common Data Service 管理湖中的實體
description: 從 Common Data Service 受管理的資料湖匯入資料。
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267796"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>連線至 Common Data Service 受管理資料湖中的資料

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

本文提供有關現有 Dynamics 365 客戶如何在 Common Data Service 受管理的資料湖中快速連接至其分析實體的資訊。 您必須是 Common Data Service 組織的系統管理員，才能繼續執行並查看受管理的資料湖中提供的實體清單。

## <a name="important-considerations"></a>重要考量

儲存在線上服務 (例如 Azure Data Lake Storage) 的資料可能會儲存在與處理資料所在位置不同的位置或儲存在 Dynamics 365 Customer Insights 中。匯入或連接至儲存在線上服務的資料，即表示您同意可以將資料傳輸或儲存至 Dynamics 365 Customer Insights。 [在 Microsoft 信任中心深入了解。](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>連接至 Common Data Service 受管理的資料湖

1. 在對象見解中，前往 **資料** > **資料來源**。

2. 選取 **新增資料來源**。

3. 選取 **連接至 Common Data Service**，然後選取 **下一步**。

4. 輸入資料來源的 **名稱**，然後選取 **下一步**。 命名方針： 
   - 名稱必須以字母開頭。
   - 只能使用字母和數字。 不可以使用空格和特殊字元。
   - 接受 3 到 64 個字元。

5. 提供 Common Data Service 組織的 **伺服器位址**，並選取 **登入**。

   > [!div class="mx-imgBorder"]
   > ![用來輸入 Common Data Service 伺服器位址的對話方塊](media/enter-CDS-org-details.png)

6. 從可用清單選取要內嵌的實體。    

   > [!NOTE]
   > 如果已選取一些實體，則其他 Dynamics 365 應用程式 (例如 Dynamics 365 Sales Insights 或 Customer Service Insights) 可能會使用這些實體。 您無法變更此選取項目。 建立資料來源之後，就可以使用這些實體。

   > [!div class="mx-imgBorder"]
   > ![顯示 Common Data Service 組織中實體清單的對話方塊](media/select-analytical-entities.png)

7. 儲存您的選取項目，開始將選取的實體同步處理至 Common Data Service 受管理的資料湖。 您會在 **資料來源** 頁面上找到最近新增的連接。 這會排入佇列等待重新整理，並在同步處理所有實體之前，將實體計數顯示為 0。

只有一個環境的資料來源可同時使用同一個 Common Data Service 管理湖。

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>編輯 Common Data Service 受管理的資料湖資料來源

只有在建立資料來源之後，才可以編輯實體選取項目。 例如，如果已將其他實體新增至 Common Data Service，但您也想要將這些實體匯入時。    
若要連接至不同的 Common Data Service，請[建立新的資料來源](#connect-to-a-common-data-service-managed-lake)。

1. 在對象見解中，前往 **資料** > **資料來源**。

2. 在您想要更新的資料來源旁邊，選取省略符號。

3. 從清單中選取 **編輯** 選項。

4. 從可用實體清單選取額外實體，然後選取 **儲存**。


[!INCLUDE[footer-include](../includes/footer-banner.md)]