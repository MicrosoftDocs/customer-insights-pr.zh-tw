---
title: 自訂機器學習模型 | Microsoft Docs
description: 在 Dynamics 365 Customer Insights 中使用 Azure Machine Learning 的自訂模型。
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609732"
---
# <a name="custom-machine-learning-models"></a>自訂機器學習模型

> [!NOTE]
> Machine Learning Studio (傳統) 將於 2024 年 8 月 31 日停止支援。 我們建議您在該日期之前轉換到 [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning)。
>
> 從 2021 年 12 月 1 月開始，您將無法建立新的 Machine Learning Studio (傳統) 資源。 到 2024 年 8 月 31 日，您可以繼續使用現有的 Machine Learning Studio (傳統) 資源。 如需詳細資訊，請參閱[遷移至 Azure Machine Learning](/azure/machine-learning/migrate-overview)。

自訂模型讓您可以管理以 Azure Machine Learning 模型為基礎的工作流程。 工作流程協助您選擇要用來產生見解的資料，並將結果對應您的統一客戶資料。 如需組建自訂 ML 模型的詳細資訊，請見 [使用 Azure Machine Learning 模型](azure-machine-learning-experiments.md)。

## <a name="prerequisites"></a>先決條件

- 透過 [Azure Machine Learning 批次準銷售案源](/azure/machine-learning/concept-ml-pipelines)發行的 Web 服務 。
- 準銷售案源必須在[準銷售案源端點](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run)下發佈。
- 與您的 Azure Studio 執行個體有關的 [Azure Data Lake Gen2 儲存體帳戶](/azure/storage/blobs/data-lake-storage-quickstart-create-account)。
- 對於帶有準銷售案源的 Azure Machine Learning 工作區，負責人或使用者要存取系統管理員進入 Azure Machine Learning 工作區的權限。

  > [!NOTE]
  > 在您的 Customer Insights 執行個體與選取的 Azure web 服務或工作流程中的準銷售案源之間傳輸資料。 當您將資料轉移到 Azure 服務時，請確保將服務設為以必要的方式和位置處理資料，以符合組織中對此資料的任何法律或法規要求。

## <a name="add-a-new-workflow"></a>新增工作流程

1. 前往 **智慧** > **自訂模型** 並選取 **新增工作流程**。

1. 提供可識別的 **名稱**。

   :::image type="content" source="media/new-workflowv2.png" alt-text="新增工作流程窗格的螢幕擷取畫面。":::

1. 在 **包含您的 Web 服務的用戶** 中，選取包含 Web 服務的組織。

1. 如果您的 Azure Machine Learning 訂閱與 Customer Insights 位於不同的用戶，請選取 **登入**，並針對所選組織使用您的認證登入。

1. 選取與您的 web 服務相關聯的 **工作區**。

1. **在包含您的模型 Web 服務** 下拉式清單中，選擇 Azure Machine Learning 管道。 然後選取 **下一步**。
   深入瞭解關於 [使用 Designer 程式](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) 或 [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 發佈 Azure Machine Learning 中的管道。

1. 針對每個 **Web 服務輸入**，從 Customer Insights 選取相符的 **實體**。 然後選取 **下一步**。
   > [!NOTE]
   > 自訂模型工作流程將會套用啟發型方法，根據欄位的名稱和資料類型，將 web 服務輸入欄位對應至實體屬性。 如果 web 服務欄位無法對應至實體，則會出現錯誤。

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="設定工作流程。":::

1. 對於 **模型輸出參數** 步驟，請設定下列屬性：
   - 準銷售案源輸出結果的 **實體名稱**
   - 您的批次準銷售案源的 **輸出資料存放區參數名稱**
   - 您的批次準銷售案源的 **輸出路徑參數名稱**

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="模型輸出參數窗格。":::

1. 從 **結果中的客戶識別碼** 選取可以找出客戶的相符屬性，並選取 **儲存**。

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="客戶資料相關結果窗格。":::

   **工作流程已儲存** 畫面會顯示關於工作流程的詳細資料。 如果您為 Azure Machine Learning 管道設定工作流程，則 Customer Insights 會附加至包含該管道的工作區。 Customer Insights 將取得 Azure 工作區的 **參與者** 角色。

1. 選取 **完成**。 **自訂模型** 頁面隨即顯示。

1. 選取工作流程的垂直省略符號 (&vellip;)，然後選取 **執行**。 您的工作流程也會自動隨每個[排定的重新整理](schedule-refresh.md)一起執行。

## <a name="manage-an-existing-workflow"></a>管理現有的工作流程

移至 **智慧** > **自訂模型** 以查看您建立的工作流程。

選取工作流程以查看可用的動作。

- **編輯** 工作流程
- **執行** 工作流程
- [**刪除**](#delete-a-workflow)工作流程

### <a name="edit-a-workflow"></a>編輯工作流程

1. 移至 **智慧** > **自訂模型**。

1. 在您想要更新的工作流程旁邊，選取垂直省略符號 (&vellip;) 並選取 **編輯**。

1. 如有需要，請變更 **顯示名稱**，然後選取 **下一步**。

1. 視需求針對每個 **Web 服務輸入**，從 Customer Insights 更新相符的 **實體**。 然後選取 **下一步**。

1. 對於 **模型輸出參數**，請變更下列所有資訊：
   - 準銷售案源輸出結果的 **實體名稱**
   - 您的批次準銷售案源的 **輸出資料存放區參數名稱**
   - 您的批次準銷售案源的 **輸出路徑參數名稱**

1. 從 **結果中的客戶識別碼** 變更相符的屬性以找出客戶。 從推論輸出中選擇屬性，其值類似客戶實體的客戶識別碼資料欄。 如果您的資料集沒有此欄，請選擇唯一識別該列的屬性。

1. 選取 **儲存**

### <a name="delete-a-workflow"></a>刪除工作流程

1. 移至 **智慧** > **自訂模型**。

1. 在您想要刪除的工作流程旁邊，選取垂直省略符號 (&vellip;) 並選取 **刪除**。

1. 確認刪除。

將會刪除您的工作流程。 您建立工作流程時所建立的 [實體](entities.md)仍然存在，而且可以從 **資料** > **實體** 頁面查看。

## <a name="view-the-results"></a>查看結果

工作流程的結果會儲存在為 **模型輸出參數** 定義的實體名稱中。 從 [**資料** > **實體** 頁面](entities.md)或使用 [API 存取](apis.md)來存取此資料。

### <a name="api-access"></a>API 存取

若要讓特定 OData 查詢從自訂模型實體取得資料，請使用下列格式：

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. 以您的 Customer Insights 環境識別碼取代 `<your instance id>`，識別碼會在存取 Customer Insights 時顯示在您瀏覽器的網址列中。

1. 以您為 **模型輸出參數** 所提供的實體名稱取代 `<custom model output entity>`。

1. 以您想要存取之客戶的客戶識別碼取代 `<guid value>`。 此識別碼顯示在客戶識別碼欄位中的[客戶設定檔頁面](customer-profiles.md)。

## <a name="frequently-asked-questions"></a>常見問題

- 為何在設定自訂模型工作流程時看不到我的準銷售案源？
  發生此問題的原因通常是由於準銷售案源的設定有問題。 確定[輸入參數已設定](azure-machine-learning-experiments.md#dataset-configuration)，而且[輸出資料存儲和路徑參數](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights)也已設定完成。

- 錯誤「無法儲存智慧工作流程」是什麼意思？ 
  通常使用者看到此錯誤訊息，是當他沒有工作區的負責人或使用者存取權系統管理員權限。 使用者需要更高等級的權限，才能以作為服務的方式啟用 Customer Insights 來處理工作流程，而非以使用者認證進行工作流程的後續執行。

- 我的自訂模型工作流程的私人端點/私人連結是否受到支援？
  Customer Insights 目前不支援現成可用的自訂模型私人端點，但是可以手動解決。 請連絡支援團隊以了解詳細資訊。

## <a name="responsible-ai"></a>負責的 AI

預測提供各項功能建立更佳的客戶體驗、改善業務功能和營收資料流。 我們強烈建議您比對預測會有的影響後取出餘值，並以符合道德的方式偏移可能帶入的餘值。 進一步瞭解 Microsoft 如何 [定址負責的 AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6)。 您也可以瞭解 Azure Machine Learning 專門負責的機器學習 [技術與流程](/azure/machine-learning/concept-responsible-ml)。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
