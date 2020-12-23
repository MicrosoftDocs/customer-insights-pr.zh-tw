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
# <a name="custom-machine-learning-models"></a>自訂機器學習模型

**智慧** > **自訂模型** 讓您根據 Azure Machine Learning 模型管理工作流程。 工作流程協助您選擇要用來產生見解的資料，並將結果對應您的統一客戶資料。 如需組建自訂 ML 模型的詳細資訊，請見 [使用 Azure Machine Learning 模型](azure-machine-learning-experiments.md)。

## <a name="responsible-ai"></a>負責的 AI

預測提供各項功能建立更佳的客戶體驗、改善業務功能和營收資料流。 我們強烈建議您比對預測會有的影響後取出餘值，並以符合道德的方式偏移可能帶入的餘值。 進一步瞭解 Microsoft 如何 [定址負責的 AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6)。 您也可以瞭解 Azure Machine Learning 專門負責的機器學習 [技術與流程](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml)。

## <a name="prerequisites"></a>先決條件

- 目前此功能支援透過 [Machine Learning Studio (經典版)](https://studio.azureml.net) 和 [Azure Machine Learning 批次處理管道](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) 發佈的 web 服務。

- 您需要與您的 Azure Studio 執行個體產生關聯的 Azure Data Lake Gen2 儲存體帳戶使用此功能。 如需詳細資訊，請參閱[建立 Azure Data Lake Storage Gen2 儲存體帳戶](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>新增工作流程

1. 前往 **智慧** > **自訂模型** 並選取 **新增工作流程**。

1. 在 **名稱** 欄位中，為自訂模型提供可辨識的名稱。

   > [!div class="mx-imgBorder"]
   > ![新增工作流程窗格的螢幕擷取畫面](media/new-workflowv2.png "新增工作流程窗格的螢幕擷取畫面")

1. 在 **包含您的 Web 服務的用戶** 中，選取包含 Web 服務的組織。

1. 如果您的 Azure Machine Learning 訂閱與 Customer Insights 位於不同的用戶，請選取 **登入**，並針對所選組織使用您的認證登入。

1. 選取與您的 web 服務相關聯的 **工作區**。 目前列出兩區：適用 Azure Machine Learning v1 (Machine Learning Studio (經典版)) 和 Azure Machine Learning v2 (Azure Machine Learning)。 如果您不確定哪個工作區適用您的 Machine Learning Studio (經典版) web 服務，請選取 **任一個**。

1. 在 **包含您的模型的下拉式選單的 Web 服務** 中選擇 Machine Learning Studio (經典版) web 服務或 Azure Machine Learning 管道。 然後選取 **下一步**。
   - 瞭解更多有關 [Machine Learning Studio (經典版) 中發佈 Web 服務](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - 深入瞭解關於 [使用 Designer 程式](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) 或 [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 發佈 Azure Machine Learning 中的管道。 
     > [!NOTE]
     > 您的管道必須在 [管道端點](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) 下發佈。

1. 各 **Web 服務輸入** 方面，請從對象見解選取符合的 **實體** 並選取 **下一步**。

   > [!div class="mx-imgBorder"]
   > ![設定工作流程](media/intelligence-screen2-updated.png "設定工作流程")

1. 請在 **模型輸出參數** 步驟中設定下列屬性：
   - Machine Learning Studio (經典版)
      1. 輸入您想讓 Web 服務輸出結果流入的輸出 **實體名稱**。
   - Azure Machine Learning
      1. 輸入您想讓管道輸出結果流入的輸出 **實體名稱**。
      1. 請從下拉式選單選取您的批次處理管道的 **輸出資料存放區參數名稱**。
      1. 請從下拉式選單選取您的批次處理管道的 **輸出路徑參數名稱**。
      
      > [!div class="mx-imgBorder"]
      > ![模型輸出參數窗格](media/intelligence-screen3-outputparameters.png "模型輸出參數窗格")

1. 請從辨識客戶的 **結果下拉式選單中的客戶識別碼** 選取符合的屬性並選取 **儲存**。
   
   > [!div class="mx-imgBorder"]
   > ![客戶資料相關結果窗格](media/intelligence-screen4-relatetocustomer.png "客戶資料相關結果窗格")

1. 您會看到 **工作流程已儲存** 畫面，其中包含工作流程的詳細資料。    
   如果您已針對 Azure Machine Learning 管道組態工作流程，對象見解將附加到包含管道的工作區。 對象見解在 Azure 工作區取得 **參與者** 角色。

1. 選取 **完成**。

1. 您現在可以從 **自訂模型** 頁面執行工作流程。

## <a name="edit-a-workflow"></a>編輯工作流程

1. 在 **自訂模型** 頁面上，選取先前建立之工作流程旁邊 **動作** 欄中的垂直省略符號，然後選取 **編輯**。

1. 您可以在 **顯示名稱** 欄位中更新您的工作流程可識別名稱，但不能變更已組態的 Web 服務或管道。 選取 **下一步**。

1. 各 **Web 服務輸入** 方面，您可以從對象見解更新符合的 **實體**。 然後選取 **下一步**。

1. 請在 **模型輸出參數** 步驟中設定下列屬性：
   - Machine Learning Studio (經典版)
      1. 輸入您想讓 Web 服務輸出結果流入的輸出 **實體名稱**。
   - Azure Machine Learning
      1. 輸入您想讓管道輸出結果流入的輸出 **實體名稱**。
      1. 請針對您的測試管道選取 **輸出資料存放區參數名稱**。
      1. 請針對您的測試管道選取 **輸出路徑參數名稱**。

1. 請從辨識客戶的 **結果下拉式選單中的客戶識別碼** 選取符合的屬性並選取 **儲存**。
   您必須從類似客戶實體的客戶識別碼的推論輸出值選擇屬性。 如果您的資料集沒有此欄位，請選擇唯一識別該行的屬性。

## <a name="run-a-workflow"></a>執行工作流程

1. 在 **自訂模型** 頁面上，選取先前建立之工作流程旁邊 **動作** 欄中的垂直省略符號。

1. 選取 **執行**。

工作流程也會自動隨每個排定的重新整理一起執行。 進一步了解[設定排定的更新](system.md#schedule-tab)。

## <a name="delete-a-workflow"></a>刪除工作流程

1. 在 **自訂模型** 頁面上，選取先前建立之工作流程旁邊 **動作** 欄中的垂直省略符號。

1. 選取 **刪除**，並確認刪除。

將會刪除您的工作流程。 您建立工作流程時所建立的 [實體](entities.md)仍然存在，而且可以從 **實體** 頁面來檢視此實體。
