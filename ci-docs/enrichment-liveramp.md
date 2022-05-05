---
title: LiveRamp 身分識別資料擴充
description: 使用 LiveRamp 資料擴充客戶個人資料。
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645758"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>使用 LiveRamp 中的身分識別資料擴充客戶個人資料 (預覽版) 

LiveRamp 提供確定性的離線身分識別解析和客戶資料的整合。 您可以將客戶資料中的個人識別碼對應至 AbiliTec 標識圖表，並接收 AbiliTec 識別碼。 您可以使用這些識別碼來取得更好的整合客戶資料。 

## <a name="prerequisites"></a>先決條件 

若要設定擴充，必須符合以下先決條件： 

- 您必須具備有效的 LiveRamp 訂閱。 若要取得訂閱，請與您的 LiveRamp 帳戶團隊聯繫，或到 [dynamics@liveramp.com](mailto:dynamics@liveramp.com) 取得詳細資訊。   

- 使用中的 AbiliTec 訂閱以用戶端識別碼和祕密來存取 API。 如需詳細資訊，請參閱 [AbiliTec API 開發人員中心](https://developers.liveramp.com/abilitec-api/)。 

## <a name="supported-countriesregions"></a>支援的國家/地區 

目前我們僅在美國支援 LiveRamp 資料擴充的客戶個人資料。 

## <a name="configure-the-enrichment"></a>擴充設定 

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。 

1. 在 **身分識別** 圖格中，選取 **擴充我的資料**。 

   :::image type="content" source="media/liveramp-tile.png" alt-text="擴充概述頁面中的身分識別圖格。":::

1. 從下拉式清單選取一個[連結](connections.md)。 如果沒有可用的連接，請與系統管理員聯繫。 如果您是系統管理員，則可以選取 **新增連接** 來建立連接。 從下拉式清單中選擇解決 **LiveRamp**。 

1. 選取 **下一步**，接著選擇要使用 LiveRamp 的身分識別資料進行擴充的 **客戶資料集**。 您可以選取 *客戶* 實體來擴充所有客戶個人資料，或選取 *客戶細分* 實體擴充位於該客戶細分的客戶個人資料。 

1. 選取 **下一步**，接著定義在 LiveRamp 比對身分識別資料時，資料整合個人資料中應使用的欄位類型。 至少一個欄位必須是 **名稱和位址**、**電話** 或 **電子郵件**。 

   > [!TIP]
   > 對應的關鍵識別碼和欄位越多，就有機會出現越高的比對率 

1. 確定用來與 LiveRamp 的 AbiliTec 識別碼圖表比對的整合 *客戶* 實體，並對應其中的欄位。 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp 擴充的資料對應選項。":::

1. 請選取 **下一步**，完成欄位對應。 

1. 提供擴充與 **輸出實體** 的 **名稱**。 

1. 檢閱選擇之後，請選取 **儲存擴充**。 

## <a name="configure-the-connection-for-liveramp"></a>設定 LiveRamp 的連接 

您必須是系統管理員才能[設定連接](connections.md)。 設定擴時，請選取 **新增連接**，或移至 **系統管理員** > **連接** 並在 **LiveRamp** 圖格上選取 **設定**。 

:::image type="content" source="media/liveramp-connection.png" alt-text="用來設定連接到 LiveRamp AbiliTec 服務的設定窗格。":::

1. 在 **顯示名稱**，請輸入連接的名稱。 

1. 提供有效的 LiveRamp 用戶端識別碼與秘密。 

1. 選取 **我同意** 核取方塊，以檢閱 **資料隱私權和合規性** 並表示同意。 

1. 選取 **驗證** 來驗證設定。 

1. 選取 **儲存**，完成連接。 

## <a name="enrichment-results"></a>擴充結果 

若要開始擴充程序，請從命令列中 選取 執行。 您也可以讓系統在 [排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。 處理時間視客戶資料的大小而定。 

擴充程序完成後，您可以在 **我的擴充** 中檢閱新擴充的客戶個人資料。 此外，您還會找到上次更新時間以及已擴充的設定檔數目。 

您可以選取 **檢視擴充** 資料來存取每個已擴充個人資料的詳細檢視表。 

## <a name="next-steps"></a>後續步驟

建立在您擴充的客戶資料之上。 您可以使用 AbiliTec 識別碼，將客戶個人資料整合至個人檢視表中。 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性 

當您啟用 Dynamics 365 Customer Insights 對 Liveramp 的資料傳輸時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，其中包括潛在敏感性資料，如個人資料。 Microsoft 將會在您指示時傳送這類資料，但是您必須負責確保 LiveRamp 符合您可能會承擔的任何隱私權或資訊安全義務。 如需更多資訊，請檢閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。 您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此富集作用，以便不再繼續使用此功能。 


[!INCLUDE [footer-include](includes/footer-banner.md)]
