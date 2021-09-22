---
title: 使用人口統計學維度來分割行為資料 (已整理的維度)
description: 使用整合個人資料的已整理維度，以啟用對象見解客戶個人資料屬性。
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50bb800c9e097d03cc6f26f79819c741ab5e8baf
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461093"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>使用人口統計學維度來分割行為資料

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

透過使用整合個人資料人口統計維度，參與見解的使用者可以存取對象見解個人資料屬性。 包括在您的網站、行動應用程式上參與服務見解擷取到的行為資料，可以用來進行互動分析，您便可以在互動分析中使用這些屬性。

>[!NOTE]
> 參與見解包含對事件屬性的立即可用維度。 其他資訊：[查看並建立維度](dimensions.md)

## <a name="prerequisite"></a>先決條件

- 參與見解的環境，在其中有連結至對象見解環境的客戶個人資料，此對象見解環境則是建立客戶細分和客戶個人資料的環境。 更多資訊：[建立對象見解與參與見解之間的連結](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> 在建立對象見解與參與見解環境之間的連結之後，您可能只想要能在參與見解中當作維度的特定客戶個人資料屬性的資料。 如需更多資訊，請移至[啟用對象見解整合個人資料屬性和客戶細分](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments)。<!--note from editor: Suggested. -->

## <a name="create-a-new-custom-report"></a>建立新自訂報表

1. 在左窗格中，選取 **自訂** > **新報表**，然後選取想要的計量。 (在此範例中，我們選取 **網頁檢視-依小時** 報表。)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="選取計量。":::

2. 在視覺化效果編輯器中，選取 **維度**，然後在 **維度類型** 下拉式功能表中選取 **人口統計**。

    :::image type="content" source="media/curated-dimensions2.png" alt-text="選取人口統計。":::

3. 選取 **Signal.Customer.*xxx*** 維度。 (此範例顯示的是 Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="選取維度。":::
  
## <a name="limitations"></a>限制

目前您可以僅使用人口統計學維度來分割行為資料。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
