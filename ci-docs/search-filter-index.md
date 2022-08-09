---
title: 管理客戶設定檔的搜尋和篩選索引
description: 快速尋找有關所指定屬性的統整客戶設定檔和篩選的相關資訊。
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187899"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>管理客戶設定檔的搜尋和篩選索引

整合您的客戶資料的結果是 *客戶* 實體，可提供整體客戶群的整合檢視。 為了讓使用者快速 [尋找特定客戶或客戶群組的資訊](customer-profiles.md)，管理員必須在 **客戶** 頁面上設定 **搜尋** 和 **篩選** 功能。

   :::image type="content" source="media/search-filter.png" alt-text="搜尋篩選":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>定義可搜尋的屬性與索引欄位

如果是第一次以系統管理員身分定義可搜尋屬性，則必須先定義索引欄位。 我們建議您在 **客戶** 頁面上選擇使用者可以用來搜尋和篩選客戶的所有屬性。 只能指定在資料整合流程中建立之 *客戶* 實體中存在的屬性。

1. 前往 **客戶** 頁面，然後選取 **搜尋和篩選索引**。

1. 選取 **+ 新增**。

1. 在清單中選取您要新增為索引欄位的屬性，然後點選 **套用**。

1. 若要新增其他屬性，請選取 **新增**。 若要移除所選屬性，請選取該屬性，然後選取 **刪除**。

   :::image type="content" source="media/search-filter-index.png" alt-text="搜尋和篩選索引頁面。":::

1. 當您準備好套用您的搜尋和篩選設定時，請選取 **執行**。 變更處理完成後，可在[客戶頁面的客戶卡片](customer-profiles.md)中檢視它們。

## <a name="define-filtering-options-for-a-given-attribute"></a>定義指定屬性的篩選選項

設定在 **客戶** 頁面上可用於篩選客戶的欄位。

1. 前往 **客戶** 頁面，然後選取 **搜尋和篩選索引**。

1. 請選取屬性，然後選取 **新增篩選**。 可定義結果的數目以及組織的順序。 視屬性的資料類型而定，會顯示下列其中一個窗格。

   - 字串類型屬性：指定 **字串篩選** 窗格上所需的結果數，以及組織這些結果所依據的順序原則。

   - 數值類型屬性：指定 **數字篩選** 窗格上包含的間隔數，以及組織這些間隔所依據的順序原則。

   - 日期類型屬性：指定 **日期篩選** 窗格上包含的間隔數，以及組織這些間隔所依據的順序原則。

1. 選取 **確定**。 對您要篩選的所有屬性重複此動作。

1. 當您準備好套用您的搜尋和篩選設定時，請選取 **執行**。 變更處理完成後，可在[客戶頁面的客戶卡片](customer-profiles.md)中檢視它們。

## <a name="view-indexed-customer-fields"></a>檢視已建立索引的客戶欄位

**搜尋和篩選索引** 頁面會顯示下列資訊：

- **名稱**：代表屬性出現在 *客戶* 實體中的名稱。
- **資料類型**：指定資料類型為字串、數字或日期。
- **包含在搜尋中**：指定此屬性是否可用於使用 **搜尋** 欄位在 **客戶** 頁面上搜尋客戶。
- **新增篩選**：控制項以定義此屬性如何在 **客戶** 頁面上用於篩選。

## <a name="next-steps"></a>後續步驟

檢閱[整合個人資料頁面](customer-profiles.md)以搜尋個人資料，或使用索引欄位來查看所有整合個人資料的子集。

[!INCLUDE [footer-include](includes/footer-banner.md)]
