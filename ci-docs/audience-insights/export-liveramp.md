---
title: LiveRamp  連接器
description: 了解如何設定連接並匯出至 LiveRamp。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: f9a0a88fb58897e4d279c181f4cdb4f6c852da60
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618925"
---
# <a name="export-segments-to-liverampreg-preview"></a>將客戶細分匯出至 LiveRamp&reg; (預覽版)

在 LiveRamp 中啟動您的資料，便能連接超過 500 多個平台，橫跨數位、社群和電視等領域。 在 LiveRamp 中使用您的資料，將廣告行銷活動設為目標、抑制和個人化。

## <a name="prerequisites-for-a-connection"></a>連接的先決條件

- 您需要 LiveRamp 訂閱才能使用此連接器。
- 若要取得訂閱，請直接[與 LiveRamp 連絡](https://liveramp.com/contact/)。 [進一步了解 LiveRamp 上線](https://liveramp.com/our-platform/data-onboarding/)。

## <a name="set-up-connection-to-liveramp"></a>設定與 LiveRamp 的連接

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **LiveRamp** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 為您的 LiveRamp Secure FTP (SFTP) 帳戶提供 **使用者名稱** 和 **密碼**。
這些認證可能與您的 LiveRamp 上線認證不同。

1. 選取 **驗證** 以測試與 LiveRamp 的連接。

1. 驗證成功後，選取 **我同意** 核取方塊，表示您對 **資料隱私權和合規性** 的同意。

1. 選取 **儲存** 來完成連接。

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 LiveRamp 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 在 **選擇金鑰識別元** 欄位中，選取 **電子郵件**、**名稱和位址** 或 **電話** 以傳送至 LiveRamp 進行身分識別解析。
   > [!div class="mx-imgBorder"]
   > ![LiveRamp 連接器與屬性對應。](media/export-liveramp-segments.png "LiveRamp 連接器與屬性對應")

1. 從您的 *客戶* 實體對應選取金鑰識別碼的屬性。

1. 選取 **新增屬性** 對應更多屬性，以傳送至 LiveRamp。

   > [!TIP]
   > 傳送至 LiveRamp 的金鑰識別元屬性越多，您獲得的對應率可能會越高。

1. 選取您要匯出至 LiveRamp 的區段。

1. 選取 **儲存**。

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Liveramp 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Liveramp 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
