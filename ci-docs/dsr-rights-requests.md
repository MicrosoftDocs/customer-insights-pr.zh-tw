---
title: 符合 GDPR 的資料主體權利 (DSR) 要求 | Microsoft Docs
description: 回應資料主旨對 Dynamics 365 Customer Insights 對象見解能力的要求。
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483648"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>符合 GDPR 的資料主體權利 (DSR) 要求

歐盟的一般資料保護規定（GDPR）已自 2018 年 5 月 25 日起生效。 它讓個人對其資料擁有重大的權利。 GDPR 與保護及賦予個人隱私權有關。 您可以在 [Microsoft 信任中心](https://www.microsoft.com/trust-center) 瞭解更多 Microsoft 對安全性和法規遵從性的詳細資訊。

我們致力於協助我們的使用者符合 GDPR 需求。 它包含刪除和匯出包含個人資訊（例如使用者 ID、電話號碼和電子郵件地址）之資料的權利。 系統管理員可以執行使用者要求以刪除或匯出個人資料。

## <a name="audience-insights"></a>對象見解

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>回應 GDPR 資料主旨刪除對 Dynamics 365 Customer Insights 對象見解能力的要求

從組織的客戶資料移除個人資料的「刪除權」是一般資料保護規定 (GDPR) 中的一項重要保護。 移除個人資料包括移除所有個人資料以及系統產生的日誌，但不包括稽核記錄資訊。

#### <a name="manage-data-subject-delete-requests"></a>管理資料主體刪除要求

對象見解提供下列產品內經驗，以刪除特定顧客或使用者的個人資料：

- **管理客戶資料的刪除要求**：Customer Insights 中的客戶資料擷取自 Customer Insights 之外的原始資料來源。 所有的 GDPR 刪除要求都必須在原始資料來源中執行。
- **管理 Customer Insights 使用者資料的刪除要求**：使用者資料透過 Customer Insights 建立。 所有的 GDPR 刪除要求都必須在 Customer Insights 中執行。

##### <a name="manage-requests-to-delete-customer-data"></a>管理刪除客戶資料的要求

Customer Insights 管理員可以依照下列步驟移除已在資料來源中刪除的客戶資料：

1. 登入 Dynamics 365 Customer Insights。
2. 在對象見解中，前往 **資料** > **資料來源**
3. 對於清單中每個包含已刪除之客戶資料的資料來源：
   1. 選取 (...)，然後選取 **重新整理**。
   2. 檢查 **狀態** 下的資料來源狀態。 核取記號表示已成功地進行重新整理。 警告三角形表示發生錯誤。 如果顯示警告三角形，請聯繫 D365CI@microsoft.com。

> [!div class="mx-imgBorder"]
> ![處理客戶資料的 GDPR 刪除要求。](audience-insights/media/gdpr-data-sources.png "處理客戶資料的 GDPR 刪除要求")

##### <a name="manage-delete-requests-for-user-data"></a>管理對使用者資料的刪除要求

Customer Insights 管理員可以依照下列步驟來刪除 Customer Insights 使用者資料：

1. 登入 Dynamics 365 Customer Insights。
2. 在對象見解中，前往 **管理員** > **權限**。
3. 選取您要刪除之使用者的核取方塊。
4. 選取 **移除**。

### <a name="responding-to-gdpr-data-subject-export-requests"></a>回應 GDPR 資料主旨匯出要求

我們致力於讓您符合一般資料保護規定 (GDPR) 的規範，因此我們開發了可協助您進行準備的文件。 本文件描述當您使用對象見解時，您可以馬上採用以支援 GDPR 合規性的步驟。

#### <a name="manage-export-and-view-requests"></a>管理匯出和檢視要求

「資料可攜權」讓資料主體可要求其個人資料的電子格式 (「結構化、通用、機器可讀取及可互通的格式」) 複本，以便傳送至另一個資料控制器。

##### <a name="export-customer-data-tenant-admin"></a>匯出客戶資料 (用戶管理員)

用戶管理員可遵循下列步驟來匯出資料：

1. 傳送電子郵件至 D365CI@microsoft.com，在要求中指定客戶的電子郵件地址。 Customer Insights 團隊會傳送電子郵件給已註冊的租用戶管理員電子郵件地址，要求確認匯出資料。
2. 認可匯出所要求之客戶資料的確認。
3. 透過用戶管理員電子郵件地址接收匯出的資料。

##### <a name="export-user-data-tenant-admin"></a>匯出使用者資料 (租用戶管理員)

1. 傳送電子郵件至 D365CI@microsoft.com，在要求中指定使用者的電子郵件地址。 Customer Insights 團隊會傳送電子郵件給已註冊的租用戶管理員電子郵件地址，要求確認匯出資料。
2. 認可匯出所要求之使用者資料的確認。
3. 透過用戶管理員電子郵件地址接收匯出的資料。

## <a name="engagement-insights"></a>參與見解

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>刪除和匯出包含終端使用者可識別資訊的事件資料

下列各節描述如何刪除和匯出可能包含個人資料的事件資料。

要刪除或匯出資料：

1. 標記包含個人資訊之資料的事件屬性。
2. 刪除或匯出與特定值相關的資料（例如，指定的使用者 ID）。

#### <a name="tag-and-update-event-properties"></a>標記和更新事件屬性

個人資料會在事件屬性等級上進行標記。 首先，標記被視為要刪除或匯出的屬性。

若要標記事件屬性為包含個人資訊，請遵循下列步驟：

1. 打開包含事件的工作區。

1. 移至 **資料** > **事件**，以在選取的工作區中查看事件清單。
  
1. 選取您要標記的事件。

1. 選取 **編輯屬性** 以打開列出所選取事件之所有屬性的窗格。
     
1. 選取 **...**，然後選擇 **編輯** 以到達 **更新屬性** 對話方塊。

   ![編輯事件。](engagement-insights/media/edit-event.png "編輯事件")

1. 在 **更新屬性** 視窗中，選擇右上角的 **...**，然後選擇 **包含 EUII** 方塊。 選擇 **更新** 以儲存變更。

   ![儲存您的變更。](engagement-insights/media/update-property.png "儲存您的變更")

   > [!NOTE]
   > 每次事件架構變更或建立一個新事件時，建議您評估有關的事件屬性，並根據需要將它們標記或取消標記為包含個人資料。

#### <a name="delete-or-export-tagged-event-data"></a>刪除或匯出帶標記的事件資料

如果所有事件屬性都已根據先前步驟中所描述的方式適當地標記了，則環境管理員就會針對標記的事件資料發出刪除要求。

管理 EUII 移除或匯出要求

1. 移至 **管理員** > **環境** > **設定**。

1. 在 **管理終端使用者可識別資訊（EUII）** 區段中，選取 **管理 EUII**。

##### <a name="deletion"></a>刪除

若要進行刪除，您可以在 **刪除終端使用者可識別資訊（EUII）** 區段中，輸入以逗點分隔的使用者 ID 清單。 這些 ID 之後會透過精確的字串比對，與目前環境中所有專案裡之全部已標記的事件屬性進行比較。 

若屬性值與其中一個提供的 ID 相符，就會永久刪除與其相關的事件。 由於此動作是不可逆的，所以您必須在選取 **刪除** 後確認刪除。

##### <a name="export"></a>Export

當您要在 **匯出終端使用者可識別資訊（EUII）** 區段中定義事件屬性值時，匯出的程序與刪除的程序相同。 此外，您還需要提供 **Azure blob 儲存體的 URL**，才能指定匯出目標。 Azure Blob 的 URL 必須包含[共用存取簽章（SAS）](/azure/storage/common/storage-sas-overview)。

選取 **匯出** 之後，所有包含相符標記屬性的現有團隊事件都會以 CSV 格式匯出至匯出目標。

### <a name="good-practices"></a>良好實務操作

* 請盡量避免傳送任何包含個人資料的事件。
* 如果您需要傳送包含 EUII 資料的事件，請限制包含 EUII 資料的事件數目和事件屬性數目。 理想的狀態是，限制自己只傳送一個此類事件。
* 務必確保有權存取已送出之個人資料的人員越少越好。
* 對於包含個人資料的事件，請務必確認已設定一個屬性，可以發出唯一識別碼，此識別碼可以輕易地連結至特定使用者（例如，使用者 ID）。 這樣可以更輕鬆地隔開資料以及匯出或刪除正確的資料。
* 在每個事件中只將一個屬性標記為包含個人資料。 理想狀態是只包含一個唯一識別碼。
* 不要標記包含詳細值（例如，整個要求主體）的屬性。 當您決定要刪除或匯出哪些事件時，業務開發見解功能會使用精準的字串比對。

[!INCLUDE[footer-include](includes/footer-banner.md)]