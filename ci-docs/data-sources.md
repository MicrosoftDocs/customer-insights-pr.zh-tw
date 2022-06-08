---
title: 使用資料來源內嵌資料
description: 了解如何從不同的來源匯入資料。
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 355d52eabde90e0764817cf479821264ebb2e5eb
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800456"
---
# <a name="data-sources-overview"></a>資料來源概觀



Dynamics 365 Customer Insights 從一組廣泛的來源連接至資料。 連接至資料來源通常稱為 *資料擷取* 程序。 擷取資料之後，您可以對資料進行[統整](data-unification.md)並採取動作。

## <a name="add-a-data-source"></a>新增資料來源

根據您選擇的選項，查閱詳細文章了解如何新增資料來源。

您可以新增下列資料來源：

- [透過多種 Power Query 連接器](connect-power-query.md)
- [從 Common Data Model 資料夾](connect-common-data-model.md)
- [從您自己的 Microsoft Dataverse 資料湖](connect-dataverse-managed-lake.md)
- [從 Azure Synapse Analytics 資料庫](connect-synapse.md)

## <a name="add-data-from-on-premises-data-sources"></a>從內部部署資料來源新增資料

透過 Microsoft Power Platform 資料流程，支援從內部部署資料來源的內嵌資料 。 若要在 Customer Insights 中啟用資料流程，可以在設定環境時，[提供 Microsoft Dataverse環境 URL](create-environment.md)。

在將 Dataverse 環境與 Customer Insights 關聯之後，根據預設，新建立的資料來源使用 [Power Platform 資料流程](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。 資料流程使用資料閘道來支援內部部署連線。 您可以移除在 Dataverse 環境關聯之前[使用內部部署資料閘道](/data-integration/gateway/service-gateway-app)的資料來源並重新建立。

來自現有 Power BI 或 Power Apps 環境的資料閘道將會顯示，並且可以在 Customer Insights 中重複使用。 資料來源頁面顯示的連結，您可移至 Microsoft Power Platform 查看和設定內部部署資料閘道的環境。

> [!IMPORTANT]
> 請確定您的閘道已更新為最新版本。 您可以從閘道畫面上的提示安裝更新並重新設定閘道，也[可以下載最新版本](https://powerapps.microsoft.com/downloads/)。 如果您不使用最新的閘道版本，資料流程重新整理會失敗，錯誤訊息會類似 **不支援此關鍵字：設定屬性。參數名稱：關鍵字**。

## <a name="review-ingested-data"></a>檢閱擷取的資料
如果您的環境包含 Power Platform 資料流程，**資料來源** 頁面會列出三個區段： 
- **共用**：所有 Customer Insights 系統管理員都可以管理的資料來源。 Power BI 資料流程、您自己的儲存體帳戶和附加到 Dataverse -受管理的 data lake 為共用資料來源的範例。
- **由我管理**：由您建立的 Power Platform 資料流程且只能由您管理。 其他的 Customer Insights 系統管理員只能查看這些資料流程，但不可以編輯、重新整理或將它們刪除。
- **由其他人管理**：由其他系統管理員建立的 Power Platform 。 您只能進行查看。 它會列出資料流程負責人，可以聯繫取得協助。
> [!NOTE]
> 其他使用者都可以查看和使用所有的實體。 使用者關聯只套用在資料來源，而不會套用於這些資料流程產生的實體。

如果沒有任何 Power Platform 資料流程被使用，您將看不到任何群組或區段。 **資料來源** 頁面只包含所有資料來源的清單。

您會看到每個擷取資料來源的名稱、其狀態以及該來源上次重新整理資料的時間。 您可以依據各欄位排序資料來源清單。

> [!div class="mx-imgBorder"]
> ![已新增資料來源。](media/configure-data-datasource-added.png "新增的資料來源")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

載入資料可能需要花費一些時間。 成功重新整理之後，即可從 **實體** 頁面查看擷取的資料。 如需詳細資訊，請參閱[實體](entities.md)。

## <a name="refresh-a-data-source"></a>重新整理資料來源

資料來源可自動排程或依照需要情況手動重新整理。 

請前往 **管理員** > **系統** > [**排程**](system.md#schedule-tab)，組態您內嵌所有資料來源的重新整理排程。

若要依照需要重新整理資料來源，請遵循下列步驟：

1. 移至 **資料** > **資料來源**。

2. 在您要重新整理的資料來源旁邊選取垂直省略符號 (&vellip;)，然後從下拉式清單中選取 **重新整理**。

3. 資料來源現在會針對手動重新整理觸發。 重新整理資料來源將會更新資料來源中所有指定實體的實體結構描述和資料。

4. 如果您要取消現有的重新整理，且資料來源將恢復成上次重新整理狀態，請選取 **停止重新整理**。

## <a name="delete-a-data-source"></a>刪除資料來源

1. 移至 **資料** > **資料來源**。

2. 在您要移除的資料來源旁邊選取垂直省略符號 (&vellip;)，然後從下拉式功能表中選取 **刪除**。

3. 確認刪除。


[!INCLUDE [footer-include](includes/footer-banner.md)]
