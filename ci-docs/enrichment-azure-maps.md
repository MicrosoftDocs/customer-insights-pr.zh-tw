---
title: 使用 Azure 地圖服務的位置資料擴充客戶個人資料
description: 關於 Azure 地圖服務第一方企業擴充的一般資訊。
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 6a1c3791076a7dda4531664ca88632f7f1b914e3
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645721"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>使用 Azure 地圖服務擴充客戶個人資料 (預覽版)

Azure 地圖服務提供以位置為中心的資料和服務，利用內建位置智慧並根據地理空間資料來提供體驗。 Azure 地圖服務資料擴充服務改善客戶位置資訊的精準度。 它可將地址正規化和緯度及經度擷取等功能帶到 Dynamics 365 Customer Insights 中。

## <a name="prerequisites"></a>先決條件

若要設定 Azure 地圖服務資料擴充，必須符合下列先決條件：

- 您必須擁有 Azure 地圖服務訂用帳戶。 若要取得訂閱，您可以[註冊或取得免費試用版](https://azure.microsoft.com/services/azure-maps/)。

- 可以使用 Azure 地圖服務 [連接](connections.md)，*或者* 您具有[系統管理員](permissions.md#admin)權限和有效的 Azure 地圖服務 API 金鑰。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**。 

1. 在 **位置** 圖格上，選取 **擴充我的資料**。

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure 地圖服務圖格。":::

1. 從下拉式清單選取一個[連結](connections.md)。 如果沒有可用的 Azure 地圖服務連接，請與系統管理員聯繫。 如果您是系統管理員，您可以[設定 Azure 地圖服務的連接](#configure-the-connection-for-azure-maps)。 

1. 選取 **下一步** 確認選取。

1. 選擇您想要以 Azure 地圖服務位置資料擴充的 **客戶資料集**。 您可以選取 **客戶** 實體來擴充所有整合客戶個人資料，或選取一個客戶細分實體來增加該客戶細分中包含的客戶個人資料。

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="選擇客戶資料集時的螢幕擷取畫面。":::

1. 選擇是否要將欄位對應至主要和/或次要地址。 您可以為這兩個地址指定欄位對應，並分別為兩個地址擴充個人資料 &mdash;例如，家庭地址和商務地址。 選取 **下一步**。

1. 定義整合個人資料欄位，以用在 Azure 地圖服務中尋找符合的人口統計資料。 選擇的主要或次要地址必須要有 **街道 1** 和 **郵遞區號** 欄位。 為了獲得更高的精準度，您可以新增更多欄位。

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Azure 地圖服務擴充設定頁面。":::

1. 請選取 **下一步**，完成欄位對應。

1. 評估是否要修改 **進階設定**。 提供這些功能是為了提供最大的彈性，以處理進階使用案例，但是預設值在大多數案例中是足夠的：
   - **地址類型**：預設行為是擴充會回傳最相符地址，即使是不完整的。 若要只取得完整的地址 &mdash;例如，包含房屋號碼的地址 &mdash;請清除 **點地址** 外的所有的核取方塊。 
   - **語言**：根據預設，會確定地址位於的地區，以該地區語言來傳回地址。 若要套用標準地址語言，請從下拉式功能表中選取語言。 例如，選取 **英語** 時，會傳回 **Copenhagen, Denmark** 而非 **København, Danmark**。

1. 提供擴充的名稱。

1. 檢閱您的選項，然後選取 **儲存擴充**。

## <a name="configure-the-connection-for-azure-maps"></a>設定 Azure 地圖服務的連接

您必須是 Customer Insights 中的系統管理員，才能設定連接。 在設定擴充時，請選取 **新增連接**，或移至 **管理** > **連接** ，並在 Azure 地圖服務圖格上選取 **設定**。

1. 在 **顯示名稱** 方塊中，輸入連接的名稱。

1. 提供有效的 Azure 地圖服務 API 金鑰。

1. 檢閱 **資料隱私權和合規性** 並選取 **我同意** 的核取方塊，表示同意

1. 選取 **驗證** 來驗證設定。

1. 完成驗證之後，請選取 **儲存**。

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure 地圖服務連接設定頁面。":::

## <a name="enrichment-results"></a>擴充結果

若要開始擴充程序，請從命令列中選取 **執行**。 您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。 處理時間將視客戶資料的大小與 API 回覆時間而定。

完成擴充程序後，您可以在 **我的擴充** 中檢閱最新擴充的客戶個人資料。 此外，您還會找到上次更新時間以及已擴充的設定檔數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸到 Azure 地圖服務時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在的敏感性資料 (例如個人資料)。 Microsoft 將會依您的指示傳送這類資料，但是您必須負責確保 Azure 地圖服務符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請移至 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此富集作用，以便不再繼續使用此功能。

[!INCLUDE [footer-include](includes/footer-banner.md)]
