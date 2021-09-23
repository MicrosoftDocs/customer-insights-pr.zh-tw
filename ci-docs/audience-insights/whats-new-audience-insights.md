---
title: 新功能以及近期即將推出的功能
description: 關於新功能、改善和 BUG 修正的資訊。
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: fcc45c24e9d89516dba9964ee16f57caf439eff0
ms.sourcegitcommit: 2abe9b661b8c3c01e9730c629e383402e3f6a655
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2021
ms.locfileid: "7465195"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 的觀象見解能力有什麼新發表的功能

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

我們很高興宣布我們最新的更新！ 本文摘要說明公開預覽功能、正式發行增強功能以及功能更新。 若要查看長期功能計劃，請參閱 [Dynamics 365 和 Power Platform 發行計劃](/dynamics365/release-plans/)。

我們會逐一在各地區推出更新。 因此可能會在特定地區提前看到其他地區尚未推出的功能。 除非另有指示，您不需要採取任何動作，我們會在不停機的情況下自動更新應用程式。

> [!TIP]
> 若要送出和票選功能要求和產品建議，請前往 [Dynamics 365 應用程式想法入口網站](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)。

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
  客戶個人資料的詳細資料頁面現在會把資料分組在不同小節中 (如人口統計資料、識別碼及其他配置個人資料屬性)中，來改善可讀性。 個人資料詳細資料頁面上的其他區段現在更具互動性。 例如，活動區段可讓您篩選和排序。


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

- **將客戶細分匯出至 RollWorks** 我們已擴展了匯出目的地，現在包括 RollWorks。 您現在可以從 Customer Insights 將客戶細分匯出至 RollWorks 對象，並用來當作 B2B 廣告的基準。    
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