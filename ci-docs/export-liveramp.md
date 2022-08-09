---
title: 將客戶細分匯出至 LiveRamp (預覽版)
description: 了解如何設定連接並匯出至 LiveRamp。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196706"
---
# <a name="export-segments-to-liverampreg-preview"></a>將客戶細分匯出至 LiveRamp&reg; (預覽版)

在 LiveRamp 中啟動您的資料，便能連接超過 500 多個平台，橫跨數位、社群和電視等領域。 在 LiveRamp 中使用您的資料，將廣告行銷活動設為目標、抑制和個人化。

## <a name="prerequisites"></a>先決條件

- LiveRamp 訂閱以使用此連接器。 若要取得訂閱，請直接[與 LiveRamp 連絡](https://liveramp.com/contact/)。 [進一步了解 LiveRamp 上線](https://liveramp.com/our-platform/data-onboarding/)。

## <a name="known-limitations"></a>已知限制

- LiveRamp 匯出使用 SFTP 匯出。 目前不支援在防火牆後的 SFTP 目標。
- 如果您使用 SSH 金鑰進行驗證，請確定您將[私密金鑰](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example)建立為 PEM 或 SSH.COM 格式。 如果您使用的是 Putty，請使用匯出為 Open SSH 來轉換您的私密金鑰。 支援的私密金鑰格式如下：
  - OpenSSL PEM 和 ssh.com 格式的 RSA
  - OpenSSL PEM 和 ssh.com 格式的 DSA
  - OpenSSL PEM 格式的 ECDSA 256/384/521
  - OpenSSH 金鑰格式的 ED25519 和 RSA
- 匯出執行時間依您的系統效能而定。 我們建議伺服器最小配置為兩個 CPU 核心和 1 Gb 的記憶體。
- 匯出最多 1 億份客戶設定檔的實體時，在使用兩個 CPU 核心和 1 Gb 記憶體的最少建議配置時，可能需要 90 分鐘。
- 您可以匯出到 LiveRamp 的客戶設定檔數目 (或資料) 取決於您和 LiveRamp 的訂閱。

## <a name="set-up-connection-to-liveramp"></a>設定與 LiveRamp 的連接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **LiveRamp**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 選擇是否要透過 SSH 或連接的使用者名/密碼進行驗證，並提供必要的詳細資料。

1. 選取 **驗證** 以測試與 LiveRamp 的連接。

1. 驗證成功後，請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 LiveRamp 區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 在 **連接資料** 欄位中，選取 **電子郵件**、**名稱和位址** 或 **電話** 以傳送至 LiveRamp 進行身分識別解析。

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="LiveRamp 連接器與屬性對應。":::

1. 從您的 *客戶* 實體對應選取金鑰識別碼的屬性。

1. 選取 **新增屬性** 對應更多屬性，以傳送至 LiveRamp。

   > [!TIP]
   > 傳送至 LiveRamp 的金鑰識別元屬性越多，您獲得的對應率可能會越高。

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
