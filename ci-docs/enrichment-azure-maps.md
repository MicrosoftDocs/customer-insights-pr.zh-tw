---
title: 使用 Azure Maps 中的位置資料擴充客戶設定檔 (預覽版)
description: 關於 Azure 地圖服務第一方企業擴充的一般資訊。
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238032"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>使用 Azure Maps 中的位置資料擴充客戶設定檔 (預覽版)

Azure 地圖服務提供以位置為核心的資料和服務，利用內建位置智慧的地理空間資料來提供體驗。 Azure 地圖服務資料擴充服務改善客戶位置資訊的精準度。 它可將地址正規化和緯度及經度擷取等功能帶到 Dynamics 365 Customer Insights 中。

## <a name="prerequisites"></a>先決條件

- 一個有效的 Azure 地圖服務訂閱。 若要取得訂閱，請[註冊或取得免費試用](https://azure.microsoft.com/services/azure-maps/)。

- Azure 地圖服務的[連接](connections.md)是由系統管理員[設定](#configure-the-connection-for-azure-maps)的。

## <a name="configure-the-connection-for-azure-maps"></a>設定 Azure 地圖服務的連接

您必須是 Customer Insights 中的[系統管理員](permissions.md#admin)，且擁有有效的 Azure 地圖服務 API 金鑰。

1. 在設定擴充時，請選取 **新增連接**，或移至 **管理** > **連接** ，並在 Azure 地圖服務圖格上選取 **設定**。

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure 地圖服務連接設定頁面。":::

1. 輸入連接的名稱以及有效的 Azure 地圖服務 API 金鑰。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **驗證** 來驗證設定，然後選取 **儲存**。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 Microsoft Azure 地圖服務磚上的 **位置**，選取 **擴充我的資料**。

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure 地圖服務圖格。":::

1. 檢閱概覽，然後選擇 **下一步**。

1. 選取連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 選取 **下一步**。

1. 選取 **客戶資料集**，然後選擇要使用 Microsoft 的資料進行擴充的個人資料或客戶細分。 *Customer* 實體可擴充所有客戶個人資料，然而客戶細分實體僅擴充位於該客戶細分的客戶個人資料。

1. 定義要用於比對的整合個人資料欄位類型：主要和/或次要地址。 您可以分別指定欄位對應到兩個地址並且指定擴充個人資料給兩個地址。 例如，如果是住家地址或公司地址。 選取 **下一步**。

1. 將您的欄位對應至 Azure 地圖服務的位置資料。 **街道 1** 和 **郵遞區號** 欄位是選取的主要和/或次要位址的必要欄位。 為了提高比對精準度，請新增更多的欄位。

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure 地圖服務的屬性對應。":::

1. 請選取 **下一步**，完成欄位對應。

1. 檢閱 **進階設定**，這提供最大的彈性來處理進階使用案例。 但是，下列預設值通常不需要變更。

   - **地址類型**：即使未完成，也會回傳最佳地址比對結果。 若要只取得完整的地址 &mdash;例如，包含房屋號碼的地址 &mdash;請清除 **點地址** 外的所有的核取方塊。
   - **語言**：根據地址地區，以該語言回傳地址。 若要套用標準地址語言，請從下拉式功能表中選取語言。 例如，選取 **英語** 時，會回傳 **Copenhagen, Denmark** 而不是 **København, Danmark**。
   - **結果的最大數量**：每個地址的結果數量。

1. 選取 **下一步**。

1. 請提供擴充的 **名稱** 與 **輸出實體名稱**。

1. 檢閱選擇之後，請選取 **儲存擴充**。

1. 選取 **執行** 以開始擴充程序，或者直接關閉返回至 **擴充** 頁面。

## <a name="view-enrichment-results"></a>查看擴充結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**已擴充欄位的客戶數** 可讓您向下鑽研到每個擴充的欄位。

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
