---
title: 將常用資料模型資料連接到 Azure Data Lake 帳戶
description: 搭配使用 Azure Data Lake Storage 的 Common Data Model 資料處理。
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833346"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>使用 Azure Data Lake 帳戶連接至 Common Data Model 資料夾

本文說明如何使用 Dynamics 365 Customer Insights Gen2 帳戶從 Common Data Model 資料夾中將資料內嵌至 Azure Data Lake Storage。

## <a name="important-considerations"></a>重要考量

- 您的 Azure Data Lake 中的資料必須遵循 Common Data Model 標準。 目前不支援其他格式。

- 資料內嵌獨家支援 Azure Data Lake *Gen2* 儲存體帳戶。 您無法使用 Azure Data Lake Gen1 儲存體帳戶內嵌資料。

- Azure Data Lake storage 帳戶必須已 [啟用階層命名空間功能](/azure/storage/blobs/data-lake-storage-namespace)。

- 若要以 Azure 服務主體驗證，請確定它已在您的租用戶中設定完成。 如需更多資訊，請參閱[使用 Azure 服務主體連接 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。

- 您想要連接和內嵌資料的 Azure Data Lake 必須與 Dynamics 365 Customer Insights 環境位於相同的 Azure 區域中。 不支援從不同 Azure 區域的 Data Lake 連接到 Common Data Model 資料夾。 若要知道環境的 Azure 區域，在 Customer Insights 請前往 **系統管理員** > **系統** > **關於**。

- 儲存在線上服務中的資料可能會儲存在跟 Dynamics 365 Customer Insights 處理或儲存資料不同的位置。 匯入或連接至儲存在線上服務的資料，即表示您同意可以將資料傳輸或儲存至 Dynamics 365 Customer Insights。 [在 Microsoft 信任中心深入了解](https://www.microsoft.com/trust-center)。

## <a name="connect-to-a-common-data-model-folder"></a>連線至 Common Data Model 資料夾

1. 移至 **資料** > **資料來源**。

1. 選取 **新增資料來源**。

1. 選取 **Azure Data Lake Storage**，輸入資料來源的 **名稱**，然後選取 **下一步**。

   - 如果出現提示，請選取一個與您的產業相關的範例資料集，然後選取 **下一步**。

1. 您可以在使用資源式選項和訂閱式選項之間選擇進行驗證。 如需更多資訊，請參閱[使用 Azure 服務主體連接 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。 輸入 **伺服器位址**，選取 **登入**，然後選取 **下一步**。
   > [!div class="mx-imgBorder"]
   > ![在 Azure Data Lake 輸入新連接詳細資料的對話方塊。](media/enter-new-storage-details.png)
   > [!NOTE]
   > 您需要容器或儲存體帳戶上的下列其中一個角色，並建立資料來源：
   >
   >  - [儲存體 Blob 資料讀者] 足以讀取儲存體帳戶，並將資料內嵌至 Customer Insights。 
   >  - 如果您想要直接在 Customer Insights 中編輯資訊清單檔案，則需要 [儲存體 Blob 資料參與者] 或 [儲存體 Blob 資料負責人]。

1. 請在 **選取 Common Data Model 資料夾** 對話方塊中選取要從中匯出資料的 model.json 或 manifest.json 檔案，然後選取 **下一步**。
   > [!NOTE]
   > 所有關聯到環境中另一個資料來源的 model.json 或 manifest.json 檔案將不會顯示在清單中。

1. 您將會在選定的 model.json 或 manifest.json 檔案中看到可用實體的清單。 檢閱並從用實體清單中選取，然後選取 **儲存**。 所有選取的實體將從新資料來源內嵌。
   > [!div class="mx-imgBorder"]
   > ![顯示 model.json 檔案中實體清單的對話方塊。](media/review-entities.png)

1. 指示您想啟用資料分析的資料實體，接著選取 **儲存**。 資料分析可啟用分析與其他功能。 您可以選取整個實體，這會選取實體的所有屬性或選取您選擇的特定屬性。 根據預設，沒有實體會啟用於資料剖析。
   > [!div class="mx-imgBorder"]
   > ![顯示資料剖析的對話方塊。](media/dataprofiling-entities.png)

1. 儲存您的選取項目後，**資料來源** 頁面隨即開啟。 現在應該會看到做為資料來源的 Common Data Model 資料夾連接。

> [!NOTE]
> model.json 或 manifest.json 檔案在同一個環境中只能與單一資料來源建立關聯。 然而同一個 model.json 或 manifest.json 檔案可在多個環境中用在資料來源。

## <a name="edit-a-common-data-model-folder-data-source"></a>編輯 Common Data Model 資料夾資料來源

您可以更新內含 Common Data Model 資料夾的儲存體帳戶存取金鑰。 您也可以變更 model.json 或 manifest.json 檔案。 若要從儲存體帳戶連接至不同的容器，或變更帳戶名稱，請[建立新的資料來源連接](#connect-to-a-common-data-model-folder)。

1. 移至 **資料** > **資料來源**。

2. 在您想要更新的資料來源旁邊，選取垂直省略符號 (&vellip;)。

3. 從清單中選取 **編輯** 選項。

4. 或者，更新 **存取金鑰**，然後選取 **下一步**。

   ![編輯和更新現有資料來源的存取金鑰的對話方塊。](media/edit-access-key.png)

5. 或者您可以從帳戶金鑰到資源式或訂閱式的連接進行更新。 如需更多資訊，請參閱[使用 Azure 服務主體連接 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。 更新連接時，您無法變更 **容器** 資訊。
   > [!div class="mx-imgBorder"]

   > ![輸入 Azure Data Lake 連結詳細資料到現有的儲存體帳戶的對話方塊。](media/enter-existing-storage-details.png)

6. 或者，選擇不同的 model.json 或 manifest.json 檔案，搭配容器中不同的實體集合。

7. 或者您可以選取要內嵌的附加實體。 如果沒有任何相依性，您也可以移除任何已選取的實體。

   > [!IMPORTANT]
   > 如果現有的 model.json 或 manifest.json file檔案對實體集合有相依性，您將會看到錯誤訊息，且無法選取不同的 model.json 或 manifest.json 檔案。 在變更 model.json 或 manifest.json 檔案之前移除這些相依性，或以您要使用的 model.json 或 manifest.json 檔案建立新的資料來源來避免移除相依性。

8. 或者您可以選取附加屬性或實體，以啟用資料剖析或停用已經選取的資料剖析功能。

[!INCLUDE [footer-include](includes/footer-banner.md)]
