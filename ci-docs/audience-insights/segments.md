---
title: 對象見解中的客戶細分
description: 客戶細分概觀及如何建立並管理它們。
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6e2080b4ad19f6f57f60da591345e80ce9083e8a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554057"
---
# <a name="segments-overview"></a>客戶細分概觀

區段讓您根據人口統計、交易性或行為屬性分組您的客戶。 為了達成業務目標，您可以使用區段來設定目標促銷活動、銷售活動和客戶支援動作。

符合客戶細分定義篩選的客戶個人資料稱為客戶細分的 *成員*。 適用若干 [服務限制](service-limits.md)。

## <a name="create-a-new-segment"></a>建立新區段

有很多方式可以建立新的客戶細分： 

- 具備客戶細分產生器的複雜客戶細分：[空白客戶細分](segment-builder.md#create-a-new-segment)
- 具有一個運算子的簡單客戶細分：[快速客戶細分](segment-builder.md#quick-segments)
- 以 AI 支援的方式尋找類似客戶：[類似客戶](find-similar-customer-segments.md)
- 基於量值或屬性，由 AI支援的建議：[改善量值的建議客戶細分](suggested-segments.md)
- 根據活動提出的建議：[根據客戶活動所建議的客戶細分](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>管理現有的區段

移至 **客戶細分** 頁面，以查看所有已儲存的客戶細分並加以管理。

每個區段都是由一個包含區段其他相關資訊的列所表示。

:::image type="content" source="media/segments-selected-segment.png" alt-text="選定的客戶細分，有選項下拉式清單和可用選項。":::

選取客戶細分時，可使用下列動作：

- **檢視** 區段詳細資料，包括成員計數趨勢和區段成員的預覽。
- **編輯** 區段以變更其屬性。
- 為客戶細分 **建立複本**。 您可以選擇立刻編輯屬性，或只是儲存複本。
- **重新整理** 區段以包括最新的資料。
- **啟用** 或 **停用** 區段。 客戶細分有兩種可能狀態：使用中或非使用中。 編輯客戶細分時，將會用到這些狀態。 如果是非使用中客戶細分，雖有客戶細分定義存在，但尚未包含任何客戶。 啟用客戶細分時，其狀態會從 [非使用中] 變更為 [使用中]，並且開始尋找符合區段定義的客戶。 如果設定了 [已排定重新整理](system.md#schedule-tab)，則非使用中客戶細分會將 **狀態** 列示為 **已跳過**，表示甚至未嘗試重新整理。 啟用非使用中客戶細分時，此客戶細分會重新整理，並納入已排定重新整理。
  或者，也可以使用 **啟用/停用** 下拉式功能表中的 **稍後再排程** 功能，指定未來啟用和停用特定客戶細分的日期和時間。
- **重新命名** 區段。
- 將成員清單 **下載** 為 .CSV 檔案。
- **管理匯出**，以查看匯出相關的客戶細分並加以管理。 [深入了解匯出。](export-destinations.md)
- **刪除** 區段。

## <a name="refresh-segments"></a>重新整理區段

您可以選取 **區段** 頁面上的 **全部重新整理**，一次重新整理所有區段，也可以在選取一個或多個區段，並從選項中選擇 **重新整理** 時重新整理這些區段。 或者，您也可以在 **管理員** > **系統** > **排程** 設定定期重新整理。

> [!TIP]
> 任務/流程目前有 [六種類型的狀態](system.md#status-types)。 此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。 您可以選取程序的狀態，以查看整個工作的進度詳細資料。 針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。

## <a name="export-segments"></a>匯出區段

您可以從客戶細分頁面或[匯出頁面](export-destinations.md)匯出客戶細分。 

1. 移至 **區段** 頁。

1. 在您要匯出的客戶細分上，選取 **顯示更多 [...]**。

1. 從動作下拉式清單中選擇 **管理匯出**。

1. 會打開 **匯出客戶細分 (預覽版)** 頁面。 您可以看到已設定的匯出，匯出會分成包含目前的客戶細分，或不包含的。

   1. 若要將選取的客戶細分新增至匯出，請在清單中選取匯出，然後選取 **新增客戶細分**。

   1. 若要使用選取的客戶細分建立新匯出，請選取 **新增匯出**。 如需建立匯出的詳細資訊，請參閱[設定新匯出](export-destinations.md#set-up-a-new-export)。

1. 選取 **上一步** 以返回至客戶細分的主要頁面。

## <a name="view-processing-history-and-segment-members"></a>查看處理歷史記錄和區段成員

您可以透過查看資料的詳細資料，查看關於該區段的合併資料。

在 **區段** 頁面上選取您想檢閱的區段。

此頁面的上半部分包括趨勢圖形，其中會視覺化呈現成員計數的變化。 將游標移到資料點上方可查看特定日期的成員計數。

您可以更新視覺效果的時間範圍。

> [!div class="mx-imgBorder"]
> ![客戶細分時間範圍。](media/segment-time-range.png "區段時間範圍")

下半部分包含區段成員的清單。

> [!NOTE]
> 此清單中顯示的欄位是根據區段實體的屬性。
>
>此清單是相符區段成員的預覽，並顯示區段的前 100 個記錄，這樣您就可以快速評估並查看其定義（如有需要）。 若要查看所有相符的記錄，您需要[匯出區段](export-destinations.md)。

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
