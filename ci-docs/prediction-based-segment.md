---
title: 以預測輸出建立客戶細分
description: 根據預測模型的輸出實體建立客戶細分。
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645920"
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

1. 選取您要查看的模型其旁邊的垂直省略號，並選取 **查看**。

1. 在結果頁面上，選取 **建立客戶細分**。 如需結果頁面的詳細資訊，請查看有關此模型的文章。

   :::image type="content" source="media/prediction-create-segment.png" alt-text="預測結果頁面的螢幕擷取畫面，其中醒目提示建立客戶細分的動作。":::

1. 根據選取模型的輸出實體建立新的客戶細分。 如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。