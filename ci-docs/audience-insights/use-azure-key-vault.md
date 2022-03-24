---
title: 帶入您自己的 Azure 金鑰保存庫管理祕密
description: 瞭解如何將 Customer Insights 組態為使用您自己的 Azure 金鑰保存庫。
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 418575f724090628da8bd01e2569a4cb9e646337
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376498"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>帶入您自己的 Azure 金鑰保存庫 (預覽版)

將專用的 [Azure 金鑰保存庫](/azure/key-vault/general/basic-concepts)連結到對象見解環境有助於組織符合法令遵循要求。
專用的金鑰保存庫可用來在組織的法令遵循邊界內分階段使用秘密。 對象見解可使用 Azure 金鑰保存庫的秘密[設定與](connections.md)協力廠商系統的連線。

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>將金鑰保存庫連結到對象見解環境

### <a name="prerequisites"></a>先決條件

若要在對象見解中組態金鑰保存庫，必須符合下列先決條件：

- 您必須具備有效的 Azure 訂閱。

- 您必須具備對象見解中[系統管理員](permissions.md#admin)的角色。 瞭解更多有關[對象見解的使用者權限](permissions.md#assign-roles-and-permissions)。

- 您在金鑰保存庫或其隸屬的資源群組上扮演[參與者](/azure/role-based-access-control/built-in-roles#contributor)和[使用者存取系統管理員](/azure/role-based-access-control/built-in-roles#user-access-administrator)的角色。 如需詳細資訊，請前往[使用 Azure 入口網站新增移除 Azure 角色指派](/azure/role-based-access-control/role-assignments-portal)。 如果您不具備金鑰保存庫上的使用者存取系統管理員角色，您必須分別為 Azure 對 Dynamics 365 Customer Insights 的服務主體設定角色型存取控制權限。 請遵照步驟針對應連結的金鑰保存庫[使用 Azure 服務主體](connect-service-principal.md)。

- 金鑰保存庫必須 **停用** 金鑰保存庫防火牆。

- 金鑰保存庫與對象見解環境位於相同的 [Azure 位置](https://azure.microsoft.com/global-infrastructure/geographies/#overview)。 對象見解 中的環境區域列在 **系統管理員** > **系統** > **關於** > **區域** 下方。

### <a name="link-a-key-vault-to-the-environment"></a>將金鑰保存庫連結到環境

1. 請前往 **系統管理員** > **系統** ，然後選取 **安全性** 索引標籤。
1. 請在 **金鑰保存庫** 圖格上選取 **設定**。
1. 選擇 **訂閱**。
1. 請從 **金鑰保存庫** 下拉式清單選擇金鑰保存庫。 如果顯示過多金鑰保存庫，請選取資源群組限制搜尋結果。
1. 請接受 **資料隱私權與法令遵循** 聲明。
1. 選取 **儲存**。

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="在對象見解中設定連結的金鑰保存庫步驟。":::

**金鑰保存庫** 圖格現在會顯示連結的金鑰保存庫名稱、資源群組和訂閱。 您現在可以在連接設定中使用它。
如需有關金鑰保存庫權限授予對象見解的詳細資訊，請前往本文稍候的[金鑰保存庫授予對象見解的權限](#permissions-granted-on-the-key-vault-to-audience-insights)。

## <a name="use-the-key-vault-in-the-connection-setup"></a>請在連接設定中使用金鑰保存庫

[設定](connections.md)與協力廠商系統的連線時，可以使用連結的金鑰保存庫秘密設定連接。

1. 移至 **管理** > **連接**。
1. 請選取 **新增連線**。
1. 支援的連線類型方面，如果您連結金鑰保存庫，可以切換到 **使用金鑰保存庫**。
1. 與其手動輸入密碼，您可以選擇指向金鑰保存庫秘密值的秘密名稱。

:::image type="content" source="media/use-key-vault-secret.png" alt-text="隨附 SFTP 連線使用 金鑰保存庫 秘密的連線窗格。":::

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>授予對象見解在金鑰保存庫的權限

如果啟用[金鑰保存庫 存取政策](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)或 [Azure 角色型存取控制](/azure/key-vault/general/rbac-guide?tabs=azure-cli)，下列權限會在連結的金鑰保存庫上授予 對象見解。

### <a name="key-vault-access-policy"></a>金鑰保存庫 存取政策

| 類型​        | 權限          |
| ----------- | -------------------- |
| 機碼         | [取得金鑰](/rest/api/keyvault/get-keys)、[取得金鑰](/rest/api/keyvault/get-key)                                 |
| 祕密      | [取得秘密](/rest/api/keyvault/get-secrets)、[取得秘密](/rest/api/keyvault/get-secret)                     |
| 憑證 | [取得證書](/rest/api/keyvault/get-certificates)、[取得證書](/rest/api/keyvault/get-certificate) |

執行期間會列出和讀取先前的最小值。

### <a name="azure-role-based-access-control"></a>Azure 角色型存取控制

金鑰保存庫 Reader 和 金鑰保存庫 Secrets 使用者角色將新增給 對象見解。 如需這些角色的詳細資訊，請前往 [Azure 金鑰保存庫 資料面作業的內建角色](/azure/key-vault/general/rbac-guide?tabs=azure-cli)。

## <a name="recommendations"></a>建議

- 請使用只包含對象見解所需秘密的獨立或專用金鑰保存庫。 閱讀更多有關為何建議[分開的金鑰保存庫](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults)。

- 遵照[金鑰保存庫 的最佳使用做法](/azure/key-vault/general/best-practices#turn-on-logging)進行控制存取、備份、稽核及復原選項。

## <a name="frequently-asked-questions"></a>常見問題

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>對象見解 可寫入秘密或將秘密覆寫到金鑰保存庫嗎？

號碼 只有本文稍早章節，[授與的權限](#permissions-granted-on-the-key-vault-to-audience-insights)中概述的讀取和列表權限才會授予 對象見解。 系統無法在金鑰保存庫新增、刪除或覆寫秘密。 這也是您無法在連接使用金鑰保存庫時輸入憑證的原因。

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>我可以將連接使用 金鑰保存庫 秘密變更為預設驗證嗎？

號碼 在您使用連結的金鑰保存庫秘密組態密碼後，您無法變回預設連接。 分開建立連接，並在不需要時刪除舊的連接。

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>如何撤回對象見解的金鑰保存庫存取權？

根據是否啟用[金鑰保存庫 存取政策](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)或 [Azure 角色型存取控制](/azure/key-vault/general/rbac-guide?tabs=azure-cli)功能，您必須移除名稱為 `Dynamics 365 AI for Customer Insights` 的`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`服務主體權限。 所有使用金鑰保存庫的連接都會停止運作。

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>連接使用的秘密已從金鑰保存庫移除。 我能做什麼?

當無法再存取金鑰保存庫的組態秘密時，對象見解 會出現通知。 如果無意間移除秘密，可在金鑰保存庫上啟用[虛刪除](/azure/key-vault/general/soft-delete-overview)恢復。

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>連接無法運作，但是我的秘密在金鑰保存庫內。 也許是什麼原因？

當無法存取金鑰保存庫時，對象見解 會出現通知。 原因可能是：

- 對象見解 服務主體權限已移除。 它們必須手動恢復。

- 已啟用金鑰保存庫上的防火牆。 您必須停用防火牆才能重新存取對象見解的金鑰保存庫。
