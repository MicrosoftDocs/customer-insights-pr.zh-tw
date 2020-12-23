---
title: 協力廠商 Enrichment Leadspace 的公司設定檔
description: 有關協力廠商 Leadspace 富集作用的一般資訊。
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668713"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>使用 Leadspace 擴充公司設定檔 (預覽)

Leadspace 是一家提供 B2B 客戶資料平台的資料科學公司。 為客戶帶來統一客戶設定檔，讓各家公司可以擴充其資料。 富集群包括其他屬性如公司大小、地點、產業及其他。

## <a name="prerequisites"></a>先決條件

若要設定 Leadspace，必須符合以下先決條件：

- 您具備有效的 Leadspace 授權和「永久金鑰」 (以下簡稱 **Leadspace 權杖**)。 直接連絡 [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/)，以取得其產品的詳細資料。
- 您擁有 [系統管理員](permissions.md#administrator) 權限。
- 您有公司的[統一客戶設定檔](customer-profiles.md)。

## <a name="configuration"></a>組態

1. 請在對象見解中前往 **資料** > **富集**。

1. 選取 Leadspace 圖標上的 **擴充我的資料**。

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 圖格的螢幕擷取畫面。":::

1. 選取 **開始使用** 然後輸入有效的 **Leadspace 權杖** (永久金鑰)。 選取 **我同意** 核取方塊，以檢閱 **資料隱私權和合規性** 並表示同意。 選取 **連接到 Leadspace** 確認這兩項輸入資料。

1. 選取 **對應資料** 然後定義應使用統一設定檔中的欄位，以便尋找符合 Leadspace 的公司資料。 **公司名稱** 欄位是必要欄位。 為了獲得更高的準確性，可以新增多達兩個欄位，**公司網站** 和 **公司位置**。

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 欄位對應窗格。":::
   
1. 選取 **套用** 完成欄位對應。

1. 選取 **執行** 以擴充公司設定檔。 富集花費的時間視統一的客戶設定檔數量而定。

## <a name="enrichment-results"></a>擴充結果

重新整理擴充內容之後，您可以在[我的擴充內容](enrichment-hub.md)中檢閱新近擴充的公司資料。 您可以找到上次更新的時間以及已擴充設定檔的數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

如需詳細資訊，請參閱 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)。

## <a name="next-steps"></a>後續步驟

建立在您擴充的客戶資料之上。 建立[客戶細分](segments.md)、[量值](measures.md)，甚至[匯出資料](export-destinations.md)，以便傳送個人化體驗給您的客戶。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Leadspace 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Leadspace 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此富集作用，以便不再繼續使用此功能。