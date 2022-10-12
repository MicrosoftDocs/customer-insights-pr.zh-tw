---
title: 資料來源概觀
description: 了解如何從不同的來源匯入或內嵌資料。
ms.date: 09/29/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610042"
---
# <a name="data-sources-overview"></a>資料來源概觀

Dynamics 365 Customer Insights 提供連結以從廣泛的來源取用資料。 連接至資料來源通常稱為 *資料擷取* 程序。 內嵌資料後，您可以進行[整合](data-unification.md)、生成見解，並啟動資料，以建立個人化體驗。

## <a name="add-or-edit-data-sources"></a>新增或編輯資料來源

您可以將資料來源附加到 Customer Insights 或選擇匯入資料來源。 下面連結提供新增和編輯資料來源的相關說明。

**附加資料來源**

如果您已在其中一種 Microsoft Azure 資料服務中準備好資料，則 Customer Insights 可以輕鬆連結至資料來源，無須重新內嵌資料。 選取下列其中一個選項：
- [Azure Data Lake Storage (csv 或 parquet 檔案在 Common Data Model 資料夾中)](connect-common-data-model.md)
- [Azure Synapse Analytics (湖資料庫)](connect-synapse.md)
- [Microsoft Dataverse 資料湖](connect-dataverse-managed-lake.md)

**匯入和轉換**

如果您使用內部部署的資料來源、Microsoft 或協力廠商資料，請使用 Power Query 連接器匯入和轉換資料。
- [Power Query 連接器](connect-power-query.md)

## <a name="review-data-sources"></a>檢閱資料來源

如果您的環境設定成使用 Customer Insights 儲存體，而且您使用的是內部部署資料來源，您可以使用 Power Platform 資料流程。 透過 Power Platform 資料流程，您可以查看共用的資料來源以及由其他人管理的資料來源。 **資料來源** 頁面會以三個區段列出資料來源：
- **共用**：所有 Customer Insights 系統管理員都可以管理的資料來源。 Power Platform 資料流程、您自己的儲存體帳戶以及附加到 Dataverse 受管理的資料湖，這些都是共用的資料來源的範例。
- **由我管理**：是僅由您建立且僅由您管理的 Power Platform 資料流程。 其他的 Customer Insights 系統管理員只能查看這些資料流程，但不可以編輯、重新整理或將它們刪除。
- **由其他人管理**：由其他系統管理員建立的 Power Platform 。 您只能進行查看。 它會列出資料流程負責人，可以聯繫取得協助。
> [!NOTE]
> 其他使用者都可以查看和使用所有的實體。 雖然資料來源的擁有者是建立資料來源的使用者，但是每個 Customer Insights 的使用者都可以使用資料擷取所生成的實體。

如果您的環境未使用 Power Platform 資料流程，則 **資料來源** 頁面只包含所有資料來源的清單。 顯示中沒有區段。

## <a name="manage-existing-data-sources"></a>管理現有的資料來源

移至 **資料** > **資料來源**，以查看每個內嵌資料來源的名稱、其狀態以及上次對該來源重新整理資料的時間。 您可以用任何欄來排序資料來源，或是使用搜尋方塊尋找您要管理的資料來源。

選取資料來源來查看可用的動作。

:::image type="content" source="media/data_sources_showmore.png" alt-text="已新增資料來源。":::

- [**編輯**](#add-or-edit-data-sources)資料來源以變更其屬性。
- [**重新整理**](#refresh-data-sources)資料來源以包括最新的資料。
- 在整合之前 [**擴充**](data-sources-enrichment.md)資料來源。
- **刪除** 資料來源。 只有在資料沒有進行任何處理 (如整合、見解、啟動或匯出) 時，才能刪除資料來源。

## <a name="refresh-data-sources"></a>重新整理資料來源

資料來源可自動排程或依照需要情況手動重新整理。 [內部部署資料來源](connect-power-query.md#add-data-from-on-premises-data-sources)會根據在資料擷取時設定的排程自行重新整理。 如需疑難排解提示，請參閱[疑難排解 PPDF Power Query 型資料來源重新整理問題](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues)。

對於附加的資料來源，資料擷取會使用該資料來源的最新資料。

請前往 **系統管理員** > **系統** > [**排程**](schedule-refresh.md)為內嵌資料來源設定系統排程的重新整理。

若要視需要重新整理資料來源：

1. 移至 **資料** > **資料來源**。

1. 選取您要重新整理的資料來源，然後選取 **重新整理**。 資料來源現在會針對手動重新整理觸發。 重新整理資料來源將會更新資料來源中所有指定實體的實體結構描述和資料。

1. 選取狀態以打開 **進度詳細資料** 窗格並查看進度。 若要取消作業，請在窗格下方選取 **取消作業**。

## <a name="corrupt-data-sources"></a>損毀資料來源

擷取的資料可能包含損毀的記錄，這可能會造成資料擷取過程完成但帶有錯誤或警告。

> [!NOTE]
> 如果資料擷取完成但帶有錯誤，則會略過利用此資料來源的後續處理 (例如，聯併或活動建立)。 如果擷取完成但帶有警告，則後續處理仍會繼續，但也許不會包含某些記錄。

您可以在工作詳細資料中看到這些錯誤。

:::image type="content" source="media/corrupt-task-error.png" alt-text="顯示損毀資料錯誤的工作詳細資料。":::

損毀記錄會顯示在系統建立的實體中。

### <a name="fix-corrupt-data"></a>修正損毀資料

1. 若要查看損毀資料，請移至 **資料** > **實體**，並在 **系統** 區段中尋找損毀實體。 損毀實體的結構描述名稱：'DataSourceName_EntityName_corrupt'。

1. 選取損毀實體，然後選取 **資料** 索引標籤。

1. 找出記錄中損毀的欄位和原因。

   :::image type="content" source="media/corruption-reason.png" alt-text="損壞原因。" lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **資料** > **實體** 只會顯示損毀記錄的一部分。 若要查看所有損毀的記錄，請使用 [Customer Insights 匯出行程](export-destinations.md)，將檔案匯出至儲存體帳戶中的容器。 如果您使用自己的儲存體帳戶，也可以在您的儲存體帳戶中查看 Customer Insights 資料夾。

1. 修正損毀的資料。 例如，如果是 Azure Data Lake 資料來源，請在 [Data Lake 儲存體中修正資料或更新 manifest/model. json 檔案中的資料類型](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data)。 如果是 Power Query 資料來源，請修正來源檔案中的資料，並在 **Power Query - 編輯查詢** 頁面上的[轉換步驟中更正資料類型](connect-power-query.md#data-type-does-not-match-data) 。

下次重新整理資料來源之後，已更正的記錄會擷取至 Customer Insights，並傳遞至下游處理程序。

例如，'birthday' 資料行會將資料類型設定為 'date'。 一筆客戶記錄的生日輸入成 '01/01/19777'。 系統會將此記錄標示為損毀。 在來源系統中將生日變更為「1977」。 在自動重新整理資料來源後，欄位現在會是有效的格式，而且該記錄已從損毀實體中移除。

[!INCLUDE [footer-include](includes/footer-banner.md)]
