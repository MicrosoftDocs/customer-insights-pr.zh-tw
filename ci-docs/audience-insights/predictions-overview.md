---
title: 支援的預測案例概述
description: Dynamics 365 Customer Insights 應用程式所涵蓋預測案例和選項。
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 57c61895d636273fc90a0ac5a942fd0c9abf583c687ae20621949554e581cdf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035999"
---
# <a name="predictions-overview"></a>預測概觀

Dynamics 365 Customer Insights 隨附多種選項，可讓您利用 AI 和機器學習來預測資料。 

## <a name="out-of-box-models"></a>立即可用的模型

開始使用預測資料最簡單的方法是預先定義模型，通常稱為立即可用模型。 他們只需要某些資料和結構，即可快速生成見解。 目前，有下列模型可以使用： 
- [客戶存留期值](predict-customer-lifetime-value.md)：預測客戶在與公司的互動中可能的營收。 
- [產品建議](predict-product-recommendation.md)：根據採購行為和具有類似購買模式的客戶，提出一組預測產品建議。
- [訂閱流失](predict-subscription-churn.md): 預測客戶是否有不再使用貴公司的訂閱產品或服務的風險。
- [交易流失](predict-transactional-churn.md)：預測客戶是否在特定時間範圍不會再購買您的產品或服務。

## <a name="azure-machine-learning-integration"></a>Azure Machine Learnings 整合

如果組織已根據 Azure Machine Learning 試驗來使用機器學習案例，則 Customer Insights 中的自訂模型功能可協助您掌握全貌。 建立工作流程，來協助您選擇想要建立見解的資料，並將結果對應至您的整合客戶個人資料。 如需詳細資訊，請參閱[自訂機器學習模型](custom-models.md)。

## <a name="ai-builder-prediction"></a>AI Builder 預測

有時資料集不完整，也會遺失某些值。 Customer Insights 可協助預測客戶實體和客戶細分的遺失值。 如需詳細資訊，請參閱[以預測完成部分資料](predictions.md)。
