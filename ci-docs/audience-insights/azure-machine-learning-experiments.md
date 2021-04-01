---
title: Azure 機器學習實驗
description: 在 Dynamics 365 Customer Insights 中使用 Azure 機器學習式模型。
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597409"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="9180d-103">使用 Azure 機器學習式模型</span><span class="sxs-lookup"><span data-stu-id="9180d-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="9180d-104">Dynamics 365 Customer Insights 中的統一資料是組建可產生額外業務見解的機器學習模型來源。</span><span class="sxs-lookup"><span data-stu-id="9180d-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="9180d-105">整合 Customer Insights 和 Machine Learning Studio (經典版) 和 Azure 機器學習的 Customer Insights 以使用您自己的自訂模型。</span><span class="sxs-lookup"><span data-stu-id="9180d-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="9180d-106">請參閱 [Machine Learning Studio (經典版) 實驗](machine-learning-studio-experiments.md) 了解以 Machine Learning Studio (經典版) 為基礎的實驗範例。</span><span class="sxs-lookup"><span data-stu-id="9180d-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9180d-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="9180d-107">Prerequisites</span></span>

- <span data-ttu-id="9180d-108">存取 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9180d-108">Access to Customer Insights</span></span>
- <span data-ttu-id="9180d-109">有效的 Azure 企業版訂用帳戶</span><span class="sxs-lookup"><span data-stu-id="9180d-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="9180d-110">統整的客戶設定檔</span><span class="sxs-lookup"><span data-stu-id="9180d-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="9180d-111">[實體匯出到 Azure Blob 儲存體](export-azure-blob-storage.md) 已組態</span><span class="sxs-lookup"><span data-stu-id="9180d-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="9180d-112">設定 Azure Machine Learning 工作區</span><span class="sxs-lookup"><span data-stu-id="9180d-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="9180d-113">請見 [建立 Azure Machine Learning 工作區](/azure/machine-learning/concept-workspace#-create-a-workspace) 了解不同的工作區建立選項。</span><span class="sxs-lookup"><span data-stu-id="9180d-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="9180d-114">為了取得最佳效能，請在地理位置上最接近您的 Customer Insights 環境的 Azure 區域中建立工作區。</span><span class="sxs-lookup"><span data-stu-id="9180d-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="9180d-115">透過 [Azure Machine Learning Studio](https://ml.azure.com/) 存取您的工作區。</span><span class="sxs-lookup"><span data-stu-id="9180d-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="9180d-116">目前有幾種 [方式與](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) 您的工作區互動。</span><span class="sxs-lookup"><span data-stu-id="9180d-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="9180d-117">搭配 Azure Machine Learning 設計師處理</span><span class="sxs-lookup"><span data-stu-id="9180d-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="9180d-118">Azure Machine Learning 設計師提供直觀畫布，您可以拖曳資料集合與模組，類似 Machine Learning Studio (經典版)。</span><span class="sxs-lookup"><span data-stu-id="9180d-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="9180d-119">如果已經組態，您從設計師建立的批次處理管道就能整合到 Customer Insights。</span><span class="sxs-lookup"><span data-stu-id="9180d-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="9180d-120">搭配 Azure Machine Learning SDK 處理</span><span class="sxs-lookup"><span data-stu-id="9180d-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="9180d-121">資料科學家和 AI 開發人員使用 [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) 組建機器學習工作流程。</span><span class="sxs-lookup"><span data-stu-id="9180d-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="9180d-122">目前使用 SDK 訓練的模型無法直接與 Customer Insights 整合。</span><span class="sxs-lookup"><span data-stu-id="9180d-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="9180d-123">使用該模型的批次推論管道需要與 Customer Insights 整合。</span><span class="sxs-lookup"><span data-stu-id="9180d-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="9180d-124">Customer Insights 整合的批次處理管道需求</span><span class="sxs-lookup"><span data-stu-id="9180d-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="9180d-125">資料集組態</span><span class="sxs-lookup"><span data-stu-id="9180d-125">Dataset Configuration</span></span>

<span data-ttu-id="9180d-126">您必須建立資料集才能使用從 Customer Insights 到您的批次處理推論管道使用實體資料。</span><span class="sxs-lookup"><span data-stu-id="9180d-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="9180d-127">這些資料集必須在工作區註冊。</span><span class="sxs-lookup"><span data-stu-id="9180d-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="9180d-128">目前我們只支援.csv 格式的 [表格式資料集](/azure/machine-learning/how-to-create-register-datasets#tabulardataset)。</span><span class="sxs-lookup"><span data-stu-id="9180d-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="9180d-129">對應實體資料的資料集必須參數化為管道參數。</span><span class="sxs-lookup"><span data-stu-id="9180d-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="9180d-130">Designer 中的資料集參數</span><span class="sxs-lookup"><span data-stu-id="9180d-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="9180d-131">在 Designer 程式中打開 **選取資料集的欄位**，然後選取 **設定為管道參數**，您即可提供參數名稱。</span><span class="sxs-lookup"><span data-stu-id="9180d-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="9180d-132">![Designer 中的資料集參數化](media/intelligence-designer-dataset-parameters.png "Designer 中的資料集參數化")</span><span class="sxs-lookup"><span data-stu-id="9180d-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="9180d-133">SDK 中的資料集參數 (Python)</span><span class="sxs-lookup"><span data-stu-id="9180d-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="9180d-134">批次處理推論管道</span><span class="sxs-lookup"><span data-stu-id="9180d-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="9180d-135">在 Designer 中，訓練管道可用來建立或更新推論管道。</span><span class="sxs-lookup"><span data-stu-id="9180d-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="9180d-136">目前只支援批次處理推論管道。</span><span class="sxs-lookup"><span data-stu-id="9180d-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="9180d-137">您可以使用 SDK 將管線發佈到端點。</span><span class="sxs-lookup"><span data-stu-id="9180d-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="9180d-138">目前 Customer Insights 與機器學習工作區中，批次處理管道端點中的預設管道整合。</span><span class="sxs-lookup"><span data-stu-id="9180d-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="9180d-139">將管道資料匯入 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9180d-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="9180d-140">Designer 程式提供 [匯出資料模組](/azure/machine-learning/algorithm-module-reference/export-data)，允許將管道輸出匯出到 Azure 儲存體。</span><span class="sxs-lookup"><span data-stu-id="9180d-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="9180d-141">目前模組必須使用資料儲存類型 **Azure Blob 儲存體** 並將 **資料儲存** 和相對 **路徑** 參數化。</span><span class="sxs-lookup"><span data-stu-id="9180d-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="9180d-142">管道執行資料儲存及產品可存取的路徑時，Customer Insights 會覆寫這兩個參數。</span><span class="sxs-lookup"><span data-stu-id="9180d-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9180d-143">![匯出資料模組組態](media/intelligence-designer-importdata.png "匯出資料模組組態")</span><span class="sxs-lookup"><span data-stu-id="9180d-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="9180d-144">當使用代碼撰寫推論輸出時，您可以將輸出上傳到工作區中 *已註冊資料儲存* 內的路徑。</span><span class="sxs-lookup"><span data-stu-id="9180d-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="9180d-145">如果路徑和資料儲存在管道中參數化，Customer Insights 將可讀取和匯入推論輸出。</span><span class="sxs-lookup"><span data-stu-id="9180d-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="9180d-146">目前支援 csv 格式的單表格式輸出。</span><span class="sxs-lookup"><span data-stu-id="9180d-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="9180d-147">路徑必須包括目錄和檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="9180d-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]