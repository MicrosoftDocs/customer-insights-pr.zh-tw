---
title: Customer Insights API 的 OData 查詢範例
description: 開放式資料通訊協定 (OData) 查詢 Customer Insights API 以檢閱資料的常用範例。
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387192"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Customer Insights API 的 OData 查詢範例

開放式資料通訊協定 (OData) 是建立在核心通訊協定 (例如 HTTP) 的資料存取通訊協定。 它使用普遍接受的方法 (例如網站的 REST)。 有多種可用來使用 OData 服務的程式庫和工具。

為了協助您根據 [Customer Insights API](apis.md) 建立自己的實作，請檢閱一些經常要求的範例查詢。

修改查詢範例，使其在目標環境中運作：

- {serviceRoot}：`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` ，其中 {instanceId} 是您要查詢的 Customer Insights 環境的 GUID。 [ListAllInstances 作業](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)可尋找您有權存取的 {InstanceId}。
- {CID}：整合客戶記錄的 GUID。 範例：`ce759201f786d590bf2134bff576c369`。
- {AlternateKey}：資料來源中，客戶記錄的主索引鍵識別碼。 範例: `CNTID_1002`
- {DSname}：包含資料來源的實體名稱的字串，該資料來源已內嵌至 Customer Insights。 範例：`Website_contacts`。
- {SegmentName}：包含 Customer Insights 的客戶細分輸出實體名稱的字串。 範例：`Male_under_40`。

## <a name="customer"></a>客戶

對 *客戶* 實體的範例查詢。

|查詢類型 |範例  | Note  |
|---------|---------|---------|
|單一客戶識別碼     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|其他索引鍵    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  其他索引鍵會保留在整合的客戶實體中       |
|選擇   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|於    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|其他索引鍵 + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|搜尋  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   回傳搜尋字串的前 10 個結果      |
|客戶細分成員資格  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | 從客戶細分實體中回傳預設的列數。      |
|客戶的客戶細分成員資格 | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | 如果使用者是指定客戶細分的成員，則傳回客戶設定檔     |

## <a name="unified-activity"></a>整合活動

對 *UnifiedActivity* 實體的範例查詢。

|查詢類型 |範例  | Note  |
|---------|---------|---------|
|CID 活動     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | 列出特定客戶個人資料的活動 |
|活動時間範圍    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  時間範圍中的客戶個人資料活動       |
|活動類型    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|活動 (依顯示名稱)     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|活動排序    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  以遞增或遞減排序活動       |
|從客戶細分成員資格展開的活動  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>其他範例

對其他實體的範例查詢。

|查詢類型 |範例  | Note  |
|---------|---------|---------|
|CID 的量值    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|CID 擴充品牌    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|CID 的興趣擴充    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-子句 + 展開     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>不支援 OData 查詢

Customer Insights 不支援下列查詢：

- 在已擷取的來源實體上進行 `$filter`。 您只能對 Customer Insights 建立的系統實體執行 $filter 查詢。
- 從 `$search` 查詢進行 `$expand`。 範例: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- 選取了屬性的子集時才能從 `$select` 進行 `$expand`。 範例: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- 對給定客戶 `$expand` 擴充品牌或興趣相似性。 範例: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- 透過其他索引鍵查詢預測模型輸出實體。 範例: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
