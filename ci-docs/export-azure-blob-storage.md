---
title: 將資料匯出至 Azure Blob 儲存體 (預覽版)
description: 了解如何設定連接並匯出至 Blob 儲存體。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195694"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>將資料匯出至 Azure Blob 儲存體 (預覽版)

將您的 Customer Insights 資料儲存在 Blob 儲存體，或使用它將資料傳輸至其他應用程式。

## <a name="prerequisites"></a>先決條件

- [Azure Blob 儲存體帳戶](/azure/storage/blobs/create-data-lake-storage-account)名稱和帳戶金鑰。 若要尋找名稱和金鑰，請參閱 [Azure 入口網站中的「管理儲存體帳戶設定」](/azure/storage/common/storage-account-manage)。
- [Azure Blob 儲存體容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

## <a name="known-limitations"></a>已知限制

- 如果是 Azure Blob 儲存體，請在[標準效能和進階效能層級](/azure/storage/blobs/storage-blob-performance-tiers)之間選擇。 如果您選擇進階效能層級，請選取[進階塊體 blob 做為帳戶類型](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-connection-to-blob-storage"></a>設定到 Blob 儲存體的連接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Azure Blob 儲存體**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 輸入您的 Blob 儲存體帳戶的 **帳戶名稱**、**帳戶金鑰** 和 **容器**。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若要設定此匯出，您必須具有此連線類型的[權限](export-destinations.md#set-up-a-new-export)。

> [!IMPORTANT]
> 如果您已打開 Azure Blob 儲存體帳戶的[虛刪除設定](/azure/storage/blobs/soft-delete-blob-enable)，匯出將會失敗。 關閉虛刪除，將資料匯出至 blob。

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 Azure Blob 儲存體區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 輸入 Blob 儲存體的資料夾名稱。

1. 選取每個要匯出至此目的地之實體旁邊的方塊。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

匯出的資料會儲存在您設定的 Blob 儲存體容器中。 容器中會自動建立下列資料夾路徑：

- 關於系統產生的來源實體和實體：  
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > 若匯出包含大量資料的實體，在每個匯出的相同資料夾中可能會產生多個 CSV 檔案。 基於效能因素，將進行分割匯出，以將完成匯出花費的時間降至最低。

- 匯出實體的 model.json 位於 *%ExportDestinationName%* 層級。  
  
  範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
