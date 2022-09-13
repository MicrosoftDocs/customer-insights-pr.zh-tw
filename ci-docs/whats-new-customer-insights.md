---
title: Dynamics 365 Customer Insights 的新功能
description: 關於新功能、改善和 BUG 修正的資訊。
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: acba06cba5fb5cbf0bca5aeb30b603003555fc32
ms.sourcegitcommit: 3ab8f1c0ba5874095a19f0b6367b9a4432f72ed1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409347"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 的新功能

我們很高興宣布我們最新的更新！ 本文摘要說明公開預覽功能、正式發行增強功能以及功能更新。 若要查看長期功能計劃，請參閱 [Dynamics 365 和 Power Platform 發行計劃](/dynamics365/release-plans/)。

我們會逐一在各地區推出更新。 因此可能會在特定地區提前看到其他地區尚未推出的功能。 除非另有說明，否則您無需執行任何動作，我們將自動更新應用程式，無需停機。

> [!TIP]
> 若要提出功能要求和產品建議並票選，請前往 [Dynamics 365 應用程式想法入口網站](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)。

## <a name="august-2022-updates"></a>2022 年 8 月更新

2022 年 8 月更新內容包括新功能、效能升級和偵錯。

### <a name="contact-unification-in-b-to-b-environments"></a>B 到 B 環境中的連絡人整合

Customer Insights 中的 B 到 B 環境現在支援增強型資料整合體驗。

除了客戶之外，您現在還可以整合連絡人來取得商務連絡人的完整檢視。 整合的連絡人與整合的客戶有關聯，而且現在會在客戶卡片上列出。 

如需詳細資訊，請參閱[建立統一連絡人設定檔](data-unification-contacts.md)。

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>根據整合的連絡人建立和匯出客戶細分

得益於新的連絡人整合，您可以使用連絡人、客戶或兩者的準則來建立連絡人的客戶細分。 您可匯出這些客戶細分，以便在其他服務中啟用。

如需詳細資訊，請參閱[匯出概觀](export-destinations.md)。

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>與 Microsoft Dataverse 保持一致的部署區域

建立新的 Customer Insights 環境時，您可以選取要部署和託管服務所在的區域。 我們已更新區域選取項目，以便與 Microsoft Dataverse 及 Power Platform 保持一致。

您現在可以輕鬆地選取與現有的 Microsoft Dataverse 環境或您的 Azure Data Lake Storage 帳戶相同的區域 (視 Customer Insights 在該區域的可用性而定)，如果您選擇該選項的話。

如需詳細資訊，請參閱[建立新環境](create-environment.md)和[依地理位置劃分的產品可用性](https://dynamics.microsoft.com/availability-reports/)。

## <a name="july-2022-updates"></a>2022 年 7 月更新

2022 年 7 月更新內容包括新功能、效能升級和偵錯。

### <a name="export-to-moengage"></a>匯出至 MoEngage

將統整客戶設定檔的客戶細分匯出至 MoEngage，並在 MoEngage 中用來進行電子郵件行銷。

如需詳細資訊，請參閱 [將客戶細分匯出至 MoEngage](export-moengage.md)。

### <a name="ssh-support-for-sftp-based-exports"></a>支援 SFTP 型匯出的 SSH 

連接至 SFTP 匯出目的地時，選擇是否要透過 SSH 或名稱/密碼來進行驗證。

如需詳細資訊，請參閱[匯出資料至 SFTP 主機](export-sftp.md)。

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>使用已知和未知使用者的相關資料，將體驗個人化

管理客戶資料並不是一項新挑戰，但隨著使用者瀏覽品牌提供的各種數字管道，變得越來越困難。 如果未登錄，則在一個頻道中已知 (已驗證) 的使用者在另一個頻道中將變為未知 (未驗證)。 問題通常是未經身份驗證 (未知) 的使用者沒有共同的 ID。 這可用於關聯有意義的設定檔文件屬性，並生成統一的客戶設定檔。 Customer Insights 能透過從源系統上的追蹤方法中擷取資料，協助解決此問題。

如需詳細資訊，請參閱 [透過已知和未知使用者的資料，來個人化體驗](unknown-to-known.md)。

## <a name="june-2022-updates"></a>2022 年 6 月更新

2022 年 6 月的更新包括新功能、效能升級和錯誤修正。

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>更新了資料來源和資料擷取的使用者體驗

從各種資料來源匯入資料是在 Dynamics 365 Customer Insights 中整合客戶資料的基礎。 我們重新審視了資料來源匯入和連接的使用者體驗。 此更新旨在讓您更輕鬆地將資料擷取到 Customer Insights。

如需更多資訊，請參閱[資料來源概觀](data-sources.md)。

### <a name="export-to-inmobi"></a>匯出到 InMobi

InMobi 協助品牌了解、識別、吸引和爭取消費者。 您可以透過 Azure Blob 儲存體帳戶將客戶細分和其他資料匯出到 InMobi 服務。

如需更多資訊，請參閱[匯出到 InMobi (預覽版)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Customer Insights 中的加密箱支援

客戶加密箱的介面可以審閱和核准 (或拒絕) 資料存取要求。 若需要客戶資料的資料存取權限以解決支援案例，就會出現這類要求。

如需更多資訊，請參閱[使用客戶加密箱安全存取客戶資料 (預覽版)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview)

### <a name="connect-to-your-data-using-azure-private-link"></a>使用 Azure Private Link 來連接到您的資料

Azure Private Link 允許 Customer Insights 透過虛擬網路中的私人端點連接到您的 Azure Data Lake Storage 帳戶。 對於未公開到公用網際網路的儲存體帳戶資料，Private Link 能進行對該限制網路的連接。

如需更多資訊，請參閱[在 Customer Insights 中使用 Private Link](security-overview.md#set-up-an-azure-private-link)。

## <a name="may-2022-updates"></a>2022 年 5 月更新

2022 年 5 月更新內容包括新功能、效能升級和偵錯。

### <a name="updated-data-unification-experience"></a>更新的資料整合體驗

 資料整合可讓您將曾經不同的資料來源整合成單一主要資料集，並提供該資料的整合檢視表。 資料可以在單一實體或多個實體上整合。 首先，[選取實體和來源欄位](map-entities.md)、[移除重複的記錄](remove-duplicates.md)、指定[比對條件](match-entities.md)的規則，以及定義[要包括在整合客戶個人資料中的欄位](merge-entities.md)。

如需詳細資訊，請參閱[資料整合概觀](data-unification.md)。

### <a name="refreshed-home-page-in-customer-insights"></a>重整的 Customer Insights 首頁

**首頁** 引導您完成主要功能的設定程序，並提供客戶細分、量值及擴充資料的摘要。 我們已重整體驗，更有效地提供相關資訊。

如需詳細資訊，請參閱[匯出 Customer Insights](home.md)。

### <a name="track-usage-of-a-segment"></a>追蹤客戶細分的使用方式

如果應用程式是由連接至 Customer Insights 的 Dataverse 組織所建立，則現在開始可以[追蹤客戶細分的使用方式](segments.md#track-usage-of-a-segment)。 對於 [Dynamics 365 Marketing 的客戶旅程中使用的 Customer Insights 客戶細分](/dynamics365/marketing/real-time-marketing-ci-profile)，系統會通知您該客戶細分的使用方式。

### <a name="export-to-criteo"></a>匯出至 Criteo

Criteo 是可協助使用者管理數位廣告的線上平台。 您現在可以匯出匯出整合客戶個人資料的客戶細分以搭配 Criteo 產生廣告活動、提供電子郵件行銷，並且使用特定的客戶群組。

如需詳細資訊，請參閱[匯出客戶細分至 Criteo (預覽版)](export-criteo.md)。

### <a name="refined-documentation-structure-for-environment-creation"></a>為環境建立而精簡的文件結構

在 Customer Insights 中，我們已重新檢視過與環境建立和環境管理相關的協助文件。 這些文章現在會分組到目錄下的「環境」節點。 重建的文章在設定環境的各種不同方式上將提供更多指引，並有著更清晰的結構。 如果您有任何意見反應，請透過説明文章結尾附近的控制項目告訴我們。

如需詳細資訊，請參閱[如何建立新環境](create-environment.md)。

## <a name="april-2022-updates"></a>2022 年 4 月更新

2022 年 4 月更新內容包括新功能、效能升級和偵錯。

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet 擴充 (預覽版)

Dun & Bradstreet 為公司供應商業資料、分析和見解。 為客戶帶來統一客戶設定檔，讓各家公司可以擴充其資料。 擴充公司屬性包括 DUNS 編碼、公司規模、位置、產業等等。

如需詳細資訊，請參閱 [以 Dun & Bradstreet 擴充公司資料 (預覽版)](enrichment-dnb.md)。

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>建立新量值時定義量值類別

您現在可以區分各個個人資料的量值和在整個業務中的量值。 業務量值措施顯示在 Customer Insights 的首頁，客戶量值則會出現在在詳細的客戶檢視表上。

更多資訊，請參閱[使用量值建立器從頭開始建立量值](measure-builder.md)。

### <a name="consolidation-of-customer-insights-documentation"></a>整合 Customer Insights 文件

我們已重新檢視過我們的文件，並已移除提及參與見解和對象見解功能的內容。 之後，當我們撰寫應用程式的核心功能時，我們會一致地將產品稱為 Customer Insights。 這項變更也造成了在基礎文件存放庫中大規模重建目錄、URL 結構及檔案路徑。 所有書簽或現有的連結都能繼續運作，並重新導向至已更新的 URL。

如果您發現或注意到未如期運作的問題，請[到此提出意見反應](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**)。

## <a name="march-2022-updates"></a>2022 年 3 月的更新

2022 年 3 月更新內容包括新功能、效能升級和偵錯。

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec 擴充 (預覽)

LiveRamp 提供身分識別解析和客戶資料的整合。 您可以將客戶資料中的個人識別碼對應至 AbiliTec 標識圖表，並接收 AbiliTec 識別碼。 您可以使用這些識別碼來取得更好的整合客戶資料。

如需詳細資訊，請參閱[使用 LiveRamp 身分識別資料擴充客戶個人資料(預覽版)](enrichment-liveramp.md)。

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>使用標籤和篩選來組織客戶細分和量值

如果您的組織維持大量的客戶細分或量值，要尋找正確的一個或多個量值，常會有點難度。 這項新功能可讓您使用標籤和欄來組織清單。 這有助於快速、方便地尋找資料，並自訂檢視表。

如需詳細資訊，請參閱[使用標籤和欄](work-with-tags-columns.md)。

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>當使用儲存體帳戶帳戶時，可啟用對 Dataverse 共用資料

如果您的環境使用 Azure Data Lake Storage 儲存 Customer Insights 資料，啟用對 Microsoft Dataverse 資料共用就需要額外設定。
之前，只有在受管理的 Data Lake 中儲存資料時，才能啟用對 Dataverse 共用資料。

如需詳細資訊，請參閱[啟用從 Azure Data Lake Storage 共用資料到 Dataverse (預覽版)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)。

### <a name="new-export-destinations-iterable-and-braze"></a>新增匯出目的地：Iterable 和 Braze

我們正在使用新的連接，繼續擴充匯出目的地的生態系統。 您現在可以將客戶細分匯出至 Iterable 及 Braze，以使用其啟用服務。

如需詳細資訊，請參閱 [將客戶細分匯出至 Iterable (預覽版)](export-iterable.md)，及 [將客戶細分匯出至 Braze (預覽版)](export-braze.md)。

### <a name="improvements-to-marketo-and-google-ads-export"></a>Marketo 和 Google Ads 匯出的改善

變更連線服務中的 API，可讓連接器更新可靠且順利執行。 我們已發佈 Marketo 和 Google Ads 服務的匯出部分更新：

- Google Ads：新版本的 Google Ads 匯出連接器簡化了驗證體驗，現在讓您能自動建立新的 Google Ads 對象。 
- Marketo：新版本的 Marketo 匯出連接器支援 Marketo 識別碼，可讓您避免資料重複、更新現有的記錄，以及在 Marketo 中建立新的記錄。 

## <a name="february-2022-updates"></a>2022 年 2 月更新

2022 年 2 月更新內容包括新功能、效能升級和偵錯。

### <a name="general-availability-for-prediction-models"></a>預測模型的正式發行

立即可用的預測模型，其中包括 **訂閱流失**、**交易流失** 和 **客戶存留期值 (CLV)**，在Customer Insights 中正式發行。 

如需詳細資訊，請參閱[預測概觀](predictions-overview.md)。

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>新資料來源：與 Azure Synapse Analytics 整合 (預覽版)

Azure Synapse Analytics 是一項企業分析服務，可加快資料倉儲和大型資料系統的見解生成速度。

已使用 Azure Synapse Analytics 的組織可以擷取資料到 Customer Insights。 

如需其他資訊，請參閱[連接至 Azure Synapse 資料來源 (預覽)](connect-synapse.md)。

### <a name="liveramp-enrichment-preview"></a>LiveRamp 擴充 (預覽)

LiveRamp 提供身分識別解析和客戶資料的整合。 您可以將客戶資料中的個人識別碼對應至 AbiliTec 標識圖表，並接收 AbiliTec 識別碼。 您可以使用這些識別碼來取得更好的整合客戶資料。

如需詳細資訊，請參閱[使用 LiveRamp 身分識別資料擴充客戶個人資料(預覽版)](enrichment-liveramp.md)。

### <a name="enrichment-for-data-sources-preview"></a>資料來源擴充 (預覽版)

使用來自 Microsoft 和其他合作夥伴等來源的資料，在資料整合前擴充您的客戶資料。 資料來源擴充協助產生更高的資料完整性與品質，當您整合資料後，可取得更好的結果。

如需詳細資訊，請參閱[資料來源擴充 (預覽版)](data-sources-enrichment.md)。

### <a name="change-owner-of-environment"></a>變更環境擁有者

雖然在 Customer Insights 可以有多個使用者擁有系統管理員權限，但是只有一個使用者是環境的負責人。 改進後的體驗可讓您變更環境的負責人，並在先前的負責人離開組織時宣告擁有權。 

如需詳細資訊，請參閱[變更環境的負責人](manage-environments.md#change-the-owner-of-an-environment)。

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>資料準備程序列出損壞記錄的損壞原因

資料準備現在會為所有含有損壞資料的欄位顯示損壞原因。 資訊在個別記錄層級提供，方便識別。 

如需其他資訊，請參閱[損壞的資料來源](entities.md#corrupted-data-sources)。

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>參與見解功能中的報表功能結束預覽

 Dynamics 365 Customer Insights 參與見解功能的預覽版已於2022 年 2 月 15 日終止。  
這項變更表示 Customer Insights 試用體驗不再包括建立漏斗圖的能力，也不包含其他報表功能。

我們邀請您探索並評估 [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/)，即 Microsoft 客戶資料平臺 (CDP) ，的其他許多功能。    
 
在轉換期間，現時預覽版的參與者仍然可以存取某些預覽功能：

- 取得程式碼來檢測網站或行動應用程式 
- 查看事件與事件屬性 
- 利用內嵌及精簡事件增強整合個人資料檔，從客戶資料的完整價值中獲益
  
轉換期間，擷取的事件仍會串流至已連線的 Data Lake 中。 關閉此功能後，將停止資料共用，並且不會向連接的儲存體傳送新事件。
如果您對功能預覽版的終止有任何問題，請直接與您的 Microsoft 帳戶團隊聯繫。 您的帳戶團隊將通知您新版的最新消息。 

## <a name="january-2022-updates"></a>2022 年 1 月更新

2022 年 1 月更新內容包括新功能、效能升級和偵錯。

### <a name="sentiment-analysis-of-your-customers-feedback"></a>在您的客戶意見反應上的情感分析

Customer Insights 提供新的 AI 支援功能，可綜合客戶情感並找出特定的業務層面，當作有目標的增進機會。 透過分析您的客戶意見反應，就可以用較低的成本取得準確的深入解析。 由自然語言處理 (NLP) 模型所支援的情感分析，為每個客戶識別碼生成兩個衍生見解。 情感分數 (-5 到 5) 和可適用的業務層面清單。 

如需詳細資訊，請參閱[分析在客戶意見反應中的情感 (預覽版)](sentiment-analysis.md)。


[!INCLUDE [footer-include](includes/footer-banner.md)]