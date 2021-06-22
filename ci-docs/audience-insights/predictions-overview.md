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
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095691"
---
# <a name="predictions-overview"></a><span data-ttu-id="56f27-103">預測概觀</span><span class="sxs-lookup"><span data-stu-id="56f27-103">Predictions overview</span></span>

<span data-ttu-id="56f27-104">Dynamics 365 Customer Insights 隨附多種選項，可讓您利用 AI 和機器學習來預測資料。</span><span class="sxs-lookup"><span data-stu-id="56f27-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="56f27-105">立即可用的模型</span><span class="sxs-lookup"><span data-stu-id="56f27-105">Out-of-box models</span></span>

<span data-ttu-id="56f27-106">開始使用預測資料最簡單的方法是預先定義模型，通常稱為立即可用模型。</span><span class="sxs-lookup"><span data-stu-id="56f27-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="56f27-107">他們只需要某些資料和結構，即可快速生成見解。</span><span class="sxs-lookup"><span data-stu-id="56f27-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="56f27-108">目前，有下列模型可以使用：</span><span class="sxs-lookup"><span data-stu-id="56f27-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="56f27-109">[客戶存留期值](predict-customer-lifetime-value.md)：預測客戶在與公司的互動中可能的營收。</span><span class="sxs-lookup"><span data-stu-id="56f27-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="56f27-110">[產品建議](predict-product-recommendation.md)：根據採購行為和具有類似購買模式的客戶，提出一組預測產品建議。</span><span class="sxs-lookup"><span data-stu-id="56f27-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="56f27-111">[訂閱流失](predict-subscription-churn.md): 預測客戶是否有不再使用貴公司的訂閱產品或服務的風險。</span><span class="sxs-lookup"><span data-stu-id="56f27-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="56f27-112">[交易流失](predict-transactional-churn.md)：預測客戶是否在特定時間範圍不會再購買您的產品或服務。</span><span class="sxs-lookup"><span data-stu-id="56f27-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="56f27-113">Azure Machine Learnings 整合</span><span class="sxs-lookup"><span data-stu-id="56f27-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="56f27-114">如果組織已根據 Azure Machine Learning 試驗來使用機器學習案例，則 Customer Insights 中的自訂模型功能可協助您掌握全貌。</span><span class="sxs-lookup"><span data-stu-id="56f27-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="56f27-115">建立工作流程，來協助您選擇想要建立見解的資料，並將結果對應至您的整合客戶個人資料。</span><span class="sxs-lookup"><span data-stu-id="56f27-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="56f27-116">如需詳細資訊，請參閱[自訂機器學習模型](custom-models.md)。</span><span class="sxs-lookup"><span data-stu-id="56f27-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="56f27-117">AI Builder 預測</span><span class="sxs-lookup"><span data-stu-id="56f27-117">AI Builder prediction</span></span>

<span data-ttu-id="56f27-118">有時資料集不完整，也會遺失某些值。</span><span class="sxs-lookup"><span data-stu-id="56f27-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="56f27-119">Customer Insights 可協助預測客戶實體和客戶細分的遺失值。</span><span class="sxs-lookup"><span data-stu-id="56f27-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="56f27-120">如需詳細資訊，請參閱[以預測完成部分資料](predictions.md)。</span><span class="sxs-lookup"><span data-stu-id="56f27-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
