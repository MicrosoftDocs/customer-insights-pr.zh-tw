---
title: 將客戶細分匯出至 Criteo (預覽版)
description: 了解如何設定 Criteo 的連線和匯出。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760016"
---
# <a name="export-segments-to-criteo-preview"></a>將客戶細分匯出至 Criteo (預覽版)

匯出統一客戶設定檔的客戶細分以產生廣告活動、提供電子郵件行銷，並且搭配 Criteo 使用特定的客戶群組。

## <a name="prerequisites"></a>先決條件

- [Criteo Dynamics Retargeting 帳戶](https://www.criteo.com/login/)及對應的系統管理員認證。
- [已設定的客戶細分](segments.md)。
- 匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 最多可以匯出 1 百萬個客戶設定檔到 Criteo，最長需要 30 分鐘才能完成。 您可以匯出到 Criteo 的客戶設定檔數目取決於您和 Criteo 簽訂的契約。
- 僅客戶細分。

## <a name="set-up-connection-to-criteo"></a>設定至 Criteo 的連線

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Criteo**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **連接** 以初始化連接。

1. 選取 **使用 Criteo 進行驗證**，並提供 Criteo 的系統管理員使用者名稱和認證。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出用的連線** 欄位，從 Criteo 區段中選擇連線。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
