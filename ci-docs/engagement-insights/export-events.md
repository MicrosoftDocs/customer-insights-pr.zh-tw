---
title: 匯出精簡事件
description: 如何匯出精簡事件和基礎事件。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032375"
---
# <a name="export-events"></a>匯出事件

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

事件代表使用者的行為。 它會在使用者查看頁面（查看事件）或與內容互動（動作事件）時進行記錄。 當您可以決定要在報表中顯示資料的哪些屬性時，這個資料的虛擬視圖稱為 *精簡事件*。 

- 您可以將事件和精簡事件匯出至外部儲存體。 
- 這些匯出是向前的資料串流。 您無法重新灌裝此串流。 
- 匯出有固定的架構。 如果您將自訂屬性新增至一個事件中，這些屬性將不會被包含在內。 您需要建立新的匯出。

## <a name="prerequisites"></a>先決條件

在設定匯出之前，您需要具備 Azure 入口網站的存取權和有效訂閱。 在匯出過程中，您將需要儲存體帳戶的資訊。 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>建立第二代 Azure Data Lake Storage 帳戶

1. 登入 Azure 入口網站，並[建立新的儲存體帳戶](/azure/storage/common/storage-account-create)。 

1. 請確認您在 **進階** 索引標籤上啟用了 **階層命名空間**。 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="在進階索引標籤上啟用階層命名空間。":::

1. 配置完成後，請移至新建立的儲存體帳戶。 在導覽窗格中，選取 **設定** > **存取金鑰**。 

1. 複製 **帳戶名稱** 和 **金鑰**，以在建立新匯出時使用。
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="儲存體帳戶中的存取金鑰。":::

## <a name="export-events"></a>匯出事件

匯出事件的方式有兩種： 
- 移至 **資料** > **匯出**，並選取 **新匯出**。
- 移至 **資料** > **事件**，在要匯出的事件旁邊選取 **其他 [...]**，然後從下拉式功能表選取 **匯出**。 

將會一步一步引導您建立匯出：

1. 提供 **匯出名稱**。

1. 在 **事件選項** 下拉式清單中，選擇要納入匯出的基準事件和精簡事件。 

1. 在 **檔案結構** 底下，選取要在目標儲存體中建立新檔案的節奏。 事件在到達時會持續被匯出。

1. 選取匯出的格式。 您可以選擇 **一般資料模型**、**CSV** 和 **JSON** 格式。 匯出時若要一併使用其他 Dynamics 365 應用程式，我們建議您使用一般資料模型格式。

1. 在 **選擇目標** 步驟中，指定第二代 Azure Data Lake Storage 的位置。
    1. **第二代 ADLS 帳戶名稱** 是您要儲存匯出的目標儲存體帳戶名稱。 
    1. **資料夾路徑** 定義了匯出在儲存體帳戶的檔案系統和目錄結構中應儲存的地方。
    1. 您可以從 Azure 入口網站儲存體帳戶中找到 **共用金鑰**。

1. 檢閱並確認您的選取。

## <a name="view-and-manage-exports"></a>檢視和管理匯出

設定好匯出之後，請移至 **資料** > **匯出** 以進行查看。 選取 **其他 [...]**，以編輯或刪除任何現存的匯出。


[!INCLUDE[footer-include](../includes/footer-banner.md)]