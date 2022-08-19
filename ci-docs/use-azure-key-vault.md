---
title: 帶入您自己的 Azure 金鑰保存庫 (預覽版)
description: 了解如何設定 Customer Insights 以使用您的 Azure Key Vault。
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246145"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>帶入您自己的 Azure 金鑰保存庫 (預覽版)

將專用的 [Azure Key Vault](/azure/key-vault/general/basic-concepts) 連結到 Customer Insights 環境將有助於組織達到合規性要求。

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>將金鑰保存庫連結到 Customer Insights 環境

設定專用的金鑰保存庫可在組織的組織合規性界限內暫存並使用秘密。

### <a name="prerequisites"></a>先決條件

- 啟用中的 Azure 訂用帳戶。

- 在 Customer Insights 中[被指派](permissions.md#add-users)[系統管理員](permissions.md#admin)角色。

- 在金鑰保存庫或其隸屬的資源群組上具備[參與者](/azure/role-based-access-control/built-in-roles#contributor)和[使用者存取系統管理員](/azure/role-based-access-control/built-in-roles#user-access-administrator)的角色。 如需詳細資訊，請前往[使用 Azure 入口網站新增移除 Azure 角色指派](/azure/role-based-access-control/role-assignments-portal)。 如果您不具備金鑰保存庫上的使用者存取系統管理員角色，請分別為 Dynamics 365 Customer Insights 的 Azure 服務主體設定角色型存取控制權限。 請遵照步驟針對應連結的金鑰保存庫[使用 Azure 服務主體](connect-service-principal.md)。

- 金鑰保存庫必須 **停用** Key Vault 防火牆。

- 金鑰保存庫與 Customer Insights 環境位於相同的 [Azure 位置](https://azure.microsoft.com/global-infrastructure/geographies/#overview)。 若要知道環境的區域，請前往 Customer Insights 中 **系統管理員** > **系統** 到 **關於** 索引標籤。

### <a name="recommendations"></a>建議

- 請使用只包含 Customer Insights 必要秘密的[獨立或專用金鑰保存庫](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults)。

- 遵照[金鑰保存庫 的最佳使用做法](/azure/key-vault/general/best-practices#turn-on-logging)進行控制存取、備份、稽核及復原選項。

### <a name="link-a-key-vault-to-the-environment"></a>將金鑰保存庫連結到環境

1. 請前往 **系統管理員** > **安全性**，然後選取 **金鑰保存庫** 索引標籤。
1. 請在 **金鑰保存庫** 圖格上選取 **設定**。
1. 選擇 **訂閱**。
1. 請從 **金鑰保存庫** 下拉式清單選擇金鑰保存庫。 如果過多金鑰保存庫可供使用，請選取資源群組限制搜尋結果。
1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。
1. 選取 **儲存**。

**金鑰保存庫** 圖格顯示連結的金鑰保存庫名稱、訂閱和資源群組。 您現在可以在連接設定中使用它。
如需深入了解有關在金鑰保存庫中 Customer Insights 被授與哪種權限，請前往[金鑰保存庫的授與權限](#permissions-granted-on-the-key-vault)。

## <a name="use-the-key-vault-in-the-connection-setup"></a>請在連接設定中使用金鑰保存庫

[設定連接](connections.md)到[受支援的協力廠商](#supported-connection-types)系統 時，使用連結的金鑰保存庫秘密設定連接。

1. 移至 **管理** > **連接**。
1. 請選取 **新增連線**。
1. 支援的連線類型方面，如果您連結金鑰保存庫，可以切換到 **使用金鑰保存庫**。
1. 無須手動輸入密碼，選擇指向金鑰保存庫秘密值的秘密名稱。

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="隨附 SFTP 連線使用 金鑰保存庫 秘密的連線窗格。":::

1. 選取 **儲存** 來建立連結。

## <a name="supported-connection-types"></a>支援的連線類型

支援的[匯出](export-destinations.md)連線如下：

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>在金鑰保存庫上授與的權限

如果啟用[Key Vault 存取原則](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)或 [Azure 角色型存取控制](/azure/key-vault/general/rbac-guide?tabs=azure-cli)，下列權限會在連結的金鑰保存庫上授與 Customer Insights 。

### <a name="key-vault-access-policy"></a>金鑰保存庫 存取政策

| 類型​        | 權限          |
| ----------- | -------------------- |
| 機碼         | [取得金鑰](/rest/api/keyvault/keys/get-keys/get-keys)、[取得金鑰](/rest/api/keyvault/keys/get-key/get-key)                                 |
| 祕密      | [取得秘密](/rest/api/keyvault/secrets/get-secrets/get-secrets)、[取得秘密](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| 憑證 | [取得證書](/rest/api/keyvault/certificates/get-certificates/get-certificates)、[取得證書](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

執行期間會列出和讀取先前的最小值。

### <a name="azure-role-based-access-control"></a>Azure 角色型存取控制

新增[金鑰保存庫讀者和金鑰保存庫秘密使用者角色](/azure/key-vault/general/rbac-guide?tabs=azure-cli)到 Customer Insights。

## <a name="frequently-asked-questions"></a>常見問題

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Customer Insights 可寫入秘密或將秘密覆寫到金鑰保存庫嗎？

不包括。 只有讀取和本文前面的 [授與的權限](#permissions-granted-on-the-key-vault)章節中列出權限才會授與給 Customer Insights。 系統無法在金鑰保存庫新增、刪除或覆寫秘密。 這也是您無法在連接使用金鑰保存庫時輸入憑證的原因。

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>我可以將連接使用 金鑰保存庫 秘密變更為預設驗證嗎？

號碼 在您使用連結的金鑰保存庫秘密組態密碼後，您無法變回預設連接。 分開建立連接，並在不需要時刪除舊的連接。

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>如何撤回 Customer Insights 的金鑰保存庫存取權？

如果啟用[金鑰保存庫存取原則](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)或 [Azure 角色型存取控制](/azure/key-vault/general/rbac-guide?tabs=azure-cli)，請移除`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`服務主體下名稱為 `Dynamics 365 AI for Customer Insights` 的權限。 所有使用金鑰保存庫的連接都會停止運作。

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>連接使用的秘密已從金鑰保存庫移除。 我能做什麼?

當金鑰保存庫設定的秘密無法存取時，Customer Insights 會出現通知。 如果無意間移除秘密，可在金鑰保存庫上啟用[虛刪除](/azure/key-vault/general/soft-delete-overview)恢復。

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>連接無法運作，但是我的秘密在金鑰保存庫內。 也許是什麼原因？

當無法存取金鑰保存庫時，Customer Insights 會出現通知。 原因可能是：

- Customer Insights 服務主體權限已移除。 它們必須手動恢復。

- 已啟用金鑰保存庫上的防火牆。 您必須停用防火牆才能重新存取 Customer Insights 的金鑰保存庫。
