---
title: 將 Customer Insights 資料匯出到 Azure Blob 儲存體
description: 了解如何設定與 Azure Blob 儲存體的連接。
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667129"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Azure Blob 儲存體的連接器 (預覽)

請在 Azure Blob 儲存體儲存您的 Customer Insights 資料或用它傳輸您的資料到其他應用程式。

## <a name="configure-the-connector-for-azure-blob-storage"></a>設定 Azure Blob 儲存體的連接器

1. 在對象見解中，前往 **系統管理員** > **匯出目的地**。

1. 在 **Azure Blob 儲存體** 底下，選取 **設定**。

1. 輸入 Azure Blob 儲存體帳戶的 **帳戶名稱**、**帳戶金鑰** 和 **容器**。
    - 若要進一步了解如何尋找 Azure Blob 儲存體帳戶名稱及帳戶金鑰，請參閱 [管理 Azure 入口網站中的儲存體帳戶設定](https://docs.microsoft.com/azure/storage/common/storage-account-manage)。
    - 若要了解如何建立容器，請參閱[建立容器](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

1. 在 **顯示名稱** 欄位中，為目的地提供可辨識的名稱。

1. 選取 **下一步**。

1. 選取每個要匯出至此目的地之實體旁邊的方塊。

1. 選取 **儲存**。

匯出的資料會儲存在您設定的 Azure Blob 儲存體容器中。 容器中會自動建立下列資料夾路徑：

- 關於系統產生的來源實體和實體：`%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - 範例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- 匯出的實體的 model.json 會位於 %ExportDestinationName% 層級
  - 範例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](/export-destinations.md#export-data-on-demand)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。
