---
title: 使用快速客戶細分建立簡單客戶細分
description: 建立簡單客戶細分，以依據各種屬性來群組。
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171127"
---
# <a name="create-simple-segments-with-quick-segments"></a>使用快速客戶細分建立簡單客戶細分

使用快速客戶細分，您可以快速組建具有單一運算子的簡單客戶細分，更快取得見解。 快速區段只在 **個別客戶** 的環境中支援。

## <a name="create-a-new-segment-with-quick-segments"></a>使用快速客戶細分建立新的客戶細分

1. 前往 **區段**。

1. 選取 **新增** > **從空白建立**。
   - 選取 **個人資料** 選項，組建基於 *統整客戶實體* 的客戶細分。
   - 請選取 **量值** 選項在您先前建立的量值四周組建區段。
   - 選取 **智慧** 選項，以使用 **預測** 或 **自訂模型** 功能產生的其中一個輸出實體建立區段。

1. 在 **新增快速區段** 對話方塊中，從 **欄位** 下拉式功能表中選取屬性。 根據您的選擇，系統會提供不同的值。
   - 對於類別欄位，會顯示 10 個最高的客戶計數。 選擇 **值** 並選取 **檢閱**。
   - 在數值屬性中，系統會顯示落在每個客戶百分位下的屬性值。 選擇 **運算子** 和 **值**，然後選取 **檢閱**。

1. 系統將提供 **估計的客戶細分大小**。 選擇是否要產生您定義的客戶細分，或回頭選擇不同的區段大小。

   :::image type="content" source="media/quick-segment-name.png" alt-text="快速客戶細分的名稱與估計。":::

1. 提供客戶細分的 **輸出實體名稱** 及 **名稱**。 或者，新增[標籤](work-with-tags-columns.md#manage-tags)。

1. 選取 **儲存** 以建立您的區段。 **客戶細分** 頁面隨即出現。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>後續步驟

[匯出一個客戶細分](export-destinations.md)，並探索[客戶卡整合](customer-card-add-in.md)，以便在其他應用中使用客戶細分。

[!INCLUDE [footer-include](includes/footer-banner.md)]
