---
title: 將 Customer Insights 資料匯出至 SFTP 主機 (含影片)
description: 了解如何設定連接並匯出至 SFTP 位置。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5170ec4ca35ad2a94f02e9d696c44a32da888120
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645769"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>將客戶細分和其他資料匯出至 SFTP (預覽版)

要在協力廠商應用程式中使用客戶資料，請將客戶資料匯出至安全檔案傳輸通訊協定 (SFTP) 位置。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>連接的先決條件

- SFTP 主機的可存取程度及對應的認證。

## <a name="known-limitations"></a>已知限制

- 目前不支援在防火牆後的 SFTP 目標。 
- 匯出執行時間依您的系統效能而定。 我們建議伺服器最小配置為兩個 CPU 核心和 1 Gb 的記憶體。 
- 匯出最多 1 億份客戶設定檔的實體時，在使用兩個 CPU 核心和 1 Gb 記憶體的最少建議配置時，可能需要 90 分鐘。 

## <a name="set-up-connection-to-sftp"></a>設定與 SFTP 的連線

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **SFTP** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供 **使用者名稱**、**密碼**、 **主機名稱** 和 **匯出資料夾** 給您的 SFTP 帳戶。

1. 選取 **驗證** 以測試連接。

1. 選擇是否要以 **Gzipped** 或 **解壓縮** 方式匯出您的資料，以及匯出檔案的 **欄位分隔符號**。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 SFTP 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 選取您要匯出的實體 (例如客戶細分)。

   > [!NOTE]
   > 匯出時，每個選取的實體會分割成最多五個輸出檔。 

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料透過 SFTP 傳輸時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保匯出目的地符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。

[!INCLUDE [footer-include](includes/footer-banner.md)]
