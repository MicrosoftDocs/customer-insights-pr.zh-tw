---
title: 匯出 Customer Insights 資料到 AdRoll
description: 瞭解如何設定到 AdRoll 的連接。
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697064"
---
# <a name="connector-for-adroll-preview"></a>AdRoll 的連接器 (預覽版)

將統整客戶個人資料的客戶細分匯出至 AdRoll，並用來進行廣告。 

## <a name="prerequisites"></a>先決條件

-   您具有 [AdRoll 帳戶](https://www.adroll.com/) 及對應的系統管理員認證。
-   您在對象見解中具有 [組態區域](segments.md) 權限。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="connect-to-adroll"></a>連線至 AdRoll

1. 移至 **管理員** > **匯出目的地**。

1. 請在 **AdRoll** 下方選取 **設定**。

1. 在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll 連接的設定窗格。":::

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 初始化與 AdRoll 的連接。

1. 選取 **使用 AdRoll 驗證** 並提供您的 AdRoll 管理員認證。 

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 輸入您的 **AdRoll 廣告客戶識別碼**[AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles)。

1. 選取 **下一步** 以設定匯出。

## <a name="configure-the-connector"></a>設定連接器

1. 在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。 必需將客戶細分匯出至 AdRoll。

1. 選取您要匯出的客戶細分。 選取一個包含最少 100 個成員的客戶細分。 您無法匯出更小的客戶細分。 此外，會出一個客戶細分最大數量為每個匯出 250'000 個成員。 

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。

## <a name="known-limitations"></a>已知限制

- 每個匯出最多可匯出總共 250'000 份的個人資料到 AdRoll。
- 您不能將少於 100 份個人資料的客戶細分匯出至 AdRoll。 
- 對 AdRoll 的匯出被限制為客戶細分。
- 匯出最多 250'000 個人資料至 AdRoll 可能需要 10 分鐘的時間才能完成。 
- 您可以匯出到 AdRoll 的個人資料數量依照且受限於您與 AdRoll 的合約。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 AdRoll 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 AdRoll 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。
