---
title: 連線至 Microsoft Dataverse 受管理資料湖中的資料
description: 從 Microsoft Dataverse 受管理的資料湖匯入資料。
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206943"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>連線至 Microsoft Dataverse 受管理資料湖中的資料

若分析實體在 Microsoft Dataverse 受管理的湖中，則 Microsoft Dataverse 的使用者可以快速連接。 只有一個環境的資料來源可同時使用同一個 Dataverse 管理湖。

> [!NOTE]
> 您必須是 Dataverse 組織的系統管理員才能繼續進行並查看受管理的 Lake 可用的實體清單。

## <a name="prerequisites"></a>先決條件

- 儲存在線上服務 (例如 Azure Data Lake Storage) 的資料可能會儲存在與處理資料所在位置不同的位置或儲存在 Dynamics 365 Customer Insights 中。 匯入或連接至儲存在線上服務的資料，即表示您同意可以將資料傳輸或儲存至 Dynamics 365 Customer Insights。 [在 Microsoft 信任中心深入了解](https://www.microsoft.com/trust-center)。

- 只有啟用了[變更追蹤](/power-platform/admin/enable-change-tracking-control-data-synchronization)的 Dataverse 實體才會顯示。 這些實體可以匯出至 Dataverse-受管理的data lake，並用於 Customer Insights 中。 立即可用的 Dataverse 資料表預設會啟用變更追蹤。 您必須打開自訂資料表的變更追蹤。 若要檢查 Dataverse 資料表是否已啟用變更追蹤，請移至 [Power Apps](https://make.powerapps.com) > **資料** > **資料表**。 尋找感興趣的資料表，並選取該資料表。 請移至 **設定** > **進階選項**，然後檢閱 **追蹤變更** 設定。

## <a name="connect-to-a-dataverse-managed-lake"></a>連接至 Dataverse 受管理的資料湖

1. 移至 **資料** > **資料來源**。

1. 選取 **新增資料來源**。

1. 選取 **Microsoft Dataverse**。

1. 輸入資料來源的 **名稱** 和 **說明** (選填)。

1. 提供 Dataverse 組織的 **伺服器位址**，並選取 **登入**。

1. 從可用清單中選取要以實體方式內嵌至 Customer Insights 的資料表。

   > [!NOTE]
   > 如果已選取某些資料表，則其他 Dynamics 365 應用程式可能會使用這些資料表 (例如 Dynamics 365 Sales Insights 或 Customer Service Insights)。 您無法變更此選取項目。 建立資料來源之後，這些資料表便能以實體的方式使用。

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="顯示 Dataverse 環境中實體清單的對話方塊。":::

1. 儲存您的選擇，開始從Dataverse同步選取的資料表。 您會在 **資料來源** 頁面上找到最近新增的連接。 它將會排入佇列進行重新整理，並在所有選取的資料表同步之前，實體計數顯示為 0。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

載入資料可能需要花費一些時間。 成功重新整理之後，即可從 [**實體**](entities.md)頁面查看擷取的資料。

## <a name="edit-a-dataverse-managed-lake-data-source"></a>編輯 Dataverse 受管理的資料湖資料來源

只有在建立資料來源之後，才可以編輯實體選取項目。 例如，如果已將其他實體新增至 Dataverse，但您也想要將這些實體匯入時。
若要連接不同的 Dataverse Data Lake，請[建立新的資料來源](#connect-to-a-dataverse-managed-lake)。

1. 移至 **資料** > **資料來源**。

1. 在您想要更新的資料來源旁邊，選取 **編輯**。

1. 從可用實體清單選取額外實體。

1. 按一下 **儲存** 以套用變更，並返回至 **資料來源** 頁面。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
