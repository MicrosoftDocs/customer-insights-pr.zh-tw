---
title: 搜尋和篩選客戶設定檔
description: 快速尋找有關所指定屬性的統整客戶設定檔和篩選的相關資訊。
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270056"
---
# <a name="customer-profiles-search--filter-index"></a>客戶設定檔：搜尋及篩選索引

統整您的客戶資料的結果是客戶設定檔實體，可提供整體客戶群的統整檢視。 若要快速 [尋找特定客戶或客戶群組的資訊](customer-profiles.md)，您可以在 **客戶** 頁面上設定 **搜尋** 和 **篩選** 功能。 請繼續閱讀，了解管理員如何在 **搜尋和篩選索引** 頁面上編輯屬性，以供使用者用來搜尋和篩選。

> [!div class="mx-imgBorder"]
> ![搜尋篩選](media/search-filter.png "搜尋篩選")

## <a name="add-fields-and-specify-attributes"></a>新增欄位並指定屬性

如果是第一次以系統管理員身分定義可搜尋屬性，則必須先定義索引欄位。 我們建議您在 **客戶** 頁面上選擇使用者可以用來搜尋和篩選客戶的所有屬性。 您只能指定在資料統整程序中所建立之客戶設定檔實體中存在的屬性。

1. 開啟 **客戶** 頁面，然後選取 **搜尋和篩選索引**。

2. 選取 **+ 新增** 以指定索引欄位。

3. 在清單中選取您要新增為索引欄位的屬性。 您可以選取 **新增**，以新增更多的屬性。 您也可以選取 **移除** 符號，移除任何選取的屬性。

## <a name="explore-the-indexed-customer-fields-table"></a>探索已建立索引的客戶欄位表格

表格中呈現下列資訊。

- **名稱**：代表屬性出現在客戶設定檔實體中的名稱。
- **資料類型**：指定資料類型為字串、數字或日期。
- **包含在搜尋中**：指定此屬性是否可用於使用 **搜尋** 欄位在 **客戶** 頁面上搜尋客戶。
- **新增篩選**：控制項以定義此屬性如何在 **客戶** 頁面上用於篩選。

## <a name="editing-filtering-options-for-a-given-attribute"></a>編輯給定屬性的篩選選項

**客戶** 頁面的 **篩選** 功能表可以包括不同數目的屬性等級（例如，不同的年齡群組以篩選客戶）。

1. 在 **搜尋和篩選索引** 頁面上，為給定的屬性選取 **新增篩選**。 您可以定義結果的數目以及組織的順序。 視屬性的資料類型而定，會顯示下列其中一個窗格。

- 字串類型屬性：指定 **字串篩選選項** 窗格上所需的結果數，以及組織這些結果所依據的順序原則。

- 數值類型屬性：指定 **數字篩選選項** 窗格上包含的間隔數，以及組織這些間隔所依據的順序原則。

- 日期類型屬性：指定 **日期篩選選項** 窗格上包含的間隔數，以及組織這些間隔所依據的順序原則。

2. 選取 **儲存** 套用變更。

3. 當您準備好套用您的設定時，請選取 **執行**。

## <a name="next-steps"></a>後續步驟

移至 **客戶** 頁面以搜尋客戶設定檔，或使用索引欄位來查看所有客戶設定檔的子集。


[!INCLUDE[footer-include](../includes/footer-banner.md)]