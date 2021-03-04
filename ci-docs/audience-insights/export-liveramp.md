---
title: LiveRamp  連接器
description: 了解如何將資料匯出到 LiveRamp。
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270148"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg; 連接器 (預覽)

在 LiveRamp 中啟用您的資料，與遍佈數位、社交和電視生態系統的 500 多個平台進行連接。 在 LiveRamp 中使用您的資料，將廣告行銷活動設為目標、抑制和個人化。

## <a name="prerequisites"></a>先決條件

- 您需要 LiveRamp 訂閱才能使用此連接器。
- 若要取得訂閱，請直接[與 LiveRamp 連絡](https://liveramp.com/contact/)。 [進一步了解 LiveRamp 上線](https://liveramp.com/our-platform/data-onboarding/)。

## <a name="connect-to-liveramp"></a>連接至 LiveRamp

1. 在對象見解中，前往 **系統管理員** > **匯出目的地**。

1. 在 **LiveRamp** 圖格中選取 **設定**。

1. 在 **顯示名稱** 欄位中，為目的地提供可辨識的名稱。

1. 為您的 LiveRamp Secure FTP (SFTP) 帳戶提供 **使用者名稱** 和 **密碼**。
這些認證可能與您的 LiveRamp 上線認證不同。

1. 選取 **驗證** 以測試與 LiveRamp 的連接。

1. 驗證成功後，選取 **我同意** 核取方塊，表示您對 **資料隱私權和合規性** 的同意。

1. 選取 **下一步** 以設定 LiveRamp 連接器。

## <a name="configure-the-connector"></a>設定連接器

1. 在 **選擇金鑰識別元** 欄位中，選取 **電子郵件**、**名稱和位址** 或 **電話** 以傳送至 LiveRamp 進行身分識別解析。

1. 從您的統一客戶實體中對應所選金鑰識別元的相應屬性。

1. 選取 **新增屬性**，以對應要傳送至 LiveRamp 的其他屬性。

   > [!TIP]
   > 傳送至 LiveRamp 的金鑰識別元屬性越多，您獲得的對應率可能會越高。

1. 選取您要匯出至 LiveRamp 的區段。

1. 選取 **儲存**。

> [!div class="mx-imgBorder"]
> ![LiveRamp 連接器與屬性對應](media/export-liveramp-segments.png "LiveRamp 連接器與屬性對應")

## <a name="export-the-data"></a>匯出資料

如果所有匯出先決條件皆已齊備，就會立即開始匯出。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。
成功完成匯出之後，就可以登入 LiveRamp 上線來啟用和散發您的資料。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Liveramp 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Liveramp 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。

[!INCLUDE[footer-include](../includes/footer-banner.md)]