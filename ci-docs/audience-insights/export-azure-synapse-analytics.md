---
title: 將 Customer Insights 資料匯出到 Azure Synapse Analytics
description: 了解如何設定 Azure Synapse Analytics 連線。
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8ace9fbee4fbd8822629a39d5902e176f8511cb5
ms.sourcegitcommit: 9f6733b2f2c273748c1e7b77f871e9b4e5a8666e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560377"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>匯出資料至 Azure Synapse Analytics (預覽版)

Azure Synapse 是一項分析服務，減少了深入解析跨資料倉儲和巨量資料系統所需要的時間。 您可以在 [Azure Synapse](/azure/synapse-analytics/overview-what-is) 中內嵌和使用您的 Customer Insights 資料。

## <a name="prerequisites"></a>先決條件

若要設定從 Customer Insights 到 Azure Synapse 的連接，必須符合下列先決條件。

> [!NOTE]
> 請務必根據說明來設定全部的 **角色指派**。  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights 的先決條件

* 您的 Azure Active Directory (AD) 使用者帳戶在 Customer Insights 中具有 **系統管理員** 角色。 深入瞭解如何[設定對象見解中的使用者權限](permissions.md#assign-roles-and-permissions)

在 Azure 中： 

- 啟用中的 Azure 訂用帳戶。

- 如果使用新的 Azure Data Lake Storage  Gen2 帳戶，則 *Customer Insights 的服務主體* 需要 **儲存體 Blob 資料參與者** 權限。 瞭解更多有關 [以 Azure 服務主體連接至 Azure Data Lake Storage Gen2 帳戶，以獲得對象見解](connect-service-principal.md)。 Data Lake Storage Gen2 **必須** 已啟用的[階層命名空間](/azure/storage/blobs/data-lake-storage-namespace)。

- 在 Azure Synapse workspace 所在的資源群組，於 *服務主體* 和 *在 Customer Insights 中具有管理員權限的 Azure AD 使用者* 至少需被指派 **讀者** 權限。 如需詳細資訊，請參閱[使用 Azure 入口網站指派 Azure 角色](/azure/role-based-access-control/role-assignments-portal)。

- *Customer Insights 具有系統管理員權限的 Azure AD 使用者*，需要資料所在且連結 Azure Synapse workspace 的 Azure Data Lake Storage Gen2 帳戶上的 **儲存體 Blob 參與者** 權限。 深入瞭解如何[使用 Azure 入口網站指派 Azure 角色，以取得 blob 和佇列資料的存取權](/azure/storage/common/storage-auth-aad-rbac-portal)，以及[儲存體 blob 資料參與者權限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 在連結至 Azure Synapse 工作區且為資料所在的 Azure Data Lake Storage Gen2 帳戶中，*[Azure Synapse 工作區受管理的身分識別](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 需要 **儲存體 Blob 資料參與者** 權限。 深入瞭解如何[使用 Azure 入口網站指派 Azure 角色，以取得 blob 和佇列資料的存取權](/azure/storage/common/storage-auth-aad-rbac-portal)，以及[儲存體 blob 資料參與者權限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 在 Azure Synapse workspace 中，*Customer Insights 的服務主體* 需要指派 **Synapse 系統管理員** 角色。 如需詳細資訊，請參閱[如何設定 Synapse 工作區的存取控制](/azure/synapse-analytics/security/how-to-set-up-access-control)。

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>設定連線並輸出至 Azure Synapse

### <a name="configure-a-connection"></a>設定連接

若要建立連接，則服務主體和在 Customer Insights 中使用者帳戶需要在 Synapse Analytics 工作區的 *資源群組* 擁有 **讀者** 權限。 此外，Synapse Analytics 工作區的服務主體和使用者也需要 **Synapse 系統管理員** 權限。 

1. 移至 **管理** > **連接**。

1. 要設定連接，請選取 **新增連線**，然後選擇 **Azure Synapse Analytics** 或在 **Azure Synapse Analytics** 圖格上選取 **設定**。

1. 在顯示名稱中，給連接一個能夠辨識的名稱。 連接的名稱與類型說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 選取或搜尋您要在其中使用 Customer Insights 資料的訂閱。 選取訂閱之後，您也可以選取 **工作區**、**儲存體帳戶** 和 **容器**。

1. 選取 **儲存** 以儲存連結。

### <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 若要使用共用的連接來設定匯出，您至少必須在 Customer Insights 中有 **參與者** 權限。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新匯出，請選取 **新增匯出**。

1. 在 **匯出用連線** 欄位中，到 **Azure Synapse Analytics** 區段中選擇連線。 如果您看不到此區段名稱，代表沒有此類型的[連接](connections.md)可供您使用。

1. 提供可辨識的 **顯示名稱** 給匯出並提供 **資料庫名稱**。

1. 選取要匯出至 Azure Synapse Analytics 的實體。
   > [!NOTE]
   > 不支援基於 [Common Data Model 資料夾](connect-common-data-model.md)的資料來源。

2. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。

若要查詢匯出至 Synapse Analytics 的資料，您需要在匯出工作區中目標儲存空間有 **儲存體 Blob 資料讀者** 存取權。 

### <a name="update-an-export"></a>更新匯出

1. 移至 **資料** > **匯出**。

1. 在您想要更新的匯出上選取 **編輯**。

   - 從選項中 **新增** 或 **移除** 實體。 從選項中移除實體，並不會從 Synapse Analytics 資料庫中刪除它們。 不過，之後的資料重新整理並不會更新該資料庫中已移除的實體。

   - **變更資料庫名稱** 會建立新的 Synapse Analytics 資料庫。 在之後的重新整理，之前設定名稱的資料庫將不會收到任何更新。
