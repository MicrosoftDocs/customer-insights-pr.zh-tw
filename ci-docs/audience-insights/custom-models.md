---
title: 自訂機器學習模型 | Microsoft Docs
description: 在 Dynamics 365 Customer Insights 中使用 Azure Machine Learning 的自訂模型。
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700658"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="8e35b-103">自訂機器學習模型</span><span class="sxs-lookup"><span data-stu-id="8e35b-103">Custom machine learning models</span></span>

<span data-ttu-id="8e35b-104">**智慧** > **自訂模型** 讓您根據 Azure Machine Learning 模型管理工作流程。</span><span class="sxs-lookup"><span data-stu-id="8e35b-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="8e35b-105">工作流程協助您選擇要用來產生見解的資料，並將結果對應您的統一客戶資料。</span><span class="sxs-lookup"><span data-stu-id="8e35b-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="8e35b-106">如需組建自訂 ML 模型的詳細資訊，請見 [使用 Azure Machine Learning 模型](azure-machine-learning-experiments.md)。</span><span class="sxs-lookup"><span data-stu-id="8e35b-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="8e35b-107">負責的 AI</span><span class="sxs-lookup"><span data-stu-id="8e35b-107">Responsible AI</span></span>

<span data-ttu-id="8e35b-108">預測提供各項功能建立更佳的客戶體驗、改善業務功能和營收資料流。</span><span class="sxs-lookup"><span data-stu-id="8e35b-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="8e35b-109">我們強烈建議您比對預測會有的影響後取出餘值，並以符合道德的方式偏移可能帶入的餘值。</span><span class="sxs-lookup"><span data-stu-id="8e35b-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="8e35b-110">進一步瞭解 Microsoft 如何 [定址負責的 AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6)。</span><span class="sxs-lookup"><span data-stu-id="8e35b-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="8e35b-111">您也可以瞭解 Azure Machine Learning 專門負責的機器學習 [技術與流程](/azure/machine-learning/concept-responsible-ml)。</span><span class="sxs-lookup"><span data-stu-id="8e35b-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8e35b-112">先決條件</span><span class="sxs-lookup"><span data-stu-id="8e35b-112">Prerequisites</span></span>

- <span data-ttu-id="8e35b-113">目前此功能支援透過 [Machine Learning Studio (經典版)](https://studio.azureml.net) 和 [Azure Machine Learning 批次處理管道](/azure/machine-learning/concept-ml-pipelines) 發佈的 web 服務。</span><span class="sxs-lookup"><span data-stu-id="8e35b-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="8e35b-114">您需要與您的 Azure Studio 執行個體產生關聯的 Azure Data Lake Gen2 儲存體帳戶使用此功能。</span><span class="sxs-lookup"><span data-stu-id="8e35b-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="8e35b-115">如需詳細資訊，請參閱[建立 Azure Data Lake Storage Gen2 儲存體帳戶](/azure/storage/blobs/data-lake-storage-quickstart-create-account)。</span><span class="sxs-lookup"><span data-stu-id="8e35b-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="8e35b-116">前往具備準銷售案源的 Azure Machine Learning 工作區，您需要具備 Azure Machine Learning 工作區負責人或使用者存取權系統管理員的權限。</span><span class="sxs-lookup"><span data-stu-id="8e35b-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8e35b-117">在您的 Customer Insights 執行個體與選取的 Azure web 服務或工作流程中的準銷售案源之間傳輸資料。</span><span class="sxs-lookup"><span data-stu-id="8e35b-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="8e35b-118">當您將資料轉移到 Azure 服務時，請確保將服務設為以必要的方式和位置處理資料，以符合組織中對此資料的任何法律或法規要求。</span><span class="sxs-lookup"><span data-stu-id="8e35b-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="8e35b-119">新增工作流程</span><span class="sxs-lookup"><span data-stu-id="8e35b-119">Add a new workflow</span></span>

1. <span data-ttu-id="8e35b-120">前往 **智慧** > **自訂模型** 並選取 **新增工作流程**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="8e35b-121">在 **名稱** 欄位中，為自訂模型提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="8e35b-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e35b-122">![新增工作流程窗格的螢幕擷取畫面](media/new-workflowv2.png "新增工作流程窗格的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="8e35b-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="8e35b-123">在 **包含您的 Web 服務的用戶** 中，選取包含 Web 服務的組織。</span><span class="sxs-lookup"><span data-stu-id="8e35b-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="8e35b-124">如果您的 Azure Machine Learning 訂閱與 Customer Insights 位於不同的用戶，請選取 **登入**，並針對所選組織使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="8e35b-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="8e35b-125">選取與您的 web 服務相關聯的 **工作區**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="8e35b-126">目前列出兩區：適用 Azure Machine Learning v1 (Machine Learning Studio (經典版)) 和 Azure Machine Learning v2 (Azure Machine Learning)。</span><span class="sxs-lookup"><span data-stu-id="8e35b-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="8e35b-127">如果您不確定哪個工作區適用您的 Machine Learning Studio (經典版) web 服務，請選取 **任一個**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="8e35b-128">在 **包含您的模型的下拉式選單的 Web 服務** 中選擇 Machine Learning Studio (經典版) web 服務或 Azure Machine Learning 管道。</span><span class="sxs-lookup"><span data-stu-id="8e35b-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="8e35b-129">然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="8e35b-130">瞭解更多有關 [Machine Learning Studio (經典版) 中發佈 Web 服務](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="8e35b-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="8e35b-131">深入瞭解關於 [使用 Designer 程式](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) 或 [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 發佈 Azure Machine Learning 中的管道。</span><span class="sxs-lookup"><span data-stu-id="8e35b-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="8e35b-132">您的管道必須在 [管道端點](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) 下發佈。</span><span class="sxs-lookup"><span data-stu-id="8e35b-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="8e35b-133">各 **Web 服務輸入** 方面，請從對象見解選取符合的 **實體** 並選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="8e35b-134">自訂模型工作流程將會套用啟發型方法，根據欄位的名稱和資料類型，將 web 服務輸入欄位對應至實體屬性。</span><span class="sxs-lookup"><span data-stu-id="8e35b-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="8e35b-135">如果 web 服務欄位無法對應至實體，則會出現錯誤。</span><span class="sxs-lookup"><span data-stu-id="8e35b-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e35b-136">![設定工作流程](media/intelligence-screen2-updated.png "設定工作流程")</span><span class="sxs-lookup"><span data-stu-id="8e35b-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="8e35b-137">請在 **模型輸出參數** 步驟中設定下列屬性：</span><span class="sxs-lookup"><span data-stu-id="8e35b-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="8e35b-138">Machine Learning Studio (經典版)</span><span class="sxs-lookup"><span data-stu-id="8e35b-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="8e35b-139">輸入您想讓 Web 服務輸出結果流入的輸出 **實體名稱**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="8e35b-140">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="8e35b-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="8e35b-141">輸入您想讓管道輸出結果流入的輸出 **實體名稱**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="8e35b-142">請從下拉式選單選取您的批次處理管道的 **輸出資料存放區參數名稱**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="8e35b-143">請從下拉式選單選取您的批次處理管道的 **輸出路徑參數名稱**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="8e35b-144">![模型輸出參數窗格](media/intelligence-screen3-outputparameters.png "模型輸出參數窗格")</span><span class="sxs-lookup"><span data-stu-id="8e35b-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="8e35b-145">請從辨識客戶的 **結果下拉式選單中的客戶識別碼** 選取符合的屬性並選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-145">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e35b-146">![客戶資料相關結果窗格](media/intelligence-screen4-relatetocustomer.png "客戶資料相關結果窗格")</span><span class="sxs-lookup"><span data-stu-id="8e35b-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="8e35b-147">您會看到 **工作流程已儲存** 畫面，其中包含工作流程的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8e35b-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="8e35b-148">如果您已針對 Azure Machine Learning 管道組態工作流程，對象見解將附加到包含管道的工作區。</span><span class="sxs-lookup"><span data-stu-id="8e35b-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="8e35b-149">對象見解在 Azure 工作區取得 **參與者** 角色。</span><span class="sxs-lookup"><span data-stu-id="8e35b-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="8e35b-150">選取 **完成**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-150">Select **Done**.</span></span>

1. <span data-ttu-id="8e35b-151">您現在可以從 **自訂模型** 頁面執行工作流程。</span><span class="sxs-lookup"><span data-stu-id="8e35b-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="8e35b-152">編輯工作流程</span><span class="sxs-lookup"><span data-stu-id="8e35b-152">Edit a workflow</span></span>

1. <span data-ttu-id="8e35b-153">在 **自訂模型** 頁面上，選取先前建立之工作流程旁邊 **動作** 欄中的垂直省略符號，然後選取 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="8e35b-154">您可以在 **顯示名稱** 欄位中更新您的工作流程可識別名稱，但不能變更已組態的 Web 服務或管道。</span><span class="sxs-lookup"><span data-stu-id="8e35b-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="8e35b-155">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-155">Select **Next**.</span></span>

1. <span data-ttu-id="8e35b-156">各 **Web 服務輸入** 方面，您可以從對象見解更新符合的 **實體**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="8e35b-157">然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="8e35b-158">請在 **模型輸出參數** 步驟中設定下列屬性：</span><span class="sxs-lookup"><span data-stu-id="8e35b-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="8e35b-159">Machine Learning Studio (經典版)</span><span class="sxs-lookup"><span data-stu-id="8e35b-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="8e35b-160">輸入您想讓 Web 服務輸出結果流入的輸出 **實體名稱**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="8e35b-161">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="8e35b-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="8e35b-162">輸入您想讓管道輸出結果流入的輸出 **實體名稱**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="8e35b-163">請針對您的測試管道選取 **輸出資料存放區參數名稱**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="8e35b-164">請針對您的測試管道選取 **輸出路徑參數名稱**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="8e35b-165">請從辨識客戶的 **結果下拉式選單中的客戶識別碼** 選取符合的屬性並選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-165">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="8e35b-166">從推論輸出中選擇屬性，其值類似客戶實體的客戶識別碼資料欄。</span><span class="sxs-lookup"><span data-stu-id="8e35b-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="8e35b-167">如果您的資料集沒有此欄位，請選擇唯一識別該行的屬性。</span><span class="sxs-lookup"><span data-stu-id="8e35b-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="8e35b-168">執行工作流程</span><span class="sxs-lookup"><span data-stu-id="8e35b-168">Run a workflow</span></span>

1. <span data-ttu-id="8e35b-169">在 **自訂模型** 頁面上，選取先前建立之工作流程旁邊 **動作** 欄中的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="8e35b-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="8e35b-170">選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="8e35b-170">Select **Run**.</span></span>

<span data-ttu-id="8e35b-171">工作流程也會自動隨每個排定的重新整理一起執行。</span><span class="sxs-lookup"><span data-stu-id="8e35b-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="8e35b-172">進一步了解[設定排定的更新](system.md#schedule-tab)。</span><span class="sxs-lookup"><span data-stu-id="8e35b-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="8e35b-173">刪除工作流程</span><span class="sxs-lookup"><span data-stu-id="8e35b-173">Delete a workflow</span></span>

1. <span data-ttu-id="8e35b-174">在 **自訂模型** 頁面上，選取先前建立之工作流程旁邊 **動作** 欄中的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="8e35b-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="8e35b-175">選取 **刪除**，並確認刪除。</span><span class="sxs-lookup"><span data-stu-id="8e35b-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="8e35b-176">將會刪除您的工作流程。</span><span class="sxs-lookup"><span data-stu-id="8e35b-176">Your workflow will be deleted.</span></span> <span data-ttu-id="8e35b-177">您建立工作流程時所建立的 [實體](entities.md)仍然存在，而且可以從 **實體** 頁面來檢視此實體。</span><span class="sxs-lookup"><span data-stu-id="8e35b-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="8e35b-178">結果​​</span><span class="sxs-lookup"><span data-stu-id="8e35b-178">Results</span></span>

<span data-ttu-id="8e35b-179">工作流程的結果會儲存在模型輸出參數階段時設定的實體中。</span><span class="sxs-lookup"><span data-stu-id="8e35b-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="8e35b-180">您可以從[實體頁面](entities.md)或使用 [API 存取](apis.md)存取此資料。</span><span class="sxs-lookup"><span data-stu-id="8e35b-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="8e35b-181">API 存取</span><span class="sxs-lookup"><span data-stu-id="8e35b-181">API Access</span></span>

<span data-ttu-id="8e35b-182">若要讓特定 OData 查詢從自訂模型實體取得資料，請使用下列格式：</span><span class="sxs-lookup"><span data-stu-id="8e35b-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="8e35b-183">以 Customer Insights 環境的識別碼取代 `<your instance id>`，在您存取 Customer Insights 時可以在瀏覽器的網址列中找到識別碼。</span><span class="sxs-lookup"><span data-stu-id="8e35b-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="8e35b-184">將 `<custom model output entity>` 以實體名稱取代，即您在自訂模型設定的模型輸出參數步驟中所提供的名稱。</span><span class="sxs-lookup"><span data-stu-id="8e35b-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="8e35b-185">您想要為哪位客戶存取記錄，將 `<guid value>` 以其客戶識別碼取代。</span><span class="sxs-lookup"><span data-stu-id="8e35b-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="8e35b-186">您通常可以在[客戶個人資料頁面](customer-profiles.md)的 CustomerID 欄位中找到此識別碼。</span><span class="sxs-lookup"><span data-stu-id="8e35b-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8e35b-187">常見問題集</span><span class="sxs-lookup"><span data-stu-id="8e35b-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="8e35b-188">為何在設定自訂模型工作流程時看不到我的準銷售案源？</span><span class="sxs-lookup"><span data-stu-id="8e35b-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="8e35b-189">發生此問題的原因通常是由於準銷售案源的設定有問題。</span><span class="sxs-lookup"><span data-stu-id="8e35b-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="8e35b-190">確定[輸入參數已設定](azure-machine-learning-experiments.md#dataset-configuration)，而且[輸出資料存儲和路徑參數](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights)也已設定完成。</span><span class="sxs-lookup"><span data-stu-id="8e35b-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="8e35b-191">錯誤「無法儲存智慧工作流程」是什麼意思？</span><span class="sxs-lookup"><span data-stu-id="8e35b-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="8e35b-192">通常使用者看到此錯誤訊息，是當他沒有工作區的負責人或使用者存取權系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="8e35b-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="8e35b-193">使用者需要更高等級的權限，才能以作為服務的方式啟用 Customer Insights 來處理工作流程，而非以使用者認證進行工作流程的後續執行。</span><span class="sxs-lookup"><span data-stu-id="8e35b-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
