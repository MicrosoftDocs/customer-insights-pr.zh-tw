---
title: 實體和實體路徑之間的關係
description: 從多個資料來源建立和管理實體之間的關係。
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405283"
---
# <a name="relationships-between-entities"></a>實體間的關聯

關聯可協助您連接實體，並在實體共用可從一個實體參考另一個實體的通用識別碼（外部索引鍵）時，產生資料圖形。 連接的實體可讓您依據多個資料來源來定義區段和量值。

關聯有兩種類型。 不可編輯的系統關聯（自動建立），以及由使用者建立和設定的自訂關聯。

在比對和合併程序期間，會根據智慧型比對，在幕後建立系統關聯。 這些關聯有助於將客戶設定檔記錄關聯至其他對應實體的記錄。 下圖顯示當客戶實體與其他實體比對以產生最終的客戶設定檔實體時，建立了三個系統關聯。

> [!div class="mx-imgBorder"]
> ![關聯建立](media/relationships-entities-merge.png "關聯建立")

- ***CustomerToContact* 關聯** 是在客戶實體與連絡人實體之間建立的。 客戶實體會取得與連絡人實體索引鍵欄位 **contactId** 相關的 **Contact_contactId** 索引鍵欄位。
- **_CustomerToAccount_ 關聯** 是在客戶實體與帳戶實體之間建立的。 客戶實體會取得與帳戶實體索引鍵欄位 **accountId** 相關的 **Account_accountId** 索引鍵欄位。
- **_CustomerToWebAccount_ 關聯** 是在客戶實體與 WebAccount 實體之間建立的。 客戶實體會取得與 WebAccount 實體索引鍵欄位 **webaccountId** 相關的 **WebAccount_webaccountId** 索引鍵欄位。

## <a name="create-a-relationship"></a>建立關聯

在 **關聯** 頁面上定義自訂關聯。 每個關聯均包含來源實體（保存外部索引鍵的實體）和目標實體（來源實體之外部索引鍵所指向的實體）。

1. 請在對象見解中前往 **資料** > **關係**。

2. 選取 **新增關聯**。

3. 在 **新增關聯** 窗格上，提供下列資訊：

   > [!div class="mx-imgBorder"]
   > ![輸入關聯詳細資料](media/relationships-add.png "輸入關聯詳細資料")

   - **關聯名稱**：反映關聯用途的名稱（例如，**AccountWebLogs**）。
   - **描述**：關聯的描述。
   - **來源實體**：選取在關聯中用作來源的實體（例如，WebLog）。
   - **基數**：選取來源實體記錄的基數。 例如，「很多」表示多個 Weblog 記錄與一個 WebAccount 相關聯。
   - **來源索引鍵欄位**：這代表來源實體中的外部索引鍵欄位。 例如，WebLog 有 **accountId** 外部索引鍵欄位。
   - **目標實體**：選取在關聯中用作目標的實體（例如，WebAccount）。
   - **目標基數**：選取目標實體記錄的基數。 例如，「一個」表示多個 Weblog 記錄與一個 WebAccount 相關聯。
   - **目標索引鍵欄位**：此欄位表示目標實體的索引鍵欄位。 例如，WebAccount 有 **accountId** 索引鍵欄位。

> [!NOTE]
> 只支援多對一或一對一關聯。 多對多關聯可使用兩個多對一關聯和連結實體（用於連接來源實體和目標實體的實體）來建立。

## <a name="delete-a-relationship"></a>刪除關聯

1. 請在對象見解中前往 **資料** > **關係**。

2. 選取您要刪除之關聯的核取方塊。

3. 在 **關聯** 表格頂端選取 **刪除**。

4. 確認刪除。

## <a name="next-step"></a>後續步驟

系統和自訂關聯是根據已不再分散的多個資料來源來建立區段。 如需詳細資訊，請參閱[區段](segments.md)。
