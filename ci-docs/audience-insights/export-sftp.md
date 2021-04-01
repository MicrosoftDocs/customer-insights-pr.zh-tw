---
title: 匯出 Customer Insights 資料到 SFTP 主機
description: 了解如何設定與 SFTP 主機的連接。
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598375"
---
# <a name="connector-for-sftp-preview"></a>適用於 SFTP 的連接器 (預覽)

將您的客戶資料匯出到安全檔案傳輸通訊協定 (SFTP) 主機，以便在協力廠商應用程式中使用您的客戶資料。

## <a name="prerequisites"></a>先決條件

- SFTP 主機的可存取程度及對應的認證。

## <a name="connect-to-sftp"></a>連線至 SFTP

1. 移至 **管理員** > **匯出目的地**。

1. 在 **SFTP** 底下選取 **設定**。

1. 在 **顯示名稱** 欄位中，為目的地提供可辨識的名稱。

1. 提供 **使用者名稱**、**密碼**、 **主機名稱** 和 **匯出資料夾** 給您的 SFTP 帳戶。

1. 選取 **驗證** 以測試連接。

1. 在驗證成功後，選擇要以 **Gzipped** 或 **解壓縮** 的方式匯出資料，並選取匯出後檔案的 **欄位分隔符號**。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **下一步** 以開始設定匯出。

## <a name="configure-the-export"></a>設定匯出

1. 選取您要匯出的實體 (例如客戶細分)。

   > [!NOTE]
   > 在匯出時最，選取的每個實體多會有五個匯出檔。 

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。

## <a name="known-limitations"></a>已知限制

- 匯出執行時間依您的系統效能而定。 我們建議伺服器最小配置為兩個 CPU 核心和 1 Gb 的記憶體。 
- 匯出最多 1 億份客戶設定檔的實體時，在使用兩個 CPU 核心和 1 Gb 記憶體的最少建議配置時，可能需要 90 分鐘。 

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料透過 SFTP 傳輸時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保匯出目的地符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]