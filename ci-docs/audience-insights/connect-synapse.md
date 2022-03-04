---
title: 內嵌 Azure Synapse Analytics 的資料
description: 以 Azure Synapse 的資料庫作為 Dynamics 365 Customer Insights 的資料來源。
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356015"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>連接至 Azure Synapse 資料來源 (預覽版)

Azure Synapse Analytics 是一項企業分析服務，可加快資料倉儲和大型資料系統的見解生成速度。 Azure Synapse Analytics 彙集了企業資料倉儲中使用到的最佳 SQL 技術、用於巨量資料的 Spark 技術、用於日誌和時間序列分析的資料總管、用於資料整合和 ETL/ELT 的 Pipelines，以及其他 Azure 服務(例如，Power BI、Cosmos DB、和 AzureML) 的深度整合。

如需詳細資訊，請參閱 [Azure Synapse 概觀](/azure/synapse-analytics/overview-what-is)。

## <a name="prerequisites"></a>先決條件

若要設定從 Customer Insights 到 Azure Synapse 的連接，必須符合下列先決條件。

> [!IMPORTANT]
> 請務必根據說明來設定全部的 **角色指派**。  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights 的先決條件

* 擁有 Customer Insights 中的 **系統管理員** 角色。 瞭解更多有關[對象見解的使用者權限](permissions.md#assign-roles-and-permissions)。

在 Azure 中： 

- 啟用中的 Azure 訂用帳戶。

- 如果使用新的 Azure Data Lake Storage Gen2 帳戶，*對象見解的服務主體* 需要 **儲存 Blob 資料參與者** 權限。 深入瞭解如何[使用對象見解的服務主體來連接 Azure Data Lake Storage](connect-service-principal.md)。 Data Lake Storage Gen2 **必須** 已啟用的[階層命名空間](/azure/storage/blobs/data-lake-storage-namespace)。

- 在 Azure Synapse 工作區所在的資源群組，*服務主體* 和 *對象見解的使用者* 至少要被指派 **讀者** 權限。 如需詳細資訊，請參閱[使用 Azure 入口網站指派 Azure 角色](/azure/role-based-access-control/role-assignments-portal)。

- 在連結至 Azure Synapse 工作區且為資料所在的 Azure Data Lake Storage Gen2 帳戶，*使用者* 需要有 **儲存體 Blob 資料參與者** 權限。 深入瞭解如何[使用 Azure 入口網站指派 Azure 角色，以取得 blob 和佇列資料的存取權](/azure/storage/common/storage-auth-aad-rbac-portal)，以及[儲存體 blob 資料參與者權限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 在連結至 Azure Synapse 工作區且為資料所在的 Azure Data Lake Storage Gen2 帳戶中，*[Azure Synapse 工作區受管理的身分識別](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 需要 **儲存體 Blob 資料參與者** 權限。 深入瞭解如何[使用 Azure 入口網站指派 Azure 角色，以取得 blob 和佇列資料的存取權](/azure/storage/common/storage-auth-aad-rbac-portal)，以及[儲存體 blob 資料參與者權限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 在 Azure Synapse 工作區中，*觀眾見解的服務主體* 需要被指派 **Synapse 系統管理員** 角色。 如需詳細資訊，請參閱[如何設定 Synapse 工作區的存取控制](/azure/synapse-analytics/security/how-to-set-up-access-control)。

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>連接至 Azure Synapse Analytics 中的 Data Lake 資料庫

1. 移至 **資料** > **資料來源**。

1. 選取 **新增資料來源**。

1. 選擇 **Azure Synapse Analytics (預覽版)** 方法。

1. 提供資料來源的 **名稱**，然後選取 **下一步** 以建立資料來源。 

1. 選擇對 Azure Synapse Analytics [可用的連線](connections.md)，或建立一個新連線。

1. 在選擇的 Azure Synapse Analytics 連線中，從連線的工作區中選擇一個 **Lake 資料庫**，然後選取 **下一步**。

1. 從連線的資料庫中選取要內嵌的實體。 

1. 或者，選擇允許進行資料分析的資料實體。 

1. 選取 **儲存** 以套用所選，並開始從連線至 Azure Synapse Analytics 內 Lake 資料庫表格的新建資料來源擷取資料。
