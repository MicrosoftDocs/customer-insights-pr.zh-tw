---
title: 利用 Experian 的人口統計資訊擴充客戶個人資料 (預覽版)
description: 關於 Experian協力廠商擴充的一般資訊。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 876853ab42e8c08ad1abacb8d8a205c0aadabcf7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195926"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>利用 Experian 的人口統計資訊擴充客戶個人資料 (預覽版)

Experian 是消費者和企業信用報告和行銷服務的全球領導者。 有了 Experian 資料擴充服務服務，您可以使用人口統計資料 (例如，家庭大小、收入和其他資訊) 來擴充您的客戶個人資料，以建立深入瞭解您的客戶。

## <a name="supported-countriesregions"></a>支援的國家/地區

目前我們僅在美國支援擴充客戶個人資料。

## <a name="prerequisites"></a>先決條件

- 一個有效的 Experian 訂閱 若要取得訂閱，請直接[聯繫 Experian](https://www.experian.com/marketing-services/contact)。 [深入了解 Experian 資料擴充](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。

- Experian 的[連接](connections.md) 是由系統管理員[設定](#configure-the-connection-for-experian)的。

- 由 Experian 建立並啟用 SSH 的安全性傳輸 (ST) 帳戶，其 Experian 使用者識別碼、合作對象識別碼和模型編號 。

## <a name="configure-the-connection-for-experian"></a>設定 Experian 的連接

您必須是 Customer Insights 中的[系統管理員](permissions.md#admin)，且具有有效的 Experian 使用者識別碼、合作對象識別碼和模型編號。

1. 在設定擴充時，請選取 **新增連接**，或前往 **管理** > **連接** ，並在 Experian 磚上選取 **設定**。

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 連接設定窗格。":::

1. 輸入連接的名稱以及安全性傳輸帳戶的有效 Experian 使用者識別碼、合作對象識別碼和模型編號。

1. 檢閱並選取 **我同意**，提供您的[資料隱私權和合規性](#data-privacy-and-compliance)許可。

1. 選取 **驗證** 來驗證設定，然後選取 **儲存**。

### <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用  Dynamics 365 Customer Insights 將資料傳輸到 Experian 時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在的敏感性資料 (例如個人資料)。 Microsoft 將會依您的指示傳送這類資料，但是您必須負責確保 Experian 符合您可能會承擔的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。 您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此擴充，不再繼續使用此功能。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 Experian 磚上的 **人口統計**，選取 **擴充我的資料**。

   :::image type="content" source="media/experian-tile.png" alt-text=" 擴充摘要頁面中的 Experian 磚。":::

1. 檢閱概覽，然後選擇 **下一步**。

1. 選取連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 選取 **下一步**。

1. 選取 **客戶資料集**，然後選擇將以 Experian 的人口統計資料進行擴充的個人資料或客戶細分。 *Customer* 實體可擴充所有客戶個人資料，然而客戶細分實體僅擴充位於該客戶細分的客戶個人資料。

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. 定義在 Experian 比對人口統計資料時，整合個人資料中要使用的欄位類型。 至少要有 **名稱和位址**、**電話** 或 **電子郵件** 中的一個欄位。 為了提高比對正確度，請新增其他欄位。 選取 **下一步**。

1. 將您的欄位對應至 Experian 的人口統計資料。

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
