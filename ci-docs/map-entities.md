---
title: 選取資料整合的來源欄位
description: 整合程序的第一個步驟是選取實體、屬性、主索引鍵及語意類型，將資料對應至整合客戶個人資料。
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740985"
---
# <a name="select-source-fields-for-data-unification"></a>選取資料整合的來源欄位

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

整合的第一個步驟是到您想整合的資料集，選取其中的實體與欄位。 選取包含客戶相關詳細資料的實體，例如名稱、位址、電話號碼和電子郵件。 您可以選取一個或一個以上的值。

## <a name="select-entities-and-fields"></a>選取實體與欄位

1. 請前往 **資料** > **整合**。

   :::image type="content" source="media/m3_unify_land.png" alt-text="螢幕擷取畫面：醒目提示 [開始使用] 的第一次執行體驗的整合登陸頁面。":::

1. 請然後選取 **開始使用**。

1. 在 **來源欄位** 頁面上，選取 **選取實體和欄位**。 **選取實體與欄位** 窗格隨即顯示。

1. 至少選取一個實體。

1. 針對每個選定的實體，找出您要用來比對客戶記錄的欄位，以及要加入整合個人資料的欄位。 這些欄位稱為 *屬性*。 藉由選取實體層級的核取方塊，您可以個別選取實體的必要屬性，或包含實體的所有屬性。 您可以在所有屬性與實體中搜尋關鍵字，以選取想要對應的必要屬性。

   :::image type="content" source="media/m3_select_entities.png" alt-text="選定實體和屬性的螢幕擷取畫面。":::

   在此範例中，我們要新增 **Contacts** 與 **CustomerLoyalty** 實體。 您可以選擇這些實體來衍生有關哪些線上商務客戶是忠誠度方案成員的見解。

1. 選取 **套用** 以確認您的選取。 顯示選定實體和屬性。

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>選取屬性的主索引鍵與語意類型

   :::image type="content" source="media/m3_select_primary.png" alt-text="未選取主索引鍵的選定實體其螢幕擷取畫面。" lightbox="media/m3_select_primary.png":::

對每個實體，執行下列步驟。

1. 選擇 **主索引鍵**。 主索引鍵是實體的唯一屬性。 若要讓屬性成為有效的主索引鍵，其中不能包含重複值、遺漏值或 Null 值。 字串、整數及 GUID 資料類型屬性均支援主索引鍵。

1. 若要將 AI 模型用於智慧型語意預測，以節省時間並改善準確性，請確保已啟用 **智慧對應**。 智慧對應會在 **類型** 欄位中反白顯示 AI 提供的語意建議。 您可以從可用選項清單中選取任何語意類型，以覆寫建議的選取。

1. 對每個屬性，選擇能最恰當地描述該屬性的語意 **類型**，例如名稱、市/鎮或電子郵件地址。

   > [!NOTE]
   > 語意類型 *Person. FullName* 應該對應至一個欄位，以填充客戶卡中的客戶名稱。 否則，客戶卡片將會以未命名的方式顯示。

   1. 若要變更系統自動識別的屬性類型，請選取其他類型。 如果類型不存在，請選取屬性的 **類型** 欄位，然後輸入自訂的語意類型名稱，以建立自訂的語意類型。

   1. 若若要新增包含連結至公用個人資料圖片或標誌 URL 的屬性，請選取包含該 URL 的實體和欄位。 在 **類型** 欄位中，請輸入下列內容：
      - 對於人員：Person.ProfileImage
      - 對於組織：Organization.LogoImage

   1. 在帳戶名稱屬性的 **類型** 欄位中輸入 "Organization.Name"。

1. 檢閱自動識別語意類型的屬性。 這些屬性會列在 **檢閱對應的欄位**。 只有相同類型的屬性才可以在 **整合客戶欄位** 步驟中組合。 語意類型是用來自動建議見解。 確保您在所有選定的實體中選擇的類型是一致的。

1. 對於未自動對應至語意類型的屬性，可以選取語意類型欄位、輸入您的自訂屬性類型名稱，或將它們保留為未對應。 這些屬性列在 **未對應欄位中定義資料**。

1. 在完成每個實體的步驟之後，請選取 **儲存來源欄位**。

1. 選取 **下一步**。

> [!div class="nextstepaction"]
> [後續步驟：移除重複資料](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
