---
title: 新功能以及近期即將推出的功能
description: 關於新功能、改善和 BUG 修正的資訊。
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 9195770255bd798636b9532d6e1ca928345b3708
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376452"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 的觀象見解能力有什麼新發表的功能

我們很高興宣布我們最新的更新！ 本文摘要說明公開預覽功能、正式發行增強功能以及功能更新。 若要查看長期功能計劃，請參閱 [Dynamics 365 和 Power Platform 發行計劃](/dynamics365/release-plans/)。

我們會逐一在各地區推出更新。 因此可能會在特定地區提前看到其他地區尚未推出的功能。 除非另有指示，您不需要採取任何動作，我們會在不停機的情況下自動更新應用程式。

> [!TIP]
> 若要提出功能要求和產品建議並票選，請前往 [Dynamics 365 應用程式想法入口網站](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)。


## <a name="february-2022-updates"></a>2022 年 2 月更新

2022 年 2 月更新內容包括新功能、效能升級和偵錯。

### <a name="general-availability-for-prediction-models"></a>預測模型的正式發行

立即可用的預測模型，其中包括 **訂閱流失**、**交易流失** 和 **客戶存留期值 (CLV)**，在Customer Insights 中正式發行。 

如需詳細資訊，請參閱[預測概觀](predictions-overview.md)。

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>新資料來源：與 Azure Synapse Analytics 整合 (預覽版)

Azure Synapse Analytics 是一項企業分析服務，可加快資料倉儲和大型資料系統的見解生成速度。

如果您的組織已經使用 Azure Synapse Analytics 進階分析功能，並將輸出儲存在 Data Lake 資料庫中，您可以輕易地將這些資料擷取至 Customer Insights。 如需其他資訊，請參閱[連接至 Azure Synapse 資料來源 (預覽)](connect-synapse.md)。

### <a name="liveramp-enrichment-preview"></a>LiveRamp 擴充 (預覽)

LiveRamp 提供確定性的離線身分識別解析和客戶資料的整合。 您可以將客戶資料中的個人識別碼對應至 AbiliTec 標識圖表，並接收 AbiliTec 識別碼。 您可以使用這些識別碼來取得更好的整合客戶資料。

如需詳細資訊，請參閱[使用 LiveRamp 身分識別資料擴充客戶個人資料(預覽版)](enrichment-liveramp.md)。

### <a name="enrichment-for-data-sources-preview"></a>資料來源擴充 (預覽版)

使用來自 Microsoft 和其他合作夥伴等來源的資料，在資料整合前擴充您的客戶資料。 資料來源擴充協助產生更高的資料完整性與品質，當您整合資料後，可取得更好的結果。

如需詳細資訊，請參閱[資料來源擴充 (預覽版)](data-sources-enrichment.md)。

### <a name="change-owner-of-environment"></a>變更環境擁有者

雖然在 Customer Insights 可以有多個使用者擁有系統管理員權限，但是只有一個使用者是環境的負責人。 改進後的體驗可讓您變更環境的負責人，並在先前的負責人離開組織時宣告擁有權。 

如需詳細資訊，請參閱[變更環境的負責人](manage-environments.md#change-the-owner-of-an-environment)。

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>資料準備程序列出損壞記錄的損壞原因

現在，所有資料損壞的欄位，資料準備程序會在個別記錄層級顯示其損壞原因，以便於識別。 

如需其他資訊，請參閱[損壞的資料來源](entities.md#corrupted-data-sources)。

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>參與見解功能中的報表功能結束預覽

 Dynamics 365 Customer Insights 參與見解功能的預覽版已於2022 年 2 月 15 日終止。  
這項變更表示 Customer Insights 試用體驗不再包括建立漏斗圖的能力，也不包含其他報表功能。

我們邀請您探索並評估 [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/)，即 Microsoft 客戶資料平臺 (CDP) ，的其他許多功能。    
 
在轉換期間，現時預覽版的參與者仍然可以存取某些預覽功能：

- 取得程式碼來檢測網站或行動應用程式 
- 查看事件與事件屬性 
- 利用內嵌及精簡事件增強整合個人資料檔，從客戶資料的完整價值中獲益
  
轉換期間，擷取的事件仍會串流至已連線的 Data Lake 中。 關閉此功能後，便會停止在參與見解與對象見解之間的資料共用，且不會將任何新事件傳送至已連線的儲存空間。
如果您對功能預覽版的終止有任何問題，請直接與您的 Microsoft 帳戶團隊聯繫。 您的帳戶團隊將通知您新版的最新消息。 

## <a name="january-2022-updates"></a>2022 年 1 月更新

2022 年 1 月更新內容包括新功能、效能升級和偵錯。

### <a name="sentiment-analysis-of-your-customers-feedback"></a>在您的客戶意見反應上的情感分析

Customer Insights 提供新的 AI 支援功能，可綜合客戶情感並找出特定的業務層面，當作有目標的增進機會。 透過分析您的客戶意見反應，就可以用較低的成本取得準確的深入解析。 由自然語言處理 (NLP) 模型所支援的情感分析，為每個客戶識別碼生成兩個衍生見解。 情感分數 (-5 到 5) 和可適用的業務層面清單。 

如需詳細資訊，請參閱[分析在客戶意見反應中的情感 (預覽版)](sentiment-analysis.md)。


## <a name="december-2021-updates"></a>2021 年 12 月更新

2021 年 12 月更新內容包括新功能、效能升級和偵錯。

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>將 Customer Insights 日誌轉寄至 Azure 監視器

Customer Insights 提供與 Azure 監視器的直接整合。 此功能包括稽核事件和作業事件。 Azure 監視器資源記錄可讓您監控並把記錄傳送至 Azure 儲存體、Azure Log Analytics，或將它們串流至 Azure 事件中樞。

如需詳細資訊，請參閱[使用 Azure 監視器在 Dynamics 365 Customer Insights 中進行日誌轉發 (預覽版)](diagnostics.md)。

### <a name="enrich-customer-profiles-with-engagement-data"></a>使用參與度資料擴充客戶個人資料

使用 Microsoft Office 365 中的資料，經由 Office 365 應用程式以參與度的見解來擴充客戶個人資料。 參與度由電子郵件和會議活動組成，並根據客戶等級進行彙總。 例如，來自商務客戶的電子郵件數量或與該客戶的會議數量。 不會共用個別使用者的任何資料。 此擴充功能只有在英國、歐洲和北美地區才能使用。

如需詳細資訊，請參閱[使用參與度資料擴充客戶設定檔 (預覽版)](enrichment-office.md)。

### <a name="advanced-data-unification-features"></a>進階資料整合功能

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>在個別屬性等級啟用衝突解決策略

當在實體中重複資料刪除客戶記錄時，您可能不想要將完整記錄選為入選方。 現在我們允許您根據每個屬性的規則，從不同記錄合併最合適的欄位。 例如，您可以選擇保留最近的電子郵件，「及」來自不同記錄的最完整地址。 

在單一實體中進行重複資料刪除和合併記錄時，您現在可以為各個屬性定義不同的合併規則。 以前，我們只會讓您選取單一合併規則 (根據新近度資料完整性保留記錄)，而且規則已在記錄等級套用至所有屬性。 當在記錄 A 中找到一些您要保留的資料，而且在記錄 B 中找到其他適當的資料時，過去那種方式並不理想。

如需更多資訊，請見 [定義比對實體的重複資料刪除](match-entities.md#define-deduplication-on-a-match-entity)。

#### <a name="custom-rules-for-matching"></a>適用比對的自訂規則

有時您必須指定一般規則的例外，才能「不要」比對記錄。 當多個人員有夠多的相同資訊，系統將它們比對成單一個體時，就會發生這種現象。 例如，有相同姓氏的雙胞胎，居住在同一個市/鎮，並有著一樣的出生日期。

例外會確保可以在整合規則中處理掉不正確的資料整合。 您可以將多個例外新增至規則。

如需詳細資訊，請參閱[在規則中加入例外](match-entities.md#add-exceptions-to-a-rule).

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>提供其他衝突解決策略，並啟用屬性群組

此功能可讓您將一組欄位當成單一單位處理。 例如，當我們的記錄包含欄位地址 1、地址 2、市/鎮、州/省和郵遞區號時。 想要讓我們的資料變得更加完整，我們可能不想要合併不同記錄的地址 2。

您現在可以組合一組相關的欄位，並將單一合併策略套用至群組。 

如需詳細資訊，請參閱[合併欄位群組](merge-entities.md#combine-a-group-of-fields)。


## <a name="november-2021-updates"></a>2021 年 11 月更新

2021 年 11 月更新內容包括新功能、效能升級和偵錯。

### <a name="segment-membership-now-available-in-dataverse"></a>客戶細分成員資格現在可在 Dataverse 中使用

客戶個人資料的客戶細分成員資格資訊，以及客戶個人資料和見解，現在可在 Dataverse 中使用。 Dynamics 365 動作應用程式和模型導向應用程式可以使用此資料，來查詢特定客戶的客戶細分成員資格詳細資料。

### <a name="activities-support-contact-level-details-for-business-accounts"></a>活動支援商務客戶連絡人層級詳細資料

您現在可以設定、顯示及篩選商務客戶活動時間表中的連絡人活動，以更清楚地瞭解哪些客戶連絡人參與特定活動。

## <a name="october-2021-updates"></a>2021 年 10 月更新

2021 年 10 月更新內容包括新功能、效能升級和偵錯。

### <a name="b-to-b"></a>B 到 B

從 2021 年 10 月開始，在 Customer Insights 中您可以使用商務客戶及其相關連絡人。 在之前，應用程式大多為個人消費者量身訂做。 除了新環境類型，也已更新數個功能區域來支援 B 到 B 案例。 如需已支援的 B 到 B 功能概述，請參閱 [對象見解中的商務客戶](work-with-business-accounts.md)。

下列各節重點節錄了一些關鍵區域，都已修改為可支援商務客戶和個人消費者。

#### <a name="export-segments-based-on-business-accounts"></a>匯出以商務客戶建立的客戶細分

在對象見解中的所有客戶細分匯出均可在商務客戶的內容上使用。 大多數的客戶細分需要額外的設定並且在基礎客戶細分有 [聯絡人資訊投影](segment-builder.md#create-a-new-segment) ，才能用於商務客戶。 如需詳細資訊，請參閱[匯出客戶細分](export-destinations.md#export-segments)。

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>使用 LinkedIn Ads 匯出商務客戶

LinkedIn Ads 匯出現在可對聯絡人目標和公司目標使用商務客戶的內容。 選取公司木邀作為 LinkedIn 匯出主要焦點時，您可以匯出以商務客戶建立的客戶細分，而不需要投影連絡人資訊。 如需詳細資訊，請移至相關文件：[LinkedIn Ads 匯出 ](export-linkedin-ads.md)以及 [連絡人目標 ](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting)與 [公司目標之間的區別 ](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)。 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>根據商務客戶及其階層建立量值

量值建立器可讓您依商務客戶建立量值，並選擇是否使用階層資訊。 階層資訊可用來彙總整個客戶及其相關的所有子客戶中的量值計算。 例如，您可以建立量值，像是由階層定義的每個商務客戶群組的總收入。 如需詳細資訊，請見 [定義和管理量值](measures.md)。

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>根據商務客戶及其階層建立客戶細分

客戶細分建立器可讓您建立商務客戶的客戶細分，並可選擇客戶細分中是否每個客戶都包括連絡人資訊。 如果您已設定客戶階層，您可以在客戶細分建立時使用客戶階層資訊。 如需詳細資訊，請參閱[建立新客戶細分](segment-builder.md#create-a-new-segment)。

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>利用流失趨勢的深入見解來保留您的商務客戶

客戶流失預測模型現在也支援商務客戶。 您可以評估不只是對客戶造成的流失風險，而不只是客戶，也包括客戶和購買產品或服務類別的組合。 這項新增功能可協助瞭解您的客戶是否很有可能停止大部分的購買或只停止特定類別的貨物或服務。 為進一步協助您使用此 AI 模型，這項功能也會列出客戶可能發生改動的原因。 如需詳細資訊，請參閱 [預測交易流失 (預覽版) ](predict-transactional-churn.md)。

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>在客戶檢視表中查看商務客戶連絡人

如果商務客戶對應至相關的客戶，則 Customer Insights 應用程式會在客戶詳細資料檢視表中顯示這些相關連絡人。 如需詳細資訊，請參閱[客戶個人資料](customer-profiles.md)。


## <a name="september-2021-updates"></a>2021 年 9 月更新

2021 年 9 月更新內容包括新功能、效能升級和偵錯。

### <a name="activities"></a>活動

- **活動時間表改善** 我們已經延伸客戶設定檔上的活動時間表篩選條件。 此外您可以使用新盤形篩選條件依活動類型和日期篩選。 日期可使用不同條件篩選。 如需詳細資訊，請參閱[在客戶設定檔上查看活動時間表](activities.md#view-activity-timelines-on-customer-profiles)。

### <a name="relationships"></a>關係

- **多重跳接式關聯支援** 組態活動和定義實體之間的關聯時，請使用多重跳接式關聯。 多重跳接式關聯使用中間實體連接兩個實體。 組態活動時，您可以使用多重跳接式關聯將活動實體連接到中間實體，然後客戶實體。 您可以結合多重跳接式關聯與多重路徑關聯。 如需詳細資訊，請參閱[多重跳接式關聯](relationships.md#multi-hop-relationship)。

- **多重路徑關聯支援** 組態活動和定義實體之間的關聯時，請使用多重跳徑關聯。 多重路徑關聯將來源實體與一個以上的實體產生關聯。 組態活動時，您可以使用多重路徑關聯將活動實體連接到一個以上的客戶實體。 您可以結合多重路徑關聯與多重跳接式關聯。 如需詳細資訊，請參閱[多重路徑關聯](relationships.md#multi-path-relationship)。

## <a name="august-2021-updates"></a>2021 年 8 月更新

2021 年 7 月及 8 月的更新包含新功能、效能升級和 BUG 修正。

### <a name="extensibility"></a>擴充性

- **將客戶細分匯出至 Klaviyo** 我們已擴充 [匯出目標，加入了Klaviyo](export-klaviyo.md)。 您在可以匯出客戶細分來建立行銷活動、執行電子郵件行銷，並且搭配 Klaviyo 使用特定客戶群組。 


## <a name="june-2021-updates"></a>2021 年 6 月更新

2021 年 6 月更新包含數項功能、效能升級和 BUG 修正。

### <a name="data-ingestion"></a>資料擷取

- **已改善的資料整合程序更新** 您現在可以在[資料整合程序](data-unification.md)步驟中，查看更精細、改善後的動態狀態更新。 此功能可讓您追蹤詳細的進度，以了解程序流程，並在任何步驟需要處理時採取行動。

### <a name="extensibility"></a>擴充性

- **將客戶細分和其他資料匯出至 Salesforce Marketing Cloud** 我們已擴充匯出目標，加入了 [Salesforce Marketing Cloud](export-salesforce.md)。 您現在可以透過署名的 SFTP 匯出，將客戶細分和其他類型的資料匯出至 Salesforce 行銷雲Salesforce Marketing Cloud。 在 Salesforce 中資料匯入會以全自動化方式進行，並用於建立更有效率的行銷廣告活動。  
 
- **將客戶細分匯出至 ActiveCampaign** 我們已擴充匯出目標，加入了 [ActiveCampaign](export-active-campaign.md)。 您在可以匯出客戶細分來建立行銷活動、執行電子郵件行銷，並且用在 ActiveCampaign 中的客戶特定群組。
 
- **將客戶細分匯出至 Sendinblue** 我們已擴充匯出目標，加入了 [Sendinblue](export-sendinblue.md)。 您在可以匯出客戶細分來建立行銷活動、執行電子郵件行銷，並且搭配 Sendinblue 用在客戶特定群組。
 
### <a name="ux-updates"></a>UX 更新 

- **全新並增強的客戶頁面與個人資料詳細資料頁面** 我們重新設計了客戶頁面及個人資料詳細資料頁面，以改善使用者體驗和增加效能。 這些變更讓您可以您查看、排序、搜尋及篩選客戶。 篩選現在表示在 URL 中，可流暢地與其他使用者共用搜尋結果。 搜尋結果也可以儲存為客戶細分。    
  客戶個人資料的詳細資料頁面現在會把資料分組在不同小節中 (如人口統計資料、識別碼及其他配置個人資料屬性)中，來改善可讀性。 個人資料詳細資料頁面上的其他區段現在更具互動性。 例如，活動分段允許篩選和排序。


## <a name="may-2021-updates"></a>2021 年 5 月更新

2021 年 5 月的更新包括幾種功能、效能升級和 bug 修正。

### <a name="data-ingestion"></a>資料擷取

- **附加來自 Azure Data Lake Storage 的資料時查看或修改中繼資料或實體定義**，從 Azure Data Lake Storage 的 Common Data Model 資料夾附加資料時，您現在可以查看和編輯對象見解中的中繼資料或實體定義 。 此功能提供即時意見反應、模型驗證及錯誤檢查。 它可讓您順暢地編輯 model.json 和 manifest.json。

### <a name="extensibility"></a>擴充性

- **改進的客戶細分匯出、自訂排程和重複值** 現在您可以在清單中[看到特定客戶細分的所有匯出](export-destinations.md#view-exports-and-export-details)。 這個新的檢視表可協助管理指定客戶細分的使用方式並調整現有匯出或建立新匯出。    
  您可以為個別匯出[定義自訂重新整理排程](export-destinations.md#schedule-and-run-exports)，或一次為複數匯出定義。 到目前為止，所有的匯出都是在每次系統重新整理時執行。    
  您可以依據現有匯出來建立新匯出，而不需從頭開始建立新的匯出。

- **將客戶細分匯出至 Microsoft Advertisingt** 我們已擴展了匯出目的地，現在包括 Microsoft Advertising。 使用整合客戶個人資料在 Microsoft Advertising 上建立「客戶比對」對象，並對這些對象使用 Advertising 行銷活動。 如需詳細資訊，請參閱 [將客戶細分匯出至 Microsoft Advertising](export-microsoft-advertising.md)。

- **將客戶細分匯出至 LinkedIn Ads** 我們擴展了匯出目的地，包括 LinkedIn Ads，匯出您的整合客戶個人資料，便可讓您透過 linkedin 解鎖連絡人鎖定，以及公司鎖定。 如需詳細資訊，請參閱[將客戶細分匯出至 LinkedIn Ads](export-linkedin-ads.md)。


- **將客戶細分匯出至 Omnisend** 我們已擴展了匯出目的地，現在包括 Omnisend。 使用在對象見解中建立的客戶細分來建立行銷活動、提供電子郵件行銷，並且以 Omnisend 使用特定客戶群組。 如需詳細資訊，請參閱 [將客戶細分匯出至 Omnisend](export-omnisend.md)

### <a name="predictions"></a>預測

- **輸入資料可用性報表** 輸入資料可用性報表提供整合檢視表，指出立即可用預測可能產生的錯誤和警告。 它也提供如何改善模型效能的建議。    
  在模型完成其定型程序之後，才可使用此報表。 它是單獨為每個模型建立的，不管是否成功完成。
  目前，此功能只適用在交易流失模型。 如需詳細資訊，請參閱[輸入資料可用性報表](manage-predictions.md#input-data-usability-report)。

### <a name="relationships"></a>關聯性

- **關聯視覺化檢視** 關聯視覺化檢視可讓您查看實體之間的所有現存關聯與其基數。 關聯現在是以群組分類：使用者建立、系統和繼承的關聯。 您也可以將匯出檢視表為影像。 如需詳細資訊，請參閱[查看關聯](relationships.md#view-relationships)。 

## <a name="april-2021-updates"></a>2021 年 4 月更新

2021 年 4 月的更新包括幾種功能、效能升級和 bug 修正。

### <a name="data-unification"></a>資料統整
 
- **增強了資料整合的合併體驗**    
  
   現在，在資料整合程序的合併設定中，我們有了更好的使用者體驗。 變更包括合併欄位的直覺排序功能，以及結合和單一欄位的詳細統計資料。

- **實體重新排序，並把所有來源記錄設定到客戶實體**  
      
   您現在可以在資料整合處理程序中，從現有的合併方案中重新排序和移除實體。 根據業務需求，它可讓您在比對程序中更靈活地重新排序實體。 此外，我們啟用了在最終的 *客戶* 實體中包含所有未比對的紀錄，讓他們定義其客戶個人資料的資料集定義。

### <a name="enrichments"></a>擴充

 - **新擴充：增強地址**    
  
   我們很高興引進新的擴充來增強客戶資料中的地址。 資料中的地址可能未結構化、不完整或不正確。 此功能使用 Microsoft 的模型，將您的地址標準化並擴充為 Common Data Model 格式，以獲得更良好的準確性和洞察力。
 
   如需詳細資訊，請參閱[以增強地址擴充客戶個人資料](enrichment-enhanced-addresses.md)。

- **擴充的引導式設定體驗**    
  
   我們以簡單的引導式體驗重新設計了擴充的設定體驗。 現在有一個清楚的逐步程序，來建立和編輯擴充。
 
   此外，我們分離了協力廠商擴充的連接設定，啟用以相同連接多個擴充。 只有系統管理員才可以設定新的連接，但其建立的連接可供系統管理員和參與者使用。    

   如需詳細資訊，請參閱[連接概觀](connections.md)。

- **多個相同類型的擴充**    
  
   現在，我們允許使用者建立和管理相同擴充類型中的多個擴充。 例如，您現在可以建立兩個獨立的地址擴充，以擴充兩個不同的客戶區段。 會限制相同類型擴充可以建立多少個，此限制因為類型不同而有所不同。
  
   如需詳細資訊，請參閱[客戶設定檔的擴充](enrichment-hub.md)。

## <a name="march-2021-updates"></a>2021 年 3 月的更新

2021 年 3 月的更新包括幾種功能、效能升級和 bug 修正。

### <a name="activities"></a>活動

- **活動精靈和語義類型**

   我們已改善並更新了活動對應體驗，以引導並簡化活動對應的建立。 在此新體驗中，使用者會取得引導式體驗，協助完成每個程式步驟。 在活動對應步驟中，除了選擇許多活動類型之外，使用者還可以選擇以語意方式將 *訂閱* 和/或 *SalesOrderLine* 的資料對應至可在下游運用的產業標準結構描述。   

   如需詳細資訊，請參閱[客戶活動](activities.md)。

### <a name="data-ingestion"></a>資料擷取

- **使用 Power Platform 資料流程和閘道來連接至內部部署資料來源** 我們非常高興地公開預覽版：Power Platform 資料流程及在 Customer Insights 中與關聯 Power Platform 或 Dataverse 的環境使用閘道的內部部署連線。 在連接至 Dataverse 環境的 Customer Insights 環境中建立任何新的資料來源，都會預設為 Power Platform 資料流程，會導入內部部署資料連線以及一組豐富的連接器和轉換功能。

### <a name="extensibility"></a>擴充性

- **匯出彙整到「連接」和「匯出」中** ，我們已將 **匯出目的地** 頁面的名稱變更為 **連接**，並為 **匯出** 新增一個獨立的頁面。 在此更新中，我們將現有的匯出轉換為成對的連接以及使用該連接的匯出。 系統管理員現在對 **連接** 頁面上即將送出的資料更加清楚。 所有使用者角色都具備 **匯出** 頁面的存取權，但是只有系統管理員可以選擇參與者來編輯已共用連接的特定匯出。     
  如需詳細資訊，請參閱[連接概述](connections.md)和[匯出概述](export-destinations.md)。

- **將客戶細分匯出至 Campaign Monitor** 我們已擴展了匯出目的地，現在包括 Campaign Monitor。 您現在可以從 Customer Insights 將客戶細分匯出至 Campaign Monitor 清單，並用來當作行銷廣告活動的基準。    
   如需詳細資訊，請參閱[匯出資料至 Campaign Monitor](export-campaign-monitor.md)。

- **將客戶細分匯出至 Constant Contact** 我們已擴展了匯出目的地，現在包括 Constant Contact。 您現在可以從 Customer Insights 將客戶細分匯出至 Constant Contact 清單，並用來當作行銷廣告活動的基準。   
   如需詳細資訊，請參閱[匯出資料至 Constant Contact](export-constant-contact.md)。

- **將客戶細分匯出至 RollWorks** 我們已擴展了匯出目的地，現在包括 RollWorks。 您現在可以從 Customer Insights 匯出區段到 RollWorks 對象，並將它們用做您刊登 B 到 B 廣告的基準線。    
   如需詳細資訊，請參閱[匯出資料至 RollWorks](export-rollworks.md)。

- **將客戶細分匯出至 Snapchat** 我們已擴展了匯出目的地，現在包括 Snapchat。 您現在可以從 Customer Insights 將客戶細分匯出至 Snapchat 對象，並用來當作廣告的基準。     
   如需詳細資訊，請參閱[匯出資料至 Snapchat](export-snapchat.md)。

### <a name="predictions"></a>預測

- **在預測產品建議中使用產品篩選** 我們在產品建議模型中新增了產品篩選的能力。 您現在可以只使用一部分產品建立預測。    
   如需詳細資訊，請參閱[設定產品篩選](predict-product-recommendation.md#configure-product-filters)。

- **從模型預測建立客戶細分** 我們新增了使用預測模型結果來建立客戶細分的快速方式。 從模型結果頁面中，您可以選取 **新的建立客戶細分** 選項，輕易地建立新的客戶細分。    
  如需詳細資訊，請參閱[根據預測模型建立客戶細分](prediction-based-segment.md)。

- **產品建議的解釋** 我們新增了一些資訊，解釋了生成產品建議時 AI 模型學習到的主要因素，以及這些因素對產品建議的影響程度。 此資訊會新增到模型結果畫面。    
   如需更多資訊，請見 [評論預測狀態和結果](predict-product-recommendation.md#review-a-prediction-status-and-results)。

## <a name="february-2021-updates"></a>2021 年 2 月更新

2021 年 2 月更新包含數個功能、效能升級和 BUG 修正。

#### <a name="extensibility"></a>擴充性

- **將客戶細分匯出至 AdRoll**

  我們的匯出目的地成功擴展，包括 AdRoll 了。 您現在可以從 Customer Insights 匯出客戶細分到 AdRoll 對象，並把它當成廣告的基準。 如需更多資訊，請見 [AdRoll 連接器](export-adroll.md)。

#### <a name="segments"></a>客戶細分
 
- **複製客戶細分**
  
  要基於現有客戶細分建立新的客戶細分，您現在可以複製一個客戶細分並透過編輯複製完成的客戶細分進一步優化它。 

- **新增其他屬性到客戶細分**

  您現在可以把屬性包含進客戶細分輸出中，即使這些屬性不是客戶個人資料的一部分。 例如，將訂閱識別碼包括在一個客戶細分中，即使它是訂閱實體的一部分，而該實體與客戶實體有 M:1 關係。 只要屬性屬於與客戶實體相關的實體，您現在就可以把這些屬性包含進去。  

#### <a name="predictions"></a>預測

- **建立預測的產品建議**

  以個人化和業務開發提高公司收入和建立客戶忠誠度，了解客戶有興趣購買什麼是必須的最初步驟之一。 提供的產品建議不符合客戶興趣可能會在客戶與公司之間產生隔閡感，並最終限制客戶的整體潛在收入和體驗。 

  使用您自己的數據，您現在可以對客戶未來可能購買的產品建立預測。 想瞭解更多資訊，請參閱[產品建議預測](predict-product-recommendation.md)。

#### <a name="system-administration"></a>系統管理

- **複製環境支援更多類型的資料來源**

  系統管理員可以將環境組態複製到在同一組織中的新環境中。 此功能會針對資料來源是基於 Microsoft Dataverse使用受管理的 Data Lake 或Common Data Model 資料夾的案例，擴充複製環境功能。

## <a name="january-2021-updates"></a>2021 年 1 月更新

2021 年 1 月更新包含數個功能、效能升級和 BUG 修正。

#### <a name="extensibility"></a>擴充性

- **SFTP 匯出的擴充功能和增強效能** 您現在可以將 Customer Insights 的所有輸出實體匯出至 SFTP 主機。 先前，匯出會限制在客戶細分實體。 此外，SFTP 匯出的效能可讓您以較少的時間完成更多的資料量，視您的 SFTP 主機效能而定。    
  如需更多資訊，請見 [ SFTP 的連接器 (預覽版)](export-sftp.md)。  

#### <a name="segments"></a>客戶細分

- **用機器學習支援建議的客戶細分以改善指標** 一種新的方式來探索並建立客戶細分。 系統會使用 AI 模型來建議客戶細分，這有助於改善正在追蹤的 KPI (量值)。 我們會顯示您選取的屬性在量值或另一個主要屬性上的影響程度。 此資訊可協助尋找存在商機的潛在客戶細分。    
  如需更多資訊，請見[建議的客戶細分 (預覽版)](suggested-segments.md)。

#### <a name="data-unification"></a>資料統整

- **增強的比對體驗** 在資料整合區域中，已更新比對體驗。 它可讓您設定並查看比對規則，包括能進一步說明比對運作方式的統計詳細資料。 有一些選項可停用比對規則，所以在保留設定、拖放比對規則或更多作業時，它已不再可以使用。
  如需詳細資訊，請參閱[比對實體](match-entities.md)。

- **來自比對程序中的重複資料刪除輸出可作為實體使用** 來自比對程序中的重複資料刪除輸出現在會寫入另一個實體中，提供進一步分析使用。 這個實體包含在重複資料刪除程序中使用的欄位，以及勝出記錄，以及與勝出記錄合併的對應替代記錄。
  如需更多資訊，請見[重複資料刪除輸出實體](match-entities.md#deduplication-output-as-an-entity)。

#### <a name="system-administration"></a>系統管理

- **將資料無縫共用給 Microsoft Dataverse** 您現在可以使用 Microsoft Dataverse Managed Data Lake 共用 Customer Insights 輸出給 Microsoft Dataverse 應用程式。 在您將 Dataverse 環境與 Customer Insights 關聯之後，便有啟用資料共用的選項。
  如需詳細資訊，請參閱[管理環境](manage-environments.md)。




[!INCLUDE[footer-include](../includes/footer-banner.md)]