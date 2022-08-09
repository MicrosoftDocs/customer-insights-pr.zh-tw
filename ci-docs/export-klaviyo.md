---
title: 將客戶細分匯出至 Klaviyo (預覽版)
description: 了解如何設定連接並匯出到 Klaviyo。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e45ca5827afa29d97a746bd1a474c2346cc32d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196752"
---
# <a name="export-segments-to-klaviyo-preview"></a>將客戶細分匯出至 Klaviyo (預覽版)

將整合客戶個人資料的客戶細分匯出到 Klaviyo ，並將其用在行銷活動上。

## <a name="prerequisites"></a>先決條件

- [Klaviyo 帳戶](https://www.klaviyo.com/)和相應的系統管理員認證。
- [Klaviyo API 金鑰](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys)。
- [Klaviyo 清單識別碼](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID)。
- 在 Customer Insights 中的[已設定的客戶細分](segments.md)。
- 匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 最多可以匯出 1 百萬個客戶設定檔到 Klaviyo，最長需要 20 分鐘才能完成。 您可以匯出到 Klaviyo 的客戶設定檔數目取決於您和 Klaviyo 簽訂的契約。
- 僅客戶細分。

## <a name="set-up-connection-to-klaviyo"></a>設定連線至 Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Klaviyo**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供您的 Klaviyo API 金鑰，以繼續進行登入。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **連接** 以初始化連接。

1. 選取 **驗證 Klaviyo**，並提供您的 Klaviyo 管理認證。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出連接** 欄位中，從 Klaviyo 區段選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 輸入您的 **Klaviyo 清單識別碼**。

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
