---
title: 對 Power Query 式資料來源的增量重新整理
description: 針對以 Power Query 為基礎的大型資料來源重新整理其新增及更新資料。
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: f614d701aeb06720a60b14549a7fe666f8fe0617
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900245"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>適用於以 Power Query 為基礎之資料來源的累加重新整理

本文討論如何對基於 Power Query 的資料來源設定累加式重新整理。

對資料來源進行累加重新整理可提供下列好處：

- **更快速的重新整理** -只有已變更的資料才會重新整理。 例如，您可能只會重新整理過去五天的歷史資料集。
- **提高的可靠性** - 進行較小量的重新整理時，您不需要長時間維持與動態來源系統的連線，並可減少發生連線問題的風險。
- **減少資源消耗** - 僅重新整理總體資料的一部分，才能更有效率地使用運算資源，並減少環境的磁碟使用量。

## <a name="configure-incremental-refresh"></a>設定累加重新整理

對象見解允許透過支援增量內嵌的 Power Query，對匯入的資料來源增量重新整理。 例如，包含日期和時間欄位 (表示資料記錄上次更新時間) 的 Azure SQL 資料庫。

1. [以 Power Query 為基礎建立新的資料來源](connect-power-query.md)。

1. 提供資料來源的 **名稱**。

1. 選取支援累加式重新整理的資料來源，例如 [ Azure SQL 資料庫](/power-query/connectors/azuresqldatabase)。

1. 選取要內嵌的實體或資料表。

1. 完成轉換步驟，然後選取 **下一步**。

1. 在 **設定增量重新整理** 對話方塊中，選取 **設定** 以開啟 **增量重新整理設定**。 如果您選取 **略過**，資料來源將會重新整理整個資料集。
   > [!TIP]
   > 您也可以編輯現有的資料來源，稍後再套用增量更新。

1. 在 **增量重新整理設定** 中，您可以為所有在建立資料來源時選取的所有實體設定增量重新整理。

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="設定資料來源中的實體以進行累加式重新整理。":::

1. 選取實體，並提供下列詳細資料：

   - **定義主索引鍵**：選取實體或資料表的主索引鍵。
   - **定義 [上次更新] 欄位**：此欄位只會顯示日期或時間類型的屬性。 選取表示記錄上次更新時間的屬性。 這會用來找出落在累加重新整理時間範圍內的記錄。
   - **檢查更新間隔**：指定您想要的增量重新整理時間範圍的時間長度。

1. 選取 **儲存** 以完成建立資料來源的作業。 初始資料重新整理會是完整重新整理。 此後，增量資料重新整理會依照上一個步驟中所設定的方式進行。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
