---
title: 匯出資料至 Azure Data Lake Storage Gen2 (預覽版)
description: 瞭解如何設定與 Azure Data Lake Storage Gen2 的連接。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196430"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>匯出資料至 Azure Data Lake Storage Gen2 (預覽版)

將您的 Customer Insights 資料儲存在 Data Lake Storage Gen2 帳戶或使用它將資料傳輸到其他應用程式。

## <a name="prerequisites"></a>先決條件

- [與 Azure Data Lake Gen2 一起使用的儲存體帳戶](/azure/storage/blobs/create-data-lake-storage-account)。 若要尋找儲存體帳戶名稱和金鑰，請參閱 [Azure 入口網站中的「管理儲存體帳戶設定」](/azure/storage/common/storage-account-manage)。
- [Azure Blob 儲存體容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

## <a name="known-limitations"></a>已知限制

- 如果是 Azure Data Lake Storage Gen2，[請在標準效能和進階效能層級之間選擇。](/azure/storage/blobs/create-data-lake-storage-account) 如果您選擇進階效能層級，請選取[進階塊體 blob 做為帳戶類型](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>設定連線到 Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Azure Data Lake Gen 2**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 在您的 Azure Data Lake Storage Gen2 輸入 **帳戶名稱**、**帳戶金鑰** 和 **容器**。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連接** 欄位中，在 Azure Data Lake 區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 輸入 Azure Data Lake Storage Gen2 儲存體的資料夾名稱。

1. 選取每個要匯出至此目的地之實體旁邊的方塊。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

匯出的資料會儲存在您設定的 Azure Data Lake Gen 2 儲存體容器中。

> [!TIP]
> 若匯出包含大量資料的實體，在每個匯出的相同資料夾中可能會產生多個 CSV 檔案。 基於效能因素，將進行分割匯出，以將完成匯出花費的時間降至最低。

[!INCLUDE [footer-include](includes/footer-banner.md)]
