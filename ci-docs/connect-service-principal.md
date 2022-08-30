---
title: 使用 Azure 服務主體連接到 Azure Data Lake Storage 帳戶
description: 使用 Azure 服務主體連接到您的 Data Lake。
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304187"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>使用 Azure 服務主體連接到 Azure Data Lake Storage 帳戶

Dynamics 365 Customer Insights 提供一個可使用 Azure 服務主體 (而不是儲存體帳戶金鑰) 連接至 Azure Data Lake Storage 帳戶的選項。

使用 Azure 服務的自動化工具，其權限必須受限制。 有別於以完整權限使用者身分登入應用程式的作法，Azure 提供服務主體。 使用服務主體，安全地[將 Common Data Model 資料夾新增或編輯成資料來源](connect-common-data-model.md)或是[建立或更新環境](create-environment.md)。

## <a name="prerequisites"></a>先決條件

- 使用服務主體的 Data Lake Storage 帳戶必須是 Gen2。 不支援 Azure Data Lake Gen1 storage 帳戶。
- Data Lake Storage 帳戶必須[已啟用階層命名空間](/azure/storage/blobs/data-lake-storage-namespace)。
- Azure 租用戶的管理員權限 (如果您需要建立服務主體的話)。

## <a name="create-an-azure-service-principal-for-customer-insights"></a>為 Customer Insights 建立 Azure 服務主體

在建立 Customer Insights 的新服務主體之前，請檢查它是否已存在於組織中。 在大多數情況下，已經存在。

### <a name="look-for-an-existing-service-principal"></a>尋找現有的服務主體

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入貴組織。

2. 在 **Azure 服務**，選擇 **Azure Active Directory**。

3. 在 **管理** 底下，選取 **Microsoft 應用程式**。

4. 篩選 **應用程式識別碼起始為** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` 或搜尋名稱 `Dynamics 365 AI for Customer Insights`。

5. 如果您發現相符的記錄，表示服務主體已存在。 [授與權限](#grant-permissions-to-the-service-principal-to-access-the-storage-account)，讓服務主體可以存取儲存體帳戶。

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="顯示現存服務主體的螢幕擷取畫面。":::

6. 如果未傳回任何結果，請[建立新的服務主體](#create-a-new-service-principal)。

### <a name="create-a-new-service-principal"></a>建立全新服務主體

1. 安裝 Azure Active Directory 圖形 PowerShell 的最新版本。 如需詳細資訊，請移至[安裝 Azure Active Directory 圖形 PowerShell](/powershell/azure/active-directory/install-adv2)。

   1. 在您的電腦上，按鍵盤上的 Windows 鍵，然後搜尋 **Windows PowerShell**，並選取 **以系統管理員身分執行**。

   1. 請在打開的 PowerShell 視窗中輸入 `Install-Module AzureAD`。

2. 使用 Azure AD PowerShell 模組建立 Customer Insights 的服務主體。

   1. 請在 PowerShell 視窗中輸入 `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`。 使用您想要在其中建立服務主體的 Azure 訂閱，其實際目錄識別碼取代 *[您的目錄識別碼]*。 環境名稱參數，`AzureEnvironmentName`，是選用的。
  
   1. 輸入 `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`。 這個命令會在選定的 Azure 訂閱上為 Customer Insights 建立服務主體。

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>將權限授與服務主體以存取儲存體帳戶

若要將權限授與 Customer Insights 中所要使用之儲存體帳戶的服務主體，請將下列其中一個角色指派給儲存體帳戶或容器：

|認證|需求|
|----------|------------|
|目前登入使用者|**角色**：儲存體 Blob 資料讀者、儲存體 blob 參與者或儲存體 Blob 擁有者。<br>**等級**：在儲存體帳戶或容器上授與的權限。</br>|
|Customer Insights 服務主體 -<br>使用 Azure Data Lake Storage 作為資料來源</br>|選項 1<ul><li>**角色**：儲存體 Blob 資料讀者、儲存體 blob 資料參與者或儲存體 Blob 資料擁有者。</li><li>**等級**：在儲存體帳戶上授與的權限。</li></ul>選項 2 *(缺乏共用服務主體的儲存體帳戶權限)*<ul><li>**角色 1**：儲存體 Blob 資料讀者、儲存體 blob 資料參與者或儲存體 Blob 資料擁有者。</li><li>**等級**：在容器上授與的權限。</li><li>**角色 2**：儲存體 Blob 資料委派者。</li><li>**等級**：在儲存體帳戶上授與的權限。</li></ul>|
|Customer Insights 服務主體 - <br>使用 Azure Data Lake Storage 作為輸出或目的地</br>|選項 1<ul><li>**角色**：儲存體 blob 資料參與者或儲存體 Blob 擁有者。</li><li>**等級**：在儲存體帳戶上授與的權限。</li></ul>選項 2 *(缺乏共用服務主體的儲存體帳戶權限)*<ul><li>**角色**：儲存體 blob 資料參與者或儲存體 Blob 擁有者。</li><li>**等級**：在容器上授與的權限。</li><li>**角色 2**：儲存體 Blob 委派者。</li><li>**等級**：在儲存體帳戶上授與的權限。</li></ul>|

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入貴組織。

1. 打開您希望 Customer Insights 服務主體可以存取的儲存體帳戶。

1. 在左窗格中，選取 **存取控制 (IAM)**，然後選取 **新增** > **新增角色指派**。

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="新增角色指派時， Azure 入口網站的螢幕擷取畫面。":::

1. 在 **新增角色指派** 窗格上，設定下列屬性：
   - **角色**：根據以上所列認證建立的儲存體 Blob 資料讀者、儲存體 Blob 參與者或儲存體 Blob 擁有者。
   - **存取權指派對象**：**使用者、群組或服務主體**
   - **選取** 成員：**Dynamics 365 AI for Customer Insights** (您先前在此程序中查詢的[服務主體](#create-a-new-service-principal))

1. 選取 **檢閱+指派**。

傳播變更內容最長耗時 15 分鐘。

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>在儲存體帳戶給 Customer Insights 附件中，輸入Azure 資源識別碼或 Azure 訂閱詳細資料

在 Customer Insights 中附加 Data Lake Storage 帳戶，以[儲存輸出資料](manage-environments.md)或[做為資料來源使用](connect-dataverse-managed-lake.md)。 在[資源型](#resource-based-storage-account-connection)或[訂閱型](#subscription-based-storage-account-connection)方法之間選擇，並依照那些步驟操作。

### <a name="resource-based-storage-account-connection"></a>資源型儲存體帳戶連接

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入您的訂閱，並打開儲存體帳戶。

1. 在左窗格中，移至 **設定** > **端點**。

1. 複製儲存體帳戶資源識別碼值。

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="複製儲存體帳戶資源識別碼值。":::

1. 在 Customer Insights 儲存體帳戶連接畫面顯示的資源欄位中插入資源識別碼。

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="輸入儲存體帳戶資源識別碼資訊。":::

1. 繼續 Customer Insights 中的其餘步驟，以附加儲存體帳戶。

### <a name="subscription-based-storage-account-connection"></a>訂閱式儲存體帳戶連接

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入您的訂閱，並打開儲存體帳戶。

1. 在左窗格中，移至 **設定** > **屬性**。

1. 請檢閱 **訂閱**、**資源群組** 和儲存體帳戶的 **名稱**，以確保您在Customer Insights 中選定正確的值。

1. 在 Customer Insights 中，在附加儲存體帳戶時，請為對應欄位選擇值。

1. 繼續 Customer Insights 中的其餘步驟，以附加儲存體帳戶。

[!INCLUDE [footer-include](includes/footer-banner.md)]
