---
title: 設定安全性設定
description: 了解 Dynamics 365 Customer Insights 中的安全性設定。
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387239"
---
# <a name="configure-security-settings"></a>設定安全性設定

管理 API 金鑰、存取客戶資料，以及設定 Azure Private Link。

## <a name="manage-api-keys"></a>管理 API 金鑰

查看和管理金鑰，此金鑰可將 [Customer Insights API](apis.md) 與環境中的資料搭配使用。

1. 移至 **管理** > **安全性**，並選取 **API** 索引標籤。

1. 如果尚未設定 API 對環境的存取權限，請選取 **啟用**。 或者，若要封鎖環境的 API 存取，請選取 **停用** 並確認。

1. 管理主要和次要 API 金鑰：

   1. 若要顯示主要或次要的 API 金鑰，請選取 **顯示** 符號。

   1. 若要複製主要或次要的 API 金鑰，請選取 **複製** 符號。

   1. 若要建立新的主要 API 金鑰和次要 API 金鑰，請選取 **重新生成主要 API 金鑰** 或 **重新生成次要 API 金鑰**。

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>使用客戶加密箱安全地存取客戶資料 (預覽版)

Customer Insights 使用 Power Platform 客戶加密箱功能。 客戶加密箱的介面可以審閱和核准 (或拒絕) 資料存取要求。 若需要客戶資料的資料存取權限以解決支援案例，就會出現這類要求。 若要使用此功能，則 Customer Insights 與您的租用戶中的 Microsoft Dataverse 環境之間必須存在現有連接。

如需有關客戶加密箱的詳細資訊，請參閱 Power Platform 客戶加密箱的[摘要](/power-platform/admin/about-lockbox#summary)。 文章中也說明[工作流程](/power-platform/admin/about-lockbox#workflow)以及啟用客戶加密箱的必要[設定](/power-platform/admin/about-lockbox#enable-the-lockbox-policy)。

> [!IMPORTANT]
> Power Platform 全域系統管理員或 Power Platform 系統管理員可以核准簽發給 Customer Insights 的客戶加密箱要求。

## <a name="set-up-an-azure-private-link"></a>設定 Azure Private Link

[Azure Private Link](/azure/private-link/private-link-overview)讓 Customer Insights 透過虛擬網路中的私人端點連接到 Azure Data Lake Storage 帳戶。 對於未公開到公用網際網路的儲存體帳戶資料，Private Link 能進行對該限制網路的連接。

> [!IMPORTANT]
> 設定 Private Link 連接的基本角色需求：
>
> - Customer Insights 系統管理員
> - Azure 內建角色：[儲存體帳戶參與者](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - 自訂 Azure 角色的權限：[Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. 在 Customer Insights，移至 **系統管理員** > **安全性** 並選取 **私人連結** 索引標籤。

1. 選取 **新增私人連結**。

   **新增 Private Link** 窗格列出租用戶中您有權限查看的儲存體帳戶。

1. 選取訂閱，資源群組，和儲存體帳戶。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **儲存**。

1. 請移至您的 Data Lake 儲存體帳戶，並打開顯示在畫面上的連結。

1. 核准私人連結。


[!INCLUDE [footer-include](includes/footer-banner.md)]
