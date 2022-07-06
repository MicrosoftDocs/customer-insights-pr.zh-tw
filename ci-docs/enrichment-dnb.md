---
title: 透過 Dun & Bradstreet 擴充公司設定檔 (預覽版)
description: Dun & Bradstreet 協力廠商的一般資訊。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 51f2e4e46aa25d10502d0feb5ea42eb7d2d637b9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080892"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>透過 Dun & Bradstreet 擴充公司設定檔 (預覽版)

Dun & Bradstreet 為公司供應商業資料、分析和見解。 為客戶帶來統一客戶設定檔，讓各家公司可以擴充其資料。 擴充公司屬性包括 DUNS 編碼、公司規模、位置、產業等等。

## <a name="prerequisites"></a>先決條件

- 一個有效的 [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) 授權。
- 公司的[整合客戶個人資料](customer-profiles.md)。
- 已設定 Dun & Bradstreet [專案](#set-up-your-dun--bradstreet-project)。
- Dun & Bradstreet 的[連接](connections.md) 是由系統管理員[設定](#configure-a-connection-for-dun--bradstreet)的。

## <a name="set-up-your-dun--bradstreet-project"></a>設定 Dun & Bradstreet 專案

作為 Dun & Bradstreet 的授權使用者，您可以在 [ Dun & Bradstreet Connect 連接](https://connect.dnb.com?lead_source=microsoft_audienceinsights)中設定專案。

1. 登入 [Dun & Bradstreet 連接](https://connect.dnb.com?lead_source=microsoft_audienceinsights)。 若要取出認證，請[還原您的密碼](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights)。

1. 下載 [csv 範本檔案](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv)，用來將 Customer Insights 欄位對應至 Dun & Bradstreet 欄位。

1. 使用 Dun & Bradstreet 專案建立體驗的 **上傳資料** 步驟，上傳檔案。

1. 在新建立的 Dun & Bradstreet 專案中，選取相關 **來源** 下方的水平點組，以查看可用的選項。

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="螢幕擷取畫面：圖上為 Dun & Bradstreet 專案中的點組。":::

1. 選擇 **取得 S3 詳細資料**。 將此資訊儲存在安全的地方。 需要用它，才能在 Customer Insights 中[設定擴充的連接](#configure-a-connection-for-dun--bradstreet)。

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="在 Dun & Bradstreet 專案中選取 s3 資訊的螢幕擷取畫面。":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>設定 Dun & Bradstreet 的連接

您必須擁有 Customer Insights 的[系統管理員](permissions.md#admin)的權限，以及 Dun & Bradstreet Connect 的認證。

1. 設定擴時，請選取 **新增連接** ，或前往 **系統管理員** > **連接**，在 Dun & Bradstreet 磚上選取 **設定**。

1. 輸入連接的名稱

1. 提供有效的 Dun & Bradstreet 認證和 Dun & Bradstreet 專案詳細資料 *區域、放置資料夾路徑及放置資料夾名稱*。 您可以從 Dun & Bradstreet 專案[取得此資訊](#set-up-your-dun--bradstreet-project)。

1. 檢閱並選取 **我同意**，提供您的[資料隱私權和合規性](#data-privacy-and-compliance)許可。

1. 選取 **驗證** 來驗證設定，然後選取 **儲存**。

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet 的連接設定頁面":::

### <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 對 Dun & Bradstreet 的資料傳輸時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，其中包括潛在敏感性資料，如個人資料。 Microsoft 將會在您指示時傳送這類資料，但是您必須負責確保 Dun & Bradstreet 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此擴充，不再繼續使用此功能。

## <a name="supported-countries-or-regions"></a>支援的國家或地區

目前我們支援下列國家/地區選項：加拿大 (英文) 或美國 (英文) 。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 Dun & Bradstreet 磚上的 **公司資料**，選取 **擴充我的資料**。

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet 磚的螢幕擷取畫面。":::

1. 檢閱概覽，然後選擇 **下一步**。

1. 選取連接並確認。 如果連接無法使用，請與系統管理員聯繫。

1. 選取 **下一步**。

1. 選取 **客戶資料集**，然後選擇要使用 Dun & Bradstreet 的公司資料進行擴充的個人資料或客戶細分。 *Customer* 實體可擴充所有客戶個人資料，然而客戶細分實體僅擴充位於該客戶細分的客戶個人資料。

1. 定義在 Dun & Bradstreet 比對公司資料時，整合個人資料中要使用的欄位類型。 至少要有 **名稱和位址**、**電話** 或 **電子郵件** 中的一個欄位。

1. 選取 **下一個**

1. 將您的欄位對應至 Dun & Bradstreet 的公司資料。 **DUNS 編號** 或 **公司名稱** 以及 **國家/地區** 欄位是必要的。

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet 欄位對應窗格。":::

1. 請選取 **下一步**，完成欄位對應。

1. 請提供擴充的 **名稱** 與 **輸出實體名稱**。

1. 檢閱選擇之後，請選取 **儲存擴充**。

1. 選取 **執行** 以開始擴充程序，或者直接關閉返回至 **擴充** 頁面。

## <a name="view-enrichment-results"></a>查看擴充結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
