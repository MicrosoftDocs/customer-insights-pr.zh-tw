---
title: 匯出 Customer Insights 資料到 SFTP 主機
description: 了解如何設定與 SFTP 主機的連接。
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643493"
---
# <a name="connector-for-sftp-preview"></a>適用於 SFTP 的連接器 (預覽)

將您的客戶資料匯出到安全檔案傳輸通訊協定 (SFTP) 主機，以便在協力廠商應用程式中使用您的客戶資料。

## <a name="prerequisites"></a>先決條件

- SFTP 主機和對應認證的可用性。

## <a name="connect-to-sftp"></a>連線至 SFTP

1. 移至 **管理員** > **匯出目的地**。

1. 在 **SFTP** 底下選取 **設定**。

1. 在 **顯示名稱** 欄位中，為目的地提供可辨識的名稱。

1. 為您的 SFTP 帳戶提供 **使用者名稱**、**密碼** 和 **主機名稱**。 範例：如果您的 SFTP 伺服器的根資料夾是 /root/folder，而您想要將資料匯出到 /root/folder/ci_export_destination_folder 中，則主機應為 sftp://<server_address>/ci_export_destination_folder。

1. 選取 **驗證** 以測試連接。

1. 成功驗證後，選擇要將資料匯出為 **壓縮** 還是 **解壓縮**，並選取所匯出檔案的 **欄位分隔符號**。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **下一步** 以開始設定匯出。

## <a name="configure-the-connection"></a>設定連接

1. 選取要匯出的 **客戶屬性**。 您可以匯出一個或多個屬性。

1. 選取 **下一步**。

1. 選取您要匯出的客戶細分。

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料透過 SFTP 傳輸時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保匯出目的地符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。
