---
title: 符合 GDPR 的資料主體權利 (DSR) 要求 | Microsoft Docs
description: 回應資料主旨對 Dynamics 365 Customer Insights 對象見解能力的要求。
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 891794321f20954533ec0374b397eaf6b30445c2b0c95f601009912b3c3950a7
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034488"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>符合 GDPR 的資料主體權利 (DSR) 要求

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>回應 GDPR 資料主旨刪除對 Dynamics 365 Customer Insights 對象見解能力的要求

從組織的客戶資料移除個人資料的「刪除權」是一般資料保護規定 (GDPR) 中的一項重要保護。 移除個人資料包括移除所有個人資料以及系統產生的日誌，但不包括稽核記錄資訊。

### <a name="manage-data-subject-delete-requests"></a>管理資料主體刪除要求

對象見解提供下列產品內經驗，以刪除特定顧客或使用者的個人資料：

- **管理客戶資料的刪除要求**：Customer Insights 中的客戶資料擷取自 Customer Insights 之外的原始資料來源。 所有的 GDPR 刪除要求都必須在原始資料來源中執行。
- **管理 Customer Insights 使用者資料的刪除要求**：使用者資料透過 Customer Insights 建立。 所有的 GDPR 刪除要求都必須在 Customer Insights 中執行。

#### <a name="manage-delete-requests-for-customer-data"></a>管理客戶資料的刪除要求

Customer Insights 管理員可以依照下列步驟移除已在資料來源中刪除的客戶資料：

1. 登入 Dynamics 365 Customer Insights。
2. 在對象見解中，前往 **資料** > **資料來源**
3. 對於清單中每個包含已刪除之客戶資料的資料來源：
   1. 選取 (...)，然後選取 **重新整理**。
   2. 檢查 **狀態** 下的資料來源狀態。 核取記號表示已成功地進行重新整理。 警告三角形表示發生錯誤。 如果顯示警告三角形，請聯繫 D365CI@microsoft.com。

> [!div class="mx-imgBorder"]
> ![處理客戶資料的 GDPR 刪除要求。](media/gdpr-data-sources.png "處理客戶資料的 GDPR 刪除要求")

#### <a name="manage-delete-requests-for-user-data"></a>管理對使用者資料的刪除要求

Customer Insights 管理員可以依照下列步驟來刪除 Customer Insights 使用者資料：

1. 登入 Dynamics 365 Customer Insights。
2. 在對象見解中，前往 **管理員** > **權限**。
3. 選取您要刪除之使用者的核取方塊。
4. 選取 **移除**。

> [!div class="mx-imgBorder"]
> ![處理使用者資料的 GDPR 刪除要求。](media/gdpr-permissions.png "處理 GDPR 對使用者資料的刪除要求")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>回應 GDPR 資料主旨匯出要求

我們致力於讓您符合一般資料保護規定 (GDPR) 的規範，因此我們開發了可協助您進行準備的文件。 本文件描述當您使用對象見解時，您可以馬上採用以支援 GDPR 合規性的步驟。

### <a name="manage-export-and-view-requests"></a>管理匯出和檢視要求

「資料可攜權」讓資料主體可要求其個人資料的電子格式 (「結構化、通用、機器可讀取及可互通的格式」) 複本，以便傳送至另一個資料控制器。

#### <a name="export-customer-data-tenant-admin"></a>匯出客戶資料 (用戶管理員)

用戶管理員可遵循下列步驟來匯出資料：

1. 傳送電子郵件至 D365CI@microsoft.com，在要求中指定客戶的電子郵件地址。 Customer Insights 團隊會傳送電子郵件給已註冊的租用戶管理員電子郵件地址，要求確認匯出資料。
2. 認可匯出所要求之客戶資料的確認。
3. 透過用戶管理員電子郵件地址接收匯出的資料。

#### <a name="export-user-data-tenant-admin"></a>匯出使用者資料 (租用戶管理員)

1. 傳送電子郵件至 D365CI@microsoft.com，在要求中指定使用者的電子郵件地址。 Customer Insights 團隊會傳送電子郵件給已註冊的租用戶管理員電子郵件地址，要求確認匯出資料。
2. 認可匯出所要求之使用者資料的確認。
3. 透過用戶管理員電子郵件地址接收匯出的資料。


[!INCLUDE[footer-include](../includes/footer-banner.md)]