---
title: 開始使用商務帳戶做為主要目標對象
description: 了解有關商務帳戶做為主要目標對象 Dynamics 365 Customer Insights。
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 88882dc727c37262c9f204fbc8049abe17bd21a3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353532"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>搭配對象見解中的商務帳戶

Dynamics 365 Customer Insights 的對象見解功能讓您為不同的主要目標對象組態自己的環境：個別消費者 (B 到 C) 和商務帳戶 (B 到 B)。 在 B 到 C 案例中，資料以個人為中心。 B 到 B 方面，主要目標對象是帳戶-組織或公司-和連絡人。 本文幫助您開始使用商務帳戶環境。 它會根據您的環境焦點列出對象見解功能區的差異。 如需有關差異的詳細資訊，請審閱功能區文件。 

## <a name="create-an-environment-for-business-accounts"></a>為商務帳戶建立環境

系統管理員可以[在現有的組織建立環境](create-environment.md)。 建立新環境的流程步驟會請系統管理員提供環境的主要目標對象。 購買授權後，如果是對象見解的初始設定，引導式體驗有助於建立第一個環境。

然後您可以從所有支援的來源將商務帳戶和相關聯絡人[的資料擷取](data-sources.md)為資料來源。

統一資料後，請將[帳戶階層指定](relationships.md#set-up-account-hierarchies)為關聯組態的一部分。 您也可以[組態語意對應](semantic-mappings.md)連接連絡人與帳戶實體。 

## <a name="switch-between-primary-target-audience"></a>在主要目標對象之間切換

如果貴組織維護個別客戶和商務帳戶的環境，您可以使用左窗格的切換器選擇主要目標對象。

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="切換器可變更個別客戶與業務帳戶之間的主要目標對象。":::

## <a name="supported-feature-areas"></a>支援功能區

- [活動](activities.md)：支援帳戶及相關連絡人以建立活動並在時間表顯示它們。
- [關聯](relationships.md)：活動精靈有助於實體之間建立關聯，因此帳戶視圖會顯示來自連絡人的所有活動。 連絡人可以向上切入查看連絡人視圖，而階層可用於帳戶活動加總。
- [量值](measures.md)：支援從內含計算式的量值 Builder 建立的量值。 非必要設定允許建立量值時彙總子帳戶。
- [區段](segments.md)：支援從內含區段 Builder 從頭開始建立的區段。 新運算子允許建立區段時合併帳戶階層。
- [資料擷取](data-sources.md)：本區對商務帳戶和個別客戶的所有功能都是相同的。
- [資料統一](data-unification.md)：本區對商務帳戶和個別客戶的所有功能都是相同的。
- [擴充](enrichment-hub.md)：某些擴充類型僅適用個別客戶案例，而其他類型則僅供商務帳戶使用。
- [預測與開箱即用模型](predictions-overview.md)：交易流失預測包含商務帳戶的其他步驟。 其他預測僅適用個別客戶。
- [啟動和匯出](export-destinations.md)：商務帳戶和個別客戶可以匯出。 某些匯出要求下層區段投影額外組態和連絡人資訊，才能用於商務帳戶。
- [系統設定](system.md)和[使用者管理](permissions.md)：本區對商務帳戶和個別客戶的所有功能都是相同的。

