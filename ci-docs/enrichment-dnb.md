---
title: 透過 Dun & Bradstreet 來擴充公司資料
description: Dun & Bradstreet 協力廠商的一般資訊。
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653698"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>透過 Dun & Bradstreet 來擴充公司資料 (預覽版)

Dun & Bradstreet 為公司供應商業資料、分析和見解。 為客戶帶來統一客戶設定檔，讓各家公司可以擴充其資料。 擴充公司屬性包括 DUNS 編碼、公司規模、位置、產業等等。

## <a name="prerequisites"></a>先決條件

若要設定 Dun & Bradstreet 擴充，必須符合以下先決條件：

- 您必須具有有效的 [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) 授權。
- 您有公司的[統一客戶設定檔](customer-profiles.md)。
- Dun & Bradstreet [連接](connections.md)是由系統管理員設定。 如果您擁有[系統管理員](permissions.md#admin)的權限，以及 Dun & Bradstreet Connect 的認證，就可以建立擴充。 

## <a name="setting-up-your-dun--bradstreet-project"></a>設定 Dun & Bradstreet 專案

作為 Dun & Bradstreet 的授權使用者，您可以在 [ Dun & Bradstreet Connect 連接](https://connect.dnb.com?lead_source=microsoft_audienceinsights)中設定專案。 


1. 登入 [Dun & Bradstreet 連接](https://connect.dnb.com?lead_source=microsoft_audienceinsights)。 若要取出認證，請[還原您的密碼](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights)。

1. 下載用來將見解欄位對應至 Dun & Bradstreet 欄位的 [csv 範本檔案](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv)。 

1. 使用 Dun & Bradstreet 專案建立體驗的 **上傳資料** 步驟，上傳檔案。 

1. 在新建立的 Dun & Bradstreet 專案中，選取相關 **來源** 下方的水平點組，以查看可用的選項。

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="螢幕擷取畫面：圖上為 Dun & Bradstreet 專案中的點組。":::

1. 選擇 **取得 S3 詳細資料**。 將此資訊儲存在安全的地方。 您將需要它，才能在對象見解中[設定擴充的連接](#configure-a-connection-for-dun--bradstreet)。 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="在 Dun & Bradstreet 專案中選取 s3 資訊的螢幕擷取畫面。":::



## <a name="configure-the-enrichment"></a>擴充設定

1. 請在對象見解中前往 **資料** > **富集**。

1. 在 Dun & Bradstreet 磚上選取 **擴充我的資料**，然後選取 **開始使用**。

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet 磚的螢幕擷取畫面。":::

1. 從下拉式清單選取一個[連結](connections.md)。 如果沒有可用的連接，請與系統管理員聯繫。 如果您是系統管理員，則可以建立連接。 選取 **新增連接**，然後選擇 **Dun & Bradstreet**。 

1. 選取 **連接至 Dun & Bradstreet** 來確認該連接。

1. 選取 **下一步**，接著選擇要使用 Dun & Bradstreet 的公司資料進行擴充的 **客戶資料集**。 您可以選取 **客戶** 實體來擴充所有客戶個人資料，或選取客戶細分實體僅擴充位於該客戶細分的整合客戶個人資料。

1. 選取 **下一步**，接著定義在 Dun & Bradstreet 比對公司資料時，整合個人資料中應使用的欄位類型。 **DUNS 編號** 或 **公司名稱** 以及 **國家/地區** 欄位是必要的。 國家/地區欄位支援 [2 或 3 個字母的國家/地區代碼](https://www.iso.org/iso-3166-country-codes.html)、英文名稱、國家/地區原文名稱、和電話首碼。 一些共同的國家/地區變化型包括：

   * US：United States of America、United States、USA、America。
   * CA：Canada。
   * GB：United Kingdom、UK、Great Britain、GB、United Kingdom of Great Britain and Northern Ireland、United Kingdom of Great Britain。
   * AU：Australia、Commonwealth of Australia。
   * FR：France、French Republic。
   * DE：Germany、German、Deutschland、Allemagne、Federal Republic of Germany、Republic of Germany。

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet 欄位對應窗格。":::

1. 請選取 **下一步**，完成欄位對應。

1. 提供擴充的名稱，並在檢閱選擇後選取 **儲存擴充**。


## <a name="configure-a-connection-for-dun--bradstreet"></a>設定 Dun & Bradstreet 的連接 

您必須是系統管理員才能設定連接。 設定擴時，請選取 **新增連接**，*或* 前往 **系統管理員** > **連接** 然後 Dun & Bradstreet 磚上選取 **設定**。

1. 選取 **開始使用**。 

1. 在 **顯示名稱** 方塊中輸入連接的名稱。

1. 提供有效的 Dun & Bradstreet 認證和 Dun & Bradstreet 專案詳細資料 *區域、放置資料夾路徑及放置資料夾名稱*。 您可以從 Dun & Bradstreet 專案[取得此資訊](#setting-up-your-dun--bradstreet-project)。

1. 檢閱並選取 **我同意**，提供您的 **資料隱私權和合規性** 許可。

1. 選取 **驗證** 來驗證設定。

1. 完成驗證之後，請選取 **儲存**。
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet 的連接設定頁面":::

## <a name="enrichment-results"></a>擴充結果

重新整理擴充內容之後，您可以在[我的擴充內容](enrichment-hub.md)中檢閱新近擴充的公司資料。 您可以找到上次更新的時間以及已擴充設定檔的數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 對 Dun & Bradstreet 的資料傳輸時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，其中包括潛在敏感性資料，如個人資料。 Microsoft 將會在您指示時傳送這類資料，但是您必須負責確保 Dun & Bradstreet 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此擴充，不再繼續使用此功能。


[!INCLUDE[footer-include](includes/footer-banner.md)]
