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
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="80820-103">使用 Azure Data Lake 帳戶連接至 Common Data Model 資料夾</span><span class="sxs-lookup"><span data-stu-id="80820-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="80820-104">本文章提供如何使用您的 Azure Data Lake Storage Gen2 帳戶從 Common Data Model 資料夾內嵌資料的資訊。</span><span class="sxs-lookup"><span data-stu-id="80820-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="80820-105">重要考量</span><span class="sxs-lookup"><span data-stu-id="80820-105">Important considerations</span></span>

- <span data-ttu-id="80820-106">您的 Azure Data Lake 中的資料必須遵循 Common Data Model 標準。</span><span class="sxs-lookup"><span data-stu-id="80820-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="80820-107">目前不支援其他格式。</span><span class="sxs-lookup"><span data-stu-id="80820-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="80820-108">資料內嵌獨家支援 Azure Data Lake *Gen2* 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="80820-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="80820-109">您無法使用 Azure Data Lake Gen1 儲存體帳戶內嵌資料。</span><span class="sxs-lookup"><span data-stu-id="80820-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="80820-110">若要以 Azure 服務主體驗證，請確定它已在您的租用戶中組態。</span><span class="sxs-lookup"><span data-stu-id="80820-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="80820-111">更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="80820-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="80820-112">您想要連接和內嵌資料的 Azure Data Lake 必須與 Dynamics 365 Customer Insights 環境位於相同的 Azure 區域中。</span><span class="sxs-lookup"><span data-stu-id="80820-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="80820-113">不支援從不同 Azure 區域的 Data Lake 連接到 Common Data Model 資料夾。</span><span class="sxs-lookup"><span data-stu-id="80820-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="80820-114">若要瞭解環境的 Azure 區域，請前往對象見解中的 **系統管理員** > **系統** > **關於**。</span><span class="sxs-lookup"><span data-stu-id="80820-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="80820-115">儲存在線上服務中的資料可能會儲存在有別於在 Dynamics 365 Customer Insights 處理或儲存的資料位置。</span><span class="sxs-lookup"><span data-stu-id="80820-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="80820-116">匯入或連接至儲存在線上服務的資料，即表示您同意可以將資料傳輸或儲存至 Dynamics 365 Customer Insights。 [在 Microsoft 信任中心深入了解。](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="80820-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="80820-117">連線至 Common Data Model 資料夾</span><span class="sxs-lookup"><span data-stu-id="80820-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="80820-118">在對象見解中，前往 **資料** > **資料來源**。</span><span class="sxs-lookup"><span data-stu-id="80820-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="80820-119">選取 **新增資料來源**。</span><span class="sxs-lookup"><span data-stu-id="80820-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="80820-120">選取 **連接到 Common Data Model 資料夾**，輸入資料來源 **名稱**，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="80820-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="80820-121">您可以在使用資源式選項和訂閱式選項之間選擇進行驗證。</span><span class="sxs-lookup"><span data-stu-id="80820-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="80820-122">更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="80820-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="80820-123">輸入 **容器** 資訊並選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="80820-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80820-124">![用於輸入 Azure Data Lake 的連接詳細資料的對話方塊](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="80820-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="80820-125">請在 **選取 Common Data Model 資料夾** 對話方塊中選取要匯入資料的 model.json 檔案，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="80820-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="80820-126">與環境中另一個資料來源有關聯的任何 model.json 檔案將不會顯示在清單中。</span><span class="sxs-lookup"><span data-stu-id="80820-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="80820-127">您將在選取的 model.json 檔案中取得可用實體清單。</span><span class="sxs-lookup"><span data-stu-id="80820-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="80820-128">您可以檢閱可用實體清單並從中選取實體，然後選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="80820-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="80820-129">所有選取的實體將從新資料來源內嵌。</span><span class="sxs-lookup"><span data-stu-id="80820-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80820-130">![顯示 model.json 檔案中的實體清單 對話方塊](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="80820-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="80820-131">指明您要啟用資料剖析功能的資料實體並選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="80820-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="80820-132">資料分析可啟用分析與其他功能。</span><span class="sxs-lookup"><span data-stu-id="80820-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="80820-133">您可以選取整個實體，這會選取實體的所有屬性或選取您選擇的特定屬性。</span><span class="sxs-lookup"><span data-stu-id="80820-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="80820-134">根據預設，沒有實體會啟用於資料剖析。</span><span class="sxs-lookup"><span data-stu-id="80820-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80820-135">![顯示資料剖析的對話方塊](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="80820-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="80820-136">儲存您的選取項目後，**資料來源** 頁面隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="80820-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="80820-137">現在應該會看到做為資料來源的 Common Data Model 資料夾連接。</span><span class="sxs-lookup"><span data-stu-id="80820-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="80820-138">model.json 檔案只能與同一個環境的一個資料來源建立關聯。</span><span class="sxs-lookup"><span data-stu-id="80820-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="80820-139">然而同一個 model.json 檔案可用於多重環境的資料來源。</span><span class="sxs-lookup"><span data-stu-id="80820-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="80820-140">編輯 Common Data Model 資料夾資料來源</span><span class="sxs-lookup"><span data-stu-id="80820-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="80820-141">您可以更新內含 Common Data Model 資料夾的儲存體帳戶存取金鑰。</span><span class="sxs-lookup"><span data-stu-id="80820-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="80820-142">您也可以變更 model.json 檔案。</span><span class="sxs-lookup"><span data-stu-id="80820-142">You may also change the model.json file.</span></span> <span data-ttu-id="80820-143">若要從儲存體帳戶連接至不同的容器，或變更帳戶名稱，請[建立新的資料來源連接](#connect-to-a-common-data-model-folder)。</span><span class="sxs-lookup"><span data-stu-id="80820-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="80820-144">在對象見解中，前往 **資料** > **資料來源**。</span><span class="sxs-lookup"><span data-stu-id="80820-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="80820-145">在您想要更新的資料來源旁邊，選取省略符號。</span><span class="sxs-lookup"><span data-stu-id="80820-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="80820-146">從清單中選取 **編輯** 選項。</span><span class="sxs-lookup"><span data-stu-id="80820-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="80820-147">或者，更新 **存取金鑰**，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="80820-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![用來編輯和更新現有資料來源存金鑰的對話方塊](media/edit-access-key.png)

5. <span data-ttu-id="80820-149">或者您可以從帳戶金鑰到資源式或訂閱式的連接進行更新。</span><span class="sxs-lookup"><span data-stu-id="80820-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="80820-150">更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="80820-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="80820-151">更新連接時，您無法變更 **容器** 資訊。</span><span class="sxs-lookup"><span data-stu-id="80820-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80820-152">![用於輸入 Azure Data Lake 的連接詳細資料的對話方塊](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="80820-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="80820-153">或者，從容器選擇包含一組不同實體的不同 model.json 檔案。</span><span class="sxs-lookup"><span data-stu-id="80820-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="80820-154">或者您可以選取要內嵌的附加實體。</span><span class="sxs-lookup"><span data-stu-id="80820-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="80820-155">如果沒有任何相依性，您也可以移除任何已選取的實體。</span><span class="sxs-lookup"><span data-stu-id="80820-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="80820-156">如果對現有 model.json 檔案和一組實體有相依性，您就會看到錯誤訊息，並且無法選取不同的 model.json 檔案。</span><span class="sxs-lookup"><span data-stu-id="80820-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="80820-157">先移除這些相依性再變更 model.json 檔案，或是使用您要用來避免移除相依性的 model.json 檔案建立新資料來源。</span><span class="sxs-lookup"><span data-stu-id="80820-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="80820-158">或者您可以選取附加屬性或實體，以啟用資料剖析或停用已經選取的資料剖析功能。</span><span class="sxs-lookup"><span data-stu-id="80820-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
