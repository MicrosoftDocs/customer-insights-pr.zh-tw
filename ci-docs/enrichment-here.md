---
title: 透過 HERE Technologies 來擴充設定檔 (預覽版)
description: 有關 HERE Technologies 協力廠商富集作用的一般資訊。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 26de9fce863c9832b70adf3ce39cb2ae0ce43d0e
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196246"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>透過 HERE Technologies 來擴充設定檔 (預覽版)

HERE Technologies 是一間位置平台公司，提供以位置為中心的資料和服務。 HERE Technologies 的資料擴充服務改善客戶位置資訊的精準度。 此服務提供地址正規化、緯度和經度擷取等等。

## <a name="prerequisites"></a>先決條件

- 一個有效的 HERE Technologies 訂閱。 若要取得訂閱，請[在此進行註冊](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) 或直接 [與 HERE Technologies聯絡](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)。 [深入瞭解 HERE Technologies 的 Location Enrichment。](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE 的[連接](connections.md) 是由系統管理員[設定](#configure-the-connection-for-here-technologies)。

## <a name="configure-the-connection-for-here-technologies"></a>設定 HERE Technologies 的連接

您必須是 Customer Insights 中的[系統管理員](permissions.md#admin)，且擁有有效的 HERE Technologies API 金鑰。

1. 在設定擴充時，請選取 **新增連接** 或前往 **管理** > **連接** 並在 HERE Technologies 磚上選取 **設定**。

1. 輸入連接的名稱以及有效的 HERE Technologies API 金鑰。

1. 檢閱並選取 **我同意**，提供您的[資料隱私權和合規性](#data-privacy-and-compliance)許可。

1. 選取 **驗證** 來驗證設定，然後選取 **儲存**。

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE technologies 的連接設定頁面。":::

### <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 HERE Technologies 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 HERE Technologies 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此擴充，不再繼續使用此功能。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 HERE Technologies 上的 **位置**，選取 **擴充我的資料**。

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies 圖標。":::

1. 檢閱概覽，然後選擇 **下一步**。

1. 選取連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 選取 **下一步**。

1. 選取 **客戶資料集**，然後選擇將以 HERE Technologies 的資料進行擴充的個人資料或客戶細分。 *Customer* 實體可擴充所有客戶個人資料，然而客戶細分實體僅擴充位於該客戶細分的客戶個人資料。

1. 定義要用於比對的整合個人資料欄位類型：主要和/或次要地址。 您可以分別指定欄位對應到兩個地址並且指定擴充個人資料給兩個地址。 例如，如果是住家地址或公司地址。 選取 **下一步**。

1. 將您的欄位對應至 HERE Technologies 的資料。 **街道 1** 和 **郵遞區號** 欄位是選取的主要和/或次要位址的必要欄位。 為了提高比對正確性，請新增更多的欄位。

1. 請選取 **下一步**，完成欄位對應。

1. 請提供擴充的 **名稱** 與 **輸出實體名稱**。

1. 檢閱選擇之後，請選取 **儲存擴充**。

1. 選取 **執行** 以開始擴充程序，或者直接關閉返回至 **擴充** 頁面。

## <a name="view-enrichment-results"></a>查看擴充結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**已擴充欄位的客戶數** 可讓您向下鑽研到每個擴充的欄位。

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
