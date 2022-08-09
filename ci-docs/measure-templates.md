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
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170763"
---
# <a name="create-measures-from-templates"></a>從範本建立量值

常用[量值](measures.md)有預先定義的範本，可用範本來建立。 範本是根據 *整合活動* 實體中的對應資料建立的。 因此，請確認在範本建立量值之前，已經設定了[客戶活動](activities.md)。

量值範本只在 **個別客戶** 的環境中支援。 若要建立自訂量值或為 B-to-B 建立量值，請參閱[使用量值建立器](measure-builder.md)。

可用範本：
- 平均交易值 (ATV)
- 總交易值
- 平均每日營收
- 平均月營收
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

1. 在 **設定期間** 區段中，定義資料的時間範圍。 如果您要讓量值涵蓋整個資料集，選擇選取 **所有時間**，或者選擇您要聚焦量值的 **特定時間間隔**。

   :::image type="content" source="media/measure-set-time-period.png" alt-text="螢幕擷取畫面，圖上為範本設定度量值時，顯示期間區段。":::

1. 在下一個區段中，選取 **新增資料** 來選擇活動，並對應 *整合活動* 實體中的相應資料。

    1. 步驟 1/2：在 **活動類型** 底下，選擇您要使用的實體類型。 對於 **活動**，請選取想要對應的實體，然後選取 **下一步**。
    1. 步驟 2/2：為公式所需的元件，從 *整合活動* 實體中選擇屬性。 例如，如果是平均交易值，則表示屬性為交易值的。 在 **活動時間戳記** 中，從 *整合活動* 實體中選擇代表活動日期和時間的屬性。
    1. 選取 **儲存**。

    資料對應成功後，狀態將顯示為 **完成**，並顯示對應後的活動和屬性的名稱。

1. 可選取 **執行** 來計算量值的結果。 如果您要保留目前的設定稍後執行測量，請選取 **儲存草稿**。 **量值** 頁面隨即出現。

## <a name="next-step"></a>下一個步驟

可使用現有的量值來建立[客戶細分](segments.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
