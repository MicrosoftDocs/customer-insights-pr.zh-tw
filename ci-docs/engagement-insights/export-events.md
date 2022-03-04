---
title: 匯出精簡事件
description: 如何匯出精簡事件和基礎事件。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d062e2982c1041454b083630404f2b68f0da9669
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232878"
---
# <a name="export-events"></a>匯出事件

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

事件代表使用者的行為。 它會在使用者查看頁面（查看事件）或與內容互動（動作事件）時進行記錄。 當您可以決定要在報表中顯示資料的哪些屬性時，這個資料的虛擬視圖稱為 *精簡事件*。 如需詳細資訊，請參閱[建立和修改事件](refined-events.md)。

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

帶出 **匯出事件** 對話方塊有兩種方法： 
- 移至 **資料** > **匯出**，並選取 **新匯出**。
- 移至 **資料** > **事件**，在要匯出的事件旁邊選取 **其他 [...]**，然後從下拉式功能表選取 **匯出**。 

:::image type="content" source="media/new-export.png" alt-text="建立新匯出。":::

將會一步一步引導您建立匯出：

1. 提供 **匯出名稱**，然後選取 **下一步**。

1. 在 **事件選項** 下拉式清單中，選擇要納入匯出的基準事件和精簡事件。 

1. 請在 **檔案結構** 分段中選取目標儲存體要建立新檔案的節奏 (每小時或每天)，然後選取 **下一步**。 事件在到達時會持續被匯出。

1. 請在 **選擇格式** 對話方塊中選取匯出的格式。 請在 **Common Data Model**、**CSV** 和 **JSON** 格式之間任選其一。 若要連同其他 Dynamics 365 應用程式匯出，我們建議 **Common Data Model** 格式。

1. 請在 **選擇目的地** 對話方塊中指明 Azure Data Lake Storage Gen 2 的位置。
    1. **第二代 ADLS 帳戶名稱** 是您要儲存匯出的目標儲存體帳戶名稱。 
    1. **資料夾路徑** 定義了匯出在儲存體帳戶的檔案系統和目錄結構中應儲存的地方。
    1. 您可以從 Azure 入口網站儲存體帳戶中找到 **共用金鑰**。

1. 完成前請審閱並確認您選取的項目。

## <a name="view-and-manage-exports"></a>檢視和管理匯出

設定好匯出之後，請移至 **資料** > **匯出** 以進行查看。 選取 **其他 [...]**，以編輯或刪除任何現存的匯出。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
