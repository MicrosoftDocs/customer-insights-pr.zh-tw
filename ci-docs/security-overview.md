---
title: Dynamics 365 Customer Insights 安全性設定
description: 了解 Dynamics 365 Customer Insights 中的安全性設定。
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653701"
---
# <a name="security-overview-page"></a>安全性概觀頁面

**安全性** 頁面會列出設定使用者權限的選項，以及有助於增進 Dynamics 365 Customer Insights 安全性的功能。 只有系統管理員才能存取此頁面。 

請移至 **系統管理員** > **安全性** 進行設定。

**安全性** 頁面包括下列索引標籤：
- [使用者](#users-tab)
- [API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>使用者索引標籤

 Customer Insights 的存取被限制在由系統管理員新增至應用程式的組織內使用者。**使用者** 索引標籤可讓您管理使用者的存取權及其權限。 如需詳細資訊，請參閱[使用者權限](permissions.md)。

## <a name="apis-tab"></a>API 索引標籤

查看和管理金鑰，以將 [Customer Insights API](apis.md) 與您的環境資料搭配使用。

您可以選取 **重新生成主索引鍵** 或 **重新生成次索引鍵** 來建立新的主索引鍵和次索引鍵。 

若要封鎖環境的 API 存取，請選取 **停用**。 如果已停用 API，您可以選取 **啟用** 來再次授與存取權。

## <a name="key-vault-tab"></a>金鑰保存庫索引標籤

**金鑰保存庫** 索引標籤能讓您連結 [Azure 金鑰保存庫](/azure/key-vault/general/basic-concepts)與環境並進行管理。
專用的金鑰保存庫可用來在組織的法令遵循邊界內分階段使用秘密。 Customer Insights 可使用 Azure 金鑰保存庫的秘密以對協力廠商系統[設定連線](connections.md)。

如需更多資訊，請參閱[帶上您自己的 Azure 金鑰保存庫](use-azure-key-vault.md)。


[!INCLUDE [footer-include](includes/footer-banner.md)]
