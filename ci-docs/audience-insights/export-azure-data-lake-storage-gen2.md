---
title: 匯出 Customer Insights 資料到 Azure Data Lake Storage Gen2
description: 瞭解如何設定與 Azure Data Lake Storage Gen2 的連接。
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596627"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>適用 Azure Data Lake Storage Gen2 的連接器 (預覽版)

將您的 Customer Insights 資料儲存在 Azure Data Lake Storage Gen2，或使用它將資料傳輸至其他應用程式。

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>設定 Azure Data Lake Storage Gen2 的連接器

1. 在對象見解中，前往 **系統管理員** > **匯出目的地**。

1. 請在 **Azure Data Lake Storage Gen2** 下方選取 **設定**。

1. 在 **顯示名稱** 欄位中，為目的地提供可辨識的名稱。

1. 在您的 Azure Data Lake Storage Gen2 輸入 **帳戶名稱**、**帳戶金鑰** 和 **容器**。
    - 若要瞭解如何建立要可搭配 Azure Data Lake Storage Gen2 使用的儲存體帳戶，請參閱[建立儲存體帳戶](/azure/storage/blobs/create-data-lake-storage-account)。 
    - 若要進一步瞭解如何尋找 Azure Data Lake Gen2 儲存體帳戶名稱及帳戶金鑰，請參閱 [在 Azure portal 中管理儲存體帳戶的設定](/azure/storage/common/storage-account-manage)。

1. 選取 **下一步**。

1. 選取每個要匯出至此目的地之實體旁邊的方塊。

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md#export-data-on-demand)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。