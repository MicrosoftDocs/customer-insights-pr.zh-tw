---
title: 語意對應 (預覽版)
description: 語意對應總覽及使用方法。
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303866"
---
# <a name="semantic-mappings-preview"></a>語意對應 (預覽版)

> [!NOTE]
> **語意對應** 頁面僅適用於已使用此頁面建立連絡人設定檔的商務環境 (B 到 B)。 您可以使用 **語意對應** 頁面，繼續建立和管理個別連絡人設定檔。 或者，[整合連絡人資料](data-unification-contacts.md)以移除重複資料、跨實體找出相符項目，以及建立一個統一連絡人設定檔。 您可以接著使用統一連絡人設定檔來建立連絡人層級活動。

語意對應讓您將非活動資料對應到預先定義的結構描述。 這些結構描述有助於 Customer Insights 更了解您的資料屬性。 語義對應和已提供的資料，將啟用 Customer Insights 中的新見解與功能。 若要將您的活動資料對應到結構描述，請審閱[活動](activities.md)文件。

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>定義 ContactProfile 語義實體對應

1. 請前往 **資料** > **語意對應 (預覽版)**。

1. 請選取 **新增語意對應** 開始引導式體驗。

1. 請在 **實體資料** 步驟中設定下列欄位值：

   - **語義實體對應名稱**：語義實體對應的名稱。
   - **來源實體**：包括連絡人資料的實體。
   - **主索引鍵**：唯一識別連絡人記錄的欄位。 其中不得包含任何重複值、空白值或遺漏值。

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="使用名稱、來源實體和主索引鍵設定語義實體對應。":::

1. 選取 **下一步**。

1. 請在 **關係** 步驟中組態詳細資料，將您的聯絡人資料連接對應的帳戶資料。 此步驟會視覺化呈現實體之間的連接。  

   目前可以落實兩種類型的關聯路徑：**直接關聯** 和 **間接關聯**。 如需詳細資訊，請前往[直接和間接關聯路徑](relationships.md#relationship-paths)。

   1. 請選取 **新增關聯** 組態關聯。
   1. 請從連接您的連絡人實體到另一個實體的來源實體中選擇屬性。
   1. 請選擇要將連絡人實體連接的實體。 可從 **帳戶實體** 或 **中間實體** 區段選擇實體。 如果選取中間實體，請定義第二個連接您的目標帳戶實體的關聯。

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="選取帳戶實體或中間實體。":::

   1. 提供 **關聯名稱**。 如果您的實體間已存在關聯，則關聯名稱是唯讀的。 如果不存在任何關聯，則新關聯會以您提供的名稱建立。
   1. 請選取 **套用** 完成關聯組態。

   > [!NOTE]
   > 您可以使用中間實體組態連絡人實體與其他帳戶實體之間的更多關聯。
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="各種關聯的視覺化將連絡人實體連接到帳戶實體。":::

1. 選取 **下一步**。

1. 請在 **設定語義類型** 步驟中選擇 **語義類型**。 目前有一個名為 *ContactProfile* 的 **語義類型**。

1. 將您的連絡人識別碼對應至 *ContactProfile* 語義類型 **連絡人識別碼**。 或者，對應其他欄位，例如名字、姓氏、性別或電子郵件。

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="將您的連絡人資料屬性對應到提供的必要和非必要欄位。":::

1. 選取 **下一步**。

1. 在 **檢閱** 步驟中，檢閱語意對應組態。 若要進行變更，請為對應區段選取 **編輯**。

1. 選取 **儲存**。

1. 若要處理語義對應，請選擇 **執行**。 或選取 **關閉** 來儲存您的語義對應而不進行處理。 若要稍後執行，請選取語意對應和 **重新整理**。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>管理現有的語意對應

移至 **資料** > **語義對應 (預覽版)**，以查看您儲存的語義對應、其來源實體、語義類型、對應類型和狀態。

:::image type="content" source="media/semantic-mapping-options.png" alt-text="管理語意對應的選項。":::

選取語意對應來查看可用的動作。
- **編輯** 目前的設定。 選取 **儲存** 並 **執行** 來處理變更。
- **重新整理** 語意對應以包括最新的資料。 重新整理任何已知的語意對應將同時重新整理所有相同類型的語意對應。
- **重新命名** 語義對應。 選取 **儲存**。
- **刪除** 語義對應。 若要一次刪除多個語意對應，可選取語意對應和刪除圖示。 請選取 **刪除**，以確認刪除。

[!INCLUDE [footer-include](includes/footer-banner.md)]
