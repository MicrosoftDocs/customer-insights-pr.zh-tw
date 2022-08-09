---
title: 連接至 Azure Synapse 資料來源 (預覽版)
description: 以 Azure Synapse 的資料庫作為 Dynamics 365 Customer Insights 的資料來源。
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 54247fbcdc27f6ed8314e0755164083eb461aa64
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206897"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>連接至 Azure Synapse Analytics 資料來源 (預覽版)

Azure Synapse Analytics 是一項企業分析服務，可加快資料倉儲和大型資料系統的見解生成速度。 Azure Synapse Analytics 彙集了企業資料倉儲中使用到的最佳 SQL 技術、用於巨量資料的 Spark 技術、用於日誌和時間序列分析的資料總管、用於資料整合和 ETL/ELT 的 Pipelines，以及其他 Azure 服務(例如，Power BI、Cosmos DB、和 AzureML) 的深度整合。

如需詳細資訊，請參閱 [Azure Synapse 概觀](/azure/synapse-analytics/overview-what-is)。

## <a name="prerequisites"></a>先決條件

> [!IMPORTANT]
> 請務必根據說明來設定全部的 **角色指派**。  

**在 Customer Insights 中**：

* 擁有 Customer Insights 中的 **系統管理員** 角色。 了解更多有關[Customer Insights 的使用者權限](permissions.md#assign-roles-and-permissions)。

**在 Azure 中**：

- 啟用中的 Azure 訂用帳戶。

- 如果使用新的 Azure Data Lake Storage  Gen2 帳戶，則 *Customer Insights 的服務主體* 需要 **儲存體 Blob 資料參與者** 權限。 深入瞭解如何[使用 Customer Insights 的服務主體來連接 Azure Data Lake Storage](connect-service-principal.md)。 Data Lake Storage Gen2 **必須** 已啟用的[階層命名空間](/azure/storage/blobs/data-lake-storage-namespace)。

- 在 Azure Synapse workspace 所在的資源群組，於 *服務主體* 和 *Customer Insights 使用者* 至少需被指派 **讀者** 權限。 如需詳細資訊，請參閱[使用 Azure 入口網站指派 Azure 角色](/azure/role-based-access-control/role-assignments-portal)。

- 在連結至 Azure Synapse 工作區且為資料所在的 Azure Data Lake Storage Gen2 帳戶，*使用者* 需要有 **儲存體 Blob 資料參與者** 權限。 深入瞭解如何[使用 Azure 入口網站指派 Azure 角色，以取得 blob 和佇列資料的存取權](/azure/storage/common/storage-auth-aad-rbac-portal)，以及[儲存體 blob 資料參與者權限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 在連結至 Azure Synapse 工作區且為資料所在的 Azure Data Lake Storage Gen2 帳戶中，*[Azure Synapse 工作區受管理的身分識別](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 需要 **儲存體 Blob 資料參與者** 權限。 深入瞭解如何[使用 Azure 入口網站指派 Azure 角色，以取得 blob 和佇列資料的存取權](/azure/storage/common/storage-auth-aad-rbac-portal)，以及[儲存體 blob 資料參與者權限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 在 Azure Synapse workspace 中，*Customer Insights 的服務主體* 需要指派 **Synapse 系統管理員** 角色。 如需詳細資訊，請參閱[如何設定 Synapse 工作區的存取控制](/azure/synapse-analytics/security/how-to-set-up-access-control)。

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>連接至 Azure Synapse Analytics 中的資料胡資料庫

1. 移至 **資料** > **資料來源**。

1. 選取 **新增資料來源**。

1. 選擇 **Azure Synapse Analytics (預覽版)** 方法。

   :::image type="content" source="media/data_sources_synapse.png" alt-text="連接至 Synapse Analytics 資料的對話方塊":::
  
1. 輸入資料來源的 **名稱** 和 **說明** (選填)。

1. 選擇對 Azure Synapse Analytics [可用的連線](connections.md)，或建立一個新連線。

1. 在選定的 Azure Synapse Analytics 連接中，從連接的工作區中選擇一個 **資料庫**，然後選取 **下一步**。 目前，我們只支援 *Lake 資料庫* 的資料庫類型。

1. 從連結的資料庫中選取要內嵌的實體，然後選取 **下一步**。

1. 或者，選擇允許進行資料分析的資料實體。

1. 選取 **儲存** 以套用所選，並開始從連線至 Azure Synapse Analytics 內 Lake 資料庫表格的新建資料來源擷取資料。 **資料來源** 頁面會打開，顯示處於 **重新整理** 狀態中的新資料來源。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

載入資料可能需要花費一些時間。 成功重新整理之後，即可從 [**實體**](entities.md)頁面查看擷取的資料。

[!INCLUDE [footer-include](includes/footer-banner.md)]
