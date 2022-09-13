---
title: 在 Microsoft Dataverse 中使用 Customer Insights 資料
description: 了解如何連接 Customer Insights 和 Microsoft Dataverse，以及了解匯出至 Dataverse 的輸出實體。
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424299"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>在 Microsoft Dataverse 中使用 Customer Insights 資料

Customer Insights 提供可讓輸出實體在 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) 中使用的選項。 這種整合可透過少量/無程式碼方法，實現輕鬆的資料共用和自訂開發。 [輸出實體](#output-entities)可以作為 Dataverse 環境中的資料表。 您可以以 Dataverse 資料表，使用其他任何應用程式的資料。 這些資料表能實現多種案例，例如：以 Power Automate 自動化工作流程，或以 Power Apps 建立應用程式的。

連接至 Dataverse 環境也讓您可以[使用 Power Platform 的資料流程和閘道從內部部署資料來源來擷取資料](connect-power-query.md#add-data-from-on-premises-data-sources)。

## <a name="prerequisites"></a>先決條件

- Customer Insights 和 Dataverse 環境必須位於相同的地區。
- 在 Dataverse 環境中設定的全域系統管理員角色。 確認此 [Dataverse 環境是否關聯](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment)到特定的安全性群組，並確定您已被新增至這些安全性群組。
- 沒有任何其他已經與所要連接之 Dataverse 環境相關聯的 Customer Insights 環境。 了解如何[移除現有的 Dataverse 環境連接](#remove-an-existing-connection-to-a-dataverse-environment)。
- 已連接至單一儲存體帳戶的 Microsoft Dataverse 環境 (如果您設定讓環境[使用 Azure Data Lake Storage](own-data-lake-storage.md) 的話)。

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse 儲存體容量權利

Customer Insights 訂閱權限可讓您為組織現有的 [Dataverse 儲存體容量](/power-platform/admin/capacity-storage)取得額外容量。 新增的容量視您的訂閱所使用的設定檔數目而定。

**範例：**

假設您每 100,000 個客戶設定檔有 15 GB 的資料庫儲存體和 20 GB 的檔案儲存體。 如果您的訂閱包含 300,000 個客戶設定檔，則總儲存容量為 45 GB (3 x 15 GB) 資料庫儲存空間和 60 GB (3 x 20 GB) 檔案儲存空間。 同樣的，如果您的 B 到 B 訂閱包含 30K 個帳戶，則總儲存容量為 45 GB (3 x 15 GB) 資料庫儲存空間和 60 GB (3 x 20 GB) 檔案儲存空間。

您組織的記錄容量不會累加，是固定的。

有關詳細容量權利的詳細資訊，請參閱 [Dynamics 365 授權指南](https://go.microsoft.com/fwlink/?LinkId=866544)。

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>將 Dataverse 環境連接至 Customer Insights

**Microsoft Dataverse** 步驟可讓您在[建立 Customer Insights 環境](create-environment.md)時，將 Customer Insights 連接至您的 Dataverse 環境。

:::image type="content" source="media/dataverse-provisioning.png" alt-text="自動啟用新環境與 Microsoft Dataverse 的資料共用。":::

1. 提供 Dataverse 環境的 URL，或保留空白讓系統為您建立此環境。

   > [!NOTE]
   > 在建立 Customer Insights 與 Dataverse 的連線後，請不要變更 Dataverse 環境的組織名稱。 在 Dataverse URL 中使用了組織的名稱，而變更後的名稱會中斷與 Customer Insights 的連接。

   [Power Platform 管理員可控制哪些人員可以建立新的 Dataverse 環境](/power-platform/admin/control-environment-creation)。 如果您要嘗試設定新的 Customer Insights 環境，但做不到時，管理員可能已針對所有除管理員以外的人員停用建立 Dataverse 環境的作業。

1. 如果您使用的是自己的 Data Lake Storage 帳戶：
   1. 選取 Dataverse 的 **啟用資料共用**。
   1. 輸入 **權限識別碼**。 若要取得權限識別碼。請[從您自己的 Azure Data Lake Storage 中啟用與 Dataverse 的資料共用](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)。

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>從您自己的 Azure Data Lake Storage 中啟用與 Dataverse 的資料共用 (預覽版)

在 [您自己的 Azure Data Lake Storage 帳戶](own-data-lake-storage.md)中，確認設定 Customer Insights 環境的使用者是否對儲存體帳戶中的 `customerinsights` 容器至少有 **儲存體 Blob 資料讀者** 權限。

### <a name="limitations"></a>限制

- Dataverse 組織與 Azure Data Lake Storage 帳戶之間只有一對一對應。 Dataverse 組織連接至儲存體帳戶後，便無法連接至另一個儲存體帳戶。 此限制可避免 Dataverse 填入多個儲存體帳戶。
- 如果需要設定 Azure Private Link 以存取您的 Azure Data Lake Storage 帳戶，則資料共用將無法進行，因為它在防火牆後面。 Dataverse 目前不支援透過 Private Link 來連接至私人端點。

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>在您自己的 Azure Data Lake Storage 上設定安全性群組

1. 在您的 Azure 訂閱上建立兩個安全性群組 - 一個 **讀者** 安全性群組和一個 **參與者** 安全性群組，並將 Microsoft Dataverse 服務設定為兩個安全性群組的負責人。

1. 透過這些安全性群組，在您的儲存體帳戶的 `customerinsights` 容器上管理存取控制清單 (ACL)。
   1. 將 Microsoft Dataverse 服務和任何 Dataverse 型商務應用程式 (例如 Dynamics 365 Marketing) 新增至 **唯讀** 權限的 **讀者** 安全性群組。
   1. *僅* 將 Customers Insights 應用程式新增至 **參與者** 安全性群組，才能授與能寫入設定檔和見解的 **讀取與寫入** 權限。

### <a name="set-up-powershell"></a>設定 PowerShell

設定 PowerShell 以執行 PowerShell 指令碼。

1. 安裝[Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)的最新版本。
   1. 在您的 PC 上，按下鍵盤上的 Windows 鍵並搜尋 **Windows PowerShell，** 然後選取 **以系統管理員身分執行**。
   1. 請在打開的 PowerShell 視窗中輸入 `Install-Module AzureAD`。

1. 匯入三個模組。
   1. 在 Powershell 視窗中輸入 `Install-Module -Name Az.Accounts` 並執行下列步驟。
   1. 重複 `Install-Module -Name Az.Resources` 和 `Install-Module -Name Az.Storage`。

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>執行 PowerShell 指令碼並取得權限識別碼

1. 從我們工程師的 [GitHub 存放庫](https://github.com/trin-msft/byol)中下載兩個需要執行的 PowerShell 腳本。
   - `CreateSecurityGroups.ps1`：需要租用戶管理員權限。
   - `ByolSetup.ps1`：需要儲存體帳戶/容器層級的儲存體 Blob 資料擁有者權限。 此指令碼將會為您建立權限。 在成功執行腳本之後，您可以手動移除角色指派。

1. 提供包含 Azure Data Lake Storage 的 Azure 訂閱識別碼，在 Windows PowerShell 中執行 `CreateSecurityGroups.ps1`。 在編輯器中開啟 PowerShell 指令碼，以檢閱其他資訊及實作邏輯。

   此指令碼會在 Azure 訂閱上建立兩個安全性群組：一個用於讀者群組，另一個用於參與者群組。 Microsoft Dataverse 服務是這兩個安全性群組的擁有者。

1. 儲存此指令碼產生的這兩個安全性群組識別碼值，以便用於 `ByolSetup.ps1` 指令碼。

   > [!NOTE]
   > 建立安全性群組在您的租用戶上可能是停用的。 在這種案例中，需要手動設定，而且您的 Azure AD系統管理員必須 [啟用安全性群組建立](/azure/active-directory/enterprise-users/groups-self-service-management)。

1. 提供包含 Azure Data Lake Storage、儲存體帳戶名稱、資源群組名稱以及讀者和參與者安全性群組識別碼值的 Azure 訂閱識別碼，以在 Windows PowerShell 中執行 `ByolSetup.ps1`。 在編輯器中開啟 PowerShell 指令碼，以檢閱其他資訊及實作邏輯。

   此指令碼會新增對 Microsoft Dataverse 服務與任何 Dataverse 型商務應用程式所需的角色型存取控制 (RBAC)。 還會針對使用 `CreateSecurityGroups.ps1` 指令碼所建立的安全性群組，更新其 `customerinsights` 容器上的存取控制清單 (ACL)。 參與者群組會獲得 *rwx* 權限，而讀者群組僅獲得 *r-x* 權限。

1. 複製如下所示的輸出字串：`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. 在 Microsoft Dataverse 環境設定步驟的 **權限識別碼** 欄位中輸入複製的輸出字串。

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="啟用共用 Azure Data Lake Storage 資料到 Microsoft Dataverse 的設定選項。":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>移除現有的 Dataverse 環境連接

當連接至 Dataverse 環境時，**此 CDS 組織已連接至另一個 Customer Insights 執行個體中** 的錯誤訊息表示 Dataverse 該環境已在 Customer Insights 環境中使用。 作為 Dataverse 環境的全域系統管理員，您可以將現有的連接移除。 可能需要花費數個小時才能填入變更。

1. 請移至 [Power Apps](https://make.powerapps.com)。
1. 從環境下選擇器中選取環境。
1. 移至 **解決方案**。
1. 解除安裝或刪除名為 **Dynamics 365 Customer Insights 客戶卡增益集 (Preview)** 的解決方案。

OR

1. 請打開您的 Dataverse 環境。
1. 移至 **進階設定** > **解決方案**。
1. 解除安裝 **CustomerInsightsCustomerCard** 解決方案。

如果由於相依性而造成移除連接失敗，則也需要移除相依性。 如需詳細資訊，請參閱[移除相依性](/power-platform/alm/removing-dependencies)。

## <a name="output-entities"></a>輸出實體

Customer Insights 的部分輸出實體可用作 Dataverse 中的資料表。 以下各節說明這些資料表的預期結構描述。

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [擴充](#enrichment)
- [預測](#prediction)
- [客戶細分成員資格](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

此資料表包含來自 Customer Insights 的統一客戶設定檔。 統一客戶設定檔的結構描述，將依資料整合處理使用的實體和屬性決定。 客戶設定檔結構描述通常包含 [CustomerProfile 的 Common Data Model 定義中 ](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile)的屬性子集。 在 B 到 B 案例中，客戶設定檔會包含整合客戶，而結構描述通常包含[客戶的 Common Data Model 定義](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account)中屬性的子集。

### <a name="contactprofile"></a>ContactProfile

ContactProfile 包含關於連絡人的整合資訊。 連絡人是在 B 到 B 案例中[對應至客戶的個人](data-unification-contacts.md)。

| Column                       | 類型​                | 名描述     |
| ---------------------------- | ------------------- | --------------- |
|  出生日期            | 日期時間       |  連絡人的出生日期               |
|  縣/市                 | 文字 |  連絡人地址的縣/市               |
|  ContactId            | 文字 |  連絡人設定檔的識別碼               |
|  ContactProfileId     | 唯一識別碼   |  連絡人的 GUID               |
|  CountryOrRegion      | 文字 |  連絡人地址的國家/地區               |
|  CustomerId           | 文字 |  連絡人對應至之客戶的識別碼               |
|  EntityName           | 文字 |  資料的來源實體                |
|  FirstName            | 文字 |  連絡人的名字               |
|  性別               | 文字 |  連絡人的性別               |
|  Id                   | 文字 |  根據 `Identifier` 建立的決定性 GUID               |
|  識別碼           | 文字 |  連絡人設定檔的內部識別碼：`ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | 文字 |  連絡人的職稱               |
|  LastName             | 文字 |  連絡人的姓氏               |
|  PostalCode           | 文字 |  連絡人地址的郵遞區號               |
|  PrimaryEmail         | 文字 |  連絡人的電子郵件               |
|  PrimaryPhone         | 文字 |  連絡人的電話號碼               |
|  StateOrProvince      | 文字 |  連絡人地址的州或省               |
|  StreetAddress        | 文字 |  連絡人地址的街道               |

### <a name="alternatekey"></a>AlternateKey

AlternateKey 資料表包含參與整合程序的實體索引鍵。

|Column  |類型​  |名描述  |
|---------|---------|---------|
|DataSourceName    |文字         | 資料來源的名稱。 例如: `datasource5`        |
|EntityName        | 文字        | Customer Insights 的實體名稱 例如: `contact1`        |
|AlternateValue    |文字         |對應至客戶識別碼的替代識別碼。 範例: `cntid_1078`         |
|KeyRing           | 文字        | JSON 值  </br> 範例：: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | 文字        | 統一客戶設定檔的識別碼。         |
|AlternateKeyId     | 唯一識別碼        |  根據 `Identifier` 建立的 AlternateKey 決定性 GUID      |
|識別碼 |   文字      |   `DataSourceName|EntityName|AlternateValue`  </br> 範例：`testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

此資料表包含在 Customer Insights 中可以由使用者使用的活動。

| Column            | 類型​        | 名描述                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | 文字      | 客戶設定檔識別碼                                                                      |
| ActivityId        | 文字      | 客戶活動的內部識別碼 (主索引鍵)                                       |
| SourceEntityName  | 文字      | 來源實體的名稱                                                                |
| SourceActivityId  | 文字      | 來源實體的主索引鍵                                                       |
| 活動類型      | 文字      | 語義活動類型或自訂活動的名稱                                        |
| ActivityTimeStamp | 日期時間    | 活動時間戳記                                                                      |
| 名稱             | 文字      | 活動的標題或名稱                                                               |
| 名描述       | 文字      | 活動描述                                                                     |
| URL               | 文字      | 連結至特定活動的外部 URL                                         |
| SemanticData      | 文字 | 包括此活動類型特有的語義對應欄位其索引鍵值對清單 |
| RangeIndex        | 文字      | 用於排序活動時間表和有效範圍查詢的 Unix 時間戳記 |
| UnifiedActivityId   | 唯一識別碼 | 客戶活動的內部識別碼 (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

此資料表包含屬性型的客戶量值輸出資料。

| Column             | 類型​             | 名描述                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | 文字           | 客戶設定檔識別碼        |
| 量值           | 文字      | 包含指定客戶的量值名稱與值其索引鍵值對清單 |
| 識別碼 | 文字           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | 唯一識別碼     | 客戶設定檔識別碼 |

### <a name="enrichment"></a>擴充

此資料表包含擴充程序的輸出。

| Column               | 類型​             |  名描述                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | 文字           | 客戶設定檔識別碼                                 |
| EnrichmentProvider   | 文字           | 提供擴充提供者的名稱                                  |
| EnrichmentType       | 文字           | 擴充類型                                      |
| 數值               | 文字      | 擴充程序產生的屬性清單 |
| EnrichmentId | 唯一識別碼            | 從 `Identifier` 產生的決定性 GUID |
| 識別碼   | 文字           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>預測

此資料表包含模型預測的輸出。

| Column               | 類型​        | 名描述                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | 文字      | 客戶設定檔識別碼                                  |
| ModelProvider        | 文字      | 提供模型提供者的名稱                                      |
| 型號                | 文字      | 模型名稱                                                |
| 數值               | 文字 | 模型產生的屬性清單 |
| PredictionId | 唯一識別碼       | 從 `Identifier` 產生的決定性 GUID |
| 識別碼   | 文字      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>客戶細分成員資格

此表格包含客戶設定檔的客戶細分成員資格資訊。

| Column        | 類型​ | 名描述                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | 文字       | 客戶設定檔識別碼        |
| SegmentProvider      | 文字       | 發佈客戶細分的應用程式。      |
| SegmentMembershipType | 文字       | 此客戶細分成員資格記錄的客戶類型。 支援多個類型，例如，客戶、連絡人或帳戶。 預設：客戶  |
| 客戶細分       | 文字  | 客戶設定檔所屬的唯一客戶細分清單      |
| 識別碼  | 文字   | 客戶細分成員資格記錄的唯一識別碼。 `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | 唯一識別碼      | 從 `Identifier` 產生的決定性 GUID          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
