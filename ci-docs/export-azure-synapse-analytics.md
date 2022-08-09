---
title: 匯出資料至 Azure Synapse Analytics (預覽版)
description: 了解如何設定 Azure Synapse Analytics 連線。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196384"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>匯出資料至 Azure Synapse Analytics (預覽版)

Azure Synapse 是一項分析服務，減少了深入解析跨資料倉儲和巨量資料系統所需要的時間。 您可以在 [Azure Synapse](/azure/synapse-analytics/overview-what-is) 中內嵌和使用您的 Customer Insights 資料。

## <a name="prerequisites"></a>先決條件

> [!NOTE]
> 請務必根據說明來設定全部的 **角色指派**。

- 在 Customer Insights 中，您的 Azure Active Directory (AD) 使用者帳戶必須具有[管理員角色](permissions.md#assign-roles-and-permissions)。

在 Azure 中：

- 啟用中的 Azure 訂用帳戶。

- 如果使用新的 Azure Data Lake Storage Gen2 帳戶，則 [Customer Insights 的服務主體](connect-service-principal.md)需具有 **儲存體 Blob 資料參與者** 權限。 Data Lake Storage Gen2 **必須** 已啟用的[階層命名空間](/azure/storage/blobs/data-lake-storage-namespace)。

- 在 Azure Synapse workspace 所在的資源群組，於 *服務主體* 和在 *Customer Insights 中具有管理員權限的 Azure AD 使用者* 至少需獲指派 **讀者**[權限](/azure/role-based-access-control/role-assignments-portal)。

- *Customer Insights 中具有系統管理員權限的 Azure AD 使用者* 對資料所在的 Azure Data Lake Storage Gen2 帳戶擁有 **儲存體 Blob 資料參與者** 權限，並連結到 Azure Synapse workspace。 深入瞭解如何[使用 Azure 入口網站指派 Azure 角色，以取得 blob 和佇列資料的存取權](/azure/storage/common/storage-auth-aad-rbac-portal)，以及[儲存體 blob 資料參與者權限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- *[Azure Synapse workspace 受管理的身分識別](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 對資料所在的 Azure Data Lake Storage Gen2 帳戶具有 **儲存體 Blob 資料參與者** 權限，並連結到 Azure Synapse workspace。 深入瞭解如何[使用 Azure 入口網站指派 Azure 角色，以取得 blob 和佇列資料的存取權](/azure/storage/common/storage-auth-aad-rbac-portal)，以及[儲存體 blob 資料參與者權限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 在 Azure Synapse workspace 中，*Customer Insights 的服務主體* 已指派 **Synapse 管理員**[角色](/azure/synapse-analytics/security/how-to-set-up-access-control)。

## <a name="set-up-connection-to-azure-synapse"></a>設定與 Azure Synapse 的連線

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Azure Synapse Analytics**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 選取或搜尋您要在其中使用 Customer Insights 資料的訂閱。 選取訂閱之後，您也可以選取 **工作區**、**儲存體帳戶** 和 **容器**。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)] 若要使用共用的連接來設定匯出，您至少必須在 Customer Insights 中有 **參與者** 權限。

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 Azure Synapse Analytics 區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 提供可辨識的 **顯示名稱** 給匯出並提供 **資料庫名稱**。 匯出會在連接定義的工作區中建立新的 [Azure Synapse 湖資料庫](/azure/synapse-analytics/database-designer/concepts-lake-database)。

1. 選取要匯出至 Azure Synapse Analytics 的實體。
   > [!NOTE]
   > 不支援基於 [Common Data Model 資料夾](connect-common-data-model.md)的資料來源。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

若要查詢匯出至 Synapse Analytics 的資料，您需要在匯出工作區中目標儲存空間有 **儲存體 Blob 資料讀者** 存取權。

## <a name="update-an-export"></a>更新匯出

1. 移至 **資料** > **匯出**。

1. 在您想要更新的匯出上選取 **編輯**。

   - 從選項中 **新增** 或 **移除** 實體。 從選項中移除實體，並不會從 Synapse Analytics 資料庫中刪除它們。 不過，之後的資料重新整理並不會更新該資料庫中已移除的實體。

   - **變更資料庫名稱** 會建立新的 Synapse Analytics 資料庫。 在之後的重新整理，之前設定名稱的資料庫將不會收到任何更新。

[!INCLUDE [footer-include](includes/footer-banner.md)]
