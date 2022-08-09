---
title: 如何連接到 Power Query 資料來源 (含影片)
description: 透過 Power Query 連接器內嵌資料 (含影片)。
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 7af51ed04fbd28149ea501c58e6fe71b5fa6d4b6
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207035"
---
# <a name="connect-to-a-power-query-data-source"></a>連線到 Power Query 資料來源

Power Query提供一組各式各樣的連接器來內嵌資料。 Dynamics 365 Customer Insights 支援大部分這些連接器。

以 Power Query 的連接器新增資料來源時，一般情況請依照本區段說明的步驟。 不過，視您使用的連接器而定，也需要不同的資訊。 若要進一步瞭解詳細資訊，請參閱 [Power Query 連接器參考](/power-query/connectors/) 中個別連接器的文件。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>建立新的資料來源

1. 移至 **資料** > **資料來源**。

1. 選取 **新增資料來源**。

1. 選取 **Microsoft Power Query**。

1. 輸入資料來源的 **名稱** 和選填的 **說明**，然後選取 **下一步**。

1. 選取其中一個[可用的連接器](#available-power-query-data-sources)。 在此範例中，我們選取 **文字/CSV** 連接器。

1. 在所選連接器的 **連接設定** 中輸入必要的詳細資料，然後選取 **下一步** 以查看資料的預覽。

1. 選取 **轉換資料**。

1. **Power Query - 編輯查詢** 對話方塊可讓您檢閱和微調資料。 系統在所選取資料來源中識別的實體會出現在左窗格中。

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="編輯查詢對話方塊":::

1. 您也可以轉換資料。 選取要編輯或變換的實體。 使用 Power Query 視窗中的選項來套用轉換。 每個轉換都會列在 **已套用的步驟**。 Power Query 提供許多[預先建立的轉換](/power-query/power-query-what-is-power-query#transformations)選項。

   我們建議您使用下列轉換：

   - 如果您要從 CSV 檔案擷取資料，則第一列通常會包含標題。 移至 **轉換** 並選取 **以第一列為標頭**。
   - 確定資料類型已正確設定。 例如，如果是日期欄位，請選取日期類型。

1. 若要在 **編輯查詢** 對話方塊中將其他實體新增至資料來源，請移至 **首頁**，然後選取 **取得資料**。 重複步驟 5-10，直到您對此資料來源新增所有實體為止。 如果您有包含多個資料集的資料庫，則每個資料集都是其自己的實體。

1. 選取 **儲存**。 **資料來源** 頁面會打開，顯示處於 **重新整理** 狀態中的新資料來源。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

載入資料可能需要花費一些時間。 成功重新整理之後，即可從 [**實體**](entities.md)頁面查看擷取的資料。

> [!CAUTION]
> 根據 Power Query 的資料來源建立 [Dataverse 中的資料流程](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。 請勿變更 Power Platform 系統管理中心中用於 Customer Insights 的資料流程名稱。 重命名資料流程會造成 Customer Insights 資料來源與 Dataverse 資料流程之間的參考發生問題。

### <a name="available-power-query-data-sources"></a>可用的 Power Query 資料來源

有關可用來將資料匯入至 Customer Insights 的連接器清單，請參閱 [Power Query 連接器參考](/power-query/connectors/)。

在 **Customer Insights (資料流程)** 欄有核取記號的連接器，可用於建立依據 Power Query 的新資料來源。 檢閱特定連接器的文件，深入瞭解先決條件、[查詢限制](/power-query/power-query-online-limits)和其他詳細資料。

## <a name="add-data-from-on-premises-data-sources"></a>從內部部署資料來源新增資料

透過 Microsoft Power Platform 資料流程 (PPDF)，支援從內部部署資料來源的內嵌資料 。 若要在 Customer Insights 中啟用資料流程，可以在設定環境時，[提供 Microsoft Dataverse環境 URL](create-environment.md)。

在將 Dataverse 環境與 Customer Insights 關聯之後，根據預設，新建立的資料來源使用 [Power Platform 資料流程](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。 資料流程使用資料閘道來支援內部部署連線。 您可以移除在 Dataverse 環境關聯之前[使用內部部署資料閘道](/data-integration/gateway/service-gateway-app)的資料來源並重新建立。

來自現有 Power BI 或 Power Apps 環境的資料閘道將會顯示，並且可以在 Customer Insights 中重複使用。 資料來源頁面顯示的連結，您可移至 Microsoft Power Platform 查看和設定內部部署資料閘道的環境。

> [!IMPORTANT]
> 請確定您的閘道已更新為最新版本。 您可以從閘道畫面上的提示安裝更新並重新設定閘道，也[可以下載最新版本](https://powerapps.microsoft.com/downloads/)。 如果您不使用最新的閘道版本，資料流程重新整理會失敗，錯誤訊息會類似 **不支援此關鍵字：設定屬性。參數名稱：關鍵字**。
>
> Customer Insights 中的內部部署資料閘道錯誤通常是由設定問題所致。 如需疑難排解資料閘道的詳細資訊，請參閱 [疑難排解內部部署資料閘道](/data-integration/gateway/service-gateway-tshoot)。

## <a name="edit-power-query-data-sources"></a>編輯 Power Query 資料來源

> [!NOTE]
> 您可能無法變更目前用於應用程式程序之一 (例如區段化或資料整合) 的資料來源。
>
> 在 **設定** 頁面，您可以追蹤每個使用中程序的進度。 當程序完成時，您可以返回 **資料來源** 頁面並進行變更。

1. 移至 **資料** > **資料來源**。

1. 在您想要更新的資料來源旁邊，選取 **編輯**。

1. 在 **Power Query 編輯查詢** 對話方塊中，依[建立新的資料來源](#create-a-new-data-source)的區段所述，套用變更和轉換。

1. 選取 **儲存** 以套用變更，並返回至 **資料來源** 頁面。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
