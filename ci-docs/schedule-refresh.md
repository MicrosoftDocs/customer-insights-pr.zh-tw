---
title: 排程系統重新整理
description: 排程應重新整理系統的時間
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246333"
---
# <a name="schedule-system-refresh"></a>排程系統重新整理

排程所有[內嵌資料來源](data-sources.md)的自動重新整理。 自動重新整理可協助確保資料來源更新會反映在您的統一客戶設定檔中。

> [!NOTE]
> 您管理的 Power Query 資料來源會依自己的排程來重新整理。 若要這些 Power Query 資料來源排程重新整理，請到 **資料來源** 頁面設定該特定資料來源的重新整理。
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform資料流程重新整理設定。":::

## <a name="set-system-refresh-schedule"></a>設定系統重新整理排程

1. 請前往 **系統管理員** > **系統** ，然後選取 **排程** 索引標籤。

   :::image type="content" source="media/schedule_refresh.png" alt-text="從系統頁面排程重新整理索引標籤。":::

1. 排程的重新整理預設狀態為 **關閉**。 若要啟用排程的重新整理，請將畫面頂端的切換變更為 **開啟**。

1. 在 **每週**（預設）和 **每日** 重新整理之間選擇。 如果想要排定每週重新整理，請選取一或多個要執行重新整理的天數。

1. 設定您的 **時區**，然後使用 **時間** 下拉式功能表來設定您的重新整理時間安排。 如果您想要在一天中安排多次重新整理，請選取 **新增其他時間**。

1. 選取 **儲存** 套用變更。

[!INCLUDE [footer-include](includes/footer-banner.md)]
