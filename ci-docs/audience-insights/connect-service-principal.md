---
title: 使用服務主體連接到 Azure Data Lake Storage Gen2 帳戶
description: 在將 data lake 附加到對象見解時，請使用適用對象見解的 Azure 服務主體連接您自己的 data lake。
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267712"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>使用適用對象見解的 Azure 服務主體連接到 Azure Data Lake Storage Gen2 帳戶

使用 Azure 服務的自動化工具應始終具有限縮權限。 有別於以完整權限使用者身分登入應用程式的作法，Azure 提供服務主體。 請閱讀以便瞭解如何以使用 Azure 服務主體的 Azure Data Lake Storage Gen2 帳戶而不是儲存體帳戶金鑰連接對象見解。 

您可以使用服務主體安全地將 [Common Data Model 資料夾新增或編輯為資料來源](connect-common-data-model.md) 或 [建立全新或更新現有的環境](manage-environments.md#create-an-environment-in-an-existing-organization)。

> [!IMPORTANT]
> - 要使用服務主體的 Azure Data Lake Gen2 儲存體帳戶必須已[啟用階層命名空間 (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace)。
> - 您需要適用您的 Azure 訂閱的系統管理員權限建立服務主體。

## <a name="create-azure-service-principal-for-audience-insights"></a>建立適用對象見解的 Azure 服務主體

在為對象見解建立全新服務主體之前，請先檢查它是否已存在於貴組織。

### <a name="look-for-an-existing-service-principal"></a>尋找現有的服務主體

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入貴組織。

2. 從 Azure 服務選取 **Azure Active Directory**。

3. 請在 **管理** 下方選取 **企業應用程式**。

4. 搜尋對象見解第一個合作對象的應用程式 ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` 或名稱 `Dynamics 365 AI for Customer Insights`。

5. 如果您發現符合的記錄，代表適用對象見解的服務主體確實存在。 您不需要再建立一次。
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="螢幕擷取畫面顯示現有服務主體。":::
   
6. 如果未傳回任何結果，請建立全新服務主體。

### <a name="create-a-new-service-principal"></a>建立全新服務主體

1. 安裝最新版本的 **Azure Active Directory PowerShell for Graph**。 如需詳細資訊，請見 [安裝 Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)。
   - 請在您的 PC 上選取鍵盤上的 Windows 鍵並搜尋 **Windows PowerShell** 和 **以系統管理員身份執行**。
   
   - 請在打開的 PowerShell 視窗中輸入 `Install-Module AzureAD`。

2. 請使用 Azure AD PowerShell 模組建立適用對象見解的服務主體。
   - 請在 PowerShell 視窗中輸入 `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`。 請將 “您的租用戶 ID “ 取代為您想要建立服務主體的租用戶實際 ID。 環境名稱參數 `AzureEnvironmentName` 為其中一個選項。
  
   - 輸入 `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`。 此命令會在選取的租用戶上建立適用對象見解的服務主體。  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>將權限授予服務主體以存取儲存體帳戶

前往 Azure 入口網站授予權限給您想要在對象見解使用儲存體帳戶的服務主體。

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入貴組織。

1. 打開您想要適用對象見解的服務主體存取的儲存體帳戶。

1. 從導覽窗格選取 **存取控制 (IAM)** 和 **新增** > **新增角色指派**。
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text=" 螢幕擷取畫面顯示 Azure 入口網站，同時新增角色指派。":::
   
1. 請在 **新增角色指派** 窗格中設定下列屬性：
   - 角色：*儲存體 Blob 資料參與者*
   - 指派存取：*使用者、群組或服務主體*
   - 選取：*適用 Customer Insights 的 Dynamics 365 AI* ([您建立的服務主體](#create-a-new-service-principal))

1.  選取 **儲存**。

傳播變更內容最長耗時 15 分鐘。

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>在附於對象見解的儲存體帳戶中輸入 Azure 資源識別碼或 Azure 訂閱詳細資料。

在對象見解附加 Azure Data Lake Storage 帳戶，以 [儲存輸出資料](manage-environments.md) 或 [將其用作資料來源](connect-common-data-service-lake.md)。 選擇 Azure Data Lake 選項可讓您在資源式或訂閱式方法之間選擇。

請遵循下列步驟提供選取方法的必要資訊。

### <a name="resource-based-storage-account-connection"></a>資源型儲存體帳戶連接

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入到您的訂閱並打開儲存體帳戶。

1. 請前往導覽窗格上的 **設定** > **屬性**。

1. 複製儲存體帳戶資源識別碼值。

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="複製儲存體帳戶資源識別碼值。":::

1. 請在對象見解中，將資源識別碼插入儲存體帳戶連接螢幕顯示的資源欄位中。

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="輸入儲存體帳戶資源識別碼資訊。":::   
   
1. 繼續進行對象見解中的其餘步驟以便附加儲存體帳戶。

### <a name="subscription-based-storage-account-connection"></a>訂閱式儲存體帳戶連接

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入到您的訂閱並打開儲存體帳戶。

1. 請前往導覽窗格上的 **設定** > **屬性**。

1. 請評論 **訂閱**、**資源群組** 和儲存體帳戶 **名稱** 以確定您在對象見解中選取正確值。

1. 請在對象見解中選擇附加儲存體帳戶的值或對應欄位。
   
1. 繼續進行對象見解中的其餘步驟以便附加儲存體帳戶。


[!INCLUDE[footer-include](../includes/footer-banner.md)]