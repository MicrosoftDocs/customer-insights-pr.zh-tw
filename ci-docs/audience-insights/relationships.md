---
title: 實體和實體路徑之間的關係
description: 從多個資料來源建立和管理實體之間的關係。
ms.date: 09/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c639cfca30cf1b57ada7d728311210b7210a37ac
ms.sourcegitcommit: f72d5b86dfdc7282c6c1918b1ab3962d7a1c9852
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2021
ms.locfileid: "7557342"
---
# <a name="relationships-between-entities"></a>實體間的關聯

當實體共用一般識別碼 (外部索引鍵) 時，關聯會連接實體並定義資料圖形。 此外部索引鍵可以從一個實體參照到另一個實體。 連接的實體依據多個資料來源來啟用客戶細分和量值定義。

有三種類型的關聯： 
- 不可編輯的系統關聯，是在資料整合程序中由系統建立的
- 不可編緝的繼承關聯，是內嵌資料來源時自動建立的 
- 可編輯的自訂關聯，由使用者建立和設定

## <a name="non-editable-system-relationships"></a>不可編輯的系統關聯

在資料整合時，會根據智慧比對自動建立系統關聯。 這些關聯有助於將客戶個人資料記錄關聯至其他對應記錄。 以下圖表將圖示三種系統型關聯的建立。 客戶實體與其他實體比對，以產生整合的的 *客戶* 實體。

:::image type="content" source="media/relationships-entities-merge.png" alt-text="具有三個 1-n 關聯的客戶實體關聯路徑圖表。":::

- ***CustomerToContact* 關聯** 是在 *客戶* 實體與 *連絡人* 實體之間建立的。 *客戶* 實體會取得 **Contact_contactID** 索引鍵欄位，來關聯 *連絡人* 實體索引鍵欄位 **contactID** 。
- ***CustomerToAccount* 關聯** 是在 *客戶* 實體與 *帳戶* 實體之間建立的。 *客戶* 實體會取得 **Account_accountID** 索引鍵欄位，來關聯 *帳戶* 實體索引鍵欄位 **accountID**。
- ***CustomerToWebAccount* 關聯** 是在 *客戶* 實體與 *WebAccount* 實體之間建立的。 *客戶* 實體會取得 **WebAccount_webaccountID** 索引鍵欄位，並關連到 *WebAccount* 實體索引鍵欄位 **webaccountID**。

## <a name="non-editable-inherited-relationships"></a>不可編輯的繼承關聯

資料擷取程序進行時，系統會檢查資料來源的現有關聯。 如果不存在任何關聯，系統會自動建立這些關聯。 這些關聯也用在下游程序中。

## <a name="create-a-custom-relationship"></a>建立自訂關聯

關聯是由包含外部索引鍵的 *來源實體* 和來源實體的外部索引鍵指向的 *目標實體* 組成。 

1. 請在對象見解中前往 **資料** > **關係**。

2. 選取 **新增關聯**。

3. 在 **新增關聯** 窗格上，提供下列資訊：

   :::image type="content" source="media/relationship-add.png" alt-text="具有空白輸入欄位的新關聯側邊窗格。":::

   - **關聯名稱**：反映關聯用途的名稱。 範例：CustomerToSupportCase。
   - **描述**：關聯的描述。
   - **來源實體**：在關聯中作為來源的實體。 範例：SupportCase。
   - **目標實體**：在關聯中作為目標的實體。 範例：客戶。
   - **來源基數**：指定來源實體的基數。 基數說明集合中可能的元素數目。 它總是與目標基數有關。 您可以選擇 **一** 和 **多個**。 只支援多對一或一對一關聯。  
     - 多對一：多個來源記錄可以關連到一個目標記錄。 範例：來自單一客戶的多個支援案例。
     - 一對一：單一來源記錄關連到一個目標記錄。 範例：一位客戶的一個忠誠度識別碼。

     > [!NOTE]
     > 多對多關聯可以使用兩個多對一關聯和一個連結實體 (連入來源實體和目標實體) 來建立。

   - **目標基數**：選取目標實體記錄的基數。 
   - **來源索引鍵欄位**：來源實體中的外部索引鍵欄位。 範例：SupportCase 可以使用 CaseID 作為外部索引鍵欄位。
   - **目標索引鍵欄位**：欄位表示目標實體的索引鍵欄位。 範例客戶可以使用 **CustomerID** 索引鍵鍵欄位。

4. 選取 **儲存** 以建立自訂關聯。

## <a name="view-relationships"></a>檢視關聯性

關聯頁面會列出已建立的所有關聯。 每一列代表一個關聯，裡面也包含有關來源實體、目標實體和基數的詳細資料。 

:::image type="content" source="media/relationships-list.png" alt-text="在關聯頁面的動作欄中的關聯和選項清單。":::

此頁面對現有與新關聯提供一組選項： 
- **新增關聯**：[建立自訂關聯](#create-a-custom-relationship)。
- **視覺化檢視**：[探索關聯視覺化檢視](#explore-the-relationship-visualizer)，以查看現有關聯及其基數的網狀圖表。
- **依...篩選**：選擇要在清單中顯示的關聯類型。
- **搜尋關聯**：在關聯的屬性上使用文字型搜尋。

### <a name="explore-the-relationship-visualizer"></a>探索關聯視覺化檢視

視覺化檢視顯示網狀圖表，表示在連接實體間的現有關聯及其基數。 它也會視覺化關聯路徑。

若要自訂檢視表，您可以透過在畫布上拖動方塊來變更位置。

:::image type="content" source="media/relationship-visualizer.png" alt-text="關聯視覺化檢視的螢幕擷取畫面，圖上為相關實體間連接的網狀圖表。":::

可用的選項： 
- **匯出成影像**：將目前的檢視表儲存為影像檔。
- **變更為橫向/垂直版面配置**：變更實體與關聯的對齊方式。
- **編輯**：在編輯窗格中更新自訂關聯的屬性，並儲存變更。

## <a name="relationship-paths"></a>關聯路徑

關聯路徑說明來源實體與目標實體之間被關聯相連的實體。 在建立客戶細分或量值時，包含整合個人資料實體以外的其他實體，而且有多個選項可抵達整合個人資料實體，會使用到關聯路徑。 

關聯路徑會提供系統要用哪個關聯存取整合個人資料實體。 不同的關聯路徑可能會產生不同的結果。

例如，實體 *eCommerce_eCommercePurchases* 具有下列關聯至整合個人資料 *Customer* 實體：

- eCommerce_eCommercePurchases > Customer
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Customer
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Customer 

關聯路徑決定在建立量值或客戶細分規則時可以使用哪些實體。 選擇具有最長關聯路徑的選項，可能會產生較少的結果，因為符合的記錄必須存在在所有實體。 在此範例中，客戶必須透過電子商務購物 (eCommerce_eCommercePurchases)、銷售點(POS_posPurchases)，並參與我們的會員計畫 (loyaltyScheme_loyCustomers)。 選擇第一個選項時，您很可能會獲得更多結果，因為客戶只需存在在一個其他實體中。

### <a name="direct-relationship"></a>直接關聯

當來源實體使用一個關聯來關聯到一個目標實體時，會分類為 **直接關聯**。

例如，如果某個名稱為 *eCommerce_eCommercePurchases* 的活動實體，僅透過  *ContactId* 連接至目標實體 *eCommerce_eCommerceContacts* 實體，則這是直接關聯。

:::image type="content" source="media/direct_Relationship.png" alt-text="來源實體直接連接至目標實體。":::

#### <a name="multi-path-relationship"></a>多路徑關聯

**多路徑關聯** 是一種特殊類型的直接關聯，會將一個來源實體連接至多個目標實體。

例如，如果一個名稱為 *eCommerce_eCommercePurchases* 的活動實體，與關聯到 *eCommerce_eCommerceContacts* 和 *loyaltyScheme_loyCustomers* 兩個目標實體，則這是多路徑關聯。

:::image type="content" source="media/multi-path_relationship.png" alt-text="來源實體透過多躍點關聯直接連接至一個以上的目標實體。":::

### <a name="indirect-relationship"></a>間接關聯

當來源實體關聯到目標實體之前，會關聯到一個以上的其他實體時，會分類到 **非直接關聯**。

#### <a name="multi-hop-relationship"></a>多躍點關聯

*多躍點關聯* 是一種 *間接關聯*，可讓您透過一個以上的其他中繼實體將來源實體連接至目標實體。

例如，如果一個名為 *eCommerce_eCommercePurchasesWest* 的活動實體連接至名為 *eCommerce_eCommercePurchasesEast* 的中繼實體，然後連接至名為  *eCommerce_eCommerceContacts* 的目標實體，則這是多躍點關聯。

:::image type="content" source="media/multi-hop_relationship.png" alt-text="來源實體直接以中繼實體連接至目標實體。":::

### <a name="multi-hop-multi-path-relationship"></a>多躍點、多路徑關聯

多躍點和多路徑關聯可以一起使用，建立 **多躍點、多路徑關聯**。 這個特殊類型會結合 **多躍點** 和 **多路徑關聯** 的功能。 它可讓您在使用中繼實體時，連接至多個目標實體。

例如，如果一個名為 *eCommerce_eCommercePurchasesWest* 的活動實體連接至名為 *eCommerce_eCommercePurchasesEast* 的中繼實體，然後連接至名為  *eCommerce_eCommerceContacts* 和 *loyaltyScheme_loyCustomers* 的兩個目標實體，則這是多躍點、多路徑關聯。

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="來源實體會直接連接至一個目標實體，並透過中繼實體連接至另一個目標實體。":::

## <a name="manage-existing-relationships"></a>管理現有關聯 

在關聯頁面上，每個關聯都是以資料列顯示。 

選取關聯，然後選擇下列其中一個選項： 
 
- **編輯**：在編輯窗格中更新自訂關聯的屬性，並儲存變更。
- **刪除**：刪除自訂關聯。
- **查看**：查看系統-建立和繼承的關聯。 

## <a name="next-step"></a>下一個步驟

系統和自訂關聯是用來[建立客戶細分](segments.md)和[量值](measures.md)，利用已不再是筒倉式的多個資料來源。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
