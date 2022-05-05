---
title: 協力廠商 Enrichment Leadspace 的公司設定檔
description: 有關協力廠商 Leadspace 富集作用的一般資訊。
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 08a4c56eb1c387015fd9e985a0c9484a13236fcf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645837"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>使用 Leadspace 擴充公司設定檔 (預覽)

Leadspace 是一間提供 B 到 B 客戶資料平台的資料科學公司。 它讓環境按帳戶隨著統一的客戶設定檔擴充其資料。 使用如公司規模、位置或行業的屬性擴充 *客戶設定檔*。 使用標題、角色或電子郵件驗證等屬性擴充 *連絡人設定檔*。

## <a name="prerequisites"></a>先決條件

若要設定 Leadspace，必須符合以下先決條件：

- 您有一個有效的 Leadspace 授權。
- 您有按帳戶基礎的[統一客戶設定檔](customer-profiles.md)。
- Leadspace 連接已由系統管理員設定，或者您有 [系統管理員](permissions.md#admin)權限和「永久金鑰」(被稱為 **Leadspace 權杖**)。 如需產品的詳細資料，請直接聯繫 [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/)。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**。

1. 在 Leadspace 圖格上選取 **擴充我的資料**，然後選取 **開始使用**。

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 圖格的螢幕擷取畫面。":::

1. 從下拉式清單選取一個[連結](connections.md)。 如果沒有可用的連接，請與系統管理員聯繫。 如果您是系統管理員，則可以選取 **新增連接** 接著選擇 **Leadspace** 來建立連接。 

1. 選取 **連接至 Leadspace** 以確認選取連接。

1. 選取 **下一步**，然後選擇想要用 Leadspace 的公司資料擴充的 **客戶資料集**。 您可以選取 **客戶** 實體來擴充所有的客戶設定檔，或選取客戶細分實體僅擴充位於該客戶細分的客戶設定檔。

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. 選取 **下一步**，接著定義在整合個人資料中的欄位，這些欄位用來在 Leadspace 尋找符合的公司資料。 **公司名稱** 欄位是必要欄位。 為了獲得更高的準確性，可以新增多達兩個欄位，**公司網站** 和 **公司位置**。

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 欄位對應窗格。":::

1. 請選取 **下一步**，完成欄位對應。

1. 如果您有想要擴充的 *連絡人設定檔*，請選取勾選方塊。 Customer Insights 將自動對應必要欄位。

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Leadspace 連絡人記錄擴充。":::
 
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


[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Leadspace 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Leadspace 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此擴充，不再繼續使用此功能。


[!INCLUDE [footer-include](includes/footer-banner.md)]
