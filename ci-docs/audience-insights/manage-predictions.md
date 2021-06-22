---
title: 預測案例的共用工作
description: 了解如何管理、疑難排解及修正預測。
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095692"
---
# <a name="manage-predictions"></a><span data-ttu-id="dbb8f-103">管理預測</span><span class="sxs-lookup"><span data-stu-id="dbb8f-103">Manage predictions</span></span>

<span data-ttu-id="dbb8f-104">本文討論大部分預測案例中都有的一些工作。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="dbb8f-105">疑難排解失敗的預測</span><span class="sxs-lookup"><span data-stu-id="dbb8f-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="dbb8f-106">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="dbb8f-107">選取您要檢視錯誤記錄的預測旁的垂直刪節號。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="dbb8f-108">選取 **記錄**。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-108">Select **Logs**.</span></span>

1. <span data-ttu-id="dbb8f-109">檢閱所有錯誤。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-109">Review all the errors.</span></span> <span data-ttu-id="dbb8f-110">可能發生的錯誤有數種類型，這些類型描述造成錯誤的狀況。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="dbb8f-111">例如，沒有足夠資料而無法準確預測的錯誤，通常是透過載入額外資料到 Customer Insights 中來解決。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="dbb8f-112">輸入資料可用性報表</span><span class="sxs-lookup"><span data-stu-id="dbb8f-112">Input data usability report</span></span>

<span data-ttu-id="dbb8f-113">輸入資料可用性報表提供錯誤和警告的整合檢視表，指出在您的立即可用的預測可能產生的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="dbb8f-114">它也提供如何改善模型效能的建議。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="dbb8f-115">在模型完成其定型程序之後，才可使用此報表。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="dbb8f-116">它是單獨為每個模型建立的，不管其是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="dbb8f-117">目前，此功能只能在交易流失模型運作。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="dbb8f-118">查看輸入資料可用性報表</span><span class="sxs-lookup"><span data-stu-id="dbb8f-118">View the input data usability report</span></span>

<span data-ttu-id="dbb8f-119">當立即可用的模型完成後，請查看報表：</span><span class="sxs-lookup"><span data-stu-id="dbb8f-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="dbb8f-120">選取模型名稱旁邊的省略號，然後選擇 **輸入資料可用性報表**。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="dbb8f-121">選取模型的狀態，然後在側面窗格中選取 **查看輸入資料可用性報表**。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="dbb8f-122">在清單中選取其中一個模型，然後在命令列中選取 **輸入資料可用性報表**。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="dbb8f-123">打開模型結果頁面，然後在命令列中選取 **輸入資料可用性報表**。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="dbb8f-124">在輸入資料可用性報表的資訊</span><span class="sxs-lookup"><span data-stu-id="dbb8f-124">Information in the input data usability report</span></span>

<span data-ttu-id="dbb8f-125">報表中的下列各資料行包含改善模型資料的實用資訊。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="輸入資料可用性報表範例，顯示內有錯誤、警告和建議的資料表。":::

- <span data-ttu-id="dbb8f-127">名稱：錯誤、警告或建議的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="dbb8f-128">步驟：模型階段，定型或分數，參照資訊。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="dbb8f-129">狀態：資訊的嚴重性 (錯誤、警告、建議)。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="dbb8f-130">資料行名稱：若要改善模型效能，實體中的需要修改的資料行。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="dbb8f-131">實體名稱：若要改善模型效能，需要修改的實體名稱。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="dbb8f-132">詳細資料：錯誤、警告或建議的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="dbb8f-133">重新整理預測</span><span class="sxs-lookup"><span data-stu-id="dbb8f-133">Refresh a prediction</span></span>

<span data-ttu-id="dbb8f-134">測試會依照設定中所設定的同樣[資料重新整理排程](system.md#schedule-tab)自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="dbb8f-135">您也可以手動重新整理它們。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="dbb8f-136">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="dbb8f-137">選取您要重新整理之預測旁邊的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="dbb8f-138">選取 **重新整理**。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="dbb8f-139">刪除預測</span><span class="sxs-lookup"><span data-stu-id="dbb8f-139">Delete a prediction</span></span>

<span data-ttu-id="dbb8f-140">刪除預測也會同時移除其輸出實體。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="dbb8f-141">請前往 **智慧** > **預測** 並選取 **我的預測** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="dbb8f-142">選取您要刪除之預測旁邊的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="dbb8f-143">選取 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="dbb8f-143">Select **Delete**.</span></span>
