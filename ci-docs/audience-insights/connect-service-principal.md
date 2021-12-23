---
title: 使用服務主體連接到 Azure Data Lake Storage 帳戶
description: 使用 Azure 服務主體連接到您的 Data Lake。
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: faef3583337fd495e7baf40b0a208f1d9f10281a
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900233"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>使用 Azure 服務主體連接到 Azure Data Lake Storage 帳戶

本文討論如何使用 Azure 服務主體 (而不是儲存帳戶金鑰) 來把 Dynamics 365 Customer Insights 連結至 Azure Data Lake Storage 帳戶。 

使用 Azure 服務的自動化工具應始終具有限縮權限。 有別於以完整權限使用者身分登入應用程式的作法，Azure 提供服務主體。 您可以使用服務主體，安全地將 [Common Data Model 資料夾新增或編輯成資料來源](connect-common-data-model.md)或是[建立或更新環境](create-environment.md)。

> [!IMPORTANT]
> - 使用服務主體的 Data Lake 儲存帳戶必須[啟用階層命名空間](/azure/storage/blobs/data-lake-storage-namespace)。
> - 您需要 Azure 訂閱的系統管理員權限，才能建立服務主體。

## <a name="create-an-azure-service-principal-for-customer-insights"></a>為 Customer Insights 建立 Azure 服務主體

在建立 Customer Insights 的新服務主體之前，請檢查它是否已存在於組織中。

### <a name="look-for-an-existing-service-principal"></a>尋找現有的服務主體

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入貴組織。

2. 在 **Azure 服務**，選擇 **Azure Active Directory**。

3. 請在 **管理** 下方選取 **企業應用程式**。

4. 搜尋 Microsoft 應用程式識別碼：
   - 對象見解：`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`且名稱為 `Dynamics 365 AI for Customer Insights`
   - 參與見解：`ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` 且名稱為 `Dynamics 365 AI for Customer Insights engagement insights`

5. 如果您發現相符的記錄，表示服務主體已存在。 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="顯示現存服務主體的螢幕擷取畫面。":::
   
6. 如果未傳回任何結果，請建立全新服務主體。

>[!NOTE]
>要使用 Dynamics 365 Customer Insights 的完整功能，我們建議您將兩個應用程式新增至服務主體。

### <a name="create-a-new-service-principal"></a>建立全新服務主體

1. 安裝 Azure Active Directory 圖形 PowerShell 的最新版本。 如需詳細資訊，請移至[安裝 Azure Active Directory 圖形 PowerShell](/powershell/azure/active-directory/install-adv2)。

   1. 在您的 PC 上，按下鍵盤上的 Windows 鍵並搜尋 **Windows PowerShell，** 然後選取 **以系統管理員身分執行**。
   
   1. 請在打開的 PowerShell 視窗中輸入 `Install-Module AzureAD`。

2. 使用 Azure AD PowerShell 模組建立 Customer Insights 的服務主體。

   1. 請在 PowerShell 視窗中輸入 `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`。 請將 *[您的租用戶識別碼]* 取代為您想要建立服務主體的實際租用戶識別碼。 環境名稱參數，`AzureEnvironmentName`，是選用的。
  
   1. 輸入 `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`。 此命令會在選取的租用戶上建立適用對象見解的服務主體。 

   1. 輸入 `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`。 這個命令會在選取的租用戶建立參與見解的服務主體。

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>將權限授予服務主體以存取儲存體帳戶

前往 Azure 入口網站授予權限給您想要在對象見解使用儲存體帳戶的服務主體。

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入貴組織。

1. 打開您想要適用對象見解的服務主體存取的儲存體帳戶。

1. 在左窗格中，選取 **存取控制 (IAM)**，然後選取 **新增** > **新增角色指派**。

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="新增角色指派時， Azure 入口網站的螢幕擷取畫面。":::

1. 在 **新增角色指派** 窗格上，設定下列屬性：
   - 角色：**儲存體 Blob 資料參與者**
   - 指派存取：**使用者、群組或服務主體**
   - 選取：**Dynamics 365 AI for Customer Insights** 和 **Dynamics 365 AI for Customer Insights 參與見解**(在此程序前面建立的兩個[服務主體](#create-a-new-service-principal))

1.  選取 **儲存**。

傳播變更內容最長耗時 15 分鐘。

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>在對象見解的儲存體帳戶附件中輸入 Azure 資源識別碼或 Azure 訂閱詳細資料

您可以在對象見解中附加 Data Lake 儲存體帳戶，以[儲存輸出資料](manage-environments.md)或[作為資料來源使用](connect-common-data-service-lake.md)。 此選項可讓您在資源型或訂閱型方式之間選擇。 視您選擇的方式而定，請依照下列其中一節中的程序進行。

### <a name="resource-based-storage-account-connection"></a>資源型儲存體帳戶連接

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入您的訂閱，並打開儲存體帳戶。

1. 在左窗格中，移至 **設定** > **屬性**。

1. 複製儲存體帳戶資源識別碼值。

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="複製儲存體帳戶資源識別碼值。":::

1. 在對象見解中，在儲存體帳戶連接畫面上的資源欄位中插入資源識別碼。

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="輸入儲存體帳戶資源識別碼資訊。":::   

1. 繼續進行對象見解中的其餘步驟以便附加儲存體帳戶。

### <a name="subscription-based-storage-account-connection"></a>訂閱式儲存體帳戶連接

1. 請前往 [Azure 管理員入口網站](https://portal.azure.com) 登入您的訂閱，並打開儲存體帳戶。

1. 在左窗格中，移至 **設定** > **屬性**。

1. 請評論 **訂閱**、**資源群組** 和儲存體帳戶 **名稱** 以確定您在對象見解中選取正確值。

1. 在對象見解中，在附加儲存體帳戶時，請在對應欄的位選擇此值。

1. 繼續進行對象見解中的其餘步驟以便附加儲存體帳戶。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
