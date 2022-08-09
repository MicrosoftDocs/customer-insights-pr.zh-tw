---
title: 將 Customer Insights 資料匯出至 InMobi
description: 了解如何設定 InMobi 的連線和匯出。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195878"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>將 Customer Insights 資料匯出至 InMobi (預覽版)

將 Customer Insights 執行個體中的客戶細分清單或其他資料匯出至 [InMobi](https://www.inmobi.com/)。

## <a name="prerequisites"></a>先決條件

- [InMobi 帳戶](https://www.inmobi.com/)和系統管理員認證。
- [Azure Blob 儲存體帳戶](/azure/storage/blobs/create-data-lake-storage-account)名稱和帳戶金鑰。 若要尋找名稱和金鑰，請參閱 [Azure 入口網站中的「管理儲存體帳戶設定」](/azure/storage/common/storage-account-manage)。
- 要將 InMobi 資料會出到的 [Azure Blob 儲存體容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。
- InMobi 將建立與 Blob 儲存體的直接連接，並將資料自動匯入至 InMobi。 請與您的 InMobi 代表聯繫，才能啟動程式。

## <a name="known-limitations"></a>已知限制

- 如果是 Azure Blob 儲存體，請在[標準效能和進階效能層級](/azure/storage/blobs/storage-blob-performance-tiers)之間選擇。 如果您選擇進階效能層級，請選取[進階塊體 blob 做為帳戶類型](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-connection-to-azure-blob-storage"></a>設定與 Azure Blob 儲存體的連接

[設定與 Azure Blob 儲存體的連接](export-azure-blob-storage.md)。

## <a name="configure-an-export"></a>設定匯出

[設定匯出](export-azure-blob-storage.md#configure-an-export)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
