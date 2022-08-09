---
title: 語意對應 (預覽版)
description: 語意對應總覽及使用方法。
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183621"
---
# <a name="semantic-mappings-preview"></a>語意對應 (預覽版)

語意對應讓您將非活動資料對應到預先定義的結構描述。 這些結構描述有助於 Customer Insights 更了解您的資料屬性。 語義對應和已提供的資料，將啟用 Customer Insights 中的新見解與功能。 若要將您的活動資料對應到結構描述，請審閱[活動](activities.md)文件。

**語意對應目前針對以商務帳戶為主的環境啟用**。 *ContactProfile* 是目前 Customer Insights 中唯一可用的語義對應類型。

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

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>使用 ContactProfile 語義實體對應來建立連絡人層級活動

建立 *ContactProfile* 語義實體對應之後，您便可以擷取連絡人的活動。 它可讓您在活動時間表中查看連絡人負責每個活動的說明。 大部分步驟均遵循一般活動對應設定。

   > [!NOTE]
   > 若要讓連絡人層級運作，您必須在活動資料中同時擁有每個記錄的 **AccountID** 和 **ContactID** 屬性。

1. [定義 *ContactProfile* 語義實體對應](#define-a-contactprofile-semantic-entity-mapping)，並執行語義對應。

1. 請移至 **資料** > **活動**。

1. 若要建立新的活動，請選取 **新增活動**。

1. 為活動命名，選取來源活動實體，然後選取活動實體的主索引鍵。

1. 在 **關聯** 步驟中，以中間實體方式，建立活動來源資料與客戶之間的間接關係。 如需詳細資訊，請查看[直接和間接關聯路徑](relationships.md#relationship-paths)。
   - 一個活動的關聯範例，名字是 *採購*：
      - 在 **ContactID** 屬性上的 **購買來源活動資料** > **連絡人資料**
      - 在屬性 **AccountID** 上的 **連絡人資料** > **客戶資料**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="範例關聯設定。":::

1. 設定關聯之後，請選取 **下一步**，然後完成活動對應設定。 如需建立活動的詳細步驟，請參閱[定義活動](activities.md)。

1. 執行您的活動對應。

1. 在執行連絡人層級活動對應之後，選取 **客戶**。 連絡人層級活動會顯示在您的客戶時間表上。

   :::image type="content" source="media/Contact_Activities2.png" alt-text="設定連絡人活動後的最終結果":::

### <a name="contact-level-activity-timeline-filtering"></a>連絡人層級活動時間表篩選

客戶的活動時間表是根據您的 *ContactProfile* 設定而定，這會包含他們所處理之活動的識別碼或名稱。 可根據時間表中的連絡人來篩選活動，查看您有興趣的特定連絡人。 若要查看未指派給特定連絡人的所有活動，請選取 **未對應至連絡人的活動**。

:::image type="content" source="media/Contact_Activities3.png" alt-text="連絡人層級活動可用的篩選選項。":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
