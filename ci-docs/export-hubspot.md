---
title: 將 Customer Insights 資料匯出至 HubSpot
description: 了解如何設定連接並匯出至 HubSpot。
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588899"
---
# <a name="export-segments-to-hubspot-preview"></a>將客戶細分匯出至 HubSpot (預覽版)

將整合客戶個人資料客戶細分匯出至 HubSpot，並在電子郵件行銷中使用這些資料。

## <a name="prerequisites-for-a-connection"></a>連接的先決條件

- [HubSpot 帳戶](https://www.hubspot.com/)以及對應的系統管理員認證。
- HubSpot 中的 [API 金鑰](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key)。
- 在 Customer Insights 中的[已設定的客戶細分](segments.md)。

## <a name="known-limitations"></a>已知限制

- 每次匯出至 HubSpot，最多 100,000 個客戶設定檔，這可能需要長達 15 分鐘才能完成。 可匯出至 HubSpot 的客戶設定檔數目取決於並受限於您與 HubSpot 簽訂的合約。
- 僅客戶細分。

## <a name="set-up-connection-to-hubspot"></a>設定與 HubSpot 的連接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，並選擇 **HubSpot** 以設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 出現提示時，輸入您的 HubSpot 認證。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **連接** 以初始化與 HubSpot 的連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 若要建立新匯出，請選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，從 HubSpot 區段選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。 對於其他可選欄位，重複相同步驟。

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
