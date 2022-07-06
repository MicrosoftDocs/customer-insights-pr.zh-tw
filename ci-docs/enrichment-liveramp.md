---
title: 使用 LiveRamp 中的身分識別資料擴充客戶個人資料 (預覽版)
description: 使用 LiveRamp 資料擴充客戶個人資料。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 334440493c50448005ec90d0cfac11358d677b73
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080851"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>使用 LiveRamp 中的身分識別資料擴充客戶個人資料 (預覽版)

LiveRamp 提供確定性的離線身分識別解析和客戶資料的整合。 您可以將客戶資料中的個人識別碼對應至 AbiliTec 標識圖表，並接收 AbiliTec 識別碼。 您可以使用這些識別碼來取得更好的整合客戶資料。

## <a name="supported-countriesregions"></a>支援的國家/地區

目前我們僅在美國支援 LiveRamp 資料擴充的客戶個人資料。

## <a name="prerequisites"></a>先決條件

- 一個有效的 LiveRamp 訂閱。 若要取得訂閱，請與您的 LiveRamp 帳戶團隊聯繫，或到 [dynamics@liveramp.com](mailto:dynamics@liveramp.com) 取得詳細資訊。

- 使用中的 AbiliTec 訂閱以用戶端識別碼和祕密來存取 API。 如需詳細資訊，請參閱 [AbiliTec API 開發人員中心](https://developers.liveramp.com/abilitec-api/)。

- LiveRamp 的[連接](connections.md) 是由系統管理員[設定](#configure-the-connection-for-liveramp)的。

## <a name="configure-the-connection-for-liveramp"></a>設定 LiveRamp 的連接

您必須是 Customer Insights 中的[系統管理員](permissions.md#admin)，且具有有效的 LiveRamp 用戶端識別碼和用戶端密碼。

1. 設定擴時，請選取 **新增連接**，或移至 **系統管理員** > **連接** 並在 LiveRamp 磚上選取 **設定**。

   :::image type="content" source="media/liveramp-connection.png" alt-text="用來設定連接到 LiveRamp AbiliTec 服務的設定窗格。":::

1. 輸入連接的名稱，以及有效的 LiveRamp 用戶端識別碼和用戶端密碼。

1. 檢閱並選取 **我同意**，提供您的[資料隱私權和合規性](#data-privacy-and-compliance)許可。

1. 選取 **驗證** 來驗證設定，然後選取 **儲存**。

### <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 對 Liveramp 的資料傳輸時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，其中包括潛在敏感性資料，如個人資料。 Microsoft 將會在您指示時傳送這類資料，但是您必須負責確保 LiveRamp 符合您可能會承擔的任何隱私權或資訊安全義務。 如需更多資訊，請檢閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。 您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此富集作用，以便不再繼續使用此功能。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 LiveRamp 磚上的 **身分識別** 中，選取 **擴充我的資料**。

   :::image type="content" source="media/liveramp-tile.png" alt-text="擴充概述頁面中的身分識別圖格。":::

1. 檢閱概覽，然後選擇 **下一步**。

1. 選取連接。 如果連接無法使用，請與系統管理員聯繫。

1. 選取 **下一步**。

1. 選取 **客戶資料集**，然後選擇將以 LiveRamp 的身分識別資料進行擴充的個人資料或客戶細分。 *Customer* 實體可擴充所有客戶個人資料，然而客戶細分實體僅擴充位於該客戶細分的客戶個人資料。

1. 定義在 LiveRamp 比對身分識別資料時，整合個人資料中要使用的欄位類型。 至少一個欄位必須是 **名稱和地址**、**電子郵件** 或 **電話**。 為了提高比對正確度，請新增其他欄位。 選取 **下一步**。

1. 將您的欄位對應至 LiveRamp 的識別資料。

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp 擴充的資料對應選項。":::

1. 請選取 **下一步**，完成欄位對應。

1. 請提供擴充的 **名稱** 與 **輸出實體名稱**。

1. 檢閱選擇之後，請選取 **儲存擴充**。

1. 選取 **執行** 以開始擴充程序，或者直接關閉返回至 **擴充** 頁面。

## <a name="view-enrichment-results"></a>查看擴充結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**已擴充欄位的客戶數** 可讓您向下鑽研到每個擴充的欄位。

## <a name="next-steps"></a>後續步驟

建立在您擴充的客戶資料之上。 您可以使用 AbiliTec 識別碼，將客戶個人資料整合至個人檢視表中。
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
