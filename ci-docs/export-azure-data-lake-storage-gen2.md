---
title: 匯出 Customer Insights 資料到 Azure Data Lake Storage Gen2
description: 瞭解如何設定與 Azure Data Lake Storage Gen2 的連接。
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22eee11666752459a1750d728c4e254ab0c59e58
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947220"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>匯出區段清單和其他資料到 Azure Data Lake Storage Gen2 (預覽版)

將您的 Customer Insights 資料儲存在 Data Lake Storage Gen2 帳戶或使用它將資料傳輸到其他應用程式。

## <a name="known-limitations"></a>已知限制

1. 對於 Azure Data Lake Storage Gen2 而言，當您為自己的 Data Lake 建立儲存體帳戶時，您可以在[標準效能和進階效能層級](/azure/storage/blobs/create-data-lake-storage-account)之間任選其一。 如果您選擇進階效能層級，請選取進階塊體 blob 做為帳戶類型。

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>設定連線到 Azure Data Lake Storage Gen2

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Azure Data Lake Gen 2** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 在您的 Azure Data Lake Storage Gen2 輸入 **帳戶名稱**、**帳戶金鑰** 和 **容器**。
    - 若要瞭解如何建立要可搭配 Azure Data Lake Storage Gen2 使用的儲存體帳戶，請參閱[建立儲存體帳戶](/azure/storage/blobs/create-data-lake-storage-account)。 
    - 若要進一步了解 Azure Data Lake Gen2 帳戶名稱及帳戶金鑰，請參閱 [Azure 入口網站中的管理儲存體帳戶設定](/azure/storage/common/storage-account-manage)。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新匯出，請選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 **Azure Data Lake** 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 選取每個要匯出至此目的地之實體旁邊的方塊。

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。
您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。

匯出的資料會儲存在您設定的 Azure Data Lake Gen 2 儲存體容器中。

> [!TIP]
> 若匯出包含大量資料的實體，在每個匯出的相同資料夾中可能會產生多個 CSV 檔案。 基於效能因素，將進行分割匯出，以將完成匯出花費的時間降至最低。

[!INCLUDE [footer-include](includes/footer-banner.md)]
