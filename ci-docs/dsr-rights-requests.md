---
title: 符合 GDPR 的資料主體權利 (DSR) 要求 | Microsoft Docs
description: 回應資料主旨對 Dynamics 365 Customer Insights 對象見解能力的要求。
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350259"
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

## <a name="consent-management-preview"></a>同意管理 (預覽版)

同意管理功能不會直接收集使用者資料。 此功能只會匯入和處理由其他應用程式中的使用者提供的同意資料。

若要移除特定使用者的同意資料，請到資料來源 (同意管理功能擷取的位置) 中移除。 在重新整理資料來源之後，移除的資料也會在同意中心被移除。 使用同意實體的應用程式也會在 [重新整理](audience-insights/system.md#refresh-processes)後，刪除已在來源上移除的資料。 為了回應資料主體要求而從所有其他程序和應用程式中移除使用者的資料後，我們建議您後盡快重新整理資料來源。


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]