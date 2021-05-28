---
title: 從 Customer Insights 匯出資料
description: 管理匯出到共用資料 。
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016604"
---
# <a name="exports-preview-overview"></a>匯出 (預覽版) 概觀

**匯出** 頁面會顯示所有已設定的匯出。 匯出與各種應用程式共用指定資料。 這可以包括客戶個人資料或實體、結構描述及對應詳細資料。 每個匯出都需要[由系統管理員設定的連接，來管理驗證和存取權](connections.md)。

移至 **資料** > **匯出** 以查看匯出頁面。 所有使用者角色都擁有存取權，可以查看設定好的匯出。 在命令列中使用搜尋欄位，可用名稱、連接名稱或連線類型來尋找匯出。

## <a name="set-up-a-new-export"></a>設定新的匯出

若要設定或編輯匯出，您需要有可用的連接。 連接依據您的[使用者角色](permissions.md)而定：
- 系統管理員可以存取所有的連接。 在設定匯出時，他們也可以建立新的連接。
- 參與者可以存取特定的連接。 他們依賴系統管理員來設定和共用連接。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。
- 檢視器只能查看現有的匯出，並不能建立。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出目的地，請選取 **新增匯出**。

1. 在 **設定匯出** 窗格中，選取要使用的連接。 [連接](connections.md)是由系統管理員所管理。 

1. 提供必要的詳細資料，並選取 **儲存** 來建立匯出。

### <a name="edit-an-export"></a>編輯匯出

1. 選取想要編輯的匯出目的地其垂直省略符號。

1. 從下拉式清單功能表中選取 **編輯**。

1. 變更想要更新的值並選取 **儲存**。

## <a name="view-exports-and-export-details"></a>查看匯出和匯出詳細資料

建立匯出目的地之後，就會在 **資料** > **匯出** 中列出。 所有使用者都可以看到已共用的資料及其最新狀態。

1. 移至 **資料** > **匯出**。

1. 沒有編輯權限的使用者選取 **查看** 而非 **編輯** 來查看匯出詳細資料。

1. 此側邊窗格會顯示這項匯出的設定。 若沒有編輯權限，就無法變更值。 選取 **關閉** 來返回匯出頁面。

## <a name="run-exports-on-demand"></a>視需要執行匯出

設定匯出之後，只要有能運作的連接，每次[排程的重新整理](system.md#schedule-tab)都會執行。

若不等待排程的重新整理，要匯出資料，請移至 **資料** > **匯出**。 您有兩個選擇：

- 若要執行所有匯出，請選取命令列中的 **全部執行**。 
- 若要執行單一匯出，請選取清單項目的省略號 (...) ，然後選擇 **執行**。

## <a name="remove-an-export"></a>移除匯出

1. 移至 **資料** > **匯出**。

1. 選取要移除的匯出目的地其垂直省略符號。

1. 從下拉式功能表中選取 **移除**。

1. 在確認畫面上選取 **移除** 以確認移除。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
