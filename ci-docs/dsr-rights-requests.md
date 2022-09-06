---
title: 符合 GDPR 的資料主體權利 (DSR) 要求 | Microsoft Docs
description: 回應 Dynamics 365 Customer Insights 的資料主體要求。
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387101"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>符合 GDPR 的資料主體權利 (DSR) 要求

歐盟的一般資料保護規定（GDPR）已自 2018 年 5 月 25 日起生效。 它讓個人對其資料擁有重大的權利。 GDPR 與保護及賦予個人隱私權有關。 在 [Microsoft 信任中心](https://www.microsoft.com/trust-center) 閱讀更多 Microsoft 對安全性與合規性所做承諾的詳細資訊。

我們致力於協助我們的使用者符合 GDPR 需求。 其中加入刪除或匯出包含個人資訊 (例如使用者識別碼、電話號碼和電子郵件地址) 之資料的權限。 系統管理員可以執行使用者要求以刪除或匯出個人資料。

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>回應 GDPR 資料主旨刪除對 Customer Insights 的要求

從組織的客戶資料移除個人資料的「刪除權」是一般資料保護規定 (GDPR) 中的一項重要保護。 移除個人資料包括移除所有個人資料以及系統產生的日誌，但不包括稽核記錄資訊。

### <a name="manage-data-subject-delete-requests"></a>管理資料主體刪除要求

Customer Insights 提供下列產品內體驗，可刪除特定顧客或 使用者的個人資料：

- **管理客戶資料的刪除要求**：Customer Insights 中的客戶資料擷取自 Customer Insights 之外的原始資料來源。 先在原始資料來源中執行 GDPR 刪除要求。
- **管理 Customer Insights 使用者資料的刪除要求**：使用者資料透過 Customer Insights 建立。 在 Customer Insights 中執行所有 GDPR 刪除要求。

#### <a name="manage-requests-to-delete-customer-data"></a>管理刪除客戶資料的要求

以 Customer Insights 管理員身分，移除資料來源中已刪除的 Customer Insights 客戶資料。 確認是否已在原始資料來源中執行 GDPR 刪除要求。

1. 登入 Dynamics 365 Customer Insights。

1. 移至 **資料** > **資料來源**。

1. 對於清單中每個包含已刪除之客戶資料的資料來源：
   1. 選取資料來源，然後選取 **重新整理**。
   1. 檢查 **狀態** 下的資料來源狀態。 核取記號表示已成功地進行重新整理。 警告三角形表示發生錯誤。 如果顯示警告三角形，請聯繫 D365CI@microsoft.com。

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="處理客戶資料的 GDPR 刪除要求。":::

1. 成功重新整理資料來源後，也請執行下游重新整理。 特別是，如果您未定期完整重新整理已排程的 Customer Insights。

   > [!IMPORTANT]
   > 在刪除要求之後，不會在完整重新整理或執行下游重新整理中包括靜態客戶細分。 若要確定客戶資料也已從靜態客戶細分中移除，請使用重新整理的來源資料重新建立靜態客戶細分。

#### <a name="manage-delete-requests-for-user-data"></a>管理對使用者資料的刪除要求

以 Customer Insights 管理員身分，刪除 Customer Insights 使用者資料。

1. 登入 Dynamics 365 Customer Insights。

1. 移至 **管理** > **安全性**，然後選取 **使用者** 索引標籤。

1. 針對您要刪除的使用者選取核取方塊。

1. 選取 **移除**。

1. 確認刪除。

## <a name="responding-to-gdpr-data-subject-export-requests"></a>回應 GDPR 資料主旨匯出要求

「資料可攜權」讓資料主體可要求其個人資料的電子格式 (「結構化、通用、機器可讀取及可互通的格式」) 複本，以便傳送至另一個資料控制器。

### <a name="manage-export-and-view-requests"></a>管理匯出和檢視要求

管理匯出客戶或使用者資料的要求。

#### <a name="export-customer-data-tenant-admin"></a>匯出客戶資料 (用戶管理員)

以租用戶管理員身分，匯出客戶資料。

1. 傳送電子郵件至 D365CI@microsoft.com，在要求中指定客戶的電子郵件地址。 Customer Insights 團隊會傳送電子郵件給已註冊的租用戶管理員電子郵件地址，要求確認匯出資料。
2. 認可匯出所要求之客戶資料的確認。
3. 透過用戶管理員電子郵件地址接收匯出的資料。

#### <a name="export-user-data-tenant-admin"></a>匯出使用者資料 (租用戶管理員)

以租用戶管理員身分，匯出使用者資料。

1. 傳送電子郵件至 D365CI@microsoft.com，在要求中指定使用者的電子郵件地址。 Customer Insights 團隊會傳送電子郵件給已註冊的租用戶管理員電子郵件地址，要求確認匯出資料。
1. 認可匯出所要求之使用者資料的確認。
1. 透過用戶管理員電子郵件地址接收匯出的資料。

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 中的資料刪除處理

如果資料分割和資料快照集處於非使用中狀態超過 30 天，則會刪除資料 (資料分割和資料快照集)，表示其已透過資料來源重新整理取代為新的資料分割和快照集。

並非所有的資料和快照都會刪除。 最新的資料分割和資料快照集會處於使用中狀態，因為 Customer Insights 中已使用這些資料。 如果是最新資料，則過去 30 天未重新整理資料來源也沒關係。

[!INCLUDE [footer-include](includes/footer-banner.md)]
