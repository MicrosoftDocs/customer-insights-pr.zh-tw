---
title: 將客戶細分匯出至 MoEngage
description: 了解如何設定 MoEngage 的連線和匯出。
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725252"
---
# <a name="export-segments-to-moengage-preview"></a>將客戶細分匯出至 MoEngage (預覽版)

將統整客戶設定檔的客戶細分匯出至 MoEngage，並在 MoEngage 中用來進行電子郵件行銷。

## <a name="prerequisites-for-a-connection"></a>連接的先決條件

- [MoEngage 帳戶](https://www.moengage.com/) 及對應的系統管理員認證。
- MoEngage API 金鑰來自 MoEngage 中的設定 > API。
- 在 Customer Insights 中的[已設定的客戶細分](segments.md)。

## <a name="known-limitations"></a>已知限制

- 不支援與自備儲存體 (BYOS) 搭配使用的私人連結。
- 每次最多匯出 100,000 個客戶設定檔到 MoEngage，最長需要花費 15 分鐘才能完成。 您可以匯出到 MoEngage 的客戶設定檔數目取決於您和 MoEngage 簽訂的契約。
- 僅客戶細分。

## <a name="set-up-connection-to-moengage"></a>設定與 MoEngage 的連接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連線**，然後選擇 **MoEngage** 來設定連線。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 輸入您的 [MoEngage 資料 API 識別碼和 API 金鑰](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY)。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **連接** 來初始化與 MoEngage 的連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 若要建立新匯出，請選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 MoEngage 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。 對於其他可選欄位，重複相同步驟。

1. 選取您要匯出的客戶細分。 我們會在 **客戶細分** > **自訂客戶細分** 底下，建立一個或多個與 MoEngage 中所選客戶細分名稱相同的客戶細分。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
