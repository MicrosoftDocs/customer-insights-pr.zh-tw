---
title: 使用服務主體連接到 Azure Data Lake Storage Gen2 帳戶
description: 當附加到對象見解時，請使用適用對象見解的 Azure 服務主體連接您自己的 Data Lake。
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644078"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="04dce-103">使用適用對象見解的 Azure 服務主體連接到 Azure Data Lake Storage Gen2 帳戶</span><span class="sxs-lookup"><span data-stu-id="04dce-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="04dce-104">使用 Azure 服務的自動化工具應始終具有限縮權限。</span><span class="sxs-lookup"><span data-stu-id="04dce-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="04dce-105">有別於以完整權限使用者身分登入應用程式的作法，Azure 提供服務主體。</span><span class="sxs-lookup"><span data-stu-id="04dce-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="04dce-106">請閱讀以便瞭解如何以使用 Azure 服務主體的 Azure Data Lake Storage Gen2 帳戶而不是儲存體帳戶金鑰連接對象見解。</span><span class="sxs-lookup"><span data-stu-id="04dce-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="04dce-107">您可以使用服務主體安全地將 [Common Data Model 資料夾新增或編輯為資料來源](connect-common-data-model.md) 或 [建立全新或更新現有的環境](manage-environments.md#create-an-environment-in-an-existing-organization)。</span><span class="sxs-lookup"><span data-stu-id="04dce-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="04dce-108">您需要適用您的 Azure 訂閱的系統管理員權限建立服務主體。</span><span class="sxs-lookup"><span data-stu-id="04dce-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="04dce-109">建立適用對象見解的 Azure 服務主體</span><span class="sxs-lookup"><span data-stu-id="04dce-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="04dce-110">在為對象見解建立全新服務主體之前，請先檢查它是否已存在於貴組織。</span><span class="sxs-lookup"><span data-stu-id="04dce-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="04dce-111">尋找現有的服務主體</span><span class="sxs-lookup"><span data-stu-id="04dce-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="04dce-112">請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入貴組織。</span><span class="sxs-lookup"><span data-stu-id="04dce-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="04dce-113">從 Azure 服務選取 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="04dce-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="04dce-114">請在 **管理** 下方選取 **企業應用程式**。</span><span class="sxs-lookup"><span data-stu-id="04dce-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="04dce-115">搜尋對象見解第一個合作對象的應用程式 ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` 或名稱 `Dynamics 365 AI for Customer Insights`。</span><span class="sxs-lookup"><span data-stu-id="04dce-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="04dce-116">如果您發現符合的記錄，代表適用對象見解的服務主體確實存在。</span><span class="sxs-lookup"><span data-stu-id="04dce-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="04dce-117">您不需要再建立一次。</span><span class="sxs-lookup"><span data-stu-id="04dce-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="螢幕擷取畫面顯示現有服務主體。":::
   
6. <span data-ttu-id="04dce-119">如果未傳回任何結果，請建立全新服務主體。</span><span class="sxs-lookup"><span data-stu-id="04dce-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="04dce-120">建立全新服務主體</span><span class="sxs-lookup"><span data-stu-id="04dce-120">Create a new service principal</span></span>

1. <span data-ttu-id="04dce-121">安裝最新版本的 **Azure Active Directory PowerShell for Graph**。</span><span class="sxs-lookup"><span data-stu-id="04dce-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="04dce-122">如需詳細資訊，請見 [安裝 Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)。</span><span class="sxs-lookup"><span data-stu-id="04dce-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="04dce-123">請在您的 PC 上選取鍵盤上的 Windows 鍵並搜尋 **Windows PowerShell** 和 **以系統管理員身份執行**。</span><span class="sxs-lookup"><span data-stu-id="04dce-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="04dce-124">請在打開的 PowerShell 視窗中輸入 `Install-Module AzureAD`。</span><span class="sxs-lookup"><span data-stu-id="04dce-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="04dce-125">請使用 Azure AD PowerShell 模組建立適用對象見解的服務主體。</span><span class="sxs-lookup"><span data-stu-id="04dce-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="04dce-126">請在 PowerShell 視窗中輸入 `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`。</span><span class="sxs-lookup"><span data-stu-id="04dce-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="04dce-127">請將 “您的租用戶 ID “ 取代為您想要建立服務主體的租用戶實際 ID。</span><span class="sxs-lookup"><span data-stu-id="04dce-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="04dce-128">環境名稱參數 `AzureEnvironmentName` 為其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="04dce-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="04dce-129">輸入 `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`。</span><span class="sxs-lookup"><span data-stu-id="04dce-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="04dce-130">此命令會在選取的租用戶上建立適用對象見解的服務主體。</span><span class="sxs-lookup"><span data-stu-id="04dce-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="04dce-131">將權限授予服務主體以存取儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="04dce-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="04dce-132">前往 Azure 入口網站授予權限給您想要在對象見解使用儲存體帳戶的服務主體。</span><span class="sxs-lookup"><span data-stu-id="04dce-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="04dce-133">請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入貴組織。</span><span class="sxs-lookup"><span data-stu-id="04dce-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="04dce-134">打開您想要適用對象見解的服務主體存取的儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="04dce-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="04dce-135">從導覽窗格選取 **存取控制 (IAM)** 和 **新增** > **新增角色指派**。</span><span class="sxs-lookup"><span data-stu-id="04dce-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text=" 螢幕擷取畫面顯示 Azure 入口網站，同時新增角色指派。":::
   
1. <span data-ttu-id="04dce-137">請在 **新增角色指派** 窗格中設定下列屬性：</span><span class="sxs-lookup"><span data-stu-id="04dce-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="04dce-138">角色：*儲存體 Blob 資料參與者*</span><span class="sxs-lookup"><span data-stu-id="04dce-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="04dce-139">指派存取：*使用者、群組或服務主體*</span><span class="sxs-lookup"><span data-stu-id="04dce-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="04dce-140">選取：*適用 Customer Insights 的 Dynamics 365 AI* ([您建立的服務主體](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="04dce-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="04dce-141">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="04dce-141">Select **Save**.</span></span>

<span data-ttu-id="04dce-142">傳播變更內容最長耗時 15 分鐘。</span><span class="sxs-lookup"><span data-stu-id="04dce-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="04dce-143">在附於對象見解的儲存體帳戶中輸入 Azure 資源識別碼或 Azure 訂閱詳細資料。</span><span class="sxs-lookup"><span data-stu-id="04dce-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="04dce-144">在對象見解附加 Azure Data Lake Storage 帳戶，以 [儲存輸出資料](manage-environments.md) 或 [將其用作資料來源](connect-common-data-service-lake.md)。</span><span class="sxs-lookup"><span data-stu-id="04dce-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="04dce-145">選擇 Azure Data Lake 選項可讓您在資源式或訂閱式方法之間選擇。</span><span class="sxs-lookup"><span data-stu-id="04dce-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="04dce-146">請遵循下列步驟提供選取方法的必要資訊。</span><span class="sxs-lookup"><span data-stu-id="04dce-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="04dce-147">資料式儲存體帳戶連接</span><span class="sxs-lookup"><span data-stu-id="04dce-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="04dce-148">請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入到您的訂閱並打開儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="04dce-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="04dce-149">請前往導覽窗格上的 **設定** > **屬性**。</span><span class="sxs-lookup"><span data-stu-id="04dce-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="04dce-150">複製儲存體帳戶資源識別碼值。</span><span class="sxs-lookup"><span data-stu-id="04dce-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="複製儲存體帳戶資源識別碼值。":::

1. <span data-ttu-id="04dce-152">請在對象見解中，將資源識別碼插入儲存體帳戶連接螢幕顯示的資源欄位中。</span><span class="sxs-lookup"><span data-stu-id="04dce-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="輸入儲存體帳戶資源識別碼資訊。":::   
   
1. <span data-ttu-id="04dce-154">繼續進行對象見解中的其餘步驟以便附加儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="04dce-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="04dce-155">訂閱式儲存體帳戶連接</span><span class="sxs-lookup"><span data-stu-id="04dce-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="04dce-156">請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入到您的訂閱並打開儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="04dce-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="04dce-157">請前往導覽窗格上的 **設定** > **屬性**。</span><span class="sxs-lookup"><span data-stu-id="04dce-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="04dce-158">請評論 **訂閱**、**資源群組** 和儲存體帳戶 **名稱** 以確定您在對象見解中選取正確值。</span><span class="sxs-lookup"><span data-stu-id="04dce-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="04dce-159">請在對象見解中選擇附加儲存體帳戶的值或對應欄位。</span><span class="sxs-lookup"><span data-stu-id="04dce-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="輸入儲存體帳戶資源識別碼資訊。":::
   
1. <span data-ttu-id="04dce-161">繼續進行對象見解中的其餘步驟以便附加儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="04dce-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
