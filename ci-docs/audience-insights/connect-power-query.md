---
title: 透過 Power Query 連接器內嵌資料 (含影片)
description: 基於 Power Query 資料來源的連接器。
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4c12933a0684094702843be309525dd6d5d9b6f4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355511"
---
# <a name="connect-to-a-power-query-data-source"></a>連線到 Power Query 資料來源

Power Query提供一組各式各樣的連接器來內嵌資料。 Dynamics 365 Customer Insights 支援大部分這些連接器。 

以 Power Query 的連接器新增資料來源時，一般情況請依照本區段說明的步驟。 不過，視您使用的連接器而定，也需要不同的資訊。 若要進一步瞭解詳細資訊，請參閱 [Power Query 連接器參考](/power-query/connectors/) 中個別連接器的文件。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>建立新的資料來源

1. 在對象見解中，前往 **資料** > **資料來源**。

1. 選取 **新增資料來源**。

1. 選取 **Microsoft Power Query**。

1. 提供資料來源的 **名稱**，然後選取 **下一步** 以建立資料來源。

1. 選取其中一個[可用的連接器](#available-power-query-data-sources)。 在此範例中，我們選取 **文字/CSV** 連接器。

1. 在所選連接器的 **連接設定** 中輸入必要的詳細資料，然後選取 **下一步** 以查看資料的預覽。

1. 選取 **轉換資料**。 在此步驟中，您會將實體新增至資料來源中。 實體是資料集。 如果您有包含多個資料集的資料庫，則每個資料集都是其自己的實體。

1. **Power Query - 編輯查詢** 對話方塊可讓您檢閱和微調資料。 系統在所選取資料來源中識別的實體會出現在左窗格中。

   > [!div class="mx-imgBorder"]
   > ![編輯查詢對話方塊。](media/data-manager-configure-edit-queries.png "編輯查詢對話方塊")

1. 您也可以轉換資料。 選取要編輯或變換的實體。 使用 Power Query 視窗中的選項來套用轉換。 每個轉換都會在 **套用的步驟** 底下列出。 Power Query 提供許多預先建立的轉換選項。 如需詳細資訊，請參閱 [Power Query 轉換](/power-query/power-query-what-is-power-query#transformations)。

   我們建議您使用下列轉換：

   - 如果您要從 CSV 檔案擷取資料，則第一列通常會包含標題。 移至 **轉換** 並選取 **以第一列為標頭**。
   - 確定資料類型已正確設定。 例如，如果是日期欄位，請選取日期類型。

1. 若要在 **編輯查詢** 對話方塊中將其他實體新增至資料來源，請移至 **首頁**，然後選取 **取得資料**。

1. 選取 Power Query 視窗最下方的 **儲存**，儲存轉換。 儲存後，您會在 **資料** > **資料來源** 上找到您的資料來源。

1. 在 **資料來源** 頁面上，您會發現新的資料來源處於 **重新整理** 狀態。

## <a name="available-power-query-data-sources"></a>可用的 Power Query 資料來源

有關可用來將資料匯入至 Customer Insights 的連接器清單，請參閱 [Power Query 連接器參考](/power-query/connectors/)。 

在 **Customer Insights (資料流程)** 欄有核取記號的連接器，可用於建立依據 Power Query 的新資料來源。 檢閱特定連接器的文件，進一步了解其先決條件、限制及其他詳細資料。

## <a name="edit-power-query-data-sources"></a>編輯 Power Query 資料來源

> [!NOTE]
> 您可能無法變更目前用於應用程式程序之一（例如 *區段化*、*比對* 或 *合併*）的資料來源。 
>
> 在 **設定** 頁面，您可以追蹤每個使用中程序的進度。 當程序完成時，您可以返回 **資料來源** 頁面並進行變更。

1. 在對象見解中，前往 **資料** > **資料來源**。

2. 在您要變更的資料來源旁邊選取垂直省略號，然後從下拉式功能表中選取 **編輯**。

   > [!div class="mx-imgBorder"]
   > ![編輯選項。](media/edit-option-data-sources.png "編輯選項")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. 在 **Power Query 編輯查詢** 對話方塊中，依[建立新的資料來源](#create-a-new-data-source)的區段所述，套用變更和轉換。

4. 完成編輯後，請在 Power Query 選取 **儲存** 來儲存變更。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
