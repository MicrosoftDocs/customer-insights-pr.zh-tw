---
title: 使用服務主體連接到 Azure Data Lake Storage 帳戶
description: 使用 Azure 服務主體連接到您的 Data Lake。
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 1dd99edc327bd41b0442b390f2e4f8664269f553
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645796"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>使用 Azure 服務主體連接到 Azure Data Lake Storage 帳戶

本文討論如何使用 Azure 服務主體 (而不是儲存帳戶金鑰) 來把 Dynamics 365 Customer Insights 連結至 Azure Data Lake Storage 帳戶。 

使用 Azure 服務的自動化工具應始終具有限縮權限。 有別於以完整權限使用者身分登入應用程式的作法，Azure 提供服務主體。 您可以使用服務主體，安全地將 [Common Data Model 資料夾新增或編輯成資料來源](connect-common-data-model.md)或是[建立或更新環境](create-environment.md)。

> [!IMPORTANT]
> - 將使用服務主體的 Data Lake Storage 帳戶必須是 Gen2 且已[啟用階層命名空間](/azure/storage/blobs/data-lake-storage-namespace)。 不支援 Azure Data Lake Gen1 storage 帳戶。
> - 您需要 Azure 訂閱的系統管理員權限，才能建立服務主體。

## <a name="create-an-azure-service-principal-for-customer-insights"></a>為 Customer Insights 建立 Azure 服務主體

在建立 Customer Insights 的新服務主體之前，請檢查它是否已存在於組織中。

### <a name="look-for-an-existing-service-principal"></a>尋找現有的服務主體

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入貴組織。

2. 在 **Azure 服務**，選擇 **Azure Active Directory**。

3. 請在 **管理** 下方選取 **企業應用程式**。

4. 搜尋名稱為 `Dynamics 365 AI for Customer Insights` 的 Microsoft 應用程式識別碼 `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`。

5. 如果您發現相符的記錄，表示服務主體已存在。 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="顯示現存服務主體的螢幕擷取畫面。":::
   
6. 如果未傳回任何結果，請建立全新服務主體。

### <a name="create-a-new-service-principal"></a>建立全新服務主體

1. 安裝 Azure Active Directory 圖形 PowerShell 的最新版本。 如需詳細資訊，請移至[安裝 Azure Active Directory 圖形 PowerShell](/powershell/azure/active-directory/install-adv2)。

   1. 在您的 PC 上，按下鍵盤上的 Windows 鍵並搜尋 **Windows PowerShell，** 然後選取 **以系統管理員身分執行**。
   
   1. 請在打開的 PowerShell 視窗中輸入 `Install-Module AzureAD`。

2. 使用 Azure AD PowerShell 模組建立 Customer Insights 的服務主體。

   1. 請在 PowerShell 視窗中輸入 `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`。 使用您想要在其中建立服務主體的 Azure 訂閱，其實際目錄識別碼取代 *[您的目錄識別碼]*。 環境名稱參數，`AzureEnvironmentName`，是選用的。
  
   1. 輸入 `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`。 這個命令會在選定的 Azure 訂閱上為 Customer Insights 建立服務主體。 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>將權限授予服務主體以存取儲存體帳戶

移至 Azure 入口網站，對服務主體授與您在其中使用 Customer Insights 的儲存體帳戶權限。

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入貴組織。

1. 打開您希望 Customer Insights 服務主體可以存取的儲存體帳戶。

1. 在左窗格中，選取 **存取控制 (IAM)**，然後選取 **新增** > **新增角色指派**。

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="新增角色指派時， Azure 入口網站的螢幕擷取畫面。":::

1. 在 **新增角色指派** 窗格上，設定下列屬性：
   - 角色：**儲存體 Blob 資料參與者**
   - 指派存取：**使用者、群組或服務主體**
   - 選取成員：**Dynamics 365 AI for Customer Insights** (在此流程前面建立的[服務主體](#create-a-new-service-principal))

1.  選取 **檢閱+指派**。

傳播變更內容最長耗時 15 分鐘。

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>在儲存體帳戶給 Customer Insights 附件中，輸入Azure 資源識別碼或 Azure 訂閱詳細資料

您可以在 Customer Insights 中附加 Data Lake 儲存體帳戶以[儲存輸出資料](manage-environments.md)或[將它用作資料來源](connect-dataverse-managed-lake.md)。 此選項可讓您在資源型或訂閱型方式之間選擇。 視您選擇的方式而定，請依照下列其中一節中的程序進行。

### <a name="resource-based-storage-account-connection"></a>資源型儲存體帳戶連接

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入您的訂閱，並打開儲存體帳戶。

1. 在左窗格中，移至 **設定** > **屬性**。

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