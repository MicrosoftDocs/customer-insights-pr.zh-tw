---
title: 開始使用 Dynamics 365 Customer Insights 對象見解功能
description: 快速開始的對象見解協助資源概觀。
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466567"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>開始使用 Dynamics 365 Customer Insights 對象見解功能

對象見解幫助您更加深入了解客戶。 連接各種不同交易、行為及觀測來源的資料，以建立全方位客戶視角。 利用這些見解來推動以客戶為中心的體驗與程序。 統整和瞭解客戶資料並充分運用以取得智慧見解和動作。

## <a name="step-1-create-an-environment"></a>步驟 1：建立環境

若要開始使用，您必須建立環境以在其中作業。 如果您的組織已購買授權，請參閱[開始使用付費訂閱](get-started-paid.md)。 若要開始試用對象見解，請參閱[設定試用環境](get-started-trial.md)。 

## <a name="step-2-explore-audience-insights"></a>步驟 2：探索對象見解

第一次登入對象見解時，您可以設定並探索產品。

1. 使用您的 Microsoft Azure Active Directory (AAD) 使用者帳戶[登入對象見解](https://home.ci.ai.dynamics.com)。

1. [變更環境](manage-environments.md#switch-environments)來查看示範資料，並 [探索對象見解](home.md)。

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>步驟 3：為您的資料擷取、整合和設定關聯

整合個人資料是取得見解並對資料進行動作的基礎。 從不同的來源取得資料，並執行資料整合程序以結合成整合個人資料。 指定擷取實體之間的關聯，來使用擴充功能將資訊新增至個人資料。 

1. 由多個選項中建立資料來源，插入資料。 在 [Power Query 連接器](connect-power-query.md)、[Common Data Model 資料夾](connect-common-data-model.md)或 [Microsoft Dataverse](connect-common-data-service-lake.md) 之間進行選擇。 

1. 經由[對應](map-entities.md)、[比對](match-entities.md)及[合併](merge-entities.md)等階段，來執行[資料整合程序](data-unification.md)。

1. 熟悉[系統所建立的實體](entities.md)，並建立[擷取實體之間的關聯](relationships.md)。
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>步驟 4：利用預測、活動及量值來增強整合個人資料

設定整合個人資料後，您可以增強資料，並進一步增加裡面提供的資訊。

1. 從擴充提供者的擴充庫中進行選擇，來擴充[您的客戶資料](enrichment-hub.md)。

1. 使用[現成模型](predictions-overview.md)，預測流失的可能性或預計的收入。

1. 根據擷取資料[設定活動](activities.md)，並在時間排序的時間表上視覺化與客戶的互動。 

1. [建立量值](measures.md)測量業務目標和 KPI。
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>步驟 5：用各種匯出選項建立客戶細分並啟動資料

現在您的資料已完成且包含了關於您的客戶的大量資訊，現在我們來看看有哪些方式能對該資料採取動作。 

1. [建立客戶細分](segments.md)，也就是客戶群的子集，以確保您的動作與目標客戶相關。

1. 瀏覽[匯出選項](export-destinations.md)的展開目錄，在這裡您可以使用客戶資料。 例如，您可以使用資料來管理促銷活動，並聯絡數位行銷人員。

1. 查看整合選項，例如，[直接連到參與見解](../engagement-insights/integrate-audience-insights-engagement-insights.md)或使用[客戶卡片增益集](customer-card-add-in.md)連到其他 Dynamics 365 應用程式。  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
