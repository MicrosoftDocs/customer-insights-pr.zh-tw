---
title: Microsoft Teams 機器人
description: 請借助機器人在 Microsoft Teams 中查閱統一的客戶設定檔。
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 9bf401124b0ffb21b046954056141e7703386d4911f89f34ffc0fcb84bf0f4be
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032472"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insights 團隊機器人 (預覽版)

連接 Microsoft Teams 讓機器人查閱 Teams 通道中的統一客戶設定檔。

> [!div class="mx-imgBorder"]
> ![顯示客戶記錄的 Teams 機器人。](media/teams-bot.png "顯示客戶記錄的 Teams 機器人")

## <a name="prerequisites"></a>先決條件

若要安裝並設定機器人，必須符合下列先決條件：

- 至少有一個[新增的資料來源 ](data-sources.md)。
- [統一程序](data-unification.md)已完成。
- 欄位已新增至[搜尋和篩選索引](search-filter-index.md)。
- Customer Insights 和 Teams 位於相同的組織中。

## <a name="configure-the-bot"></a>設定機器人

1. 在對象見解中，前往 **系統管理員** > **匯出目的地**。
1. 在 Microsoft Teams 圖標中，選取 **設定**。
1. 系統會將您重新導向至 Teams 中的 **應用程式** 區域。 您也可以開啟 Teams 並選取左下角的 **應用程式**，或是直接[從 AppSource 中取得](https://go.microsoft.com/fwlink/?linkid=2124104)。
1. 搜尋 **Customer Insights** 並選取此應用程式。
1. 選取 **新增**。
1. 在 Teams 中登入 Customer Insights 之後，您會看到歡迎訊息，並且可以開始使用。

## <a name="things-you-can-do-with-the-bot"></a>您可以使用機器人執行的作業

機器人提供對統一客戶設定檔的查詢功能。

- 輸入 **搜尋** 並在後面接著名稱、電子郵件地址，或任何其他在新增至搜尋及篩選索引之統一客戶設定檔中的欄位。

  您會從產生的客戶設定檔中取得最多 15 個欄位。 有多個相符項目時，會傳回可讓您選取設定檔的結果清單。 您可在雙引號中加入搜尋字詞，以查詢完全相符的項目。

- 如果貴組織在同一個組織維護多個 Customer Insights 環境，您可以輸入 **switchinstance** 選擇將您要連接機器人的環境。

- 輸入 **說明**，以查看機器人的可用命令清單。  


[!INCLUDE[footer-include](../includes/footer-banner.md)]