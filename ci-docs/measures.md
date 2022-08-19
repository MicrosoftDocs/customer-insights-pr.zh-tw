---
title: 量值概觀
description: 了解量值是如何協助分析並反映業務表現。
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245363"
---
# <a name="measures-overview"></a>量值概觀

量值可協助您更清晰地了解客戶行為和業務績效。 它們會從[整合個人資料](data-unification.md)中檢查相關的值。 例如，公司想要查看 *每位客戶的總花費*，以瞭解單一客戶的購買歷史，或量值 *公司的總銷售人*，以瞭解整體業務中的總營收。

查詢客戶資料和擷取深入解析來建立規劃商務活動的量值。 例如，建立 *每個客戶的總消費額* 以及 *每個客戶的總利潤額*，能協助找出大量消費額度高且利潤高的客戶。 然後，根據這些量值[建立客戶細分](segments.md)，來推動下一個最佳行動。

## <a name="create-a-measure"></a>建立量值

選擇如何根據目標對象建立量值。

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- 使用量值建立器從頭開始：[建立自己的](measure-builder.md)。
- 從常用的量值：[使用預先定義的範本](measure-templates.md)。

# <a name="business-accounts-b-to-b"></a>[商務帳戶 (B2B)](#tab/b2b)

使用量值建立器從頭開始：[建立自己的](measure-builder.md)。

---

## <a name="manage-existing-measures"></a>管理現有的量值

移至 **量值** 頁面，以查看您所建立的量值、其狀態、量值類型，以及上次重新整理資料的時間。 您可以用任何欄來排序量值清單，或是使用搜尋方塊尋找您要管理的量值。

選取量值旁的按鈕來查看可用的動作。 選擇量值名稱以預覽輸出並下載 CSV 檔案。

:::image type="content" source="media/measures-actions.png" alt-text="管理單一量值的動作。"lightbox="media/measures-actions.png":::

- **編輯** 量值以變更其屬性。
- **重新整理** 量值以包括最新的資料。
- **重新命名** 量值。
- **啟用** 或 **停用** 量值。 非使用中量值在 [已排程的重新整理](schedule-refresh.md)期間不會重新整理，並且 **狀態** 列示為 **已跳過**，表示甚至未嘗試重新整理。
- **標記** 以針對量值[管理標籤](work-with-tags-columns.md#manage-tags)。
- **刪除** 量值。
- **欄**，可[自訂顯示的欄](work-with-tags-columns.md#customize-columns)。
- **篩選** 可[篩選標籤](work-with-tags-columns.md#filter-on-tags)。
- **搜尋名稱**，依據量值名稱進行搜尋。

## <a name="refresh-measures"></a>重新整理量值

量值可自動排程或依照需要情況手動重新整理。 若要手動重新整理一個或多個量值，請選取它們，然後選擇 **重新整理**。 若要 [排程自動重新整理](schedule-refresh.md)，請前往 **系統管理** > **系統** > **排程**。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
