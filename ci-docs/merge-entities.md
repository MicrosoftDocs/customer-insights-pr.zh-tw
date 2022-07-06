---
title: 為資料整合進行客戶欄位的整合
description: 合併實體以建立統整的客戶設定檔。
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: ceb2724ad490c1ba44fd9b7ff2be04721892fca4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080943"
---
# <a name="unify-customer-fields-for-data-unification"></a>為資料整合進行客戶欄位的整合

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

在整合程序的這個步驟中，請選取屬性並從可合併到整合個人資料實體中的屬性中排除。 例如，如果有三個實體中存在電子郵件資料，您可能會想要將所有三個不同的電子郵件欄位放在一起，或合併至整合個人資料的單一電子郵件欄位中。 系統會自動合併某些屬性。 您可以建立穩定且獨特的客戶識別碼，並將相關個人資料分組至叢集。

:::image type="content" source="media/m3_unify.png" alt-text="資料統整處理中的合併頁面，顯示定義整合客戶個人資料且具有合併欄位的表格。":::

## <a name="review-and-update-the-customer-fields"></a>檢閱和更新客戶欄位

1. 在表格的 **客戶欄位** 索引標籤下，檢閱將整合的欄位清單。 進行任何適當的變更。

   1. 對於任何整合欄位，您可以：
      - [編輯](#edit-a-merged-field)
      - [重新命名](#rename-fields)
      - [個別](#separate-merged-fields)
      - [排除](#exclude-fields)
      - [上移或下移](#change-the-order-of-fields)

   1. 對於任何單獨欄位，您可以：
      - [結合欄位](#combine-fields-manually)
      - [合併一組欄位群組](#combine-a-group-of-fields)
      - [重新命名](#rename-fields)
      - [排除](#exclude-fields)
      - [上移或下移](#change-the-order-of-fields)

1. 或者，[生成客戶識別碼設定](#configure-customer-id-generation)。

1. 或者，[將個人資料以家戶或叢集單位分組](#group-profiles-into-households-or-clusters)。

> [!div class="nextstepaction"]
> [後續步驟：檢閱整合](review-unification.md)

### <a name="edit-a-merged-field"></a>編輯合併的欄位

1. 選取合併的欄位，然後選擇 **編輯**。 合併欄位窗格隨即顯示。

1. 指定如何以三個選項中之一將欄位結合或合併：
    - **重要**：根據指定給參與欄位的重要性等級，找出勝出值。 這是預設合併選項。 選取 **上移/下移** 來設定重要性等級。

      :::image type="content" source="media/importance-merge-option.png" alt-text="合併欄位對話方塊中的重要性選項。":::

    - **最新**：根據新近度來找出勝出值。 要定義新近度，在合併欄位範圍中，每個參與的實體都需要一個日期或數字欄位。

      :::image type="content" source="media/recency-merge-option.png" alt-text="合併欄位對話方塊中的新近度選項。":::

    - **最低新近度**：根據最低的新近度來找出勝出值。 要定義新近度，在合併欄位範圍中，每個參與的實體都需要一個日期或數字欄位。

1. 您可以新增更多欄位參加合併程式。

1. 您可以重新命名合併欄位。

1. 選取 **完成** 套用變更。

### <a name="rename-fields"></a>重新命名欄位

變更合併或不同欄位的顯示名稱。 您無法變更輸出實體的名稱。

1. 選取欄位並選擇 **重新命名**。

1. 輸入新的顯示名稱。

1. 選取 **完成**。

### <a name="separate-merged-fields"></a>分割合併欄位

若要分割合併欄位，請在表格中尋找屬性。 分割欄位會以個別資料點顯示在整合的客戶個人資料上。

1. 選取合併的欄位，然後選擇 **個別欄位**。

1. 確認分割。

### <a name="exclude-fields"></a>排除欄位

從整合客戶個人資料中排除合併或個別的欄位。 如果欄位是用於其他程序中 (例如，客戶細分)，則請先從這些程序中移除該欄位，然後再從客戶個人資料中排除它。

1. 選取合併的欄位，然後選擇 **排除**。

1. 確認排除。

若要查看排除欄位的全部清單，請選取 **排除的欄位**。 如有需要，您可以讀取排除的欄位。

### <a name="change-the-order-of-fields"></a>變更欄位順序

某些實體比其他實體包含更多詳細資料。 如果實體包含欄位的最新資料，您可以在合併值時，設定它優先於其他實體。

1. 請選取該欄位。
  
1. 選擇 **上移/下移** 來設定順序，或將它們拖放至想要的位置。

### <a name="combine-fields-manually"></a>手動合併欄位

合併個別欄位來建立合併的屬性。

1. 選取 **合併** > **欄位**。 合併欄位窗格隨即顯示。

1. 在 **以...合併欄位** 中，以下拉式清單指定合併入選方原則。

1. 選取 **新增欄位** 以結合更多欄位。

1. 提供 **名稱** 和 **輸出欄位名稱**。

1. 選取 **完成** 套用變更。

### <a name="combine-a-group-of-fields"></a>合併一組欄位群組

將一組欄位當作單一單位處理。 例如，如果記錄包含欄位地址 1、地址 2、市/鎮、州和郵遞區號，我們不想要合併不同的記錄地址 2 中，並認為這樣可讓資料變得更完整。

1. 選取 **合併** > **欄位群組**。

1. 在 **以...排名群組** 中，以下拉式清單指定合併入選方原則。

1. 如果您要新增更多欄位或群組到欄位，請選取 **新增** 並選擇。

1. 提供每個合併欄位的 **名稱** 和 **輸出名稱**。

1. 提供群組欄位的 **名稱**。

1. 選取 **完成** 套用變更。

## <a name="configure-customer-id-generation"></a>設定客戶識別碼產生

定義如何生成客戶識別碼值，獨特的客戶個人資料識別碼。 資料整合處理程序中的整合欄位步驟會生成唯一的客戶個人資料識別碼。 識別碼是 *Customer* 實體中的 *CustomerId* ，是由資料整合程序產生的。

*CustomerId* 是根據 入選方 主索引鍵 的 第一個 非 null 值 的雜湊決定。 這些索引鍵來 自資料整合使用到的實體，並受比對順序的影響。 因此在主要實體的比對順序中的主索引鍵變更時，生成的客戶識別碼也會變更。 因此主索引鍵值 可能不見得永遠代表相同客戶。

組態穩定的客戶識別碼能讓您避開那樣的行為。

1. 請選取 **金鑰** 索引標籤。

1. 將游標停留在 **CustomerId** 列上，然後選取 **設定**。
   :::image type="content" source="media/customize-stable-id.png" alt-text="識別碼生成的自訂控制項。":::

1. 最多選取五個欄位來構成唯一的客戶識別碼，而且更穩定。 不符合您設定的記錄，會使用系統設定的識別碼。  

1. 選取 **完成**。

## <a name="group-profiles-into-households-or-clusters"></a>將設定檔以家戶或叢集單位分組

您可以定義規則，將相關個人資料分組至叢集。 目前有兩種可用的叢集類型–家戶叢集和自訂叢集。 如果 *客戶* 實體包含語義欄位 *Person. LastName* 和 *Location.Address*，系統會自動選擇已有預定義規則的家戶。 您也可以使用自己的規則和條件建立叢集，類似[相符規則](match-entities.md#define-rules-for-match-pairs)。

1. 選取 **進階** > **建立叢集**。

   :::image type="content" source="media/create-cluster.png" alt-text="控制項建立新叢集。":::

1. 請在 **家戶** 或 **自訂** 叢集之間選擇。 如果 *客戶* 實體存在語義欄位 *Person.LastName* 和 *Location.Address*，會自動選取家戶。

1. 提供叢集名稱並選取 **完成**。

1. 請選取 **叢集** 索引標籤尋找您建立的叢集。

1. 指明規則和條件以定義您的叢集。

1. 選取 **完成**。 在整合程序完成時，會建立叢集。 執行合併程式後會將叢集識別碼新增為 *Customer* 實體的新欄位。

> [!div class="nextstepaction"]
> [後續步驟：檢閱整合](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
