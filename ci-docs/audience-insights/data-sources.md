---
title: 使用資料來源內嵌資料
description: 了解如何從不同的來源匯入資料。
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085520"
---
# <a name="data-sources-overview"></a>資料來源概觀

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Customer Insights 中的對象見解功能從一組廣泛的來源集連接到資料。 連接至資料來源通常稱為 *資料擷取* 程序。 擷取資料之後，您可以對資料進行[統整](data-unification.md)並採取動作。

## <a name="add-a-data-source"></a>新增資料來源

根據您所選擇的選項，參考有關如何新增資料來源的詳細文章。

有三種主要方式可以新增資料來源：

- [透過數十個 Power Query 連接器](connect-power-query.md)
- [從 Common Data Model 資料夾](connect-common-data-model.md)
- [從您自己的 Common Data Service 資料湖](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>從內部部署資料來源新增資料

Power Platform 資料流程支援在對象見解中從內部部署的資料來源內嵌資料。 設定環境時，[在 Microsoft Dataverse 提供環境 URL](manage-environments.md#create-an-environment-in-an-existing-organization)，便可以在 Customer Insights 中啟用資料流程。

將 Dataverse 環境與 Customer Insights 關聯之後，所建立的資料來源預設使用 [Power Platform 資料流程](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。 資料流程使用資料閘道來支援內部部署連線。 在關聯 Dataverse 環境前就已存在的資料來源，請移除並重新建立，才能[使用內部部署資料閘道](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md)。

來自現有 Power BI 或 Power Apps 環境的資料閘道將會顯示，並且可以在 Customer Insights 中重複使用。 資料來源頁面顯示的連結可前往 Power Platform 環境，並在其中查看和設定內部部署資料閘道。

## <a name="review-ingested-data"></a>檢閱擷取的資料

您會看到每個擷取資料來源的名稱、其狀態以及該來源上次重新整理資料的時間。 您可以依據各欄位排序資料來源清單。

> [!div class="mx-imgBorder"]
> ![新增的資料來源](media/configure-data-datasource-added.png "新增的資料來源")

|Status  |描述  |
|---------|---------|
|成功   |如果 **重新整理的** 欄位提到時間，代表已成功內嵌資料來源。
|未開始   |資料來源尚未內嵌任何資料或仍在草稿模式中。         |
|正在重新整理    |資料擷取進行中。 您可以選取 **動作** 欄中的 **停止重新整理** 來取消此作業。 停止重新整理資料來源會將它還原至上次重新整理的狀態。       |
|失敗     |資料擷取執行時遇到錯誤。         |

在任何資料來源中選取 **狀態** 欄中的值，以查看更多詳細資料。 在 **進度詳細資料** 窗格中，展開 **資料來源**。 請選取 **查看詳細資料** 來查看更新狀態的更多詳細資料，包括錯誤詳細資料與下游程序更新。

載入資料可能需要一些時間。 成功重新整理之後，即可從 **實體** 頁面查看擷取的資料。 如需詳細資訊，請參閱[實體](entities.md)。

## <a name="refresh-a-data-source"></a>重新整理資料來源

資料來源可自動排程或依照需要情況手動重新整理。 

請前往 **管理員** > **系統** > [**排程**](system.md#schedule-tab)，組態您內嵌所有資料來源的重新整理排程。

若要依照需要重新整理資料來源，請遵循下列步驟：

1. 在對象見解中，前往 **資料** > **資料來源**

2. 請選取您要重新整理資料來源旁邊的垂直刪節號並從下拉式選單選取 **重新整理**。

3. 資料來源現在會針對手動重新整理觸發。 重新整理資料來源將會更新資料來源中所有指定實體的實體結構描述和資料。

4. 如果您要取消現有的重新整理，且資料來源將恢復成上次重新整理狀態，請選取 **停止重新整理**。

## <a name="delete-a-data-source"></a>刪除資料來源

1. 在對象見解中，前往 **資料** > **資料來源**。

2. 選取您想要移除的資料來源旁邊的垂直省略符號，然後從下拉式功能表中選取 **刪除**。

3. 確認刪除。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
