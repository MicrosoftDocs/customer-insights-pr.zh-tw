---
title: 支援的預測案例概述
description: Dynamics 365 Customer Insights 應用程式所涵蓋預測案例和選項。
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: a5e4503cf9ce0cea562bab9389748d8ca1451f9d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487489"
---
# <a name="predictions-overview"></a>預測概觀

Dynamics 365 Customer Insights 隨附多種選項，可讓您利用 AI 和機器學習來預測資料。 

## <a name="out-of-box-models"></a>立即可用的模型

開始使用預測資料最簡單的方法是預先定義模型，通常稱為立即可用模型。 他們只需要某些資料和結構，即可快速生成見解。 目前，有下列模型可以使用： 

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- [客戶存留期值](predict-customer-lifetime-value.md)：預測客戶在與公司的互動中可能的營收。
- [產品建議](predict-product-recommendation.md)：根據採購行為和具有類似購買模式的客戶，提出一組預測產品建議。
- [訂閱流失](predict-subscription-churn.md): 預測客戶是否有不再使用貴公司的訂閱產品或服務的風險。
- [交易流失](predict-transactional-churn.md)：預測客戶是否在特定時間範圍不會再購買您的產品或服務。
- [情感分析](sentiment-analysis.md)：分析客戶意見反應的情感，並找出經常提及的業務層面。

# <a name="business-accounts-b-to-b"></a>[商務帳戶 (B2B)](#tab/b2b)

- [交易流失](predict-transactional-churn.md)：預測客戶是否在特定時間範圍不會再購買您的產品或服務。

---

> [!TIP]
> 我們建議您定期使用更新過的資料來重新整理立即可用模型，以確保它們能準確地支援您的業務使用案例。 當系統擷取新的或更新的資料來源時，會對資料進行專門的重新整理。 但是，模型只會在此案例中重新評分，並繼續使用現有的訓練資料。
> 
> 在設定體驗中設定模型重新定型排程，您可以設定 **更新排程**。 模型將重新定型及重新評分此排程，且您可以隨時變更。


## <a name="azure-machine-learning-integration"></a>Azure Machine Learnings 整合

如果組織已根據 Azure Machine Learning 試驗來使用機器學習案例，則 Customer Insights 中的自訂模型功能可協助您掌握全貌。 建立工作流程，來協助您選擇想要建立見解的資料，並將結果對應至您的整合客戶個人資料。 如需詳細資訊，請參閱[自訂機器學習模型](custom-models.md)。

## <a name="ai-builder-prediction"></a>AI Builder 預測

有時資料集不完整，也會遺失某些值。 Customer Insights 可協助預測客戶實體和客戶細分的遺失值。 如需詳細資訊，請參閱[以預測完成部分資料](predictions.md)。
