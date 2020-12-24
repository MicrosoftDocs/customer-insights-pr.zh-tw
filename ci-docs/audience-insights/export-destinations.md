---
title: 匯出目的地
description: 匯出資料和管理匯出目的地。
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643853"
---
# <a name="export-destinations-preview"></a>匯出目的地 (預覽)

**匯出目的地** 頁面會顯示所有您已設定要匯出到的位置。 您也可以加入新的匯出目的地。 此外它顯示匯出目前可用的選項。 取得快速概觀、描述，並了解每個擴充性選項可用來執行的工作。 將統一的設定檔、量值及區段匯出至與您的業務相關的支援應用程式。

移至 **管理** > **匯出目的地**，尋找下列擴充性選項：

- [Dynamics 365 Customer 卡片增益集](customer-card-add-in.md)
- [Facebook 廣告管理員連接器](export-facebook.md)
- [Power Automate 連接器](export-power-automate.md)
- [Power Apps 連接器](export-power-apps.md)
- [Power BI 連接器](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob 儲存體](export-azure-blob-storage.md)
- [LiveRamp &reg; 連接器](export-liveramp.md)
- [Microsoft Teams 的機器人](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>新增匯出目的地

若要新增匯出目的地，您具有 [系統管理員權限](permissions.md)。 如果您匯出至 Microsoft 服務，我們會假設這兩個服務都位於相同的組織中。

1. 移至 **管理員** > **匯出目的地**。

1. 切換至 **我的匯出目的地** 索引標籤。

1. 選取 **新增目的地** 以建立新的匯出目的地。

1. 在 **新增目的地** 窗格中，從下拉式清單選取匯出目的地的 **類型**。

1. 提供必要詳細資料，並選取 **下一步** 以建立匯出目的地。

您也可以在 **探索** 索引標籤中選取圖標上的 **設定**。

## <a name="view-export-destinations"></a>檢視匯出目的地

建立匯出目的地之後，您會在 **我的匯出目的地** 索引標籤的表格中找到這些目的地。此表格有三個欄：

- **顯示名稱**：建立目的地時輸入的名稱。
- **類型**：建立目的地時所設定的匯出目的地類型。
- **建立日期**：目的地建立日期。

## <a name="edit-an-export-destination"></a>編輯匯出目的地

1. 選取所要編輯之匯出目的地的垂直省略符號。

   > [!div class="mx-imgBorder"]
   > ![垂直省略符號](media/export-destinations-page-ellipsis.png "垂直省略符號")

1. 從下拉式功能表中選取 **編輯**。

1. 變更需要更新的值，然後選取 **儲存**。

## <a name="export-data-on-demand"></a>視需要匯出資料

為匯出目的地設定連接器之後，匯出將會隨每個[排定的重新整理](system.md#schedule-tab)執行。

若要匯出資料，而不等待排定的重新整理，請在 **管理** > **匯出目的地** 上移至 **我的匯出目的地** 索引標籤。

> [!div class="mx-imgBorder"]
> ![垂直省略符號](media/export-destinations-page-ellipsis.png "垂直省略符號")

- 選取清單上方的 **匯出**，同時執行對所有匯出目的地的匯出。
- 選取清單項目後的省略符號 (...)，然後選擇 **匯出** 選項，針對單一匯出目的地執行匯出。

## <a name="remove-an-export-destination"></a>移除匯出目的地

若要移除匯出目的地，請從主要 **匯出目的地** 頁面開始。

1. 選取要移除之匯出目的地的垂直省略符號。

   > [!div class="mx-imgBorder"]
   > ![垂直省略符號](media/export-destinations-page-ellipsis.png "垂直省略符號")

2. 從下拉式功能表中選取 **移除**。

3. 在確認畫面上選取 **移除** 以確認移除。