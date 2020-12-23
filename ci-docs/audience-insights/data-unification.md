---
title: 資料統整
description: 瞭解如何統一內嵌資料。
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405245"
---
# <a name="data-unification"></a>資料統整

[設定資料來源](data-sources.md) 之後，您可以統一資料。 資料統整包含三個步驟：**對應**、**比對** 及 **合併**。

資料統整程序可讓您將曾經完全不同的資料來源統整成單一主要資料集，以提供您客戶的統整檢視表。 統整階段是必要的，並依下列順序執行：

1. [對應](map-entities.md)
2. [Match](match-entities.md)
3. [合併](merge-entities.md)

在完成資料統整之後，您可以選擇

- [設定實體之間的關係](relationships.md) 以建立錯綜複雜的區段
- [擴充您的資料](enrichment-hub.md) 以更廣泛洞悉您的客戶
- 從若干內嵌的屬性 [定義活動](activities.md)
