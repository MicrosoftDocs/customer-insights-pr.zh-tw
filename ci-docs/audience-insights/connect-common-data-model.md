---
title: 將常用資料模型資料連接到 Azure Data Lake 帳戶
description: 搭配使用 Azure Data Lake Storage 的 Common Data Model 資料處理。
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643448"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>使用 Azure Data Lake 帳戶連接至 Common Data Model 資料夾

本文章提供如何使用您的 Azure Data Lake Storage Gen2 帳戶從 Common Data Model 資料夾內嵌資料的資訊。

## <a name="important-considerations"></a>重要考量

- 您的 Azure Data Lake 中的資料必須遵循 Common Data Model 標準。 目前不支援其他格式。

- 資料內嵌獨家支援 Azure Data Lake *Gen2* 儲存體帳戶。 您無法使用 Azure Data Lake Gen1 儲存體帳戶內嵌資料。

- 若要以 Azure 服務主體驗證，請確定它已在您的租用戶中組態。 更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。

- 您想要連接和內嵌資料的 Azure Data Lake 必須與 Dynamics 365 Customer Insights 環境位於相同的 Azure 區域中。 不支援從不同 Azure 區域的 Data Lake 連接到 Common Data Model 資料夾。 若要瞭解環境的 Azure 區域，請前往對象見解中的 **系統管理員** > **系統** > **關於**。

- 儲存在線上服務中的資料可能會儲存在有別於在 Dynamics 365 Customer Insights 處理或儲存的資料位置。匯入或連接至儲存在線上服務的資料，即表示您同意可以將資料傳輸或儲存至 Dynamics 365 Customer Insights。 [在 Microsoft 信任中心深入了解。](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>連線至 Common Data Model 資料夾

1. 在對象見解中，前往 **資料** > **資料來源**。

1. 選取 **新增資料來源**。

1. 選取 **連接到 Common Data Model 資料夾**，輸入資料來源 **名稱**，然後選取 **下一步**。

1. 您可以在使用資源式選項和訂閱式選項之間選擇進行驗證。 更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。 輸入 **容器** 資訊並選取 **下一步**。
   > [!div class="mx-imgBorder"]
   > ![用於輸入 Azure Data Lake 的連接詳細資料的對話方塊](media/enter-new-storage-details.png)

1. 請在 **選取 Common Data Model 資料夾** 對話方塊中選取要匯入資料的 model.json 檔案，然後選取 **下一步**。
   > [!NOTE]
   > 與環境中另一個資料來源有關聯的任何 model.json 檔案將不會顯示在清單中。

1. 您將在選取的 model.json 檔案中取得可用實體清單。 您可以檢閱可用實體清單並從中選取實體，然後選取 **儲存**。 所有選取的實體將從新資料來源內嵌。
   > [!div class="mx-imgBorder"]
   > ![顯示 model.json 檔案中的實體清單 對話方塊](media/review-entities.png)

8. 指明您要啟用資料剖析功能的資料實體並選取 **儲存**。 資料分析可啟用分析與其他功能。 您可以選取整個實體，這會選取實體的所有屬性或選取您選擇的特定屬性。 根據預設，沒有實體會啟用於資料剖析。
   > [!div class="mx-imgBorder"]
   > ![顯示資料剖析的對話方塊](media/dataprofiling-entities.png)

9. 儲存您的選取項目後，**資料來源** 頁面隨即開啟。 現在應該會看到做為資料來源的 Common Data Model 資料夾連接。

> [!NOTE]
> model.json 檔案只能與同一個環境的一個資料來源建立關聯。 然而同一個 model.json 檔案可用於多重環境的資料來源。

## <a name="edit-a-common-data-model-folder-data-source"></a>編輯 Common Data Model 資料夾資料來源

您可以更新內含 Common Data Model 資料夾的儲存體帳戶存取金鑰。 您也可以變更 model.json 檔案。 若要從儲存體帳戶連接至不同的容器，或變更帳戶名稱，請[建立新的資料來源連接](#connect-to-a-common-data-model-folder)。

1. 在對象見解中，前往 **資料** > **資料來源**。

2. 在您想要更新的資料來源旁邊，選取省略符號。

3. 從清單中選取 **編輯** 選項。

4. 或者，更新 **存取金鑰**，然後選取 **下一步**。

   ![用來編輯和更新現有資料來源存金鑰的對話方塊](media/edit-access-key.png)

5. 或者您可以從帳戶金鑰到資源式或訂閱式的連接進行更新。 更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。 更新連接時，您無法變更 **容器** 資訊。
   > [!div class="mx-imgBorder"]
   > ![用於輸入 Azure Data Lake 的連接詳細資料的對話方塊](media/enter-existing-storage-details.png)

6. 或者，從容器選擇包含一組不同實體的不同 model.json 檔案。

7. 或者您可以選取要內嵌的附加實體。 如果沒有任何相依性，您也可以移除任何已選取的實體。

   > [!IMPORTANT]
   > 如果對現有 model.json 檔案和一組實體有相依性，您就會看到錯誤訊息，並且無法選取不同的 model.json 檔案。 先移除這些相依性再變更 model.json 檔案，或是使用您要用來避免移除相依性的 model.json 檔案建立新資料來源。

8. 或者您可以選取附加屬性或實體，以啟用資料剖析或停用已經選取的資料剖析功能。   
