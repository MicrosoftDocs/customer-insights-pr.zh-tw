---
title: 透過 Leadspace 來擴充公司設定檔 (預覽版)
description: 有關協力廠商 Leadspace 富集作用的一般資訊。
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237940"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>透過 Leadspace 來擴充公司設定檔 (預覽版)

Leadspace 是一間提供 B 到 B 客戶資料平台的資料科學公司。 它讓環境按帳戶隨著統一的客戶設定檔擴充其資料。 使用如公司規模、位置或行業的屬性擴充 *客戶設定檔*。 使用標題、角色或電子郵件驗證等屬性擴充 *連絡人設定檔*。

## <a name="prerequisites"></a>先決條件

- 一個有效的 Leadspace 授權
- 您有按帳戶基礎的[整合客戶個人資料](customer-profiles.md)。
- Leadspace 的[連接](connections.md) 是由系統管理員[設定](#configure-the-connection-for-leadspace)的。 如需產品的詳細資料，請直接聯繫 [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/)。

## <a name="configure-the-connection-for-leadspace"></a>設定 Leadspace 的連接

您必須是 Customer Insights 的 [系統管理員](permissions.md#admin)，且具有永久金鑰 (稱為 **Leadspace 權杖**)。

1. 在設定擴充時，請選取 **新增連接**，或移至 **管理** > **連接** 並在 Leadspace 磚上選取 **設定**。

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 的連接設定頁面。":::

1. 輸入連接的名稱以及有效的 Leadspace 權杖。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **驗證** 來驗證設定，然後選取 **儲存**。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 Leadspace 磚上的 **公司資料** 中，選取 **擴充我的資料**。

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 圖格的螢幕擷取畫面。":::

1. 檢閱概覽，然後選擇 **下一步**。

1. 選取連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 選取 **下一步**。

1. 選取 **客戶資料集**，然後選擇將以 Leadspace 的公司資料進行擴充的個人資料或客戶細分。 *Customer* 實體可擴充所有客戶個人資料，然而客戶細分實體僅擴充位於該客戶細分的客戶個人資料。

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. 定義要用於比對的整合個人資料欄位類型：主要和/或次要地址。 您可以分別指定欄位對應到兩個地址並且指定擴充個人資料給兩個地址。 例如，如果是住家地址或公司地址。 選取 **下一步**。

1. 將您的欄位對應至 Leadspace 的公司資料。 **公司名稱** 欄位是必要欄位。 為了獲得更高的準確性，可以新增多達兩個欄位，**公司網站** 和 **公司位置**。

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 欄位對應窗格。":::

1. 請選取 **下一步**，完成欄位對應。

1. 如果您有想要擴充的 *連絡人設定檔*，請選取勾選方塊。 Customer Insights 將自動對應必要欄位。

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Leadspace 連絡人記錄擴充。":::

1. 選取 **下一步**。

1. 請提供擴充的 **名稱** 與 **輸出實體名稱**。

1. 檢閱選擇之後，請選取 **儲存擴充**。

1. 選取 **執行** 以開始擴充程序，或者直接關閉返回至 **擴充** 頁面。

## <a name="view-enrichment-results"></a>查看擴充結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

如需詳細資訊，請參閱 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)。

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
