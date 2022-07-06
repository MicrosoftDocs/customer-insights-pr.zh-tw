---
title: 將 Customer Insights 資料匯出至 InMobi
description: 了解如何設定 InMobi 的連線和匯出。
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056535"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>匯出客戶細分清單和其他資料到 InMobi (預覽版)

將 Customer Insights 執行個體中的客戶細分清單或其他資料匯出至 [InMobi](https://www.inmobi.com/)。

## <a name="prerequisites"></a>先決條件

1. 您擁有一個 [InMobi 帳戶](https://www.inmobi.com/)和系統管理員認證。
1. 您擁有 Azure Blob 儲存體帳戶名稱及對應的帳戶金鑰。 如需詳細資訊，請參閱 [Azure 入口網站中的「管理儲存體帳戶設定」](/azure/storage/common/storage-account-manage)。 儲存帳戶中有一個容器，可存放匯出的 inMobi 資料。 如需詳細資訊，請參閱[建立容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。
1. InMobi 將建立與 Blob 儲存體的直接連接，並將資料自動匯入至 InMobi。 請與您的 InMobi 代表聯繫，才能啟動程式。

## <a name="known-limitations"></a>已知限制

1. 在 Azure Blob 儲存體，您可以在[標準效能和進階效能層級](/azure/storage/blobs/storage-blob-performance-tiers)之間選擇。 如果您選擇進階效能層級，請選取[進階塊體 blob 做為帳戶類型](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>設定與 Azure Blob 儲存體的連接，並設定匯出

1. 依照指示[設定到 Azure Blob 儲存體](export-azure-blob-storage.md)的連接。
2. 依照指示[設定匯出](export-azure-blob-storage.md#configure-an-export)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
