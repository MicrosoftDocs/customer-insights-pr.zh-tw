---
title: 在 Microsoft Dataverse 中使用 Customer Insights 資料
description: 了解如何連接 Customer Insights 和 Microsoft Dataverse，以及了解匯出至 Dataverse 的輸出實體。
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833666"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>在 Microsoft Dataverse 中使用 Customer Insights 資料

Customer Insights 提供可讓輸出實體用作 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) 的選項。 這種整合可透過少量/無程式碼方法，實現輕鬆的資料共用和自訂開發。 [輸出實體](#output-entities)可以作為 Dataverse 環境中的資料表。 您可以以 Dataverse 資料表，使用其他任何應用程式的資料。 這些資料表能實現多種案例，例如：以 Power Automate 自動化工作流程，或以 Power Apps 建立應用程式的。

連接至 Dataverse 環境也讓您可以[使用 Power Platform 的資料流程和閘道從內部部署資料來源來擷取資料](data-sources.md#add-data-from-on-premises-data-sources)。

## <a name="prerequisites"></a>先決條件

- Customer Insights 和 Dataverse 環境必須位於相同的地區。
- Dataverse 環境中必須有全域系統管理員角色。 確認此 [Dataverse 環境是否關聯](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment)到特定的安全性群組，並確定您已被新增至這些安全性群組。
- 沒有其他 Customer Insights 環境已與您要連接的 Dataverse 環境相關聯。 了解如何[移除現有的 Dataverse 環境連接](#remove-an-existing-connection-to-a-dataverse-environment)。
- 一個 Microsoft Dataverse 環境只能連接至單一儲存體帳戶。 它只適用於將環境設定為[使用您的 Azure Data Lake Storage](own-data-lake-storage.md)。

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>將 Dataverse 環境連接至 Customer Insights

**Microsoft Dataverse** 步驟可讓您在[建立 Customer Insights 環境](create-environment.md)時，將 Customer Insights 連接至您的 Dataverse 環境。

:::image type="content" source="media/dataverse-provisioning.png" alt-text="為全新環境自動啟用 Microsoft Dataverse 的資料共用。":::

系統管理員可以設定 Customer Insights 來連接現有的 Dataverse 環境。 透過提供 Dataverse 環境 URL，它會附加至它們的新 Customer Insights 環境。

如果您不想要使用現有 Dataverse 的環境，系統會為您的租用戶中的 Customer Insights 資料建立新的環境。 [Power Platform 管理員可控制哪些人員可以建立環境](/power-platform/admin/control-environment-creation)。 當您設定新的 Customer Insights 環境，且管理員已停用除管理員以外的所有人建立 Dataverse 環境時，您可能無法建立新的環境。

選取資料共用核取方塊，以 **啟用與 Dataverse 共用資料**。

如果您使用的是自己的 Data Lake Storage 帳戶，也需要 **權限識別碼**。 如需取得權限識別碼的詳細資訊，請參閱下列章節。

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>啟用資料共用，從 Azure Data Lake Storage 到 Dataverse (預覽版)

當您的環境[使用您自己的 Azure Data Lake Storage 帳戶](own-data-lake-storage.md)時，啟用與 Microsoft Dataverse 共用資料需要一些額外的設定。 設定 Customer Insights 環境的使用者對於 Azure Data Lake Storage 帳戶中的 *CustomerInsights* 容器，至少必須擁有 **儲存體 Blob 資料讀者** 權限。

1. 在您的 Azure 訂閱上建立兩個安全性群組 - 一個 **讀者** 安全性群組和一個 **參與者** 安全性群組，並將 Microsoft Dataverse 服務設定為兩個安全性群組的負責人。
2. 透過這些安全性群組，在您的儲存體帳戶的 CustomerInsights 容器上管理存取控制清單 (ACL)。 將 Microsoft Dataverse 服務和任何 Dataverse 型商務應用程式 (例如 Dynamics 365 Marketing) 新增至 **唯讀** 權限的 **讀者** 安全性群組。 *僅* 將 Customers Insights 應用程式新增至 **參與者** 安全性群組，才能授與能寫入設定檔和見解的 **讀取與寫入** 權限。

### <a name="limitations"></a>限制

將 Dataverse 與您自己的 Azure Data Lake Storage 帳戶搭配使用時，有兩個限制：

- Dataverse 組織與 Azure Data Lake Storage 帳戶之間存在一對一的對應關係。 Dataverse 組織連接至儲存體帳戶後，便無法連接至另一個儲存體帳戶。 這個限制可防止 Dataverse 不填入多個儲存體帳戶。
- 如果需要設定 Azure Private Link 來存取您的 Azure Data Lake Storage 帳戶，則資料共用將無法運作，因為它位於防火牆後面。 Dataverse 目前不支援透過 Private Link 來連接至私人端點。

### <a name="set-up-powershell"></a>設定 PowerShell

若要執行 PowerShell 指令碼，您必須先相應地設定 PowerShell。

1. 安裝[Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)的最新版本。
   1. 在您的 PC 上，按下鍵盤上的 Windows 鍵並搜尋 **Windows PowerShell，** 然後選取 **以系統管理員身分執行**。
   1. 請在打開的 PowerShell 視窗中輸入 `Install-Module AzureAD`。
2. 匯入三個模組。
    1. 在 Powershell 視窗中輸入 `Install-Module -Name Az.Accounts` 並執行下列步驟。
    1. 重複 `Install-Module -Name Az.Resources` 和 `Install-Module -Name Az.Storage`。

### <a name="configuration-steps"></a>設定步驟

1. 從我們工程師的 [GitHub 存放庫](https://github.com/trin-msft/byol)中下載兩個需要執行的 PowerShell 腳本。
    1. `CreateSecurityGroups.ps1`
       - 若要執行 PowerShell 腳本，需要擁有 *租用戶系統管理員* 權限。
       - 此 PowerShell 腳本會在您的 Azure 訂閱上建立兩個安全性群組。 一個是讀者群組，另一個是投稿人群組，並以 Microsoft Dataverse 服務作為這兩個安全性群組的負責人。
       - 請提供包含您 Azure Data Lake Storage 的 Azure 訂閱識別碼，在 Windows PowerShell 中執行此 PowerShell 腳本。 在編輯器中打開 PowerShell 腳本，以查看其他資訊與實施的邏輯。
       - 儲存此腳本生成的兩個安全性群組識別碼值，因為我們會在 `ByolSetup.ps1`腳本中使用它們。

        > [!NOTE]
        > 建立安全性群組在您的租用戶上可能是停用的。 在這種案例中，需要手動設定，而且您的 Azure AD系統管理員必須 [啟用安全性群組建立](/azure/active-directory/enterprise-users/groups-self-service-management)。

    2. `ByolSetup.ps1`
        - 必須有儲存體帳戶/容器層級的 *儲存體 Blob 資料擁有者* 權限，才能執行此腳本，或者這個腳本將為您建立一個。 在成功執行腳本之後，您可以手動移除角色指派。
        - 此 PowerShell 腳本會為 Microsoft Dataverse 服務和任何 Dataverse 商務應用程式新增必要的 tole 型存取控制 (RBAC)。 對於使用 `CreateSecurityGroups.ps1` 腳本建立的安全性群組，它也會在 CustomerInsights 容器上更新存取控制清單 (ACL) 。 參與者群組將具有 *rwx* 權限，而讀者群組則僅擁有 *r-x* 權限。
        - 提供 Azure Data Lake Storage 的 Azure 訂閱識別碼、儲存體帳戶名稱、資源群組名稱和讀者及參與者安全性群組識別碼值，在 Windows PowerShell 中執行此 PowerShell 腳本。 在編輯器中打開 PowerShell 腳本，以查看其他資訊與實施的邏輯。
        - 在成功執行腳本之後，複製輸出字串。 輸出字串形式如：`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. 將從上方複製的輸出字串輸入至 Microsoft Dataverse 環境設定步驟的 **權限識別碼** 欄位。

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="啟用共用 Azure Data Lake Storage 資料到 Microsoft Dataverse 的設定選項。":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>移除現有的 Dataverse 環境連接

當連接至 Dataverse 環境時，**此 CDS 組織已連接至另一個 Customer Insights 執行個體中** 的錯誤訊息表示 Dataverse 該環境已在 Customer Insights 環境中使用。 作為 Dataverse 環境的全域系統管理員，您可以將現有的連接移除。 可能需要花費數個小時才能填入變更。

1. 請移至 [Power Apps](https://make.powerapps.com)。
1. 從環境下選擇器中選取環境。
1. 移至 **解決方案**
1. 解除安裝或刪除名為 **Dynamics 365 Customer Insights 客戶卡增益集 (Preview)** 的解決方案。

OR

1. 請打開您的 Dataverse 環境。
1. 移至 **進階設定** > **解決方案**。
1. 解除安裝 **CustomerInsightsCustomerCard** 解決方案。

如果由於相依性而造成移除連接失敗，則也需要移除相依性。 如需詳細資訊，請參閱[移除相依性](/power-platform/alm/removing-dependencies)。

## <a name="output-entities"></a>輸出實體

Customer Insights 的部分輸出實體可用作 Dataverse 中的資料表。 以下各節說明這些資料表的預期結構描述。

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [擴充](#enrichment)
- [預測](#prediction)
- [客戶細分成員資格](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

此資料表包含來自 Customer Insights 的整合客戶個人資料。 整合客戶個人資料的結構描述，將依資料整合處理使用的實體和屬性決定。 客戶個人資料結構描述通常包含 [CustomerProfile 的 Common Data Model 定義中 ](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile)的屬性子集。

### <a name="alternatekey"></a>AlternateKey

AlternateKey 資料表包含參與整合程序的實體索引鍵。

|Column  |類型​​  |描述  |
|---------|---------|---------|
|DataSourceName    |String         | 資料來源的名稱。 例如: `datasource5`        |
|EntityName        | 字串        | Customer Insights 的實體名稱 例如: `contact1`        |
|AlternateValue    |字串         |對應至客戶識別碼的替代識別碼。 範例: `cntid_1078`         |
|KeyRing           | 多行文字        | JSON 值  </br> 範例：: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | 整合客戶個人資料的識別碼。         |
|AlternateKeyId     | GUID         |  基於 msdynci_identifier 的 AlternateKey 確定性 GUID       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> 範例：`testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

此資料表包含在 Customer Insights 中可以由使用者使用的活動。

| Column            | 類型​​        | 描述                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | 客戶個人資料識別碼                                                                      |
| ActivityId        | String      | 客戶活動的內部識別碼 (主索引鍵)                                       |
| SourceEntityName  | String      | 來源實體的名稱                                                                |
| SourceActivityId  | String      | 來源實體的主索引鍵                                                       |
| 活動類型      | String      | 語義活動類型或自訂活動的名稱                                        |
| ActivityTimeStamp | DATETIME    | 活動時間戳記                                                                      |
| 職稱             | String      | 活動的標題或名稱                                                               |
| 描述       | String      | 活動描述                                                                     |
| URL               | String      | 連結至特定活動的外部 URL                                         |
| SemanticData      | JSON 字串 | 包括此活動類型特有的語義對應欄位其索引鍵值對清單 |
| RangeIndex        | String      | 用於排序活動時間表和有效範圍查詢的 Unix 時間戳記 |
| mydynci_unifiedactivityid   | GUID | 客戶活動的內部識別碼 (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

此資料表包含屬性型的客戶量值輸出資料。

| Column             | 類型​​             | 描述                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | 客戶個人資料識別碼        |
| 量值           | JSON 字串      | 包含指定客戶的量值名稱與值其索引鍵值對清單 | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | 客戶個人資料識別碼 |


### <a name="enrichment"></a>擴充

此資料表包含擴充程序的輸出。

| Column               | 類型​​             |  描述                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | 客戶個人資料識別碼                                 |
| EnrichmentProvider   | String           | 提供擴充提供者的名稱                                  |
| EnrichmentType       | String           | 擴充類型                                      |
| 值               | JSON 字串      | 擴充程序產生的屬性清單 |
| msdynci_enrichmentid | GUID             | 從 msdynci_identifier 生成的確定性 GUID |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>預測

此資料表包含模型預測的輸出。

| Column               | 類型​​        | 描述                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | 客戶個人資料識別碼                                  |
| ModelProvider        | String      | 提供模型提供者的名稱                                      |
| 型號                | String      | 模型名稱                                                |
| 值               | JSON 字串 | 模型產生的屬性清單 |
| msdynci_predictionid | GUID        | 從 msdynci_identifier 生成的確定性 GUID | 
| msdynci_identifier   | 字串      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>客戶細分成員資格

此表格包含客戶設定檔的客戶細分成員資格資訊。

| Column        | 類型​ | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | 字串       | 客戶個人資料識別碼        |
| SegmentProvider      | 字串       | 發佈客戶細分的應用程式。      |
| SegmentMembershipType | 字串       | 此客戶細分成員資格記錄的客戶類型。 支援多個類型，例如，客戶、連絡人或帳戶。 預設：客戶  |
| 客戶細分       | JSON 字串  | 客戶設定檔所屬的唯一客戶細分清單      |
| msdynci_identifier  | 字串   | 客戶細分成員資格記錄的唯一識別碼。 `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | 從 `msdynci_identifier` 產生的決定性 GUID          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
