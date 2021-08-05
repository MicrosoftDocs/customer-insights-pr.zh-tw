---
title: 以 Experian 協力廠商擴充進行擴充
description: 關於 Experian協力廠商擴充的一般資訊。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: abe9ee447745081e3c462d44e5901b6dac919adf
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555343"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>利用 Experian 的人口統計資訊擴充客戶個人資料 (預覽版)

Experian 是消費者和企業信用報告和行銷服務的全球領導者。 有了 Experian 資料擴充服務服務，您可以使用人口統計資料 (例如，家庭大小、收入和其他資訊) 來擴充您的客戶個人資料，以建立深入瞭解您的客戶。

## <a name="prerequisites"></a>先決條件

若要設定 Experian，必須符合以下先決條件：

- 您必須擁有 Experian 訂用帳戶。 若要取得訂閱，請直接[聯繫 Experian](https://www.experian.com/marketing-services/contact)。 [深入了解 Experian 資料擴充](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。

- Experian 連接已由系統管理員設定，*或* 您擁有[系統管理員](permissions.md#administrator)權限。 您也需要 Experian 為您建立的支援 SSH 的安全傳輸 (ST) 帳戶的使用者識別碼、當事人識別碼和型號編號。

## <a name="supported-countriesregions"></a>支援的國家/地區

目前我們僅在美國支援擴充客戶個人資料。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 Experian 圖格上，選取 **擴充我的資料**。

   > [!div class="mx-imgBorder"]
   > ![Experian 圖標。](media/experian-tile.png "Experian tile")
   > 

1. 從下拉式清單選取一個[連結](connections.md)。 如果沒有可用的連接，請與系統管理員聯繫。 如果您是系統管理員，則可以選取 **新增連接**，然從下拉式清單中選擇 Experian，來建立連接。 

1. 選取 **連接至 Experian** 來確認選取連接。

1.  選取 **下一步**，然後選擇要以 Experian 人口統計資料擴充的 **客戶資料集**。 您可以選取 **客戶** 實體來擴充所有的客戶設定檔，或選取客戶細分實體僅擴充位於該客戶細分的客戶設定檔。

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. 選取 **下一步**，並定義應該使用的整合個人資料欄位類型，來在 Experian 中尋找符合的人口統計資料。 至少要有 **名稱和位址**、**電話** 或 **電子郵件** 中的一個欄位。 為了獲得更高的比對準確性，其他欄位最多可新增兩個。 這項選取將會影響在下一個步驟中可以存取的對應欄位。

    > [!TIP]
    > 傳送更多的金鑰識別碼屬性，Experian更容易會產生較佳的符合率。

1. 請選取 **下一步**，開始欄位對應。

1. 定義應該使用的整合個人資料欄位類型，來在 Experian 中尋找符合的人口統計資料。 必要欄位被標記。

1. 提供擴充的名稱以及輸出實體的名稱。

1. 檢閱選擇之後，請選取 **儲存擴充**。

## <a name="configure-the-connection-for-experian"></a>設定 Experian 的連接 

您必須是系統管理員才能設定連接。 在設定擴充時，請選取 **新增連接**，*或* 移至 **管理** > **連接**，並在 Experian 圖格上選取 **設定**。

1. 選取 **開始使用**。

1. 在 **顯示名稱** 方塊中輸入連接的名稱。

1. 輸入您的 Experian 安全傳輸帳戶的有效使用者識別碼、當事人識別碼和型號編號。

1. 檢閱並選取 **我同意**，提供您的 **資料隱私權和合規性** 許可。

1. 選取 **驗證** 來驗證設定。

1. 完成驗證之後，請選取 **儲存**。
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 連接設定窗格。":::

## <a name="enrichment-results"></a>擴充結果

若要開始擴充程序，請從命令列中選取 **執行**。 您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。 處理時間將視客戶資料大小和 Experian 為您的帳戶設定的擴充程序而定。

擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。 此外，您還會找到上次更新時間以及已擴充的設定檔數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

## <a name="next-steps"></a>後續步驟

建立在您擴充的客戶資料之上。 建立[客戶細分](segments.md)和 [量值 ](measures.md)，甚至 [匯出資料](export-destinations.md)，為您的客戶提供個人化的體驗。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用  Dynamics 365 Customer Insights 將資料傳輸到 Experian 時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在的敏感性資料 (例如個人資料)。 Microsoft 將會依您的指示傳送這類資料，但是您必須負責確保 Experian 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此擴充，不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
