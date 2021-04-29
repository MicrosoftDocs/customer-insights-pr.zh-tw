---
title: 以預測輸出建立客戶細分
description: 根據預測模型的輸出實體建立客戶細分。
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741419"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="809e5-103">根據預測模型建立客戶細分 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="809e5-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="809e5-104">而預測結果有時只會套用至客戶的子集。</span><span class="sxs-lookup"><span data-stu-id="809e5-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="809e5-105">從預測模型的結果建立客戶細分，以增加建議的個人化程度。</span><span class="sxs-lookup"><span data-stu-id="809e5-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="809e5-106">例如，您可能想要給喜歡特定服務類型客戶一些專屬建議。</span><span class="sxs-lookup"><span data-stu-id="809e5-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="809e5-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="809e5-107">Prerequisites</span></span>

- <span data-ttu-id="809e5-108">至少有 Customer Insights 中的[參與者權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="809e5-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="809e5-109">在 Customer Insights 中設定好的產品建議、交易流失、訂閱流失或客戶存留期值模型。</span><span class="sxs-lookup"><span data-stu-id="809e5-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="809e5-110">檢閱需求以設定不同的模型：</span><span class="sxs-lookup"><span data-stu-id="809e5-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="809e5-111">產品建議模型</span><span class="sxs-lookup"><span data-stu-id="809e5-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="809e5-112">訂閱流失模型</span><span class="sxs-lookup"><span data-stu-id="809e5-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="809e5-113">交易流失模型</span><span class="sxs-lookup"><span data-stu-id="809e5-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="809e5-114">客戶存留期值模型</span><span class="sxs-lookup"><span data-stu-id="809e5-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="809e5-115">根據預測建立客戶細分</span><span class="sxs-lookup"><span data-stu-id="809e5-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="809e5-116">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="809e5-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="809e5-117">選取您要查看的模型其旁邊的垂直省略號，並選取 **查看**。</span><span class="sxs-lookup"><span data-stu-id="809e5-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="809e5-118">在結果頁面上，選取 **建立客戶細分**。</span><span class="sxs-lookup"><span data-stu-id="809e5-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="809e5-119">如需結果頁面的詳細資訊，請查看有關此模型的文章。</span><span class="sxs-lookup"><span data-stu-id="809e5-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="預測結果頁面的螢幕擷取畫面，其中醒目提示建立客戶細分的動作。":::

1. <span data-ttu-id="809e5-121">根據選取模型的輸出實體建立新的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="809e5-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="809e5-122">如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="809e5-122">For more information, see [Create and manage segments](segments.md).</span></span>