---
title: 從範本建立量值
description: 以一般使用案例的範本定義量值。
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: f6bcdfc45a49c36f22d6ebc6e919f43b27f899d8
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051673"
---
# <a name="create-measures-from-templates"></a>從範本建立量值

常用[量值](measures.md)有預先定義的範本，您可以用範本來建立。 範本的詳細說明及引導式體驗可協助您輕鬆建立量值。 範本是根據 *整合活動* 實體中的對應資料建立的。 因此，請確認在範本建立量值之前，已經設定了[客戶活動](activities.md)。

若要建立自訂的量值，請參閱[使用量值建立器從頭開始建立量值](measure-builder.md)。

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

可用範本： 
- 平均交易值 (ATV)
- 總交易值
- 平均每日營收
- 平均年營收
- 交易計數
- 已獲得忠誠點數
- 已兌換忠誠點數
- 忠誠點數餘額
- 使用中客戶留存期
- 忠誠成員資格期間
- 上次購買至今的時間

## <a name="build-a-new-measure-using-a-template"></a>使用範本建立新的量值

1. 返回 **量值**。

1. 選取 **新增** 並選取 **選擇範本**。

   :::image type="content" source="media/measure-use-template.png" alt-text="下拉式功能表的螢幕擷取畫面，並醒目提示範本上的新量值。":::

1. 找到符合您的需求的範本，然後選取 **選擇範本**。

1. 查看必要的資料，若有所有資料都在妥當位置，接著選取 **開始使用**。

1. 選取量值名稱旁邊的 **編輯詳細資料**。 提供量值的名稱。 或者，將[標籤](work-with-tags-columns.md#manage-tags)新增至量值。

   :::image type="content" source="media/measures_edit_details.png" alt-text="編輯詳細資料對話方塊。":::

1. 選取 **完成**。

1. 在 **設定期間** 區段中，定義要使用的資料時間範圍。 如果您要讓量值涵蓋整個資料集，選擇選取 **所有時間**，或者選擇您要聚焦量值的 **特定時間間隔**。

   :::image type="content" source="media/measure-set-time-period.png" alt-text="螢幕擷取畫面，圖上為範本設定度量值時，顯示期間區段。":::

1. 在下一個區段中，選取 **新增資料** 來選擇活動，並對應 *整合活動* 實體中的相應資料。

    1. 步驟 1/2：在 **活動類型** 底下，選擇您要使用的實體類型。 對於 **活動**，請選取想要對應的實體。
    1. 步驟 2/2：為公式所需的元件，從 *整合活動* 實體中選擇屬性。 例如，如果是平均交易值，則表示屬性為交易值的。 在 **活動時間戳記** 中，從整合活動實體中選擇代表活動日期和時間的屬性。
   
1. 資料對應成功後，您就可以看到狀態顯示為 **完成**，以及對應後的活動和屬性的名稱。

1. 您現在可以選取 **執行** 來計算量值的結果。 若要稍後調整，請選取 **儲存草稿**。

# <a name="business-accounts-b-to-b"></a>[商務帳戶 (B2B)](#tab/b2b)

唯有在個別客戶為主要目標對象的環境建立的量值才能使用此項功能。

---
