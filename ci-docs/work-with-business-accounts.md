---
title: 搭配商務客戶
description: 了解在 Dynamics 365 Customer Insights 中當作主要目標對象商務客戶。
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303906"
---
# <a name="work-with-business-accounts"></a>搭配商務客戶

Dynamics 365 Customer Insights 讓您為不同的主要目標對象設定環境：個別消費者 (B 到 C) 和公司客戶 (B 到 B)。 在 B 到 C 案例中，資料以個人為中心。 B 到 B 方面，主要目標對象是帳戶-組織或公司-和連絡人。 本文幫助您開始使用商務客戶環境。 它會根據您的環境焦點列出 Customer Insights 功能區的差異。 如需有關差異的詳細資訊，請審閱功能區文件。 

## <a name="create-an-environment-for-business-accounts"></a>為商務客戶建立環境

系統管理員可以[在現有的組織建立環境](create-environment.md)。 建立新環境的流程步驟會請系統管理員提供環境的主要目標對象。 購買授權後的初始設定，引導式體驗可協助建立第一個環境。

然後您可以從所有支援的來源將商務客戶及相關連絡人的[資料擷取](data-sources.md)為資料來源。

 [整合](data-unification.md)客戶資料，然後整合連絡人資料，以連接連絡人與客戶實體。

## <a name="switch-between-primary-target-audience"></a>在主要目標對象之間切換

如果貴組織維護個別客戶和商務客戶的環境，您可以使用左窗格的切換器選擇主要目標對象。

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="切換器可變更個別客戶與業務帳戶之間的主要目標對象。":::

## <a name="supported-feature-areas"></a>支援功能區

- [活動](activities.md)：支援帳戶及相關連絡人以建立活動並在時間表顯示它們。
- [關聯](relationships.md)：活動精靈有助於實體之間建立關聯，因此帳戶視圖會顯示來自連絡人的所有活動。 連絡人可以向上切入查看連絡人視圖，而階層可用於帳戶活動加總。
- [量值](measures.md)：支援從內含計算式的量值建立器建立的量值。 非必要設定允許建立量值時彙總子帳戶。
- [客戶細分](segments.md)：支援從內含客戶細分建立器從頭開始建立的客戶細分。 客戶細分可以根據客戶或連絡人來建立。
- [資料擷取](data-sources.md)：本區域對商務客戶和個別客戶的所有功能都是相同的。
- B 到 B 資料整合非常類似於 B 到 C 資料整合，但是有額外的步驟要在客戶整合後整合連絡人。 請參閱[商務客戶 (B 到 B)](data-unification.md)。
- [擴充](enrichment-hub.md)：某些擴充類型僅適用個別客戶案例，而其他類型則僅供商務客戶使用。
- [預測與開箱即用模型](predictions-overview.md)：交易流失預測包含商務客戶的其他步驟。 其他預測僅適用個別客戶。
- [啟動和匯出](export-destinations.md)：商務客戶和個別客戶可以匯出。 部分匯出要求必須以基礎客戶細分推斷額外組態和連絡人資訊，才能用於商務客戶。
- [系統設定](system.md)和[使用者管理](permissions.md)：本區對商務客戶和個別客戶的所有功能都是相同的。

[!INCLUDE [footer-include](includes/footer-banner.md)]
