---
title: 了解並管理量值
description: 了解量值是如何協助分析並反映業務表現。
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: ef10f480086ccac4fa5c6c58818e35ecae67532c
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529667"
---
# <a name="measures-overview"></a>量值概觀

量值可協助您更清晰地了解客戶行為和業務績效。 它們會從[整合個人資料](data-unification.md)中檢查相關的值。 例如，公司想要查看 *每位客戶的總花費*，以瞭解單一客戶的購買歷史，或量值 *公司的總銷售人*，以瞭解整體業務中的總營收。  

量值可以使用[量值建立器](measure-builder.md) 建立，量值建立器是一種包含各種運算子和簡單對應選項的資料查詢平臺。 它可讓您篩選資料、分組結果、偵測 [實體關聯路徑](relationships.md)，以及預覽輸出。 [使用預先定義的範本](measure-templates.md)可以有效率的設定常用量值。

規劃商務活動時，您可以使用量值建立工具查詢客戶資料並抽取見解。 例如，建立 *每個客戶的總消費額* 以及 *每個客戶的總利潤額*，能協助找出大量消費額度高且利潤高的客戶。 您可以根據這些量值[建立客戶細分](segments.md)，採取之後的最佳動作。

## <a name="manage-your-measures"></a>管理您的量值

您可以在 **量值** 頁面上找到量值清單。

您可以找到有關量值類型、建立者、建立日期、狀態及狀況的資訊。 當您從清單中選取量值時，您可以預覽輸出並下載 CSV 檔。

:::image type="content" source="media/measures-actions.png" alt-text="管理單一量值的動作。"lightbox="media/measures-actions.png":::

選取量值時，可使用下列動作：

- **編輯** 量值的設定。
- **複製** 量值。 您可以選擇立刻編輯屬性，或只是儲存複本。
- **重新整理** 根據最新資料的量值。 若要同時重新整理所有的量值，請選取所有量值，然後 **重新整理**。
- **重新命名** 量值。
- **啟用** 或 **停用**。 停用量值時，不會在[排程的重新整理](system.md#schedule-tab)時進行重新整理。
- **標籤** 可在客戶細分[管理標籤](work-with-tags-columns.md#manage-tags)。
- **刪除** 量值。

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>下一個步驟

您可以使用現有的量值來建立[客戶細分](segments.md)。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
