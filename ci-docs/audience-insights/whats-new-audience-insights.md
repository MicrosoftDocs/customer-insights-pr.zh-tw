---
title: 新功能以及近期即將推出的功能
description: 關於新功能、改善和 BUG 修正的資訊。
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2020
ms.locfileid: "4649994"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 的觀象見解能力有什麼新發表的功能

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

我們很高興宣布我們最新的更新！ 本文摘要說明公開預覽功能、正式發行增強功能以及功能更新。 若要查看長期功能計劃，請參閱 [Dynamics 365 和 Power Platform 發行計劃](https://docs.microsoft.com/dynamics365/release-plans/)。

您也可以觀看下列影片，多瞭解過去六個月已規劃的功能。

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

我們會逐一在各地區推出更新。 因此可能會在特定地區提前看到其他地區尚未推出的功能。 除非另有指示，您不需要採取任何動作，我們會在不停機的情況下自動更新應用程式。

> [!TIP]
> 若要送出和票選功能要求和產品建議，請前往 [Dynamics 365 應用程式想法入口網站](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)。

## <a name="november-2020-updates"></a>2020 年 11 月更新

2020 年 11 月的更新包括數項功能、效能升級和 BUG 修正。

### <a name="new-and-updated-features-in-november-2020"></a>2020 年 11 月的全新和更新功能

#### <a name="data-enrichment"></a>資料擴充

- **透過安全檔案傳輸通訊協定 (SFTP) 自訂匯入您自己的富集資料**
  
  安全檔案傳輸通訊協定 (SFTP) 讓您匯入毋須經歷資料統整流程的富集資料。 了解更多關於 SFTP 自訂匯入。

  如需更多資訊，請見 [使用自訂資料富集客戶設定檔 (預覽版)](enrichment-SFTP-custom-import.md)。
 
- **使用源自 HERE Technologies 的位置資料富集您的客戶資料**

  您可以使用 HERE Technologies 的資料富集服務建立對您客戶位址正規化、緯度和經度擷取等更精確的位置瞭解。 了解更多關於使用 HERE Technologies 進行富集。

  如需更多資訊，請見 [使用 HERE Technologies 富集客戶設定檔](enrichment-here.md)。

#### <a name="data-unification"></a>資料統整

- **在選取實體上和您的儲存體帳戶欄位啟用資料剖析的彈性**

  您可以指出位於您的 Azure Data Lake Storage 帳戶中，您想要啟用資料內嵌流程其中一部分的資料剖析功能的 Common Data Model 資料實體和欄位。

  如需更多資訊，請見 [連接到 Common Data Model 資料夾](connect-common-data-model.md#connect-to-a-common-data-model-folder)。

#### <a name="extensibility"></a>擴充性

- **透過 Google Ads 啟動您的區段**

  將區段匯出到 Google Ads 對象清單並用在 Google Search、Google Display Network、YouTube 和 Gmail 上刊登廣告。 瞭解更多關於透過 Google Ads 啟動您的區段的資訊。

  如需更多資訊，請見 [Google Ads 連接器](export-google-ads.md)。

- **透過 Marketo 啟動您的區段**

  將區段匯出到 Marketo 觀眾並使用這些對象進行行銷自動化。 瞭解更多關於透過 Marketo 啟動您的區段的資訊。 

  如需更多資訊，請見 [Marketo 連接器](export-marketo.md)。

- **透過 DotDigital 啟動您的區段**

  將區段匯出到 DotDigital 並用於行銷目的。 瞭解更多關於透過 DotDigital 啟動您的區段的資訊。 

  如需更多資訊，請見 [DotDigital 連接器](export-dotdigital.md)。

#### <a name="predictions"></a>預測

- **預測交易性流失**

  交易流失預測功能讓您不需要資料科學家就能預測客戶停止購買產品或服務的可能性。  您可以使用預測分數結合有關客戶的其他資訊，像是客戶價值，建立高流失風險或高價值客戶的區段。 使用此區段直接透過行銷活動、客戶支援及其他案例鎖定客戶的目標以降低流失風險。
 
  將流失的定義組態為您業務專屬的時間型視窗，定義客戶視同為已流失的時間點。 例如假使雜貨店裡的顧客未能在過去 30 天內購買任何產品，雜貨店可能想認定已流失客戶。
 
  由於您繼續建立預測，因此我們將引導您掌握需要的資料，並讓您將有關業務的資料對應到需預測您客戶流失的欄位。 您也可以根據系統中的新資訊設定排程重新培養模型，以適應不斷變動的業務環境。
 
  如需更多資訊，請見 [交易性流失預測 (預覽版)](predict-transactional-churn.md)。

#### <a name="system-administration"></a>系統管理

- **重設環境**

  將選取執行個體環境中的一切重新設定為開始重新整理。

  如需更多資訊，請見 [重新設定現有環境](manage-environments.md#reset-an-existing-environment)。


- **使用服務主體連接到您的 Azure Data Lake Storage 帳戶**

  使用 Azure 服務主體將資料輸出寫入您的儲存體帳戶並讀取資料。 現有儲存體帳戶連接可繼續使用帳戶金鑰。 它們也會提供升級選項，以便繼續使用服務主體。 新連接將根據您的儲存體帳戶服務主體驗證方法進行。

  更多資訊請見 [使用 Azure 服務主體對象見解連接到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。

## <a name="october-2020-updates"></a>2020 年 10 月更新

2020 年 10 月的更新包括數項功能、效能升級和 BUG 修正。

### <a name="new-and-updated-features-in-october-2020"></a>2020 年 10 月的全新和更新功能

#### <a name="extensibility"></a>擴充性

- **匯出到 Mailchimp**

將區段匯出到 Mailchimp 中的現有對象清單，以便為您的客戶提供個人化的電子郵件體驗。

如需更多資訊，請見 [Mailchimp 連接器](export-mailchimp.md)。

#### <a name="data-enrichment"></a>資料擴充

- **重複資料刪除比對實體中的來源記錄**

針對比對流程使用的實體指定重複資料刪除規則，以便找出重複記錄。 將它們合併為一筆記錄並將所有來源記錄連結到此合併記錄。 接著這筆重複遭刪除的記錄將用在跨實體比對流程。

如需更多資訊，請見 [定義比對實體的重複資料刪除](match-entities.md#define-deduplication-on-a-match-entity)。

#### <a name="system-administration"></a>系統管理

- **協調流程：Merge 中的新重新整理選項**

截至今天為止，當您執行合併流程時，系統已執行過所有以合併及後續流程為主的下游流程。 您現在可以審核合併流程 (統整的客戶實體) 的輸出，再將它用在下游處理像是區段或量值。
您現在可以在合併頁面上選擇只執行合併步驟及此道流程。 若是也要重新整理所有下游流程，您可以選擇執行合併和下游流程。 

## <a name="september-2020-updates"></a>2020 年 9 月更新

2020 年 9 月更新包含數項功能、效能升級和 BUG 修正。

### <a name="new-and-updated-features-in-september-2020"></a>2020 年 9 月的新增及更新功能

#### <a name="activities"></a>活動

- **屬性語意智慧預測**

這項新功能可預測傳遞給資料統合程序的輸入屬性語意類型。 採用可改善準確性和節省時間的機器學習模型。

#### <a name="enrichments"></a>擴充

- **Experian 的人口統計擴充內容**

Experian 的人口統計擴充內容現已開放預覽。 Experian 是消費者與企業信用報告以及行銷服務的全球領導者。 有了 [Experian 的資料擴充服務](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)，您就可以透過人口統計資料 (例如家庭人數、收入及其他) 擴充您的客戶設定檔，加深對客戶的了解。

若要使用此功能，您必須已加入有效的 Experian 訂閱。

如需詳細資訊，請參閱[使用 Experian 提供的人口統計資料擴充客戶設定檔](enrichment-experian.md)


#### <a name="system-administration"></a>系統管理

- **工作詳細資料窗格**

工作詳細資料窗格可讓您查看有關系統所執行工作的詳細資料。 這是識別問題和尋找解決方案的便捷方式。
檢閱錯誤訊息，以了解如何處理潛在問題。
 
- **處理新已增至其他頁面的資訊**

這項改善會在 **實體** 和 **客戶** 頁面上新增有關實體狀態的資訊。
 
此外，您還可以在這兩個頁面上找到有關處理進度的詳細資訊，以及工作詳細資料。

- **系統狀態頁面的改善**

我們已改進 **系統** > **狀態** 上的狀態詳細資料表格在檢閱資料匯出時的結構。
 
此外，**詳細資料** 欄中的錯誤現在更加詳細且可操作。 
 
- **取消將工作還原為先前狀態**

取消工作時 (例如，在比對程序中)，工作會還原為其最近一次的狀態。 例如，如果比對程序在昨天完成，而您今天將其取消，則此工作會還原為昨天的成功狀態。


## <a name="august-2020-updates"></a>2020 年 8 月更新

2020 年 8 月更新包含數項功能、效能升級和 BUG 修正。

### <a name="new-and-updated-features-in-august-2020"></a>2020 年 8 月的新增及更新功能

#### <a name="data-unification"></a>資料統整

- **改善資料統合期間對應階段的體驗**

  資料統合程序中對應階段的體驗可讓您選取實體、屬性，並以更加流暢的方式來定義語意。

  這些變更包括：
  
  - 新增實體與欄位所需的互動較少
  - 改善對應頁面上的搜尋功能
  - 直觀且易於識別建議的欄位類型

#### <a name="enrichment"></a>擴充

- **其他市場中提供的興趣相關擴充內容**

  我們正在將興趣相關擴充內容的供應範圍擴展到五個美國以外的其他市場：加拿大、澳大利亞、英國、法國和德國。 經過此次供應範圍擴大後，您就可以使用適用於這些市場的其他興趣來充實您的客戶資料。 我們也會使用 Microsoft Graph 的當地專有資料專，擴充您位於這些市場的客戶設定檔。
  如需詳細資訊，請參閱[使用品牌及興趣同質性擴充客戶設定檔](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>2020 年 7 月更新

2020 年 7 月更新包含數項功能、效能升級和 BUG 修正。

### <a name="new-and-updated-features-in-july-2020"></a>2020 年 7 月的新增及更新功能

#### <a name="extensibility"></a>擴充性

- **已完成的統整程序的 Power Automate 觸發程序**

  我們已擴充 Power Automate 的觸發程序，並且允許您在統整程序 (對應、比對、合併) 重新整理完成時，建立通知或動作。    
  如需詳細資訊，請參閱[Power Automate 連接器](export-power-automate.md)

#### <a name="enrichment"></a>擴充

- **其他市場中提供的品牌同質性擴充內容**

  我們將延伸品牌同質性擴充內容的可用性到美國以外的五個其他市場：加拿大、澳大利亞、英國、法國和德國。 隨著此次延伸，您可以使用這些市場中的當地品牌來擴充客戶資料。 我們也會使用 Microsoft Graph 的當地專有資料專，擴充您位於這些市場的客戶設定檔。
  如需詳細資訊，請參閱[使用品牌及興趣同質性擴充客戶設定檔](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>2020 年 6 月更新

2020 年 6 月更新包含數項功能、效能升級和 BUG 修正。

### <a name="new-and-updated-features-in-june-2020"></a>2020 年 6 月的新增及更新功能

#### <a name="enrichment"></a>擴充

- **Leadspace 提供的公司資料擴充**
  
  定義統整客戶設定檔中的欄位，這些欄位可用來向 Leadspace 查詢相關的公司資料。 執行擴充程序之後，B2B 設定檔會使用其他屬性 (包括公司大小、地點、行業及其他) 來進行擴充。    
  此共同作業可讓您利用協力廠商服務提供的資訊來改善資料品質。 若要使用此擴充內容，您需要 Leadspace 的授權，才能存取其 B2B 公司資料。 系統將使用該授權保持您的資料不斷富集。    
  如需詳細資訊，請參閱 [使用 Leadspace 的公司設定檔擴充](enrichment-leadspace.md)。

- **擴充中心頁面**

  第一方和第三方擴充內容提供者的所有可用資料擴充都是在同一個位置進行設定。 設定資料擴充是從共同位置管理的順暢體驗。    
  如需詳細資訊，請參閱[客戶設定檔的擴充](enrichment-hub.md)。

- **個別品牌及興趣同質性擴充**

  品牌及興趣同質性現在可當做兩個獨立的擴充內容來使用。 分開的擴充內容可讓您靈活地根據業務需求或需要個別加以設定和管理。    
  如需詳細資訊，請參閱[使用品牌及興趣同質性擴充客戶設定檔](enrichment-microsoft-graph.md)。

#### <a name="extensibility"></a>擴充性

- **Dynamics 365 Customer 卡片增益集上的統整活動的可點選 URL**

  如果活動組態期間已定義此類 URL，則客戶卡增益集中的統整活動現在就會顯示可點按的 URL。    
  如需詳細資訊，請參閱[客戶卡片增益集](customer-card-add-in.md)。

- **Dynamics 365 客戶卡片增益集中可用的品牌及興趣同質性**

  Dynamics 365 客戶卡片增益集的新控制項可讓您在 Dynamics 365 的客戶參與應用程式中顯示有關連絡人的品牌及興趣擴充內容。    
  如需詳細資訊，請參閱[客戶卡片增益集](customer-card-add-in.md)。

- **其他 Power Automate 觸發程序**

  我們已擴充 Power Automate 的觸發程序，並新增下列觸發程序：
  - 在自動化完整重新整理 (資料來源、統整、客戶細分、量值、匯出) 完成時，取得通知或執行動作
  - 定義業務量值的閾值。 例如，您可以建立會在越過定義的閾值時傳送的通知。 此外，觸發程序還會提供可讓您在 Power Automate 中建置更複雜工作流程的資訊 。    
  如需詳細資訊，請參閱[Power Automate 連接器](export-power-automate.md)

- **匯出至 Facebook 廣告管理員**
  
  此功能讓您將區段匯出到 Facebook Ads 管理員。 區段匯出為自訂對象，在 Facebook 行銷廣告活動和廣告中使用統整的客戶設定檔。 自訂對象也適用在 Instagram 中透過 Facebook 廣告管理員建立行銷活動。    
  如需詳細資訊，請參閱 [Facebook 廣告管理員的連接器](export-facebook.md)。

#### <a name="predictions"></a>預測

- **訂閱流失預測**

  遵循引導式體驗，在雲端服務、客戶成員資格和其他部門等訂閱區域中建立流失預測。 

  訂閱流失預測功能，讓您不聘用資料科學家，也能預測客戶停止使用訂閱型產品或服務的可能性。 您可以使用預測分數，結合客戶的其他相關資訊來建立高流失風險的客戶細分。 藉助此區段，您可以直接鎖定行銷客戶、客戶支援及其他案例，減少特定客戶改善營收和降低成本產生的流失風險。

  在此體驗中，您可以將流失的定義設定為適合特定業務的時間範圍。 例如，具有每月訂閱程序的視訊串流業務可能需要在客戶訂閱到期後 15 天過後，將該客戶視為已流失。

  當您繼續進行預測時，我們將引導您瀏覽所需的資料，並讓您可以將業務相關資料對應至需要預測客戶流失的欄位。 業務資訊變更時，您也可以設定排程，根據系統中的新資訊重新定型，以適應不斷變化的業務環境。    
  如需詳細資訊，請參閱[訂閱流失預測 (預覽)](predict-subscription-churn.md)。

#### <a name="segments"></a>客戶細分

- **尋找類似的客戶**
  
  使用人工智慧，在您的客戶群中尋找類似的客戶。 二元分類機器學習模型會將相似性分數指派給展開的客戶細分中的客戶。 分數是根據與來源客戶細分中客戶的相似性所建立。 客戶設定檔會根據相似性分數新增至新建立的客戶細分。

  這在數位行銷中有時稱為相似受眾 (Lookalike) 模型建立，其使用 AI 模型，藉由考慮其他屬性來協助尋找類似於其他客戶細分的客戶。 不僅可讓您選擇屬性，也允許您指定這個新的客戶細分中應有的客戶數目上限。 AI 模型接著根據您選取的屬性計算每個客戶的相似性分數，並尋找相似性分數高於平均值的客戶。 產生的客戶細分將會包含看起來與原始客戶細分中客戶相似的客戶。    
  如需詳細資訊，請參閱[類似客戶](find-similar-customer-segments.md)。

- **客戶細分重疊和區別因素**

  客戶細分重疊可讓您了解兩個或多個客戶細分有多少共同的客戶，以及有哪些共同客戶。 例如，高消費者客戶細分與高滿意度客戶細分的重疊情形，或是客戶流失客戶細分與低滿意度客戶細分的重疊情形。 此外，您還可以根據您選擇的其他屬性，分析重疊的變化情況。

  客戶細分區別因素揭示一個客戶細分與其餘客戶或其他客戶細分有什麼區別。 您所要做的只是識別客戶細分，系統就會找出區分客戶細分的設定檔屬性及量值，其形式為區別因素的排名清單，從最強至最弱列出這些區別因素。    
  如需詳細資訊，請參閱[客戶細分見解 (預覽)](segment-insights.md)。

- **客戶細分存留期**
  
  定義排程，以啟用或停用客戶細分。    
  如需詳細資訊，請參閱[管理現有的客戶細分](segments.md#manage-existing-segments)。

## <a name="may-2020-updates"></a>2020 年 5 月更新

2020 年 5 月更新包含數項功能的的、效能升級和 BUG 修正。

### <a name="new-and-updated-features-in-may-2020"></a>2020 年 5 月的新增及更新功能

#### <a name="data-ingestion"></a>資料擷取

- **即時資料擷取：歷程記錄檢視**

  使用我們的 API 來擷取即時更新時，您可以查看這些更新最多 30 天的彙總歷程記錄。 您可以存取所有成功或失敗 API 呼叫的彙總，包括其結果、來源系統以及其他有用的中繼資料。    
  如需詳細資訊，請參閱[即時資料擷取](real-time-data-ingestion.md)。

- **即時資料擷取：設定檔更新**

  這項即時資料擷取的擴充功能讓您在數秒內就能了解特定使用者設定檔欄位的變更。    
  除了即時活動功能以外，系統也支援對設定檔欄位低延隔的更新動作。 設定檔欄位的即時更新有到期時間，因此不會取代已排定的重新整理。    
  如需詳細資訊，請參閱[即時資料擷取](real-time-data-ingestion.md)。

#### <a name="extensibility"></a>擴充性

- **客戶卡片增益集上已更新的時間表和分頁**

  客戶卡增益集解決方案的時間表符合活動時間表。 時間表的分頁已改善，最多可一次顯示 50 項活動。 同時也允許在時間表中載入其他的活動。    
  如需詳細資訊，請參閱[客戶卡片增益集](customer-card-add-in.md)。

- **客戶細分變更的 Power Automate 觸發程序**

  Power Automate 的觸發程序定義您可從中建置流程的內容。 新加入的觸發程序可讓您定義客戶細分的閾值。 例如，您可以建立會在越過定義的閾值時傳送的通知。    
  如需詳細資訊，請參閱 [Power Automate 連接器](export-power-automate.md)。

- **自訂模型的多組織用戶共享支援**

  透過不同 Azure Machine Learning 租用戶的 Web 服務，設定自訂模型的工作流程。 當您建立自訂模型的新工作流程時，您可以登入 Azure Machine Learning 租用戶。 這項功能是附加在整合於您自己自訂 Azure Machine Learning Web 服務之現有功能的項目。    
  如需詳細資訊，請參閱[自訂機器學習模型](custom-models.md)。

#### <a name="segments"></a>客戶細分

- **實體路徑自動化**

  當建立區段時，使用者必須定義實體路徑。 此功能會在自動化實體路徑定義時採取第一個步驟，這樣您就可以將專注於建立您所構想的客戶區隔準則。    
  如果您要據以細分客戶的實體與統一客戶實體直接相關，就不需要再定義實體路徑。 不過，如果有多個可能的實體路徑，您還是必須手動加以定義。

- **對多個客戶細分的動作**
  
  使用者只需按一下即可選取多個客戶細分並對其執行動作 (例如重新整理客戶細分)。    

- **重新整理客戶細分**

  使用者可以重新整理單一客戶細分，或是只選取要重新整理的客戶細分。    

  
- **對複合客戶細分的改善**

  使用者可以建立、編輯和刪除在其他客戶細分基礎上建立的客戶細分。 例如，在其他建構於第三個客戶細分的客戶細分上所建構的客戶細分。    

- **客戶細分清單頁面**

  客戶細分頁面的新設計採用可讓您一次查看更多客戶細分的清單格式。 已新增搜尋欄位，以便快速尋找客戶細分。 使用者現在可同時在多個客戶細分上套用動作，例如下載或刪除。 引進新的趨勢體驗，可快速識別客戶細分上的重大變更。    
  如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。

#### <a name="system-administration"></a>系統管理

- **可在 Microsoft Dynamics 365 Online Government 中使用 Customer Insights**

  隨著越來越多的管道可供互動之用，公民資料已散佈在無數的系統中，形成孤立資料，並導致對公民互動相關資訊的觀點也變得支離破碎。 如果對不同管道上個別公民的互動情形沒有完整的觀點，政府就無法大規模推行現代化。 Microsoft 致力於支援政府的技術需求，以維持民眾對一致且回應迅速體驗的期望。    
  隨著 2020 年第 1 段發行浪潮到來，Dynamics 365 Customer Insights 將可用於政府社群雲端 (GCC) 這個旨在符合美國政府機關更高合規性需求的環境。 這些政府機關會獲得對民眾的統一觀點，並使用預建 AI 來產生改善互動情形、增強員工權能強和推動社群轉型的見解，同時降低 IT 複雜性，以及符合美國的合規性與安全性標準。 Dynamics 365 Government 符合美國聯邦風險與授權管理計畫 (Federal Risk and Authorization Management Program，FedRAMP) 的嚴苛需求，使美國聯邦機構因 Microsoft 雲端的成本節約與嚴格安全性而獲益匪淺。

## <a name="april-2020-updates"></a>2020 年 4 月更新

2020 年 4 月更新包含數項功能的的、效能升級和 BUG 修正。

### <a name="new-and-updated-features-in-april-2020"></a>2020 年 4 月的新增及更新功能

#### <a name="activities"></a>活動

- **將活動實體對應至標準活動類型**
  
  活動設定和儲存空間目前以靜態設計為基礎，您可在時間表中進行檢視。 目前並未完全使用活動的語意含義，這些活動在 AI 模型中可能會有多種使用案例。 我們規劃要根據活動類型以及更好的活動語意理解，讓活動時間表變得更具動態。 此功能旨在識別 Common Data Model 中針對任何已擷取活動所定義的活動類型。
  如需詳細資訊，請參閱[客戶活動](activities.md)。

#### <a name="data-ingestion"></a>資料擷取

- **即時資料擷取：活動**
  
  即時資料內嵌功能立即提供資料方便使用，直到後續排程的重新整理作業將此資料從資料來源拉出為止。    
  如需詳細資訊，請參閱[即時資料擷取](real-time-data-ingestion.md)。

- **對資料準備的改善**
  
  進一步了解實體中擷取的資料。 您可以透過資料摘要了解可協助採取適當動作的資料品質特性。    
  如需詳細資訊，請參閱[探索實體資料](entities.md#exploring-a-specific-entitys-data)。

- **透過 Common Data Service 從 Dynamics 365 擷取分析資料**
  
  Common Data Service 可做為建立資料來源的方式。 現有的 Dynamics 365 客戶可以將 Common Data Service 中的分析實體擷取到 Customer Insights。 單一資料來源可同時在 Customer Insights 環境中使用同一個 Common Data Service 管理的湖。    
  如需詳細資訊，請參閱[連接至 Common Data Service 受管理資料湖中的資料](connect-common-data-service-lake.md)。

#### <a name="extensibility"></a>擴充性

- **匯出至 LiveRamp**

  在 LiveRamp® 中啟用您的資料，與遍佈數位、社交和電視生態系統的 500 多個平台進行連接。 利用 LiveRamp 中的資料來對廣告行銷活動進行目標設定、抑制和個人化。    
  如需詳細資訊，請參閱[LiveRamp&reg; 連接器](export-liveramp.md)。

- **Customer Insights Teams 增益集**
  
  機器人提供對統一客戶設定檔的查詢功能。 其中會顯示包含最多 15 個來自所產生客戶設定檔中欄位的卡片。 有多個相符項目時，會傳回可讓您選取設定檔的結果清單。    
  如需詳細資訊，請參閱 [Customer Insights 的 Teams 機器人](export-teams-bot.md)。

#### <a name="measures"></a>量值

- **量值清單頁面**
  
  對量值頁面的改善包括支援對單一量值以及同時對多個量值採取的動作。 此外，您還會發現有搜尋欄位可快速尋找和追蹤量值。    
  如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。

- **對複合量值的改善**
  
  使用者可以建立、編輯和刪除在其他量值基礎上建立的量值。 例如，在其他建構於第三個量值的量值上所建構的量值。

#### <a name="segments"></a>客戶細分

- **加法運算子**
  
  IN 集運算子允許依數個可能的字串值進行客戶區隔。 將此運算子加入之前，您必須使用多個「或」條件來建構這類客戶細分。 IN 集運算子可讓您使用單一條件來執行此動作。    
  如需詳細資訊，請參閱[建立和管理客戶細分](segments.md)。

#### <a name="system-administration"></a>系統管理

- **將組態設定複製到新環境**
  
  將您的組態從一個環境複製到另一個環境。 建立新環時，您可以選取要從中複製設定的現有環境。 我們目前支援複製資料來源、資料統整、關聯、量值和客戶細分。 不會複製資料來源認證和實際資料。    
  如需詳細資訊，請參閱[管理環境](manage-environments.md)。
