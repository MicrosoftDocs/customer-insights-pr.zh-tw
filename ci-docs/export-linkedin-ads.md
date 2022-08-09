---
title: 將客戶細分匯出至 LinkedIn Ads (預覽版)
description: 了解如何設定連接並匯出至 LinkedIn Ads。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d1a9ae985043398f4bc38163be26ecf0c3c8e2ba
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196798"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>將客戶細分匯出至 LinkedIn Ads (預覽版)

將整合客戶個人資料的客戶細分匯出至LinkedIn Ads，以建立符合的對象。 使用符合對象給公司鎖定和連絡人鎖定。

## <a name="prerequisites"></a>先決條件

- [LinkedIn Campaign Manager 帳戶](https://business.linkedin.com/marketing-solutions/ads)及對應的系統管理員認證。
- [LinkedIn Campaign Manager 帳戶識別碼](https://www.linkedin.com/help/lms/answer/a424270)
- 在 Customer Insights 中的[已設定的客戶細分](segments.md)。
- 匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 最多可以匯出 100,000 個客戶設定檔到 LinkedIn Ads，最長需要 10 分鐘才能完成。
- 僅客戶細分。 客戶細分必須至少包含 300 個唯一設定檔。

## <a name="set-up-connection-to-linkedin-ads"></a>設定與 LinkedIn Ads 的連線

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **LinkedIn Ads**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供您的 LinkedIn Campaign Manager 帳戶識別碼。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **連接** 以初始化連接。

1. 選取 **驗證 LinkedIn**，並提供 LinkedIn Campaign Manager 的系統管理員認證。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 LinkedIn Ads 區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 選擇您是否要匯出資料，以執行 LinkedIn 上的[連絡人鎖定](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting)或[公司鎖定](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)。

1. 請在 **資料相符** 的分段中針對連絡人目標選取至少一個代表客戶電子郵件地址、APPLE Ad ID、Google Ad ID、Google 使用者 ID 或名字和姓氏的欄位。 如果您選擇公司目標，請至少選取一個代表公司名稱、電子郵件網域、LinkedIn 頁面 URL、Stock 代號或網站的欄位。

1. 或者，新增欄位以進一步定義您的匯出。 選取 **新增屬性** 對應這些欄位。

1. 選取您要匯出的客戶細分。 使用您選取要匯出的區段名稱，LinkedIn Campaign Manager 中的符合對象會自動建立。 每一個客戶細分都會造成不同的符合對象。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
