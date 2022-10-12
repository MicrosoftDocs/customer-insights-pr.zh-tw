---
title: 根據預測模型建立客戶細分
description: 根據預測模型的輸出實體建立客戶細分。
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610410"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>根據預測模型建立客戶細分 (預覽版)

而預測結果有時只會套用至客戶的子集。 從預測模型的結果建立客戶細分，以增加建議的個人化程度。 例如，您可能想要給喜歡特定服務類型客戶一些專屬建議。

## <a name="prerequisites"></a>先決條件

- 至少有 Customer Insights 中的[參與者權限](permissions.md)。

- 在 Customer Insights 中設定好的產品建議、交易流失、訂閱流失或客戶存留期值模型。 檢閱需求以設定不同的模型：

  - [產品建議模型](predict-product-recommendation.md)
  - [訂閱流失模型](predict-subscription-churn.md)
  - [交易流失模型](predict-transactional-churn.md)
  - [客戶存留期值模型](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>根據預測建立客戶細分

1. 請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。

1. 選取您要檢視的模型，並選取 **查看**。

1. 在結果頁面上，選取 **建立客戶細分**。 如需結果頁面的詳細資訊，請查看有關此模型的文章。

   :::image type="content" source="media/prediction-create-segment.png" alt-text="預測結果頁面的螢幕擷取畫面，其中醒目提示建立客戶細分的動作。":::

1. 從所選模型的輸出實體建立使用屬性的新客戶細分。 如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。

> [!TIP]
> 您也可以選取 **新** 並選擇 **從** > **智慧建立**，以從 **客戶細分** 頁面，建立預測模型的客戶細分。 如需詳細資訊，請參閱[使用快速客戶細分建立客戶細分](segment-quick.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
