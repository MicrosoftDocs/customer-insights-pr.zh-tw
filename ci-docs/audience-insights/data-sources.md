---
title: 使用資料來源內嵌資料
description: 了解如何從不同的來源匯入資料。
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 6846c73cb156aaa049e2656c8e327bcba1f73abc
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900326"
---
# <a name="data-sources-overview"></a>資料來源概觀

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Customer Insights 中的對象見解功能從一組廣泛的來源集連接到資料。 連接至資料來源通常稱為 *資料擷取* 程序。 擷取資料之後，您可以對資料進行[統整](data-unification.md)並採取動作。

## <a name="add-a-data-source"></a>新增資料來源

根據您選擇的選項，查閱詳細文章了解如何新增資料來源。

您可以新增下列資料來源：

- [Power Query 連接器](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse 湖](connect-dataverse-managed-lake.md)

> [!NOTE]
> 如果您使用的是試用版，匯入方法區段會包含 **Customer Insights 資料庫** 選項。 選擇此選項則可選取給各種產業使用的範例資料集。 如需詳細資訊，請參閱 [Dynamics 365 Customer Insights 試用](../trial-signup.md)。

## <a name="add-data-from-on-premises-data-sources"></a>從內部部署資料來源新增資料

Microsoft Power Platform 資料流程支援在對象見解中從內部部署的資料來源內嵌資料。 若要在 Customer Insights 中啟用資料流程，可以在設定環境時，[提供 Microsoft Dataverse環境 URL](create-environment.md)。

在將 Dataverse 環境與 Customer Insights 關聯之後，根據預設，新建立的資料來源使用 [Power Platform 資料流程](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。 資料流程使用資料閘道來支援內部部署連線。 您可以移除在 Dataverse 環境關聯之前[使用內部部署資料閘道](/data-integration/gateway/service-gateway-app)的資料來源並重新建立。

來自現有 Power BI 或 Power Apps 環境的資料閘道將會顯示，並且可以在 Customer Insights 中重複使用。 資料來源頁面顯示的連結，您可移至 Microsoft Power Platform 查看和設定內部部署資料閘道的環境。

## <a name="review-ingested-data"></a>檢閱擷取的資料

您會看到每個擷取資料來源的名稱、其狀態以及該來源上次重新整理資料的時間。 您可以依據各欄位排序資料來源清單。

> [!div class="mx-imgBorder"]
> ![已新增資料來源。](media/configure-data-datasource-added.png "新增的資料來源")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

載入資料可能需要花費一些時間。 成功重新整理之後，即可從 **實體** 頁面查看擷取的資料。 如需詳細資訊，請參閱[實體](entities.md)。

## <a name="refresh-a-data-source"></a>重新整理資料來源

資料來源可自動排程或依照需要情況手動重新整理。 

請前往 **管理員** > **系統** > [**排程**](system.md#schedule-tab)，組態您內嵌所有資料來源的重新整理排程。

若要依照需要重新整理資料來源，請遵循下列步驟：

1. 在對象見解中，前往 **資料** > **資料來源**。

2. 在您要重新整理的資料來源旁邊選取垂直省略號，然後從下拉式清單中選取 **重新整理**。

3. 資料來源現在會針對手動重新整理觸發。 重新整理資料來源將會更新資料來源中所有指定實體的實體結構描述和資料。

4. 如果您要取消現有的重新整理，且資料來源將恢復成上次重新整理狀態，請選取 **停止重新整理**。

## <a name="delete-a-data-source"></a>刪除資料來源

1. 在對象見解中，前往 **資料** > **資料來源**。

2. 在您要移除的資料來源旁邊選取垂直省略號，然後從下拉式功能表中選取 **刪除**。

3. 確認刪除。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
