---
title: 將客戶細分匯出至 Braze (預覽版)
description: 了解如何設定 Braze 的連線和匯出。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 84dc7f13f30e0334d431fe5b5866c7f87e82ab27
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195097"
---
# <a name="export-segments-to-braze-preview"></a>將客戶細分匯出至 Braze (預覽版)

將整合客戶個人資料客戶細分匯出至 Braze，並在行銷活動使用。

## <a name="prerequisites"></a>先決條件

- 一個 [Braze 帳戶](https://www.braze.com/)及對應的系統管理員認證。
- [BRAZE API 金鑰](https://www.braze.com/docs/api/basics/)
- 在 Customer Insights 中的[已設定的客戶細分](segments.md)。
- 在匯出客戶細分中的整合客戶個人資料，包含表示電子郵件地址和 Braze 客戶識別碼的欄位。

## <a name="known-limitations"></a>已知限制

- 匯出多達 1 百萬個客戶個人資料到 Braze 需要花費最多 40 分鐘完成。 您可以匯出到 Braze 的客戶設定檔數目取決於您和 Braze 簽訂的契約。
- 僅客戶細分。

## <a name="set-up-connection-to-braze"></a>設定至 Braze 的連線

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Braze**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供您的 BRAZE API 金鑰以繼續登入。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **連接** 以初始化連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出用的連線** 欄位，到 Braze 區段中選擇連線。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。 在 **客戶識別碼** 欄位，選取代表客戶 Braze 識別碼的欄位。 Braze 中建立的客戶細分將與 Dynamics 365 Customer Insights 的客戶細分名稱相同。 您可以選擇其他可選欄位來符合資料。

1. 選取您要匯出的實體或客戶細分。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
