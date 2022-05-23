---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755534"
---
內嵌資料之後，請開始進行資料整合程序，建立整合的客戶個人資料。 如需更多資訊，請見 [資料統整](../data-unification.md)。

### <a name="select-source-fields"></a>選取來源欄位

1. 內嵌資料後，將電子商務的聯絡人與忠誠度資料對應到常用資料類型。 請前往 **資料** > **整合**。

1. 選取代表客戶設定檔的實體 – **eCommerceContacts** 和 **loyCustomers**。

   ![統整電子商務與忠誠度資料來源。](../media/unify-ecommerce-loyalty.png)

1. 選取 **ContactId** 做為 **eCommerceContacts** 主鍵，而 **LoyaltyID** 做為 **loyCustomers** 主鍵。

1. 選取 **下一步**。 略過重複資料記錄，然後選取 **下一步**。

### <a name="match-conditions"></a>比對條件

1. 選擇 **eCommerceContacts : eCommerce** 作為主要實體，並包含所有的記錄。

1. 選擇 **loyCustomers : LoyaltyScheme**，並包含所有的記錄。

1. 加入規則：
   - 請為 eCommerceContacts 和 loyCustomers 選取 **FullName**。
   - 選取 **類型 (電話、名稱、位址、...)** 以進行 **標準化**。
   - 設定 **精密等級**：**基本** 與 **值**：**高**。
   - 輸入 **FullName, Email** 的名稱。

1. 對電子郵件地址新增第二個條件：
   - 請為 eCommerceContacts 和 loyCustomers 選取 **Email**。
   - 保留正規化空白。
   - 設定 **精密等級**：**基本** 與 **值**：**高**。

   ![統整比對規則的名稱和電子郵件。](../media/unify-match-rule.png)

1. 選取 **完成**。

1. 選取 **下一步**。

### <a name="unify-fields"></a>整合欄位

1. 將 **loyCustomers** 實體的 **ContactId** 重新命名為 **ContactIdLOYALTY**，以將它與其他識別碼內嵌區分開來。

1. 選取 **下一步** 以進行審查，然後選取 **建立客戶個人資料**。
