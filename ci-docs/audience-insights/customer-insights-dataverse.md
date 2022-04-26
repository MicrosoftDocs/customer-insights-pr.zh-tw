---
title: Microsoft Dataverse 中的 Customer Insights 資料
description: 在 Microsoft Dataverse 中以資料表使用 Customer Insights 實體。
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547616"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>在 Microsoft Dataverse 中使用 Customer Insights 資料

Customer Insights 提供可讓輸出實體在 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) 中使用的選項。 這種整合可透過少量/無程式碼方法，實現輕鬆的資料共用和自訂開發。 [輸出實體](#output-entities)可以作為 Dataverse 環境中的資料表。 您可以以 Dataverse 資料表，使用其他任何應用程式的資料。 這些資料表能實現多種案例，例如：以 Power Automate 自動化工作流程，或以 Power Apps 建立應用程式的。 目前的實作主要支援查詢，以給定客戶識別碼從適當的 Customer Insights 實體中取得資料。

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>將 Dataverse 環境附加至 Customer Insights

**現有組織**

系統管理員在建立 Customer Insights 環境時，可以把 Customer Insights 設定為[使用現有 Dataverse 環境](create-environment.md)。 藉由提供連接 Dataverse 環境的 URL，將環境附加至新的對象見解環境。 Customer Insights 和 Dataverse 環境必須位於相同的地區。 

如果您不想要使用現有 Dataverse 的環境，系統會為您的租用戶中的 Customer Insights 資料建立新的環境。 

> [!NOTE]
> 如果您的組織已經在其租用戶中使用 Dataverse，請謹記 [Dataverse 環境的建立由系統管理員控制](/power-platform/admin/control-environment-creation)。例如，如果您正在您的組織帳戶中設定新的對象見解環境，而且系統管理員已禁止每個人 (除系統管理員) 建立 Dataverse 試用環境，您就無法建立新的試用環境。
> 
> 在 Customer Insights 中所建立的 Dataverse 試用環境有 3 GB 的儲存空間，不會計入該租用戶的整體容量權利中。 付費訂閱取得 Dataverse 的 15 GB 資料庫權利，並有 20 GB 的檔案儲存。

**新增組織**

如果您在設定 Customer Insights 時建立新組織，系統就會在您的組織中自動建立新 Dataverse 的環境。

## <a name="output-entities"></a>輸出實體

來自對象見解的某些輸出實體可當成 Dataverse 中的資料表使用。 以下各節說明這些資料表的預期結構描述。

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [擴充](#enrichment)
- [預測](#prediction)
- [客戶細分成員資格](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

此資料表包含來自 Customer Insights 的整合客戶個人資料。 整合客戶個人資料的結構描述依照合併程序中所使用的實體和屬性而定。 客戶個人資料結構描述通常包含 [CustomerProfile 的 Common Data Model 定義中 ](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile)的屬性子集。

### <a name="alternatekey"></a>AlternateKey

AlternateKey 資料表包含參與整合程序的實體索引鍵。

|Column  |類型​​  |描述  |
|---------|---------|---------|
|DataSourceName    |String         | 資料來源的名稱。 例如: `datasource5`        |
|EntityName        | String        | 對象見解中的實體名稱。 例如: `contact1`        |
|AlternateValue    |String         |對應至客戶識別碼的替代識別碼。 範例: `cntid_1078`         |
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

| Column        | 類型​ | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | 字串       | 客戶個人資料識別碼        |
| SegmentProvider      | 字串       | 發佈客戶細分的應用程式。 預設：對象見解         |
| SegmentMembershipType | 字串       | 此客戶細分成員資格記錄的客戶類型。 支援多種類型，例如，客戶、連絡人或帳戶。 預設：客戶  |
| 客戶細分       | JSON 字串  | 為客戶個人資料所屬，唯一客戶細分的清單      |
| msdynci_identifier  | 字串   | 客戶細分成員資格記錄的唯一識別碼。 `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | 從 `msdynci_identifier` 產生的決定性 GUID          |
