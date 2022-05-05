---
title: 符合 GDPR 的資料主體權利 (DSR) 要求 | Microsoft Docs
description: 回應 Dynamics 365 Customer Insights 的資料主體要求。
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 5b39452d7a4612242739e8000e57217954c71289
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641506"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>符合 GDPR 的資料主體權利 (DSR) 要求

歐盟的一般資料保護規定（GDPR）已自 2018 年 5 月 25 日起生效。 它讓個人對其資料擁有重大的權利。 GDPR 與保護及賦予個人隱私權有關。 您可以在 [Microsoft 信任中心](https://www.microsoft.com/trust-center) 瞭解更多 Microsoft 對安全性和法規遵從性的詳細資訊。

我們致力於協助我們的使用者符合 GDPR 需求。 它包含刪除和匯出包含個人資訊（例如使用者 ID、電話號碼和電子郵件地址）之資料的權利。 系統管理員可以執行使用者要求以刪除或匯出個人資料。

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>回應 Dynamics 365 Customer Insights 的 GDPR 資料主體刪除要求

從組織的客戶資料移除個人資料的「刪除權」是一般資料保護規定 (GDPR) 中的一項重要保護。 移除個人資料包括移除所有個人資料以及系統產生的日誌，但不包括稽核記錄資訊。

#### <a name="manage-data-subject-delete-requests"></a>管理資料主體刪除要求

Customer Insights 提供下列產品內體驗，可刪除特定顧客或 使用者的個人資料：

- **管理客戶資料的刪除要求**：Customer Insights 中的客戶資料擷取自 Customer Insights 之外的原始資料來源。 所有的 GDPR 刪除要求都必須在原始資料來源中執行。
- **管理 Customer Insights 使用者資料的刪除要求**：使用者資料透過 Customer Insights 建立。 所有的 GDPR 刪除要求都必須在 Customer Insights 中執行。

##### <a name="manage-requests-to-delete-customer-data"></a>管理刪除客戶資料的要求

Customer Insights 管理員可以依照下列步驟移除已在資料來源中刪除的客戶資料：

1. 登入 Dynamics 365 Customer Insights。
2. 移至 **資料** > **資料來源**
3. 對於清單中每個包含已刪除之客戶資料的資料來源：
   1. 選取 (...)，然後選取 **重新整理**。
   2. 檢查 **狀態** 下的資料來源狀態。 核取記號表示已成功地進行重新整理。 警告三角形表示發生錯誤。 如果顯示警告三角形，請聯繫 D365CI@microsoft.com。

> [!div class="mx-imgBorder"]
> ![處理客戶資料的 GDPR 刪除要求。](media/gdpr-data-sources.png "處理客戶資料的 GDPR 刪除要求")

##### <a name="manage-delete-requests-for-user-data"></a>管理對使用者資料的刪除要求

Customer Insights 管理員可以依照下列步驟來刪除 Customer Insights 使用者資料：

1. 登入 Dynamics 365 Customer Insights。
2. 移至 **系統管理員** > **權限**。
3. 選取您要刪除之使用者的核取方塊。
4. 選取 **移除**。

### <a name="responding-to-gdpr-data-subject-export-requests"></a>回應 GDPR 資料主旨匯出要求

我們致力於讓您符合一般資料保護規定 (GDPR) 的規範，因此我們開發相關文件，協助您回應資料主體要求。

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

若要移除特定使用者的同意資料，請到資料來源 (同意管理功能擷取的位置) 中移除。 在重新整理資料來源之後，移除的資料也會在同意中心被移除。 使用同意實體的應用程式也會在 [重新整理](system.md#refresh-processes)後，刪除已在來源上移除的資料。 為了回應資料主體要求而從所有其他程序和應用程式中移除使用者的資料後，我們建議您後盡快重新整理資料來源。

[!INCLUDE [footer-include](includes/footer-banner.md)]