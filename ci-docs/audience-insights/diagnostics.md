---
title: 使用 Azure 監視器稽核 Dynamics 365 Customer Insights
description: 了解如何將記錄傳送至 Microsoft Azure 監視器。
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 2e0801c2b6af591e48a7df485a8523903c07617c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354362"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>使用 Azure 監視器在 Dynamics 365 Customer Insights 轉寄記錄 (預覽版)

Dynamics 365 Customer Insights 提供對 Azure 監視器的直接整合。 Azure 監視器資源記錄可讓您監控並把記錄傳送至 [Azure 儲存體](https://azure.microsoft.com/services/storage/)、[Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview)，或將它們串流至 [Azure 事件中樞](https://azure.microsoft.com/services/event-hubs/)。

Customer Insights 會傳送下列事件記錄檔：

- **稽核事件**
  - **APIEvent** - 讓變更追蹤能透過 Dynamics 365 Customer Insights 完成。
- **作業事件**
  - **WorkflowEvent** -工作流程允許設定[資料來源](data-sources.md)、[整合](data-unification.md)和[豐富](enrichment-hub.md)，並最終把資料 [匯出](export-destinations.md)至其他系統。 所有的步驟都可以單獨完成 (例如，觸發單一匯出) 或協調 (例如，在資料來源進行資料重新整理，且這將觸發整合程序，而整合程序會提取新的擴充並在完成後匯出其他系統)。 如需詳細資訊，請參閱 [WorkflowEvent 結構描述](#workflow-event-schema)。
  - **APIEvent** - 所有對 Dynamics 365 Customer Insights 的客戶執行個體的 API 呼叫。 如需詳細資訊，請參閱 [APIEvent 結構描述](#api-event-schema)。

## <a name="set-up-the-diagnostic-settings"></a>設定診斷設定

### <a name="prerequisites"></a>先決條件

若要在 Customer Insights 中設定診斷，必須符合下列先決條件：

- 您必須具備有效的 [ Azure 訂閱](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)。
- 您擁有 Customer Insights 中的[系統管理員](permissions.md#administrator)權限。
- 您擁有 Azure 中目的地資源的 **參與者** 及 **使用者存取系統管理員** 角色。 資源可以是 Azure 儲存體帳戶、Azure 事件中樞或 Azure Log Analytics 工作區。 如需詳細資訊，請參閱[使用 Azure 入口網站新增移除 Azure 角色指派](/azure/role-based-access-control/role-assignments-portal)。
- Azure 儲存體、Azure 事件中樞或 Azure Log Analytics 符合的[目的地需求](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements)。
- 在資源所屬的資源群組上至少要有 **讀者** 角色。

### <a name="set-up-diagnostics-with-azure-monitor"></a>使用 Azure 監視器設定診斷

1. 在 Customer Insights 中，選取 **系統** > **診斷** 以查看設定此執行個體的診斷目的地。

1. 選取 **新增目的地**。

   > [!div class="mx-imgBorder"]
   > ![診斷連接](media/diagnostics-pane.png "診斷連接")

1. 在 **診斷目的地的名稱** 欄位的名稱中輸入名稱。

1. 選擇具備目的地資源的 Azure 訂閱其 **租用戶**，並選取 **登入**。

1. 選取 **資源類型**（儲存體、事件中樞或記錄分析）。

1. 選取目的地資源的 **訂閱**。

1. 選取目的地資源的 **資源群組**。

1. 選取 **資源**。

1. 確認 **資料隱私權與合規性** 聲明。

1. 選取 **連接至系統** 以連接至目的地資源。 如果此 API 正在使用中且會生成事件，15 分鐘後記錄會在目的地開始顯示。

### <a name="remove-a-destination"></a>移除目的地

1. 移至 **系統** > **診斷**。

1. 選取清單中的診斷目的地。

1. 在 **動作** 資料行中，選取 **刪除** 圖示。

1. 確認刪除以停止記錄轉發。 Azure 訂閱上的資源將不會被刪除。 您可以在 **動作** 資料行中選取連結，打開選取資源的 Azure 入口網站，並在這裡進行刪除。

## <a name="log-categories-and-event-schemas"></a>記錄類別及事件結構描述

目前支援 [ API 事件](apis.md)和工作流程事件，並適用下列類別和架構。
日誌結構描述會遵循 [Azure 監視器通用結構描述](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema)。

### <a name="categories"></a>類別

Customer Insights 提供兩個類別：

- **稽核事件**：[API 事件](#api-event-schema)，以追蹤服務上的設定變更。 `POST|PUT|DELETE|PATCH` 作業屬於此類別。
- **作業事件**：使用服務時生成的 [API 事件](#api-event-schema)或[工作流程事件](#workflow-event-schema)。  例如，`GET`要求或工作流程的執行事件。

## <a name="configuration-on-the-destination-resource"></a>對目的地資源的設定

根據您在資源類型上做出的選擇，下列步驟將會自動套用：

### <a name="storage-account"></a>Storage account

Customer Insights 服務主體取得已選資源的 **儲存體帳戶參與者** 權限，並在已選的命名空間下建立兩個容器：

- `insight-logs-audit` 包含 **稽核事件**
- `insight-logs-operational` 包含 **作業事件**

### <a name="event-hub"></a>事件中樞

Customer Insights 服務主體取得已選資源的 **Azure 事件中樞資料擁有者** 權限，並在已選的命名空間下建立兩個事件中樞：

- `insight-logs-audit` 包含 **稽核事件**
- `insight-logs-operational` 包含 **作業事件**

### <a name="log-analytics"></a>Log Analytics

Customer Insights 服務主體取得資源的 **記錄分析參與者** 權限。 記錄將會在選定的 Log Analytics 工作區 **記錄** > **資料表** > **記錄管理** 下方。 展開 **記錄管理** 解決方案，並找到 `CIEventsAudit` 和 `CIEventsOperational` 資料表。

- `CIEventsAudit` 包含 **稽核事件**
- `CIEventsOperational` 包含 **作業事件**

在 **查詢** 視窗中，展開 **稽核** 解決方案，並搜尋 `CIEvents` 找到提供的範例查詢 。

## <a name="event-schemas"></a>事件結構描述

API 事件和工作流程事件有相同的結構以及不同的細節，請參閱 [API 事件架構](#api-event-schema)或[工作流程事件架構](#workflow-event-schema)。

### <a name="api-event-schema"></a>API 事件結構描述

| 欄位             | DataType  | 必要/選用 | Description       | 範例        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | TimeStamp | 是必要欄位          | 事件的時間戳記 (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | 字串    | 是必要欄位          | 發出事件的執行個體其 ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | 字串    | 是必要欄位          | 代表此事件的操作名稱。                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | 字串    | 是必要欄位          | 事件的記錄類別。 `Operational` 或 `Audit`。 所有 POST/PUT/PATCH/DELETE 的 HTTP 要求均會以 `Audit` 標記，其他則都以`Operational` 標記 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | 字串    | 是必要欄位          | 事件的狀態。 `Success`、`ClientError`、`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | 字串    | 選用          | 事件的結果狀態。 如果該作業對應到 REST API 呼叫，則它是 HTTP 狀態碼。        | `200`             |
| `durationMs`      | Long      | 選用          | 作業的期間 (以毫秒為單位)。     | `133`     |
| `callerIpAddress` | 字串    | 選用          | 呼叫者 IP 位址 (如果該作業對應到的 API 呼叫來自公開可見 IP 位址)。                                                 | `144.318.99.233`         |
| `identity`        | 字串    | 選用          | 說明執行作業的使用者或應用程式的身分識別的 JSON 物件。       | 請參閱[身分識別](#identity-schema) 區段。     |  |
| `properties`      | 字串    | 選用          | 對特定類別的事件有更多屬性的 JSON 物件。      | 請參閱[屬性](#api-properties-schema)區段。    |
| `level`           | 字串    | 是必要欄位          | 事件的嚴重性層級。    | `Informational`、`Warning`、`Error` 或 `Critical`。           |
| `uri`             | 字串    | 選用          | 絕對要求 URI。    |               |

#### <a name="identity-schema"></a>身分識別結構描述

`identity` JSON 物件有以下結構

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| 欄位                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | 指派給使用者或應用程式的角色。 如需詳細資訊，請參閱[使用者權限](permissions.md)。                                     |
| `Authorization.RequiredRoles` | 執行作業需要的角色。 `Admin` 角色可以執行所有的作業。                                                    |
| `Claims`                      | 使用者或應用程式 JSON web 權杖 (JWT) 的宣告。 聲明屬性因組織和 Azure Active Directory 設定而異。 |

#### <a name="api-properties-schema"></a>API 屬性結構描述

[API 事件](apis.md)有下列屬性。

| 欄位                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | 有 `ApiEvent` 標示記錄事件為 API 事件。                                                                 |
| `properties.userAgent`       | 瀏覽器代理程式傳送要求或 `unknown`。                                                                        |
| `properties.method`          | HTTP 方法：`GET/POST/PUT/PATCH/HEAD`。                                                                                |
| `properties.path`            | 要求的相對路徑。                                                                                          |
| `properties.origin`          | URI 表示 fetch 的來源或是`unknown`。                                                                  |
| `properties.operationStatus` | `Success` 的 HTTP 狀態代碼 < 400 <br> `ClientError` 的 HTTP 狀態代碼 < 500 <br> `Error` 的 HTTP 狀態 > = 500 |
| `properties.tenantId`        | 組織識別碼                                                                                                        |
| `properties.tenantName`      | 組織的名稱。                                                                                              |
| `properties.callerObjectId`  | 呼叫者的 Azure Active Directory ObjectId。                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>工作流程事件結構描述

工作流程包含多個步驟。 [內嵌資料來源](data-sources.md)、[整合](data-unification.md)、[擴充](enrichment-hub.md)和[匯出](export-destinations.md)資料。 所有的步驟都可以單獨執行，或使用下列程序協調。 

#### <a name="operation-types"></a>作業類型

| OperationType     | 群組                                     |
| ----------------- | ----------------------------------------- |
| 擷取         | [資料來源](data-sources.md)           |
| DataPreparation   | [資料來源](data-sources.md)           |
| 對應               | [資料統整](data-unification.md)   |
| 比對             | [資料統整](data-unification.md)   |
| 執行合併​​             | [資料統整](data-unification.md)   |
| ProfileStore      | [客戶設定檔](customer-profiles.md) |
| 搜尋            | [客戶設定檔](customer-profiles.md) |
| 活動          | [活動](activities.md)                  |
| AttributeMeasures | [客戶細分與量值](segments.md)      |
| EntityMeasures    | [客戶細分與量值](segments.md)      |
| 量值          | [客戶細分與量值](segments.md)      |
| 分割      | [客戶細分與量值](segments.md)      |
| 擴充        | [擴充](enrichment-hub.md)                                          |
| 智慧      | [預測](predictions-overview.md)                                          |
| AiBuilder         | [預測](predictions-overview.md)                                          |
| 深入解析          | [預測](predictions-overview.md)                                          |
| Export            | [匯出](export-destinations.md)                                          |
| ModelManagement   | [預測](custom-models.md)                                           |
| 關聯性      | [資料統整](relationships.md)                                           |

#### <a name="field-description"></a>欄位描述

| 欄位           | DataType  | 必要/選用 | Description                                                                                                                                                   | 範例                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | TimeStamp | 是必要欄位          | 事件的時間戳記 (UTC)。                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | 字串    | 是必要欄位          | 發出事件的執行個體其 ResourceId。                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | 字串    | 是必要欄位          | 代表此事件的操作名稱。 `{OperationType}.[WorkFlow|Task][Started|Completed]`。 請參閱[操作類型](#operation-types)作為參考。 | `Segmentation.WorkflowStarted`，<br> `Segmentation.TaskStarted`， <br> `Segmentation.TaskCompleted`， <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | 字串    | 是必要欄位          | 事件的記錄類別。 工作流程事件永遠是`Operational`                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | 字串    | 是必要欄位          | 事件的狀態。 `Running`、`Skipped`、`Successful`、`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | 選用          | 作業的期間 (以毫秒為單位)。                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | 字串    | 選用          | 對特定類別的事件有更多屬性的 JSON 物件。                                                                                        | 請參閱[工作流程屬性](#workflow-properties-schema)子區段                                                                                                       |
| `level`         | 字串    | 是必要欄位          | 事件的嚴重性層級。                                                                                                                                  | `Informational`、`Warning` 或 `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>工作流程屬性結構描述

工作流程事件有下列屬性。

| 欄位              | Workflow | 工作 | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | .是      | .是  | 有 `WorkflowEvent` 標示的事件為工作流程事件。                                                                                                                                                                                                |
| `properties.workflowJobId`                   | .是      | .是  | 工作流程執行的識別碼。 工作流程執行中的所有工作流程和工作事件都有著相同的 `workflowJobId`。                                                                                                                                   |
| `properties.operationType`                   | .是      | .是  | 作業的識別碼，請參閱 [操作類型]。（#operation 類型）                                                                                                                                                                                       |
| `properties.tasksCount`                      | .是      | 無   | 僅工作流程。 工作流程觸發的工作數。                                                                                                                                                                                                       |
| `properties.submittedBy`                     | .是      | 無   | 選擇性。 僅工作流程事件。 觸發工作流程的[使用者其 Azure Active Directory objectId ](/azure/marketplace/find-tenant-object-id#find-user-object-id)，也請參閱`properties.workflowSubmissionKind`。                                   |
| `properties.workflowType`                    | .是      | 無   | `full` 或 `incremental` 重新整理。                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | .是      | 無   | `OnDemand` 或 `Scheduled`。                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | .是      | 無   | `Running` 或 `Successful`。                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | .是      | .是  | UTC 時間戳記`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | .是      | .是  | UTC 時間戳記`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | .是      | .是  | UTC 時間戳記`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | .是      | .是  | Customer Insights `instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | 無       | .是  | - 對於 OperationType = `Export`，識別碼是匯出設定的 guid。 <br> - 對於 OperationType = `Enrichment`，它是擴充的 guid <br> - 對於 OperationType 是 `Measures`和 `Segmentation`，識別碼是實體名稱。 |
| `properties.friendlyName`                    | 無       | .是  | 匯出的自訂名稱或被處理的實體。                                                                                                                                                                                           |
| `properties.error`                           | 無       | .是  | 選擇性。 包含詳細資料的錯誤訊息。                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | 無       | .是  | 選擇性。 僅供 OperationType `Export`。 識別匯出類型。 如需詳細資訊，請參閱[匯出目的地概觀](export-destinations.md)。                                                                                          |
| `properties.additionalInfo.AffectedEntities` | 無       | .是  | 選擇性。 僅供 OperationType `Export`。 包含匯出中已設定的實體清單。                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | 無       | .是  | 選擇性。 僅供 OperationType `Export`。 匯出的詳細訊息。                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | 無       | .是  | 選擇性。 僅供 OperationType `Segmentation`。 表示客戶細分中成員的總數。                                                                                                                                                    |
