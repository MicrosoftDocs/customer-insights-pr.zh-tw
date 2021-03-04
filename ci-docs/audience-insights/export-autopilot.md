---
title: 匯出 Customer Insights 資料到 Autopilot
description: 瞭解如何設定與 Autopilot 的連接。
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269228"
---
# <a name="connector-for-autopilot-preview"></a>適用 Autopilot 的連接器 (預覽版)

將統整客戶設定檔的客戶細分匯出至 Autopilot，並在 Autopilot 中用來進行電子郵件行銷。 

## <a name="prerequisites"></a>先決條件

-   您具有 [Autopilot 帳戶](https://www.autopilothq.com/) 及對應的系統管理員認證。
-   您在對象見解中具有 [組態區域](segments.md) 權限。
-   匯出區段的統一客戶設定檔包含代表電子郵件地址的欄位。

## <a name="connect-to-autopilot"></a>連接至 Autopilot

1. 移至 **管理員** > **匯出目的地**。

1. 請在 **Autopilot** 下方選取 **設定**。

1. 在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot 連接的設定窗格。":::

1. 輸入您的 **Autopilot API 金鑰**[Autopilot API 金鑰 ](https://autopilot.docs.apiary.io/#)。

1. 選取 **我同意** 以確認 **資料隱私權與合規性**。

1. 選取 **連接** 初始化與 Autopilot 的連接。

1. 選取 **將您自己新增為匯出使用者** 並提供您的 Customer Insights 認證。

1. 選取 **下一步** 以設定匯出。

## <a name="configure-the-connector"></a>設定連接器

1. 在 **資料符合** 區段的 **電子郵件** 欄位中，選取代表客戶電子郵件地址的統一客戶設定檔欄位。 對其他可選欄位 (如 **名**、**姓**) 重複相同步驟。

1. 選取您要匯出的客戶細分。 我們強烈 **建議您不要匯出總計超過 100'000 份客戶設定檔** 到 Autopilot。 

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。

## <a name="known-limitations"></a>已知限制

- 您最多可匯出總共 100'000 份的客戶設定檔到 Autopilot。
- 匯出到 Autopilot 被限制在客戶細分。
- 匯出多達 100'000 份設定檔到 Autopilot 需要花費幾個小時。 
- 您可以匯出到 Autopilot 的設定檔數量是根據且受限於您與 Autopilot 的合約。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 來傳輸資料給 Autopilot，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，其中包括潛在敏感資料 (如個人資料)。 Microsoft 將依據您的指示傳輸此資料，但您有責任確保 Autopilot 符合任何您承擔的隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]