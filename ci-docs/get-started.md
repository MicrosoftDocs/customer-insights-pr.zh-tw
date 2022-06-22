---
title: 開始使用 Dynamics 365 Customer Insights
description: 快速開始使用 Customer Insights 的説明資源摘要。
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011969"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>開始使用 Dynamics 365 Customer Insights

Customer Insights 可協助您深入瞭解您的客戶。 連接各種不同交易、行為及觀測來源的資料，以建立全方位客戶視角。 利用這些見解來推動以客戶為中心的體驗與程序。 統整和瞭解客戶資料並充分運用以取得智慧見解和動作。

## <a name="step-1-create-an-environment"></a>步驟 1：建立環境

首先，建立一個工作環境。 如果您的組織已經購買授權，請參閱[建立環境](create-environment.md)。 若要開始試用以進行 Customer Insights，請參閱[設定試用環境](trial-signup.md)。

## <a name="step-2-explore-customer-insights"></a>步驟 2：探索 Customer Insights

第一次登入 Customer Insights 時，請進行設定並探索產品。

1. 使用您的 Microsoft Azure Active Directory (AAD) 使用者帳戶[登入 Customer Insights](https://home.ci.ai.dynamics.com)。

1. 變更環境以查看示範資料，並[探索 Customer Insights](home.md)。

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>步驟 3：為您的資料擷取、整合和設定關聯

整合個人資料是取得見解並對資料進行動作的基礎。 從不同的來源取得資料，並執行資料整合程序以結合成整合個人資料。 指定已擷取實體之間的關聯，並使用擴充功能將資訊新增至設定檔。

1. 由多個選項中建立資料來源，插入資料。  [Azure Data Lake Storage (包括 Common Data Model)](connect-common-data-model.md)、 [Azure Synapse Analytics](connect-synapse.md)、[Microsoft Dataverse](connect-dataverse-managed-lake.md)，或 [Power Query 連接器](connect-power-query.md)之間做選擇。

1. 透過確認[來源欄位](map-entities.md)、移除[重複資料](remove-duplicates.md)、 [比對條件](match-entities.md)以及 [整合欄位](merge-entities.md)，執行[資料整合程序](data-unification.md)。

1. 熟悉[系統所建立的實體](entities.md)，並建立[擷取實體之間的關聯](relationships.md)。

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>步驟 4：利用預測、活動及量值來增強整合個人資料

設定統一設定檔，可增強您的資料，並進一步增加他們所提供的資訊。

1. 從擴充提供者的擴充庫中進行選擇，來擴充[您的客戶資料](enrichment-hub.md)。

1. 使用[現成模型](predictions-overview.md)，預測流失的可能性或預計的收入。

1. 根據擷取資料[設定活動](activities.md)，並在時間排序的時間表上視覺化與客戶的互動。

1. [建立量值](measures.md)測量業務目標和 KPI。

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>步驟 5：用各種匯出選項建立客戶細分並啟動資料

現在您的資料已完成，而且包含關於您的客戶的大量資訊，請尋找對該資料採取動作的方式。

1. [建立客戶細分](segments.md)，也就是客戶群的子集，以確保您的動作與目標客戶相關。

1. 瀏覽[匯出選項](export-destinations.md)的展開目錄，在這裡您可以使用客戶資料。 例如，您可以使用資料來管理促銷活動，並聯絡數位行銷人員。

1. 檢閱整合選項，例如，[客戶卡片增益集](customer-card-add-in.md)與其他 Dynamics 365 應用程式。  


[!INCLUDE [footer-include](includes/footer-banner.md)]
