---
title: 語意對應 (預覽版)
description: 語意對應總覽及使用方法。
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622925"
---
# <a name="semantic-mappings"></a>語意對應

語意對應讓您將非活動資料對應到預先定義的結構描述。 這些結構描述有助於對象見解更瞭解您的資料屬性。 語意對應和提供的資料啟用對象見解中的新見解與功能。 若要將您的活動資料對應到結構描述，請審閱[活動](activities.md)文件。

**語意對應目前針對以商務帳戶為主的環境啟用**。 *ContactProfile* 是目前對象見解中唯一可用的語意對應類型。

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>定義 ContactProfile 語義實體對應

1. 請在 對象見解中，前往 **資料** > **語意對應 (預覽版)**。

1. 請選取 **新增語意對應** 開始引導式體驗。

1. 請在 **實體資料** 步驟中設定下列欄位值：

   - **語義實體對應名稱**：提供語義實體對應的名稱。
   - **來源實體**：請選取包括連絡人資料的實體。
   - **主索引鍵**：選取唯一識別連絡人記錄的欄位。 其中不得包含任何重複值、空白值或遺漏值。

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="使用名稱、來源實體和主索引鍵設定語義實體對應。":::

1. 選取 **下一步** 以繼續。

1. 請在 **關係** 步驟中組態詳細資料，將您的聯絡人資料連接對應的帳戶資料。 此步驟會視覺化呈現實體之間的連接。  

   目前可以落實兩種類型的關聯路徑：**直接關聯** 和 **間接關聯**。 如需詳細資訊，請前往[直接和間接關聯路徑](relationships.md#relationship-paths)。

   1. 請選取 **新增關聯** 組態關聯。
   1. 請從連接您的連絡人實體到另一個實體的來源實體中選擇屬性。
   1. 請選擇要將連絡人實體連接的實體。 您可以從 **帳戶實體** 或 **中間實體** 分段選擇實體。 如果您選取中間實體，您需要定義第二個連接您的目標帳戶實體的關聯。

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="選取帳戶實體或中間實體。":::

   1. 提供 **關聯名稱**。 如果您的實體間已存在關聯，則關聯名稱是唯讀的。 如果不存在任何關聯，則新關聯會以您提供的名稱建立。
   1. 請選取 **套用** 完成關聯組態。

   > [!NOTE]
   > 您可以使用中間實體組態連絡人實體與其他帳戶實體之間的更多關聯。
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="各種關聯的視覺化將連絡人實體連接到帳戶實體。":::

1. 當您完成關聯組態時，請選取 **下一步**。

1. 請在 **設定語義類型** 步驟中選擇 **語義類型**。 目前有一個名為 *ContactProfile* 的 **語義類型**。

1. 請將您的資料對應到顯示欄位的 **語意類型**，*ContactProfile*。
   - 必要欄位：連絡人識別碼
   - 選擇性欄位：名字、姓氏、出生日期、性別、主要電子郵件以及主要電話

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="將您的連絡人資料屬性對應到提供的必要和非必要欄位。":::

1. 選取 **下一步** 以繼續。

1. 請在 **審查** 步驟中查看語意對應組態。 請選取 **編輯** 變更對應分段。

1. 請選取 **儲存** 以儲存您的新 **語意對應**。

1. 儲存後，您可以選取 **執行** 處理語意對應或選取 **關閉** 儲存您的語意對應，不進行處理。

1. 若要稍候執行語意對應，請選取語意對應和 **重新整理**。

> [!TIP]
> 任務/流程目前有 [六種類型的狀態](system.md#status-types)。 此外，大部分程序都要[依賴其他下游程序](system.md#refresh-policies)。 您可以選取程序的狀態，以查看整個工作的進度詳細資料。 針對其中一項作業的工作選取 **查看詳細資料** 之後，您會找到其他資訊：處理時間、上次處理日期以及所有與工作相關的錯誤和警告。

## <a name="manage-existing-semantic-mappings"></a>管理現有的語意對應

請在 **資料** > **語意對應 (預覽版)** 上檢視所有已儲存的語意對應，並加以管理。 每個語意對應以分開的行項代表。 您將會找到來源實體、語義類型、對應類型及其狀態的詳細資料。

:::image type="content" source="media/semantic-mapping-options.png" alt-text="管理語意對應的選項。":::

- **編輯**：在審查步驟中開啟語意對應組態設定。 您可以變更目前的組態。 選取 **儲存** 並 **執行** 來處理變更。

- **重新整理**：從隸屬組態一部份的實體使用最新版本的資料重新整理選取的語意對應。 重新整理任何已知的語意對應將同時重新整理所有相同類型的語意對應。

- **重新命名**：打開對話方塊，您可以針對選取的語意對應輸入不同名稱。 選取 **儲存** 套用變更。

- **刪除**：打開對話方塊確認是否刪除選取的語意對應。 您也可以藉由選取語意對應和刪除圖示一次刪除多個語意對應。 請選取 **刪除**，以確認刪除。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
