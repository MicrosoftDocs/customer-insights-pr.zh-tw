---
title: 將常用資料模型資料連接到 Azure Data Lake 帳戶
description: 搭配使用 Azure Data Lake Storage 的 Common Data Model 資料處理。
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267850"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="8eb93-103">使用 Azure Data Lake 帳戶連接至 Common Data Model 資料夾</span><span class="sxs-lookup"><span data-stu-id="8eb93-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="8eb93-104">本文章提供如何使用您的 Azure Data Lake Storage Gen2 帳戶從 Common Data Model 資料夾內嵌資料的資訊。</span><span class="sxs-lookup"><span data-stu-id="8eb93-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="8eb93-105">重要考量</span><span class="sxs-lookup"><span data-stu-id="8eb93-105">Important considerations</span></span>

- <span data-ttu-id="8eb93-106">您的 Azure Data Lake 中的資料必須遵循 Common Data Model 標準。</span><span class="sxs-lookup"><span data-stu-id="8eb93-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="8eb93-107">目前不支援其他格式。</span><span class="sxs-lookup"><span data-stu-id="8eb93-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="8eb93-108">資料內嵌獨家支援 Azure Data Lake *Gen2* 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="8eb93-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="8eb93-109">您無法使用 Azure Data Lake Gen1 儲存體帳戶內嵌資料。</span><span class="sxs-lookup"><span data-stu-id="8eb93-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="8eb93-110">若要以 Azure 服務主體驗證，請確定它已在您的租用戶中組態。</span><span class="sxs-lookup"><span data-stu-id="8eb93-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="8eb93-111">更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb93-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="8eb93-112">您想要連接和內嵌資料的 Azure Data Lake 必須與 Dynamics 365 Customer Insights 環境位於相同的 Azure 區域中。</span><span class="sxs-lookup"><span data-stu-id="8eb93-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="8eb93-113">不支援從不同 Azure 區域的 Data Lake 連接到 Common Data Model 資料夾。</span><span class="sxs-lookup"><span data-stu-id="8eb93-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="8eb93-114">若要瞭解環境的 Azure 區域，請前往對象見解中的 **系統管理員** > **系統** > **關於**。</span><span class="sxs-lookup"><span data-stu-id="8eb93-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="8eb93-115">儲存在線上服務中的資料可能會儲存在有別於在 Dynamics 365 Customer Insights 處理或儲存的資料位置。</span><span class="sxs-lookup"><span data-stu-id="8eb93-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="8eb93-116">匯入或連接至儲存在線上服務的資料，即表示您同意可以將資料傳輸或儲存至 Dynamics 365 Customer Insights。 [在 Microsoft 信任中心深入了解。](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="8eb93-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="8eb93-117">連線至 Common Data Model 資料夾</span><span class="sxs-lookup"><span data-stu-id="8eb93-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="8eb93-118">在對象見解中，前往 **資料** > **資料來源**。</span><span class="sxs-lookup"><span data-stu-id="8eb93-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="8eb93-119">選取 **新增資料來源**。</span><span class="sxs-lookup"><span data-stu-id="8eb93-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="8eb93-120">選取 **連接到 Common Data Model 資料夾**，輸入資料來源 **名稱**，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="8eb93-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="8eb93-121">命名方針：</span><span class="sxs-lookup"><span data-stu-id="8eb93-121">Name guidelines:</span></span> 
   - <span data-ttu-id="8eb93-122">名稱必須以字母開頭。</span><span class="sxs-lookup"><span data-stu-id="8eb93-122">Start with a letter.</span></span>
   - <span data-ttu-id="8eb93-123">只能使用字母和數字。</span><span class="sxs-lookup"><span data-stu-id="8eb93-123">Use letters and numbers only.</span></span> <span data-ttu-id="8eb93-124">不可以使用空格和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="8eb93-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="8eb93-125">接受 3 到 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="8eb93-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="8eb93-126">您可以在使用資源式選項和訂閱式選項之間選擇進行驗證。</span><span class="sxs-lookup"><span data-stu-id="8eb93-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="8eb93-127">更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb93-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="8eb93-128">輸入 **容器** 資訊並選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="8eb93-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8eb93-129">![在 Azure Data Lake 輸入新連接詳細資料的對話方塊](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="8eb93-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="8eb93-130">要對上述的容器或儲存體帳戶連接並建立資料來源，您必須擁有下列其中一種角色：</span><span class="sxs-lookup"><span data-stu-id="8eb93-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="8eb93-131">儲存體 Blob 資料讀者</span><span class="sxs-lookup"><span data-stu-id="8eb93-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="8eb93-132">儲存體 Blob 負責人</span><span class="sxs-lookup"><span data-stu-id="8eb93-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="8eb93-133">儲存體 Blob 資料參與者</span><span class="sxs-lookup"><span data-stu-id="8eb93-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="8eb93-134">請在 **選取 Common Data Model 資料夾** 對話方塊中選取要從中匯出資料的 model.json 或 manifest.json 檔案，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="8eb93-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="8eb93-135">所有關聯到環境中另一個資料來源的 model.json 或 manifest.json 檔案將不會顯示在清單中。</span><span class="sxs-lookup"><span data-stu-id="8eb93-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="8eb93-136">您可以在選取的 model.json 或 manifest.json f檔案中取得可用實體清單。</span><span class="sxs-lookup"><span data-stu-id="8eb93-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="8eb93-137">您可以檢閱可用實體清單並從中選取實體，然後選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="8eb93-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="8eb93-138">所有選取的實體將從新資料來源內嵌。</span><span class="sxs-lookup"><span data-stu-id="8eb93-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8eb93-139">![顯示 model.json 檔案中的實體清單 對話方塊](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="8eb93-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="8eb93-140">指明您要啟用資料剖析功能的資料實體並選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="8eb93-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="8eb93-141">資料分析可啟用分析與其他功能。</span><span class="sxs-lookup"><span data-stu-id="8eb93-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="8eb93-142">您可以選取整個實體，這會選取實體的所有屬性或選取您選擇的特定屬性。</span><span class="sxs-lookup"><span data-stu-id="8eb93-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="8eb93-143">根據預設，沒有實體會啟用於資料剖析。</span><span class="sxs-lookup"><span data-stu-id="8eb93-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8eb93-144">![顯示資料剖析的對話方塊](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="8eb93-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="8eb93-145">儲存您的選取項目後，**資料來源** 頁面隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="8eb93-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="8eb93-146">現在應該會看到做為資料來源的 Common Data Model 資料夾連接。</span><span class="sxs-lookup"><span data-stu-id="8eb93-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="8eb93-147">model.json 或 manifest.json 檔案在同一個環境中只能與單一資料來源建立關聯。</span><span class="sxs-lookup"><span data-stu-id="8eb93-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="8eb93-148">然而同一個 model.json 或 manifest.json 檔案可在多個環境中用在資料來源。</span><span class="sxs-lookup"><span data-stu-id="8eb93-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="8eb93-149">編輯 Common Data Model 資料夾資料來源</span><span class="sxs-lookup"><span data-stu-id="8eb93-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="8eb93-150">您可以更新內含 Common Data Model 資料夾的儲存體帳戶存取金鑰。</span><span class="sxs-lookup"><span data-stu-id="8eb93-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="8eb93-151">您也可以變更 model.json 或 manifest.json 檔案。</span><span class="sxs-lookup"><span data-stu-id="8eb93-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="8eb93-152">若要從儲存體帳戶連接至不同的容器，或變更帳戶名稱，請[建立新的資料來源連接](#connect-to-a-common-data-model-folder)。</span><span class="sxs-lookup"><span data-stu-id="8eb93-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="8eb93-153">在對象見解中，前往 **資料** > **資料來源**。</span><span class="sxs-lookup"><span data-stu-id="8eb93-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8eb93-154">在您想要更新的資料來源旁邊，選取省略符號。</span><span class="sxs-lookup"><span data-stu-id="8eb93-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="8eb93-155">從清單中選取 **編輯** 選項。</span><span class="sxs-lookup"><span data-stu-id="8eb93-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="8eb93-156">或者，更新 **存取金鑰**，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="8eb93-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![用來編輯和更新現有資料來源存金鑰的對話方塊](media/edit-access-key.png)

5. <span data-ttu-id="8eb93-158">或者您可以從帳戶金鑰到資源式或訂閱式的連接進行更新。</span><span class="sxs-lookup"><span data-stu-id="8eb93-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="8eb93-159">更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb93-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="8eb93-160">更新連接時，您無法變更 **容器** 資訊。</span><span class="sxs-lookup"><span data-stu-id="8eb93-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![在 Azure Data Lake 輸入連結詳細資料至現有的儲存體帳戶的對話方塊](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="8eb93-162">要對上述的容器或儲存體帳戶連接並建立資料來源，您必須擁有下列其中一種角色：</span><span class="sxs-lookup"><span data-stu-id="8eb93-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="8eb93-163">儲存體 Blob 資料讀者</span><span class="sxs-lookup"><span data-stu-id="8eb93-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="8eb93-164">儲存體 Blob 負責人</span><span class="sxs-lookup"><span data-stu-id="8eb93-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="8eb93-165">儲存體 Blob 資料參與者</span><span class="sxs-lookup"><span data-stu-id="8eb93-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="8eb93-166">或者，選擇不同的 model.json 或 manifest.json 檔案，搭配容器中不同的實體集合。</span><span class="sxs-lookup"><span data-stu-id="8eb93-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="8eb93-167">或者您可以選取要內嵌的附加實體。</span><span class="sxs-lookup"><span data-stu-id="8eb93-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="8eb93-168">如果沒有任何相依性，您也可以移除任何已選取的實體。</span><span class="sxs-lookup"><span data-stu-id="8eb93-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="8eb93-169">如果現有的 model.json 或 manifest.json file檔案對實體集合有相依性，您將會看到錯誤訊息，且無法選取不同的 model.json 或 manifest.json 檔案。</span><span class="sxs-lookup"><span data-stu-id="8eb93-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="8eb93-170">在變更 model.json 或 manifest.json 檔案之前移除這些相依性，或以您要使用的 model.json 或 manifest.json 檔案建立新的資料來源來避免移除相依性。</span><span class="sxs-lookup"><span data-stu-id="8eb93-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="8eb93-171">或者您可以選取附加屬性或實體，以啟用資料剖析或停用已經選取的資料剖析功能。</span><span class="sxs-lookup"><span data-stu-id="8eb93-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]