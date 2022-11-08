---
title: 匯出客戶細分到 Sendinblue (預覽版)
description: 了解如何設定連接並匯出到 Sendinblue。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724884"
---
# <a name="export-segments-to-sendinblue-preview"></a>匯出客戶細分到 Sendinblue (預覽版)

匯出整合個人資料的客戶細分，以使用 Sendinblue 建立行銷活動、提供電子郵件行銷，並使用特定客戶群組。

## <a name="prerequisites"></a>先決條件

- [Sendinblue 帳戶](https://www.sendinblue.com/)和相應的系統管理員認證。
- [SendinBlue API 金鑰](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)
- Sendinblue 中現有的清單和相應的識別碼。
- [已設定的客戶細分](segments.md)。
- 匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="known-limitations"></a>已知限制

- 不支援與自備儲存體 (BYOS) 搭配使用的私人連結。
- 最多可以匯出 1 百萬個客戶設定檔到 Sendinblue，最長需要 90 分鐘才能完成。 您可以匯出到 Sendinblue 的客戶設定檔數目取決於您和 Sendinblue 簽訂的契約。
- 僅客戶細分。

## <a name="set-up-connection-to-sendinblue"></a>設定到 Sendinblue 連接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Sendinblue**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 請輸入 **SendinBlue API 金鑰**。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **連接** 以初始化連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出連接** 欄位中，從 Sendinblue 區段選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 輸入您的 **Sendinblue 清單識別碼**。

1. 請在 **資料相符** 分段的 **電子郵件** 欄位中選取代表客戶電子郵件地址的欄位。

1. 或者，可以匯出 **名字**、**姓氏** 和 **電話** 以建立更個人化的電子郵件。 選取 **新增屬性** 對應這些欄位。

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
