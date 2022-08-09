---
title: 匯出資料至 SFTP 主機 (預覽版) (含影片)
description: 了解如何設定連接並匯出至 SFTP 位置。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207219"
---
# <a name="export-data-to-sftp-hosts-preview"></a>匯出資料至 SFTP 主機 (預覽版)

要在協力廠商應用程式中使用客戶資料，請將客戶資料匯出至安全檔案傳輸通訊協定 (SFTP) 位置。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>先決條件

- SFTP 主機的可存取程度及對應的認證。

## <a name="known-limitations"></a>已知限制

- 目前不支援在防火牆後的 SFTP 目標。
- 匯出執行時間依您的系統效能而定。 我們建議伺服器最小配置為兩個 CPU 核心和 1 Gb 的記憶體。
- 多達 1 億個客戶資料，如果使用推薦的兩個 CPU 核心和 1 Gb 記憶體的最低配置，這可能需要 90 分鐘。
- 如果您使用 SSH 金鑰進行驗證，請確定您將[私密金鑰](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example)建立為 PEM 或 SSH.COM 格式。 如果您使用的是 Putty，請使用匯出為 Open SSH 來轉換您的私密金鑰。 支援的私密金鑰格式如下：
  - OpenSSL PEM 和 ssh.com 格式的 RSA
  - OpenSSL PEM 和 ssh.com 格式的 DSA
  - OpenSSL PEM 格式的 ECDSA 256/384/521
  - OpenSSH 金鑰格式的 ED25519 和 RSA

## <a name="set-up-connection-to-sftp"></a>設定與 SFTP 的連線

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **SFTP**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 根據預設，只有系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 選擇是否要透過 SSH 或連接的使用者名/密碼進行驗證，並提供必要的詳細資料。 如果您使用 SSH 金鑰進行驗證，請確定您將[私密金鑰](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example)建立為 PEM 或 SSH.COM 格式。 如果您使用的是 Putty，請使用匯出為 Open SSH 來轉換您的私密金鑰。 支援的私密金鑰格式如下：
   - OpenSSL PEM 和 ssh.com 格式的 RSA
   - OpenSSL PEM 和 ssh.com 格式的 DSA
   - OpenSSL PEM 格式的 ECDSA 256/384/521
   - OpenSSH 金鑰格式的 ED25519 和 RSA

1. 選取 **驗證** 以測試連接。

1. 請檢查 [資料隱私權和合規性](connections.md#data-privacy-and-compliance)，並選取 **我同意**。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 移至 **資料** > **匯出**。

1. 選取 **新增匯出**。

1. 在 **匯出的連結** 欄位中，在 SFTP 區段中選擇連接。 如果沒有可用的連接，請與系統管理員聯繫。

1. 輸入匯出的名稱。

1. 選擇是否要以 **Gzipped** 或 **解壓縮** 方式匯出您的資料，以及匯出檔案的 **欄位分隔符號**。

1. 選取您要匯出的實體 (例如客戶細分)。

   > [!NOTE]
   > 匯出時，每個選取的實體會分割成最多五個輸出檔案。

1. 選取 **儲存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> 若匯出包含大量資料的實體，在每個匯出的相同資料夾中可能會產生多個 CSV 檔案。 基於效能因素，將進行分割匯出，以將完成匯出花費的時間降至最低。

[!INCLUDE [footer-include](includes/footer-banner.md)]
