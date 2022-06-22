---
title: 將 Customer Insights 資料匯出到 Azure Blob 儲存體
description: 了解如何設定連接並匯出至 Blob 儲存體。
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 623926bf520b19ee4156b7a05e953241cd819e9e
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947128"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>將客戶細分清單及其他資料匯出至 Azure Blob 儲存體 (預覽版)

將您的 Customer Insights 資料儲存在 Blob 儲存體，或使用它將資料傳輸至其他應用程式。

## <a name="known-limitations"></a>已知限制

1. 對於 Azure Blob 儲存體而言，您可以在[標準效能和進階效能層](/azure/storage/blobs/storage-blob-performance-tiers)之間任選其一。 如果您選擇進階效能層級，請選取[進階塊體 blob 做為帳戶類型](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-the-connection-to-blob-storage"></a>設定到 Blob 儲存體的連接

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Azure Blob 儲存體** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 輸入您的 Blob 儲存體帳戶的 **帳戶名稱**、**帳戶金鑰** 和 **容器**。
    - 若要進一步了解如何找到 Blob 儲存體帳戶名稱及帳戶金鑰，請參閱 [Azure 入口網站中的管理儲存體帳戶設定](/azure/storage/common/storage-account-manage)。
    - 若要了解如何建立容器，請參閱[建立容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

1. 選取 **儲存** 來完成連接。 

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

> [!IMPORTANT]
> 如果您已打開 Azure Blob 儲存體帳戶的虛刪除設定，匯出將會失敗。 關閉虛刪除，將資料匯出至 blob。 如需詳細資訊，請參閱[啟用 blob 虛刪除](/azure/storage/blobs/soft-delete-blob-enable)

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 Azure Blob 儲存體區段中選擇連接。 如果您沒有看到此區段名稱，則代表此類型中的連接沒有您可以使用的。

1. 選取每個要匯出至此目的地之實體旁邊的方塊。

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。

您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。

匯出的資料會儲存在您設定的 Blob 儲存體容器中。 容器中會自動建立下列資料夾路徑：

- 關於系統產生的來源實體和實體：  
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - 範例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
  
  > [!TIP]
  > 若匯出包含大量資料的實體，在每個匯出的相同資料夾中可能會產生多個 CSV 檔案。 基於效能因素，將進行分割匯出，以將完成匯出花費的時間降至最低。

- 匯出實體的 model.json 將在 %ExportDestinationName% 層級。  
  - 範例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
