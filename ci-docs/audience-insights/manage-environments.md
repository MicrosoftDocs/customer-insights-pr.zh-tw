---
title: 建立和管理環境
description: 瞭解如何註冊服務及管理環境。
ms.date: 03/26/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8cc1401251ed7c45c598bd4a8fb33a9709fabbc8
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887976"
---
# <a name="manage-environments"></a><span data-ttu-id="abdf1-103">管理環境</span><span class="sxs-lookup"><span data-stu-id="abdf1-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="abdf1-104">本文章解釋如何建立新組織及佈建環境。</span><span class="sxs-lookup"><span data-stu-id="abdf1-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="abdf1-105">註冊和建立組織</span><span class="sxs-lookup"><span data-stu-id="abdf1-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="abdf1-106">前往 [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) 網站。</span><span class="sxs-lookup"><span data-stu-id="abdf1-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="abdf1-107">選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="abdf1-108">選擇您偏好的註冊案例，並選取對應的連結。</span><span class="sxs-lookup"><span data-stu-id="abdf1-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="abdf1-109">接受條款及條件，然後選取 **繼續** 以開始建立組織。</span><span class="sxs-lookup"><span data-stu-id="abdf1-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="abdf1-110">建立環境之後，就會重新導向至 [Customer Insights](https://home.ci.ai.dynamics.com)。</span><span class="sxs-lookup"><span data-stu-id="abdf1-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="abdf1-111">使用示範環境來探索應用程式，或依照下一節中的步驟建立新環境。</span><span class="sxs-lookup"><span data-stu-id="abdf1-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="abdf1-112">指定環境設定之後，選取 **建立**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="abdf1-113">待環境建立成功後，您即可登入。</span><span class="sxs-lookup"><span data-stu-id="abdf1-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="abdf1-114">在現有的組織中建立環境</span><span class="sxs-lookup"><span data-stu-id="abdf1-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="abdf1-115">建立新環境的方式有兩種。</span><span class="sxs-lookup"><span data-stu-id="abdf1-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="abdf1-116">您可以指定全新的環境設定，也可以從現有環境複製一些組態設定。</span><span class="sxs-lookup"><span data-stu-id="abdf1-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="abdf1-117">每個 Customer Insights 授權，組織可以建立 *兩種* 環境。</span><span class="sxs-lookup"><span data-stu-id="abdf1-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="abdf1-118">如果您的組織購買授權超過一次，請[與我們的支援小組聯繫](https://go.microsoft.com/fwlink/?linkid=2079641)，增加可用環境的數目。</span><span class="sxs-lookup"><span data-stu-id="abdf1-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="abdf1-119">如需容量和附加容量的詳細資訊，請下載 [Dynamics 365 授權指南](https://go.microsoft.com/fwlink/?LinkId=866544)。</span><span class="sxs-lookup"><span data-stu-id="abdf1-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="abdf1-120">若要建立環境：</span><span class="sxs-lookup"><span data-stu-id="abdf1-120">To create an environment:</span></span>

1. <span data-ttu-id="abdf1-121">在應用程式的標頭中選取 **環境** 選取器。</span><span class="sxs-lookup"><span data-stu-id="abdf1-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="abdf1-122">選取 **新增**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="abdf1-123">![環境設定](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="abdf1-123">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="abdf1-124">在 **建立新環境** 對話方塊中，選取 **新增環境**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-124">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="abdf1-125">如果您想要 [從目前的環境複製資料](#considerations-for-copy-configuration-preview)，請選取 **從現有環境複製**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="abdf1-126">您會看到組織中所有可用環境的清單，您可以從此清單複製資料。</span><span class="sxs-lookup"><span data-stu-id="abdf1-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="abdf1-127">提供下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="abdf1-127">Provide the following details:</span></span>
   - <span data-ttu-id="abdf1-128">**名稱**：此環境的名稱。</span><span class="sxs-lookup"><span data-stu-id="abdf1-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="abdf1-129">如果您已複製現有環境，則欄位已填入資料，但是您可以變更此欄位。</span><span class="sxs-lookup"><span data-stu-id="abdf1-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="abdf1-130">**地區**：服務部署和託管所在的地區。</span><span class="sxs-lookup"><span data-stu-id="abdf1-130">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="abdf1-131">**類型**：選取要建立生產環境還是沙箱環境。</span><span class="sxs-lookup"><span data-stu-id="abdf1-131">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

1. <span data-ttu-id="abdf1-132">您可選擇性選取 **進階設定** 核取方塊：</span><span class="sxs-lookup"><span data-stu-id="abdf1-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="abdf1-133">**將所有資料儲存到**：指定要儲存 Customer Insights 所產生之輸出資料的位置。</span><span class="sxs-lookup"><span data-stu-id="abdf1-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="abdf1-134">您有兩個選項：**Customer Insights 儲存空間** (由 Customer Insights 團隊管理的 Azure Data Lake) 和 **Azure Data Lake Storage Gen2** (您自己的 Azure Data Lake Storage)。</span><span class="sxs-lookup"><span data-stu-id="abdf1-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="abdf1-135">預設會選取 [Customer Insights 儲存空間] 選項。</span><span class="sxs-lookup"><span data-stu-id="abdf1-135">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="abdf1-136">將資料儲存至 Azure Data Lake Storage，即表示您同意將資料傳送並儲存在相應的 Azure 儲存體帳戶的地理位置，這可能不同於將資料儲存在 Dynamics 365 Customer Insights 中的位置。</span><span class="sxs-lookup"><span data-stu-id="abdf1-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="abdf1-137">在 Microsoft 信任中心深入了解。</span><span class="sxs-lookup"><span data-stu-id="abdf1-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="abdf1-138">目前，已擷取的實體永遠都是儲存在 Customer Insights 管理的 Data Lake 中。</span><span class="sxs-lookup"><span data-stu-id="abdf1-138">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="abdf1-139">我們只在建立環境時從同一個 Azure 區域支援 Azure Data Lake Gen2 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="abdf1-139">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="abdf1-140">我們只支援 Azure Data Lake Gen2 階層命名空間 (HNS) 啟用的儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="abdf1-140">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="abdf1-141">Azure Data Lake Storage Gen2 選項方面，您可以在資源式選項和訂閱式選項之間選擇進行驗證。</span><span class="sxs-lookup"><span data-stu-id="abdf1-141">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="abdf1-142">更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="abdf1-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="abdf1-143">**容器** 名稱無法變更，將為 "customerinsights"。</span><span class="sxs-lookup"><span data-stu-id="abdf1-143">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="abdf1-144">如果您想要使用 [預測](predictions.md)、設定應用 Microsoft Dataverse 的應用程式和解決方案的資料共用，或者從內部部署資料來源中進行資料擷取，請在 **設定與 Microsoft Dataverse 共用資料並啟用其他功能** 下，提供 Microsoft Dataverse 環境 URL。</span><span class="sxs-lookup"><span data-stu-id="abdf1-144">If you want to use [predictions](predictions.md), configure data sharing with applications and solutions based on Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="abdf1-145">選取 **啟用資料共用** 與 Microsoft Dataverse Managed Data Lake 共用 Customer Insights 輸出資料。</span><span class="sxs-lookup"><span data-stu-id="abdf1-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="abdf1-146">當您將所有資料儲存到自己的 Azure Data Lake Storage ，目前不支援共用資料給 Microsoft Dataverse Managed Data Lake。</span><span class="sxs-lookup"><span data-stu-id="abdf1-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="abdf1-147">當您啟用資料共用給 Microsoft Dataverse Managed Data Lake 時，目前不支援[實體中遺失值的預測](predictions.md)。</span><span class="sxs-lookup"><span data-stu-id="abdf1-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="abdf1-148">![啟用與 Microsoft Dataverse 共用資料的組態選項](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="abdf1-148">![Configuration options to enable data sharing with Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="abdf1-149">當您執行流程如資料內嵌或區段建立時，對應資料夾會在您上述指定的儲存體帳戶中建立。</span><span class="sxs-lookup"><span data-stu-id="abdf1-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="abdf1-150">資料檔案和 model.json 檔案會根據您執行的程序，建立並新增至各自的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="abdf1-150">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="abdf1-151">如果您建立多個 Customer Insights 環境並選擇從您的儲存體帳戶環境中儲存輸出實體，各資料夾將針對容器含有 ci_<environmentid> 每個環境分開建立。</span><span class="sxs-lookup"><span data-stu-id="abdf1-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="abdf1-152">複製設定的考量 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="abdf1-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="abdf1-153">下列組態設定已複製，</span><span class="sxs-lookup"><span data-stu-id="abdf1-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="abdf1-154">功能設定</span><span class="sxs-lookup"><span data-stu-id="abdf1-154">Feature configurations</span></span>
- <span data-ttu-id="abdf1-155">內嵌/匯入的資料來源</span><span class="sxs-lookup"><span data-stu-id="abdf1-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="abdf1-156">資料統一 (對應、比對、合併) 設定</span><span class="sxs-lookup"><span data-stu-id="abdf1-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="abdf1-157">客戶細分</span><span class="sxs-lookup"><span data-stu-id="abdf1-157">Segments</span></span>
- <span data-ttu-id="abdf1-158">量值</span><span class="sxs-lookup"><span data-stu-id="abdf1-158">Measures</span></span>
- <span data-ttu-id="abdf1-159">關聯</span><span class="sxs-lookup"><span data-stu-id="abdf1-159">Relationships</span></span>
- <span data-ttu-id="abdf1-160">活動</span><span class="sxs-lookup"><span data-stu-id="abdf1-160">Activities</span></span>
- <span data-ttu-id="abdf1-161">搜尋和篩選索引</span><span class="sxs-lookup"><span data-stu-id="abdf1-161">Search & filter Index</span></span>
- <span data-ttu-id="abdf1-162">匯出目的地</span><span class="sxs-lookup"><span data-stu-id="abdf1-162">Export destinations</span></span>
- <span data-ttu-id="abdf1-163">已排程的重新整理</span><span class="sxs-lookup"><span data-stu-id="abdf1-163">Scheduled refresh</span></span>
- <span data-ttu-id="abdf1-164">擴充內容</span><span class="sxs-lookup"><span data-stu-id="abdf1-164">Enrichments</span></span>
- <span data-ttu-id="abdf1-165">模型管理</span><span class="sxs-lookup"><span data-stu-id="abdf1-165">Model management</span></span>
- <span data-ttu-id="abdf1-166">角色指派</span><span class="sxs-lookup"><span data-stu-id="abdf1-166">Role assignments</span></span>

<span data-ttu-id="abdf1-167">下列設定 *未* 複製：</span><span class="sxs-lookup"><span data-stu-id="abdf1-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="abdf1-168">客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="abdf1-168">Customer profiles.</span></span>
- <span data-ttu-id="abdf1-169">資料來源認證。</span><span class="sxs-lookup"><span data-stu-id="abdf1-169">Data source credentials.</span></span> <span data-ttu-id="abdf1-170">您必須提供每個資料來源的認證，並手動重新整理資料來源。</span><span class="sxs-lookup"><span data-stu-id="abdf1-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="abdf1-171">Common Data Model 資料夾和 Common Data Service 受管理資料湖的資料來源。</span><span class="sxs-lookup"><span data-stu-id="abdf1-171">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="abdf1-172">您必須使用與來源環境相同的名稱，手動建立這些資料來源。</span><span class="sxs-lookup"><span data-stu-id="abdf1-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="abdf1-173">複製環境時，您會看到一則指示已建立新環境的確認訊息。</span><span class="sxs-lookup"><span data-stu-id="abdf1-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="abdf1-174">選取 **移至資料來源** 以查看資料來源清單。</span><span class="sxs-lookup"><span data-stu-id="abdf1-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="abdf1-175">所有的資料來源都會顯示 **需要認證** 狀態。</span><span class="sxs-lookup"><span data-stu-id="abdf1-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="abdf1-176">編輯資料來源，並輸入認證以進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="abdf1-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="abdf1-177">![資料來源已複製](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="abdf1-177">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="abdf1-178">重新整理資料來源之後，移至 **資料** > **統一**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="abdf1-179">您會在此處找到來源環境的設定。</span><span class="sxs-lookup"><span data-stu-id="abdf1-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="abdf1-180">視需要編輯，或選取 **執行** 以開始進行資料統一處理程序，並建立統一的客戶實體。</span><span class="sxs-lookup"><span data-stu-id="abdf1-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="abdf1-181">資料統一完成時，移至 **測量** 和 **分段** 進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="abdf1-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="abdf1-182">編輯現有環境</span><span class="sxs-lookup"><span data-stu-id="abdf1-182">Edit an existing environment</span></span>

<span data-ttu-id="abdf1-183">您可以編輯現有環境的部分詳細資料。</span><span class="sxs-lookup"><span data-stu-id="abdf1-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="abdf1-184">在應用程式的標頭中選取 **環境** 選取器。</span><span class="sxs-lookup"><span data-stu-id="abdf1-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="abdf1-185">選取 **編輯** 圖示。</span><span class="sxs-lookup"><span data-stu-id="abdf1-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="abdf1-186">在 **編輯環境** 方塊中，您可以更新環境的 **顯示名稱**，但是不可以變更 **區域** 或 **類型**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="abdf1-187">如果環境設定為在 Azure Data Lake Storage Gen2 中儲存資料，您可以更新 **帳戶金鑰**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-187">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="abdf1-188">不過，您無法變更 **帳戶名稱** 或 **容器** 名稱。</span><span class="sxs-lookup"><span data-stu-id="abdf1-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="abdf1-189">或者您可以從帳戶金鑰式連接到資源式或訂閱式連接更新。</span><span class="sxs-lookup"><span data-stu-id="abdf1-189">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="abdf1-190">一旦升級，您就無法在更新後恢復到帳戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="abdf1-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="abdf1-191">更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="abdf1-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="abdf1-192">更新連接時，您無法變更 **容器** 資訊。</span><span class="sxs-lookup"><span data-stu-id="abdf1-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="abdf1-193">或者，您可以在 **設定與 Microsoft Dataverse 共用資料並啟用其他功能** 下，提供 Microsoft Dataverse 環境 URL。</span><span class="sxs-lookup"><span data-stu-id="abdf1-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="abdf1-194">這些功能包含運用 Microsoft Dataverse 與應用程式和解決方案共用資料、從內部部署資料來源擷取資料、或使用[預測](predictions.md)。</span><span class="sxs-lookup"><span data-stu-id="abdf1-194">These capabilities inlcude data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="abdf1-195">選取 **啟用資料共用** 與 Microsoft Dataverse Managed Data Lake 共用 Customer Insights 輸出資料。</span><span class="sxs-lookup"><span data-stu-id="abdf1-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="abdf1-196">當您將所有資料儲存到自己的 Azure Data Lake Storage ，目前不支援共用資料給 Microsoft Dataverse Managed Data Lake。</span><span class="sxs-lookup"><span data-stu-id="abdf1-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="abdf1-197">當您以 Microsoft Dataverse Managed Data Lake 啟用資料共用時，目前不支援[預測實體中缺少的值](predictions.md)。</span><span class="sxs-lookup"><span data-stu-id="abdf1-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="abdf1-198">當您啟用與 Microsoft Dataverse 的資料共用，將對資料來源和其他程序觸發一次完整的重新整理。</span><span class="sxs-lookup"><span data-stu-id="abdf1-198">Once you enable data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes will be triggered.</span></span> <span data-ttu-id="abdf1-199">如果程序目前正在執行並排入佇列，您將看不到用來啟用與 Microsoft Dataverse 共用資料的選項。</span><span class="sxs-lookup"><span data-stu-id="abdf1-199">If processes are currently running and queued, you will not see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="abdf1-200">您可以等待這些程序完成，或者取消它們以啟用資料共用。</span><span class="sxs-lookup"><span data-stu-id="abdf1-200">You can wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="啟用與 Microsoft Dataverse 共用資料的設定選項。":::
   
   <span data-ttu-id="abdf1-202">當您執行流程如資料內嵌或區段建立時，對應資料夾會在您上述指定的儲存體帳戶中建立。</span><span class="sxs-lookup"><span data-stu-id="abdf1-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="abdf1-203">根據您執行的程序，會建立資料檔案和 model.json 並新增至各自的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="abdf1-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="abdf1-204">重設現有環境中</span><span class="sxs-lookup"><span data-stu-id="abdf1-204">Reset an existing environment</span></span>

<span data-ttu-id="abdf1-205">作為管理員，如果您要刪除所有組態並移除內嵌的資料，您可以將環境重設為空白狀態。</span><span class="sxs-lookup"><span data-stu-id="abdf1-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="abdf1-206">在應用程式的標頭中選取 **環境** 選取器。</span><span class="sxs-lookup"><span data-stu-id="abdf1-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="abdf1-207">選取您要重設的環境，並選取省略號 **...**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-207">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="abdf1-208">選擇 **重設** 選項。</span><span class="sxs-lookup"><span data-stu-id="abdf1-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="abdf1-209">若要確認刪除，請輸入環境名稱並選取 **重設**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="abdf1-210">刪除現有的環境 (只有系統管理員可以使用)</span><span class="sxs-lookup"><span data-stu-id="abdf1-210">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="abdf1-211">作為管理員，您可以刪除您所管理的環境。</span><span class="sxs-lookup"><span data-stu-id="abdf1-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="abdf1-212">在應用程式的標頭中選取 **環境** 選取器。</span><span class="sxs-lookup"><span data-stu-id="abdf1-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="abdf1-213">選取您要重設的環境，並選取省略號 **...**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-213">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="abdf1-214">選擇 **刪除** 選項。</span><span class="sxs-lookup"><span data-stu-id="abdf1-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="abdf1-215">若要確認刪除，請輸入環境名稱，然後選取 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="abdf1-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
