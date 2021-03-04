---
title: 實體和資料集
description: 在實體頁面上檢視資料。
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269366"
---
# <a name="entities-in-audience-insights"></a>對象見解中的實體

[設定資料來源](data-sources.md)之後，請移至 **實體** 頁面，評估所擷取資料的品質。 實體被視為資料集。 Dynamics 365 Customer Insights 的多重功能圍繞這些實體組建。 仔細檢閱它們可協助您驗證這些功能的輸出。

**實體** 頁面會列出實體，並包含數欄：

- **名稱**：您的資料實體名稱。 如果實體名稱旁邊出現警告符號，表示無法順利載入該實體的資料。
- **來源**：擷取實體的資料來源類型
- **建立者**：建立實體的人員名稱
- **建立時間**：建立實體的日期與時間
- **更新者**：更新實體的人員名稱
- **上次更新日期**：上次更新實體的日期與時間
- **上次重新整理**：上次資料重新整理的日期與時間

## <a name="exploring-a-specific-entitys-data"></a>探索特定實體的資料

選取一個實體，以探索該實體中包含的不同欄位和記錄。

> [!div class="mx-imgBorder"]
> ![選取實體](media/data-manager-entities-data.png "選取實體")

- 預設會選取 **資料** 索引標籤，並顯示一份表格，其中列出有關實體各個記錄的詳細資料。

> [!div class="mx-imgBorder"]
> ![欄位表格](media/data-manager-entities-fields.PNG "欄位表格")

- **欄位** 索引標籤會顯示一個表格，用以檢視所選實體的詳細資料，例如欄位名稱、資料類型和類型。 **類型** 欄會顯示 Common Data Model 關聯的類型，它們是由系統自動識別或由使用者[手動對應](map-entities.md)。 這些語意類型可以不同於屬性的資料類型，例如，下列的欄位 *電子郵件* 有資料類型 *文字*，但是其 (語意) Common Data Model 類型可能是 *電子郵件* 或 *EmailAddress*。

> [!NOTE]
> 這兩個表格只會顯示您實體之資料的範例。 若要查看完整資料集，請移至 **資料來源** 頁面，選取實體，選取 **編輯**，然後使用 Power Query 編輯器查看此實體的資料（如[資料來源](data-sources.md)中所述）。

若要進一步了解實體中擷取的資料，**摘要** 欄提供了一些重要的資料特徵，例如 null、遺失值、唯一值、計數和分佈（視何者適用於您的資料）。

選取圖表圖示以查看資料的摘要。

> [!div class="mx-imgBorder"]
> ![摘要符號](media/data-manager-entities-summary.png "資料摘要表格")

### <a name="next-step"></a>後續步驟

若要了解如何 *對應*、*比對* 和 *合併* 擷取的資料，請參閱[統整](data-unification.md)主題。


[!INCLUDE[footer-include](../includes/footer-banner.md)]