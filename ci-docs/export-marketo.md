---
title: 將客戶細分匯出至 Marketo (預覽版)
description: 了解如何設定連接並匯出至 Marketo。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195234"
---
# <a name="export-segments-to-marketo-preview"></a>將客戶細分匯出至 Marketo (預覽版)

匯出統一的客戶設定檔區段以便產生行銷活動，提供電子郵件行銷及使用含 Marketo 的特定族群客戶。

## <a name="prerequisites"></a>先決條件

- [Marketo 帳戶](https://login.marketo.com/) 及對應的系統管理員認證。
- [Marketo 用戶端識別碼、用戶端秘密和 REST 端點主機名稱](https://developers.marketo.com/rest-api/authentication/)。
- [Marketo 中的現有清單](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)和對應的識別碼。
- [已設定的客戶細分](segments.md)。
- 匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 最多可以匯出一百萬個客戶設定檔到 Marketo，最長需要 3 小時才能完成。 您可以匯出到 Marketo 的客戶設定檔數目取決於您和 Marketo 簽訂的契約。
- 僅客戶細分。

## <a name="set-up-connection-to-marketo"></a>設定對 Marketo 的連接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Marketo**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 輸入您的 **Marketo 用戶端識別碼、用戶端秘密和 REST 端點主機名稱**。 REST 端點主機名稱僅是主機名稱，沒有 https://。 範例：xyz-abc-123.mktorest.com。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **連接** 以初始化連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 Marketo 區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 輸入您的 **Marketo 清單識別碼**。 清單 ID 是純數字值。 例如，如果您的 Marketo 清單識別碼是 ST12345A7，請移除數字前後的字元，然後輸入 *12345*。

1. 在 **資料對應** 區段中，至少選取一個代表客戶電子郵件地址或客戶 Marketo 識別碼的欄位。

1. 或者，您可以匯出 **名字**、**姓氏**、**市/鎮**、**縣/市** 和 **國家/地區**，以建立更個人化的電子郵件。 選取 **新增屬性** 對應這些欄位。

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

在 Marketo 中，可以在 [Marketo 清單](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) 下方找到您的客戶細分。

[!INCLUDE [footer-include](includes/footer-banner.md)]
