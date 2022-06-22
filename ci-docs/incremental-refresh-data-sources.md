---
title: Power Query 與 Azure Data Lake 資料來源的累加式重新整理
description: 對於新資料和更新資料位於以 Power Query 設置的大型資料來源或 Azure data lake 資料來源，進行重新整理。
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012015"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Power Query 與 Azure Data Lake 資料來源的累加式重新整理

本文討論對於對建立在 Power Query 或 Azure Data Lake 的資料來源，如何設定累加式重新整理。

對資料來源進行累加重新整理可提供下列好處：

- **更快速的重新整理** -只有已變更的資料才會重新整理。 例如，您可能只會重新整理過去五天的歷史資料集。
- **提高的可靠性** - 進行較小量的重新整理時，您不需要長時間維持與動態來源系統的連線，並可減少發生連線問題的風險。
- **減少資源消耗** - 僅重新整理總體資料的一部分，才能更有效率地使用運算資源，並減少環境的磁碟使用量。

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>對以 Power Query 設置的資料來源設定累加式重新整理

只要是透過支援累加式擷取的 Power Query匯入的資料來源，Customer Insights 允許其進行累加式重新整理。 例如，包含日期和時間欄位 (表示資料記錄上次更新時間) 的 Azure SQL 資料庫。

1. [建立新的 Power Query 資料來源](connect-power-query.md)。

1. 選取支援累加式重新整理的資料來源，例如 [ Azure SQL 資料庫](/power-query/connectors/azuresqldatabase)。

1. 選取要內嵌的實體或資料表。

1. 完成轉換步驟，然後選取 **下一步**。

1. 在 **設定增量重新整理** 對話方塊中，選取 **設定** 以開啟 **增量重新整理設定**。 如果您選取 **略過**，資料來源將會重新整理整個資料集。
   > [!TIP]
   > 您也可以編輯現有的資料來源，稍後再套用增量更新。

1. 在 **增量重新整理設定** 中，您可以為所有在建立資料來源時選取的所有實體設定增量重新整理。

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="設定累加式重新整理。":::

1. 選取實體，並提供下列詳細資料：

   - **定義主索引鍵**：選取實體或資料表的主索引鍵。
   - **定義 [上次更新] 欄位**：此欄位只會顯示日期或時間類型的屬性。 選取表示記錄上次更新時間的屬性。 這會用來找出落在累加重新整理時間範圍內的記錄。
   - **檢查更新間隔**：指定您想要的增量重新整理時間範圍的時間長度。

1. 選取 **儲存** 以完成建立資料來源的作業。 初始資料重新整理會是完整重新整理。 此後，增量資料重新整理會依照上一個步驟中所設定的方式進行。

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>設定 Azure Data Lake 資料來源的累加式重新整理

Customer Insights 允許對連接至 Azure Data Lake Storage 的資料來源進行累加式重新整理。 若要使用實體的累加式內嵌和重新整理，請在新增 Azure Data Lake 資料來源或稍後編輯資料來源時，設定該實體。 實體資料的資料夾必須包含下列資料夾：

- **FullData**：資料夾中包含初始記錄的資料檔案
- **IncrementalData**：資料夾中有累加式更新且日期/時間階層資料夾格式為 **yyyy/mm/dd/hh**。 **hh** 表示更新的 UTC 時間，且包含 **Upserts** 及 **Deletes** 資料夾。 **Upserts** 包含現有記錄或新記錄的更新的資料檔案。 **Deletes** 包含要移除的記錄的資料檔案。

1. 在新增或編輯資料來源時，請瀏覽至該實體的 **屬性** 窗格。

1. 檢閱屬性。 請確定已建立或上次更新的日期屬性是設定為 *dateTime* **資料格式** 和 *Calendar.Date* **語義類型**。 如有需要，請編輯屬性，然後選取 **完成**。

1. 從 **選取實體** 窗格，編輯實體。 **累加式內嵌** 核取方塊已選取。

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="設定資料來源中的實體以進行累加式重新整理。":::

   1. 完整資料、累加式資料更新插入和累加式資料刪除的 .csv 或 .parquet 檔案位於同一個根資料夾，請瀏覽至該根資料夾。
   1. 輸入完整資料和兩個累加式檔案的副檔名 (\.csv or \.parquet)。
   1. 選取 **儲存**。

1. **在上次更新** 中，選取時間戳記屬性。

1. 如果 **主索引鍵** 未選取，請選取主索引鍵。 主索引鍵是實體的唯一屬性。 若要讓屬性成為有效的主索引鍵，其中不能包含重複值、遺漏值或 Null 值。 字串、整數及 GUID 資料類型屬性均支援主索引鍵。

1. 選取 **關閉** 以儲存並關閉窗格。

1. 繼續新增或編輯資料來源。

[!INCLUDE [footer-include](includes/footer-banner.md)]
