---
title: 使用 Azure 機器學習式模型
description: 在 Dynamics 365 Customer Insights 中使用 Azure 機器學習式模型。
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609741"
---
# <a name="use-azure-machine-learning-based-models"></a>使用 Azure 機器學習式模型

Dynamics 365 Customer Insights 中的統一資料是組建可產生額外業務見解的機器學習模型來源。 Customer Insights 可與 Azure Machine Learning 整合來使用您自己的自訂模型。

## <a name="prerequisites"></a>先決條件

- 存取 Customer Insights
- 有效的 Azure 企業版訂用帳戶
- [統整的客戶設定檔](data-unification.md)
- [實體匯出到 Azure Blob 儲存體](export-azure-blob-storage.md) 已組態

## <a name="set-up-azure-machine-learning-workspace"></a>設定 Azure Machine Learning 工作區

1. 請見 [建立 Azure Machine Learning 工作區](/azure/machine-learning/concept-workspace#-create-a-workspace) 了解不同的工作區建立選項。 為了取得最佳效能，請在地理位置上最接近您的 Customer Insights 環境的 Azure 區域中建立工作區。

1. 透過 [Azure Machine Learning Studio](https://ml.azure.com/) 存取您的工作區。 目前有幾種 [方式與](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) 您的工作區互動。

## <a name="work-with-azure-machine-learning-designer"></a>搭配 Azure Machine Learning 設計師處理

Azure Machine Learning 設計師提供了視覺效果的畫布，您可以在其中拖放資料集和模組。 如果已經組態，您從設計師建立的批次處理管道就能整合到 Customer Insights。 

## <a name="working-with-azure-machine-learning-sdk"></a>搭配 Azure Machine Learning SDK 處理

資料科學家和 AI 開發人員使用 [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) 組建機器學習工作流程。 目前使用 SDK 訓練的模型無法直接與 Customer Insights 整合。 使用該模型的批次推論管道需要與 Customer Insights 整合。

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Customer Insights 整合的批次處理管道需求

### <a name="dataset-configuration"></a>資料集設定

建立資料集以從 Customer Insights 使用實體資料查找您的批次推斷管線。 將這些資料集在工作區註冊。 目前我們只支援.csv 格式的 [表格式資料集](/azure/machine-learning/how-to-create-register-datasets#tabulardataset)。 將符合實體資料的資料集參數化為管線參數。

- Designer 中的資料集參數

  在 Designer 程式中打開 **選取資料集的欄位**，然後選取 **設定為管道參數**，您即可提供參數名稱。

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Designer 中的資料集參數化。":::

- SDK 中的資料集參數 (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>批次處理推論管道
  
- 在設計工具中，使用訓練管線來建立或更新推斷管線。 目前只支援批次處理推論管道。

- 使用 SDK，將管線發佈到端點。 目前 Customer Insights 與機器學習工作區中，批次處理管道端點中的預設管道整合。

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>將管道資料匯入 Customer Insights

- Designer 程式提供 [匯出資料模組](/azure/machine-learning/algorithm-module-reference/export-data)，允許將管道輸出匯出到 Azure 儲存體。 目前模組必須使用資料儲存類型 **Azure Blob 儲存體** 並將 **資料儲存** 和相對 **路徑** 參數化。 管道執行資料儲存及產品可存取的路徑時，Customer Insights 會覆寫這兩個參數。

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="匯出資料模組組態。":::

- 使用代碼撰寫推斷輸出時，將輸出上傳到工作區中 *已註冊資料存放區* 內的路徑。 如果路徑和資料儲存在管道中參數化，Customer Insights 將可讀取和匯入推論輸出。 目前支援 csv 格式的單表格式輸出。 路徑必須包括目錄和檔案名稱。

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


[!INCLUDE [footer-include](includes/footer-banner.md)]