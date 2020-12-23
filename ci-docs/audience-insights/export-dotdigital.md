---
title: 匯出 Customer Insights 資料到 DotDigital
description: 瞭解如何組態到 DotDigital 的連接。
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644438"
---
# <a name="connector-for-dotdigital-preview"></a>適用 DotDigital 的連接器 (預覽版)

將統一的客戶設定檔區段匯出到 DotDigital 通訊錄，並用於行銷活動、電子郵件行銷及使用 DotDigital 組建客戶區段。 

## <a name="prerequisites"></a>先決條件

-   您具有 [DotDigital 帳戶](https://dotdigital.com/) 及對應的系統管理員認證。
-   DotDigital 和對應的識別碼中含有現有的通訊錄。 當您選取和打開通訊錄時，可以在 URL 找到識別碼。 如需詳細資訊，請見 [DotDigital 通訊錄](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)。
-   您在對象見解中具有 [組態區域](segments.md) 權限。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="connect-to-dotdigital"></a>連接到 DotDigital

1. 移至 **管理員** > **匯出目的地**。

1. 請在 **DotDigital** 下方選取 **設定**。

1. 在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital 匯出的組態窗格。":::

1. 輸入您的 **DotDigital 使用者名稱和密碼**。

1. 輸入您的 **[DotDigital 通訊錄 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 初始化到 DotDigital 的連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **下一步** 以設定匯出。

## <a name="configure-the-connector"></a>設定連接器

1. 在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。 針對其他可選欄位如 **名字**、**姓氏**、**全名**、**性別** 和 **貼文代碼** 重複相同步驟。

1. 選取您要匯出的客戶細分。 您總共最多可匯出 1 百萬個客戶設定檔到 DotDigital。

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。 您現在可以在 [DotDigital 通訊錄](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) 中找到您的區段。

## <a name="known-limitations"></a>已知限制

- 每個到 DotDigital 的匯出最多可達 1 百萬個設定檔。
- 匯出到 DotDigital 被限制為區段。
- 因供應商端的限制，匯出總計 1 百萬個設定檔的區段最長會耗時 3 小時。 
- 您可以匯出到 DotDigital 的設定檔數量端賴且受限於您與 DotDigital 的合約。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 DotDigital 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 DotDigital 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。
