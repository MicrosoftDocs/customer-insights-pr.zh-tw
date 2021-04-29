---
title: 藉助協力廠商 Enrichment Experian 的富集作用
description: 有關 Experian 協力廠商富集作用的一般資訊。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896363"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>使用 Experian 提供的人口統計資料擴充客戶設定檔 (預覽)

Experian 是消費者與企業信用報告以及行銷服務的全球領導者。 有了 Experian 的資料擴充服務，您就可以透過人口統計資料 (例如家庭人數、收入及其他) 擴充您的客戶設定檔，加深對客戶的了解。

## <a name="prerequisites"></a>先決條件

若要設定 Experian，必須符合以下先決條件：

- 您擁有有效的 Experian 訂閱。 若要取得訂閱，請直接[與 Experian 連絡](https://www.experian.com/marketing-services/contact)。 [深入了解t Experian 資料擴充](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。

- Experian 連接已由系統管理員設定，*或* 您擁有[系統管理員](permissions.md#administrator)權限。 您也需要啟用 SSH 的安全傳輸 (ST) 帳戶的使用識別碼、合作對象識別碼和模型編碼，該帳戶是由 Experian 所建立的。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 選取 Experian 圖標上的 **擴充我的資料**。

   > [!div class="mx-imgBorder"]
   > ![Experian 圖標](media/experian-tile.png "Experian 圖標")
   > 

1. 在下拉式清單中選取一個[連接](connections.md)。 如果沒有可用的連接，請與系統管理員聯繫。 如果您是系統管理員，則可以選取 **新增連接**，並從下拉式清單中選擇 Experian 來建立連接。 

1. 選取 **連接至 Experian** 以確認選取連接。

1.  選取 **下一步**，然後選擇想要用 Experian 的人口統計資料擴充的 **客戶資料集**。 您可以選取 **客戶** 實體來擴充所有的客戶設定檔，或選取客戶細分實體僅擴充位於該客戶細分的客戶設定檔。

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. 選取 **下一步**，接著定義在整合個人資料中的欄位類型，該類型用來在 Experian 尋找符合的人口統計資料。 至少要有 **名稱和位址**、**電話** 或 **電子郵件** 中的一個欄位。 為了獲得更高的比對準確性，其他欄位最多可新增兩個。 這項選取將會影響在下一個步驟中可以存取的對應欄位。

    > [!TIP]
    > 傳送至 Experian 的金鑰識別元屬性愈多，可能產生的適配率愈高。

1. 請選取 **下一步**，開始欄位對應。

1. 定義在整合個人資料中的欄位類型，該欄位用來在 Experian 尋找符合的人口統計資料。 必要欄位被標記。

1. 提供擴充的名稱以及輸出實體的名稱。

1. 檢閱選擇之後，請選取 **儲存擴充**。

## <a name="configure-the-connection-for-experian"></a>設定 Experian 的連接 

您必須是系統管理員才能設定連接。 在設定擴充時，請選取 **新增連接***或* 在 Experian 圖格上移至 **管理** > **連接** 並選取 **設定**。

1. 選取 **開始使用**。

1. 在 **顯示名稱** 方塊中輸入連接的名稱。

1. 為您的 Experian 安全傳輸帳戶輸入有效的使用者識別碼、合作對象識別碼和模型編號。

1. 檢閱 **資料隱私權和合規性** 並選取 **我同意** 的核取方塊，表示同意

1. 選取 **驗證** 來驗證設定。

1. 完成驗證之後，請選取 **儲存**。
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 連接設定窗格。":::

## <a name="enrichment-results"></a>擴充結果

若要開始擴充程序，請從命令列中選取 **執行**。 您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。 處理時間取決於客戶資料的大小以及 Experian 為您帳戶設定的擴充程序。

擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。 此外，您還會找到上次更新時間以及已擴充的設定檔數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

## <a name="next-steps"></a>後續步驟

建立在您擴充的客戶資料之上。 建立[客戶細分](segments.md)、[量值](measures.md)，甚至[匯出資料](export-destinations.md)，以便傳送個人化體驗給您的客戶。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Experian 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Experian 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此富集作用，以便不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
