---
title: 將客戶細分匯出至 Microsoft Advertising (預覽版)
description: 了解如何設定連接並匯出至 Microsoft Advertising。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196522"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>將客戶細分匯出至 Microsoft Advertising (預覽版)

將 Customer Insights 客戶細分匯出至 Microsoft Advertising，以建立客戶相符的對象。 將在您的廣告行銷活動使用這些對象。

## <a name="prerequisites"></a>先決條件

- [Microsoft Advertising 帳戶](https://ads.microsoft.com/)及對應的系統管理員認證。
- Microsoft Advertising 客戶識別碼和帳戶識別碼。 當您登入 Microsoft Advertising 時，可以在 URL 的參數中找到客戶識別碼 (`cid`) 和帳戶識別碼 (`aid`)。
- 已接受 Customer Match 的使用條款。
- 在 Customer Insights 中的[已設定的客戶細分](segments.md)。
- 匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 每次最多匯出 500,000 個客戶設定檔到 Microsoft Advertising，最長需要花費 10 分鐘才能完成。
- 僅客戶細分。

## <a name="set-up-connection-to-microsoft-advertising"></a>設定與 Microsoft Advertising 的連線

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Microsoft Advertising**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 預設為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 輸入 **Microsoft Advertising 客戶識別碼**。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **連接** 以初始化連接。

1. 選取 **驗證 Microsoft Advertising**，並提供您的 Microsoft Advertising 管理認證。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 Microsoft Advertising 區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 選取要匯出的客戶細分。 會以選取要匯出的客戶細分名稱自動建立 Microsoft Advertising 中客戶比對的對象。 每一個客戶細分都會造成不同的客戶比對對象。

1. 輸入您的 **Microsoft Advertising 客戶識別碼和帳戶識別碼**。

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取含客戶電子郵件地址的欄位。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
