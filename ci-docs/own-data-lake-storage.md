---
title: 使用您自己的 Azure Data Lake Storage Gen2 帳戶
author: mukeshpo
description: 了解使用您自己的 Azure Data Lake Storage 帳戶來儲存 Customer Insights 資料的需求。
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304371"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>使用您自己的 Azure Data Lake Storage Gen2 帳戶

Dynamics 365 Customer Insights 提供選項，讓您可以選擇將所有資料儲存在 [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction) 中。 藉由儲存資料到 Data Lake Storage，表示您同意資料將傳輸並儲存在 Azure 儲存體帳戶適當的地理位置。 如需詳細資訊，請參閱 [Microsoft 信任中心](https://www.microsoft.com/trust-center)。

Customer Insights 中的系統管理員可以[建立環境](create-environment.md)並在程序中[指定資料儲存選項](create-environment.md#step-2-configure-data-storage)。

## <a name="prerequisites"></a>先決條件

- 建立 Customer Insights 環境時，Azure Data Lake Storage 帳戶必須位於您選取的同一個 Azure 區域。 若要知道環境的區域，請移至 Customer Insights 中的 **系統管理員** > **系統** > **關於**。
- Data Lake Storage 帳戶必須是 Gen2。 不支援 Azure Data Lake Gen1 storage 帳戶。
- Data Lake Storage 帳戶必須[已啟用階層命名空間](/azure/storage/blobs/data-lake-storage-namespace)。
- 名為 `customerinsights` 的容器必須存在於儲存體帳戶。 在 Customer Insights 中使用自己的 Data Lake Storage 之前，先加以建立。
- 設定 Customer Insights 環境的系統管理員，需要儲存體帳戶或 `customerinsights` 容器上的 [儲存體 Blob 資料參與者] 或 [儲存體 Blob 資料負責人] 角色。 如需在儲存體帳戶中指派權限的詳細資訊，請參閱[建立儲存體帳戶](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal)。

## <a name="connect-customer-insights-with-your-storage-account"></a>將 Customer Insights 連接到您的儲存體帳戶

當您建立新的環境時，請確認 Data Lake Storage 帳戶已存在，且符合所有的先決條件。

1. 在環境建立過程的 **資料儲存** 步驟中，將 **儲存輸出資料** 設定為 **Azure Data Lake Storage Gen2**。
1. 選擇如何 **連接您的儲存體**。 您可以選擇資源型選項和訂閱型選項來進行驗證。 如需更多資訊，請參閱[使用 Azure 服務主體連接 Azure Data Lake Storage 帳戶](connect-service-principal.md)。
   - 對於 **Azure 訂閱**，請選擇 **訂閱**、**資源群組** 和包含 `customerinsights` 容器的 **儲存體帳戶**。
   - 對於 **帳戶金鑰**，請提供 Data Lake Storage 帳戶的 **帳戶名稱** 和 **帳戶金鑰**。 使用此驗證方法，表示您的組織輪換金鑰時您會收到通知。 在輪換時，您必須使用新的金鑰來[更新環境設定](manage-environments.md#edit-an-existing-environment)。
1. 選擇是否要使用 Azure Private Link 來連接至儲存體帳戶，並[建立與 Private Link 的連接](security-overview.md#set-up-an-azure-private-link)。

當資料擷取等系統處理程序完成時，系統會在儲存體帳戶中建立對應的資料夾。 資料檔案和 model.json 檔案會根據處理名稱建立並新增到資料夾。

如果您建立 Customer Insights 多重環境並選擇將環境輸出實體儲存到您的儲存體帳戶，Customer Insights 會針對容器中每個 `ci_environmentID` 環境分開建立資料夾。
