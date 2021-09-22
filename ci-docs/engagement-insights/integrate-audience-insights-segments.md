---
title: 使用對象見解客戶細分來篩選參與見解報表
description: 請在互動分析中使用對象見解客戶細分，此互動分析將分析在客戶網站上參與服務見解擷取到的行為資料。
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461048"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>使用對象見解客戶細分來篩選參與見解報表

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

有了參與見解，您可以在互動分析中使用對象見解客戶細分，此互動分析將分析在客戶網站上參與服務見解擷取到的行為資料。

## <a name="prerequisite"></a>先決條件

- 參與見解的環境，在其中有連結至對象見解環境的對象見解客戶細分資料，此對象見解環境則是建立客戶細分和客戶個人資料的環境。 更多資訊：[建立對象見解與參與見解之間的連結](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>建立對象見解客戶細分 

> [!IMPORTANT]
> 若要讓對象見解客戶細分顯示在參與見解中，您必須先[執行合併和下游處理](../audience-insights/merge-entities.md)。 下游程序很重要，因為它們會生成唯一的資料表，以準備要與參與見解共用的對象見解客戶細分。 (如果已排程系統重新整理，則會自動包括下游程序。)

在參與見解中，您可以在現成報表或已建立的自訂報表中使用對象見解客戶細分。 如需詳細資訊，請移至[現成個人資料報表](profile-reports.md)，以及[建立及編輯自訂報表](custom-reports.md)。

**在參與見解報表中使用對象見解客戶細分**

1. 從您的 **工作區** 頁面中，選取 **資料**，然後選取 **客戶細分** 索引標籤。

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="選取客戶細分索引標籤。":::

   >[!NOTE]
   > 選取對象見解客戶細分可以進入對象見解，您可以看到該客戶細分是依照什麼規則條款和邏輯建立的。 如需對象見解客戶細分的詳細資訊，請移至[查看並建立客戶細分](../audience-insights/segments.md)。

2. 選取現成報表或 [建立自訂報表](custom-reports.md)，然後選取 **新增條件**。 (在此範例中，我們選取 **網頁檢視** 報表。)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="新增條件。":::

3. 選取 **依客戶細分篩選**，展開 **客戶細分類型** 清單，然後選取 **人口統計**。

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="選取人口統計客戶細分類型。":::

4. 展開 **客戶細分名稱** 清單，然後選擇對象見解客戶細分。

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text=" 選擇客戶細分。":::

5. 您可以套用一或多個客戶細分，包括行為 (參與見解) 和人口統計(對象見解) 客戶細分。 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="網頁檢視報表限美國的客戶和首頁客戶細分使用。":::

在先前的影像中，已選取 **USA 客戶** 和 **首頁** 客戶細分，這會限制 **網頁檢視** 報表只會顯示這兩個客戶細分。 


>[!NOTE]
> 在參與見解中，您可以在現成報表、已建立的自訂報表、或漏斗圖中使用對象見解客戶細分篩選。 


[!INCLUDE[footer-include](../includes/footer-banner.md)]