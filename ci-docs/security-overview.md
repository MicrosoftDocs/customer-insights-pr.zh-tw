---
title: Customer Insights 安全性設定
description: 了解 Dynamics 365 Customer Insights 中的安全性設定。
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947405"
---
# <a name="security-settings-in-customer-insights"></a>Customer Insights 安全性設定

**安全性** 頁面會列出設定使用者權限的選項，以及有助於增進 Dynamics 365 Customer Insights 安全性的功能。 只有系統管理員才能存取此頁面。

請移至 **系統管理員** > **安全性** 進行設定。

**安全性** 頁面包括下列索引標籤：

- [使用者](#users-tab)
- [API](#apis-tab)
- [私人連結](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [使用客戶加密箱安全地存取客戶資料 (預覽版)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>使用者索引標籤

 Customer Insights 的存取被限制在由系統管理員新增至應用程式的組織內使用者。**使用者** 索引標籤可讓您管理使用者的存取權及其權限。 如需詳細資訊，請參閱[使用者權限](permissions.md)。

## <a name="apis-tab"></a>API 索引標籤

查看和管理金鑰，以將 [Customer Insights API](apis.md) 與您的環境資料搭配使用。

您可以選取 **重新生成主索引鍵** 或 **重新生成次索引鍵** 來建立新的主索引鍵和次索引鍵。 

若要封鎖環境的 API 存取，請選取 **停用**。 如果已停用 API，您可以選取 **啟用** 來再次授與存取權。

## <a name="private-links-tab"></a>私人連結索引標籤

[Azure Private Link](/azure/private-link/private-link-overview)讓 Customer Insights 透過虛擬網路中的私人端點連接到 Azure Data Lake Storage 帳戶。 對於未公開到公用網際網路的儲存體帳戶資料，Private Link 能進行對該限制網路的連接。

> [!IMPORTANT]
> 設定 Private Link 連接的基本角色需求：
>
> - Customer Insights 系統管理員
> - Azure 內建角色：[儲存體帳戶參與者](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - 自訂 Azure 角色的權限：[Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

在 Customer Insights 中設定 Private Link 的過程分為兩個步驟。 首先，您可以從 Customer Insights **系統管理員** > **安全性** > **私人連結** 開始建立 Private Link。 **新增 Private Link** 窗格列出租用戶中您有權限查看的儲存體帳戶。 選取儲存體帳戶，並提供同意來建立 Private Link。

接下來，您需要到 Data Lake Storage 帳戶端核准 Private Link。 打開出現在畫面上的連結，核准新的 Private Link。

## <a name="key-vault-tab"></a>金鑰保存庫索引標籤

**金鑰保存庫** 索引標籤能讓您連結 [Azure 金鑰保存庫](/azure/key-vault/general/basic-concepts)與環境並進行管理。
專用的金鑰保存庫可用來在組織的法令遵循邊界內分階段使用秘密。 Customer Insights 可使用 Azure 金鑰保存庫的秘密以對協力廠商系統[設定連線](connections.md)。

如需更多資訊，請參閱[帶上您自己的 Azure 金鑰保存庫](use-azure-key-vault.md)。

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>使用客戶加密箱安全地存取客戶資料 (預覽版)

Customer Insights 正在使用 Power Platform 客戶加密箱功能。 客戶加密箱的介面可以審閱和核准 (或拒絕) 資料存取要求。 若需要客戶資料的資料存取權限以解決支援案例，就會出現這類要求。 若要使用此功能，則 Customer Insights 與您的租用戶中的 Microsoft Dataverse 環境之間必須存在現有連接。

如需有關客戶加密箱的詳細資訊，請參閱 Power Platform 客戶加密箱的[摘要](/power-platform/admin/about-lockbox#summary)。 文章中也說明[工作流程](/power-platform/admin/about-lockbox#workflow)以及啟用客戶加密箱的必要[設定](/power-platform/admin/about-lockbox#enable-the-lockbox-policy)。

> [!IMPORTANT]
> Power Platform 全域系統管理員或 Power Platform 系統管理員可以核准簽發給 Customer Insights 的客戶加密箱要求。

[!INCLUDE [footer-include](includes/footer-banner.md)]
