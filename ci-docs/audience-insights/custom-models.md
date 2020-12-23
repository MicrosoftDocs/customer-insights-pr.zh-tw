---
title: 自訂機器學習模型 | Microsoft Docs
description: 在 Dynamics 365 Customer Insights 中使用 Azure Machine Learning 的自訂模型。
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668893"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="77b07-103">自訂機器學習模型</span><span class="sxs-lookup"><span data-stu-id="77b07-103">Custom machine learning models</span></span>

<span data-ttu-id="77b07-104">**智慧** > **自訂模型** 讓您根據 Azure Machine Learning 模型管理工作流程。</span><span class="sxs-lookup"><span data-stu-id="77b07-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="77b07-105">工作流程協助您選擇要用來產生見解的資料，並將結果對應您的統一客戶資料。</span><span class="sxs-lookup"><span data-stu-id="77b07-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="77b07-106">如需組建自訂 ML 模型的詳細資訊，請見 [使用 Azure Machine Learning 模型](azure-machine-learning-experiments.md)。</span><span class="sxs-lookup"><span data-stu-id="77b07-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="77b07-107">負責的 AI</span><span class="sxs-lookup"><span data-stu-id="77b07-107">Responsible AI</span></span>

<span data-ttu-id="77b07-108">預測提供各項功能建立更佳的客戶體驗、改善業務功能和營收資料流。</span><span class="sxs-lookup"><span data-stu-id="77b07-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="77b07-109">我們強烈建議您比對預測會有的影響後取出餘值，並以符合道德的方式偏移可能帶入的餘值。</span><span class="sxs-lookup"><span data-stu-id="77b07-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="77b07-110">進一步瞭解 Microsoft 如何 [定址負責的 AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6)。</span><span class="sxs-lookup"><span data-stu-id="77b07-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="77b07-111">您也可以瞭解 Azure Machine Learning 專門負責的機器學習 [技術與流程](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml)。</span><span class="sxs-lookup"><span data-stu-id="77b07-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="77b07-112">先決條件</span><span class="sxs-lookup"><span data-stu-id="77b07-112">Prerequisites</span></span>

- <span data-ttu-id="77b07-113">目前此功能支援透過 [Machine Learning Studio (經典版)](https://studio.azureml.net) 和 [Azure Machine Learning 批次處理管道](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) 發佈的 web 服務。</span><span class="sxs-lookup"><span data-stu-id="77b07-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="77b07-114">您需要與您的 Azure Studio 執行個體產生關聯的 Azure Data Lake Gen2 儲存體帳戶使用此功能。</span><span class="sxs-lookup"><span data-stu-id="77b07-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="77b07-115">如需詳細資訊，請參閱[建立 Azure Data Lake Storage Gen2 儲存體帳戶](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="77b07-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="77b07-116">新增工作流程</span><span class="sxs-lookup"><span data-stu-id="77b07-116">Add a new workflow</span></span>

1. <span data-ttu-id="77b07-117">前往 **智慧** > **自訂模型** 並選取 **新增工作流程**。</span><span class="sxs-lookup"><span data-stu-id="77b07-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="77b07-118">在 **名稱** 欄位中，為自訂模型提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="77b07-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77b07-119">![新增工作流程窗格的螢幕擷取畫面](media/new-workflowv2.png "新增工作流程窗格的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="77b07-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="77b07-120">在 **包含您的 Web 服務的用戶** 中，選取包含 Web 服務的組織。</span><span class="sxs-lookup"><span data-stu-id="77b07-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="77b07-121">如果您的 Azure Machine Learning 訂閱與 Customer Insights 位於不同的用戶，請選取 **登入**，並針對所選組織使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="77b07-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="77b07-122">選取與您的 web 服務相關聯的 **工作區**。</span><span class="sxs-lookup"><span data-stu-id="77b07-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="77b07-123">目前列出兩區：適用 Azure Machine Learning v1 (Machine Learning Studio (經典版)) 和 Azure Machine Learning v2 (Azure Machine Learning)。</span><span class="sxs-lookup"><span data-stu-id="77b07-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="77b07-124">如果您不確定哪個工作區適用您的 Machine Learning Studio (經典版) web 服務，請選取 **任一個**。</span><span class="sxs-lookup"><span data-stu-id="77b07-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="77b07-125">在 **包含您的模型的下拉式選單的 Web 服務** 中選擇 Machine Learning Studio (經典版) web 服務或 Azure Machine Learning 管道。</span><span class="sxs-lookup"><span data-stu-id="77b07-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="77b07-126">然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="77b07-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="77b07-127">瞭解更多有關 [Machine Learning Studio (經典版) 中發佈 Web 服務](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="77b07-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="77b07-128">深入瞭解關於 [使用 Designer 程式](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) 或 [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 發佈 Azure Machine Learning 中的管道。</span><span class="sxs-lookup"><span data-stu-id="77b07-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="77b07-129">您的管道必須在 [管道端點](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) 下發佈。</span><span class="sxs-lookup"><span data-stu-id="77b07-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="77b07-130">各 **Web 服務輸入** 方面，請從對象見解選取符合的 **實體** 並選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="77b07-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77b07-131">![設定工作流程](media/intelligence-screen2-updated.png "設定工作流程")</span><span class="sxs-lookup"><span data-stu-id="77b07-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="77b07-132">請在 **模型輸出參數** 步驟中設定下列屬性：</span><span class="sxs-lookup"><span data-stu-id="77b07-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="77b07-133">Machine Learning Studio (經典版)</span><span class="sxs-lookup"><span data-stu-id="77b07-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="77b07-134">輸入您想讓 Web 服務輸出結果流入的輸出 **實體名稱**。</span><span class="sxs-lookup"><span data-stu-id="77b07-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="77b07-135">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="77b07-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="77b07-136">輸入您想讓管道輸出結果流入的輸出 **實體名稱**。</span><span class="sxs-lookup"><span data-stu-id="77b07-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="77b07-137">請從下拉式選單選取您的批次處理管道的 **輸出資料存放區參數名稱**。</span><span class="sxs-lookup"><span data-stu-id="77b07-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="77b07-138">請從下拉式選單選取您的批次處理管道的 **輸出路徑參數名稱**。</span><span class="sxs-lookup"><span data-stu-id="77b07-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="77b07-139">![模型輸出參數窗格](media/intelligence-screen3-outputparameters.png "模型輸出參數窗格")</span><span class="sxs-lookup"><span data-stu-id="77b07-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="77b07-140">請從辨識客戶的 **結果下拉式選單中的客戶識別碼** 選取符合的屬性並選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="77b07-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77b07-141">![客戶資料相關結果窗格](media/intelligence-screen4-relatetocustomer.png "客戶資料相關結果窗格")</span><span class="sxs-lookup"><span data-stu-id="77b07-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="77b07-142">您會看到 **工作流程已儲存** 畫面，其中包含工作流程的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="77b07-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="77b07-143">如果您已針對 Azure Machine Learning 管道組態工作流程，對象見解將附加到包含管道的工作區。</span><span class="sxs-lookup"><span data-stu-id="77b07-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="77b07-144">對象見解在 Azure 工作區取得 **參與者** 角色。</span><span class="sxs-lookup"><span data-stu-id="77b07-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="77b07-145">選取 **完成**。</span><span class="sxs-lookup"><span data-stu-id="77b07-145">Select **Done**.</span></span>

1. <span data-ttu-id="77b07-146">您現在可以從 **自訂模型** 頁面執行工作流程。</span><span class="sxs-lookup"><span data-stu-id="77b07-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="77b07-147">編輯工作流程</span><span class="sxs-lookup"><span data-stu-id="77b07-147">Edit a workflow</span></span>

1. <span data-ttu-id="77b07-148">在 **自訂模型** 頁面上，選取先前建立之工作流程旁邊 **動作** 欄中的垂直省略符號，然後選取 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="77b07-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="77b07-149">您可以在 **顯示名稱** 欄位中更新您的工作流程可識別名稱，但不能變更已組態的 Web 服務或管道。</span><span class="sxs-lookup"><span data-stu-id="77b07-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="77b07-150">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="77b07-150">Select **Next**.</span></span>

1. <span data-ttu-id="77b07-151">各 **Web 服務輸入** 方面，您可以從對象見解更新符合的 **實體**。</span><span class="sxs-lookup"><span data-stu-id="77b07-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="77b07-152">然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="77b07-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="77b07-153">請在 **模型輸出參數** 步驟中設定下列屬性：</span><span class="sxs-lookup"><span data-stu-id="77b07-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="77b07-154">Machine Learning Studio (經典版)</span><span class="sxs-lookup"><span data-stu-id="77b07-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="77b07-155">輸入您想讓 Web 服務輸出結果流入的輸出 **實體名稱**。</span><span class="sxs-lookup"><span data-stu-id="77b07-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="77b07-156">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="77b07-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="77b07-157">輸入您想讓管道輸出結果流入的輸出 **實體名稱**。</span><span class="sxs-lookup"><span data-stu-id="77b07-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="77b07-158">請針對您的測試管道選取 **輸出資料存放區參數名稱**。</span><span class="sxs-lookup"><span data-stu-id="77b07-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="77b07-159">請針對您的測試管道選取 **輸出路徑參數名稱**。</span><span class="sxs-lookup"><span data-stu-id="77b07-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="77b07-160">請從辨識客戶的 **結果下拉式選單中的客戶識別碼** 選取符合的屬性並選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="77b07-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="77b07-161">您必須從類似客戶實體的客戶識別碼的推論輸出值選擇屬性。</span><span class="sxs-lookup"><span data-stu-id="77b07-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="77b07-162">如果您的資料集沒有此欄位，請選擇唯一識別該行的屬性。</span><span class="sxs-lookup"><span data-stu-id="77b07-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="77b07-163">執行工作流程</span><span class="sxs-lookup"><span data-stu-id="77b07-163">Run a workflow</span></span>

1. <span data-ttu-id="77b07-164">在 **自訂模型** 頁面上，選取先前建立之工作流程旁邊 **動作** 欄中的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="77b07-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="77b07-165">選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="77b07-165">Select **Run**.</span></span>

<span data-ttu-id="77b07-166">工作流程也會自動隨每個排定的重新整理一起執行。</span><span class="sxs-lookup"><span data-stu-id="77b07-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="77b07-167">進一步了解[設定排定的更新](system.md#schedule-tab)。</span><span class="sxs-lookup"><span data-stu-id="77b07-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="77b07-168">刪除工作流程</span><span class="sxs-lookup"><span data-stu-id="77b07-168">Delete a workflow</span></span>

1. <span data-ttu-id="77b07-169">在 **自訂模型** 頁面上，選取先前建立之工作流程旁邊 **動作** 欄中的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="77b07-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="77b07-170">選取 **刪除**，並確認刪除。</span><span class="sxs-lookup"><span data-stu-id="77b07-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="77b07-171">將會刪除您的工作流程。</span><span class="sxs-lookup"><span data-stu-id="77b07-171">Your workflow will be deleted.</span></span> <span data-ttu-id="77b07-172">您建立工作流程時所建立的 [實體](entities.md)仍然存在，而且可以從 **實體** 頁面來檢視此實體。</span><span class="sxs-lookup"><span data-stu-id="77b07-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
