---
title: 協力廠商 Enrichment Leadspace 的公司設定檔
description: 有關協力廠商 Leadspace 富集作用的一般資訊。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 34b73b37670ed45e2c31ea164c0788b793bee433829ce21317c83903f3fca1fe
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031693"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>使用 Leadspace 擴充公司設定檔 (預覽)

Leadspace 是一家提供 B2B 客戶資料平台的資料科學公司。 為客戶帶來統一客戶設定檔，讓各家公司可以擴充其資料。 擴充包括更多屬性，例如公司規模、位置、產業等等。

## <a name="prerequisites"></a>先決條件

若要設定 Leadspace，必須符合以下先決條件：

- 您有一個有效的 Leadspace 授權。
- 您有公司的[統一客戶設定檔](customer-profiles.md)。
- Leadspace 連接已由系統管理員設定，或者您有 [系統管理員](permissions.md#administrator)權限和「永久金鑰」(被稱為 **Leadspace 權杖**)。 如需產品的詳細資料，請直接聯繫 [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/)。

## <a name="configure-the-enrichment"></a>擴充設定

1. 請在對象見解中前往 **資料** > **富集**。

1. 在 Leadspace 圖格上選取 **擴充我的資料**，然後選取 **開始使用**。

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 圖格的螢幕擷取畫面。":::

1. 從下拉式清單選取一個[連結](connections.md)。 如果沒有可用的連接，請與系統管理員聯繫。 如果您是系統管理員，則可以選取 **新增連接** 接著選擇 **Leadspace** 來建立連接。 

1. 選取 **連接至 Leadspace** 以確認選取連接。

1. 選取 **下一步**，然後選擇想要用 Leadspace 的公司資料擴充的 **客戶資料集**。 您可以選取 **客戶** 實體來擴充所有的客戶設定檔，或選取客戶細分實體僅擴充位於該客戶細分的客戶設定檔。

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. 選取 **下一步**，接著定義在整合個人資料中的欄位，這些欄位用來在 Leadspace 尋找符合的公司資料。 **公司名稱** 欄位是必要欄位。 為了獲得更高的準確性，可以新增多達兩個欄位，**公司網站** 和 **公司位置**。

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 欄位對應窗格。":::

1. 請選取 **下一步**，完成欄位對應。

1. 提供擴充的名稱，並在檢閱選擇後選取 **儲存擴充**。


## <a name="configure-the-connection-for-leadspace"></a>設定 Leadspace 的連接 

您必須是系統管理員才能設定連接。 在設定擴充時，請選取 **新增連接***或* 在 Leadspace 圖格上移至 **管理** > **連接** 並選取 **設定**。

1. 選取 **開始使用**。 

1. 在 **顯示名稱** 方塊中輸入連接的名稱。

1. 提供有效的 Leadspace 權杖。

1. 檢閱並選取 **我同意**，提供您的 **資料隱私權和合規性** 許可。

1. 選取 **驗證** 來驗證設定。

1. 完成驗證之後，請選取 **儲存**。
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 的連接設定頁面。":::

## <a name="enrichment-results"></a>擴充結果

重新整理擴充內容之後，您可以在[我的擴充內容](enrichment-hub.md)中檢閱新近擴充的公司資料。 您可以找到上次更新的時間以及已擴充設定檔的數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

如需詳細資訊，請參閱 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)。

## <a name="next-steps"></a>後續步驟

建立在您擴充的客戶資料之上。 建立[客戶細分](segments.md)和 [量值 ](measures.md)，甚至 [匯出資料](export-destinations.md)，為您的客戶提供個人化的體驗。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Leadspace 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Leadspace 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此擴充，不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]