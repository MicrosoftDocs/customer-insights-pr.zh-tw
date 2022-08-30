---
title: 客戶細分概觀
description: 客戶細分概觀及如何建立並管理它們。
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d4de3a6af6bc7d54305a23e3fbd3cc95d464d352
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304785"
---
# <a name="segments-overview"></a>客戶細分概觀

客戶細分讓您根據人口統計、交易性或行為屬性分組您的客戶。 為了達成業務目標，您可以使用客戶細分來設定目標促銷活動、銷售活動和客戶支援動作。

符合客戶細分定義篩選條件的客戶或連絡人設定檔稱為客戶細分的 *成員*。 適用若干 [服務限制](/dynamics365/customer-insights/service-limits)。

## <a name="create-a-segment"></a>建立客戶細分

選擇如何根據目標對象建立客戶細分。

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- 包含客戶細分建立器的複雜客戶細分：[建立自己的](segment-builder.md)
- 具有一個運算子的簡單客戶細分：[快速客戶細分](segment-quick.md)
- 以 AI 支援的方式尋找類似客戶：[類似客戶](find-similar-customer-segments.md)
- 根據量值或屬性的 AI 建議：[根據量值的建議客戶細分](suggested-segments.md)
- 根據活動提出的建議：[根據客戶活動所建議的客戶細分](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[商務客戶 (B 到 B)](#tab/b2b)

使用客戶細分建立器的帳戶客戶細分或連絡人客戶細分 (預覽版)：[自行建立](segment-builder.md)

> [!NOTE]
> 大多數匯出目的地都需要用於行銷的連絡人資訊。 因此，請建立連絡人客戶細分以便用於這些匯出。

---

## <a name="manage-existing-segments"></a>管理現有的客戶細分

移至 **客戶細分** 頁面，以檢視您所建立的客戶細分、其階段與狀態，以及上次重新整理資料的時間。 您可以用任何欄來排序客戶細分清單，或是使用搜尋方塊尋找您要管理的客戶細分。

> [!TIP]
> 在 B 到 B 環境中，**對象類型** 欄可識別據以建立客戶細分的是客戶還是連絡人。

選取客戶細分來查看可用的動作。

:::image type="content" source="media/segments-selected-segment.png" alt-text="選定的客戶細分，有選項下拉式清單和可用選項。" lightbox="media/segments-selected-segment.png":::

- [**檢視**](#view-segment-details)客戶細分詳細資料，包括成員計數趨勢和客戶細分成員的預覽。
- 將成員清單 **下載** 為 .CSV 檔案。
- **編輯** 客戶細分以變更其屬性。
- 為客戶細分 **建立複本**。 您可以選擇立即編輯其屬性，或儲存複本。
- [**重新整理**](#refresh-segments)客戶細分以包括最新的資料。
- **啟用** 或 **停用** 客戶細分。 非使用中客戶細分在 [已排程的重新整理](schedule-refresh.md)期間不會重新整理，並且 **狀態** 列示為 **已跳過**，表示甚至未嘗試重新整理。 活動段根據其類型進行重新整理：靜態或動態。
- 使 **靜態** 或 **動態** 成為客戶細分類型。 靜態客戶細分手動重新整理。 在系統重新整理期間，會自動重新整理動態客戶細分
- 從客戶細分中 [**尋找類似的客戶**](find-similar-customer-segments.md)。
- **重新命名** 客戶細分。
- **標籤** 可在客戶細分[管理標籤](work-with-tags-columns.md#manage-tags)。
- [**管理匯出**](#export-segments)，以查看匯出相關的客戶細分並加以管理。 [深入了解匯出。](export-destinations.md)
- **刪除** 客戶細分。
- **欄**，可[自訂顯示的欄](work-with-tags-columns.md#customize-columns)。
- **篩選** 可[篩選標籤](work-with-tags-columns.md#filter-on-tags)。
- **搜尋名稱**，依據客戶細分名稱進行搜尋。

## <a name="view-segment-details"></a>檢視客戶細分詳細資料

在 **客戶細分** 頁面上，選取客戶細分以查看處理歷史記錄和客戶細分成員。

此頁面的上半部分包括趨勢圖形，其中會視覺化呈現成員計數的變化。 將游標移到資料點上方可查看特定日期的成員計數。 可變更視覺效果的時間範圍。

:::image type="content" source="media/segment-time-range.png" alt-text="客戶細分時間範圍。":::

下半部分包含客戶細分成員的清單。

> [!NOTE]
> 此清單中顯示的欄位是根據客戶細分實體的屬性。
>
> 此清單是相符客戶細分成員的預覽，並顯示客戶細分的前 100 個記錄，這樣您就可以快速評估並查看其定義 (如有需要)。 若要查看所有相符的記錄，請選取 **查看更多**，這會開啟 [**實體**](entities.md)頁面，或[匯出客戶細分](export-destinations.md)。

## <a name="refresh-segments"></a>重新整理客戶細分

客戶細分可自動排程或依照需要情況手動重新整理。 若要手動重新整理一個或多個客戶細分，請選取它們，然後選擇 **重新整理**。

若要 [排程自動重新整理](schedule-refresh.md)，請前往 **系統管理** > **系統** > **排程**。 適用於以下規則：

- 所有具有 **動態** 或 **展開** 類型的客戶細分，都會在設定的步調自動重新整理。 重新整理完成時，**狀態** 會指示在重新整理該客戶細分是否有任何問題。 **上次重新整理** 時，會顯示上次成功重新整理的時間戳記。 如果發生錯誤，請選取錯誤查看問題的詳細資料。
- 類型為 **靜態** 的客戶細分將 *不* 會自動重新整理。 **上次重新整理** 顯示上次執行的時間戳記，靜態客戶細分來自手動重新整理。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>匯出客戶細分

將客戶細分匯出至其他應用程式以進一步使用資料。 可從客戶細分頁面或[匯出頁面](export-destinations.md)匯出客戶細分。

1. 前往 **客戶細分** 頁面，然後選取您想匯出的客戶細分。

1. 選擇 **管理匯出**。 會打開 **匯出客戶細分 (預覽版)** 頁面。 依是否包含目前客戶細分的分組查看所有設定的匯出。

   1. 若要將選取的客戶細分新增到匯出，請 **編輯** 各自匯出以選取對應的客戶細分，然後儲存。 在個別客戶環境中，選取清單中的匯出和 **新增客戶細分** 以取得相同的結果。

   1. 若要使用選取的客戶細分建立新匯出，請選取 **新增匯出**。 如需建立匯出的詳細資訊，請參閱[設定新匯出](export-destinations.md#set-up-a-new-export)。

1. 選取 **上一步** 以返回至客戶細分的主要頁面。

## <a name="track-usage-of-a-segment"></a>追蹤客戶細分的使用方式

如果您在應用程式中使用客戶細分 (這些客戶細分是根據連接至 Customer Insights 的相同 Microsoft Dataverse 組織)，則可以追蹤客戶細分的使用方式。 對於 [Dynamics 365 Marketing 的客戶旅程中使用的 Customer Insights 客戶細分](/dynamics365/marketing/real-time-marketing-ci-profile)，系統會通知您該客戶細分的使用方式。

在編輯在 Customer Insights 環境中或在 Marketing 的客戶旅程中使用的客戶細分時，[客戶細分建立器](segment-builder.md)中的橫幅會通知您有關相依性的資訊。 可直接從標題中檢查相依性詳細資料，或是透過選取客戶細分建立器中的 **使用方式** 來檢查。

**客戶細分使用方式** 窗格會顯示有關此客戶細分在 Dataverse 應用程式中使用方式的詳細資料。 對於在客戶旅程中使用的客戶細分，您會發現一個連結，可檢查使用此客戶細分的 Marketing 旅程。 如果您擁有存取 Marketing 應用程式的權限，可在那裡檢視更多詳細資料。

:::image type="content" source="media/segment-usage-pane.png" alt-text="側邊窗格，包含客戶細分建立器中客戶細分使用方式的詳細資料。":::

當您嘗試刪除所追蹤的客戶細分時，系統會通知您關於該客戶細分的使用方式。 如果您要刪除的客戶細分用在 Marketing 的客戶旅程中，則該旅程將會針對該客戶細分中的所有使用者停止。 如果旅程是行銷廣告活動的一部分，則刪除會影響該行銷活動本身。 不過，即使發生警告，仍可以刪除客戶細分。

:::image type="content" source="media/segment-usage-delete.png" alt-text="當客戶細分用於 Dataverse 應用程式時，確認刪除客戶細分的對話方塊。":::

### <a name="supported-apps"></a>支援的應用程式

目前在下列 Dataverse 應用程式中追蹤使用方式：

- [Dynamics 365 Marketing 中的客戶旅程](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
