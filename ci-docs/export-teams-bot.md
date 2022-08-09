---
title: Dynamics 365 Customer Insights 團隊機器人 (預覽版)
description: 請借助機器人在 Microsoft Teams 中查閱統一的客戶設定檔。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195832"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insights 團隊機器人 (預覽版)

連接 Microsoft Teams 讓機器人查閱 Teams 通道中的統一客戶設定檔。

:::image type="content" source="media/teams-bot.png" alt-text="顯示客戶記錄的 Teams 機器人":::

## <a name="prerequisites"></a>先決條件

- 至少有一個[新增的資料來源](data-sources.md)。
- [統一程序](data-unification.md)已完成。
- 欄位已新增至[搜尋 & 篩選索引](search-filter-index.md)。
- Customer Insights 和 Teams 位於相同的組織中。
- 您的環境有主要目標對象設定為個人客戶。 不支援商務帳戶。


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>設定機器人

1. 移至 **管理** > **連接**。
1. 在 Microsoft Teams 圖標中，選取 **設定**。
1. 系統會將您重新導向至 Teams 中的 **應用程式** 區域。 您也可以開啟 Teams 並選取左下角的 **應用程式**，或是直接[從 AppSource 中取得](https://go.microsoft.com/fwlink/?linkid=2124104)。
1. 搜尋 **Customer Insights** 並選取此應用程式。
1. 選取 **新增**。
1. 登入 Teams 中的 Customer Insights。 將顯示歡迎訊息。

## <a name="things-you-can-do-with-the-bot"></a>您可以使用機器人執行的作業

機器人提供對統一客戶設定檔的查詢功能。

- 輸入 **搜尋** 並在後面接著名稱、電子郵件地址，或任何其他在新增至搜尋 & 篩選索引之統一客戶設定檔中的欄位。

  您會從產生的客戶設定檔中取得最多 15 個欄位。 有多個相符項目時，會傳回可讓您選取設定檔的結果清單。 若要查詢完全相符，請在雙引號中加入搜尋字詞。

- 如果貴組織在同一個組織維護多個 Customer Insights 環境，可輸入 **switchinstance** 選擇將您要連接機器人的環境。

- 輸入 **說明**，以查看機器人的可用命令清單。  

[!INCLUDE [footer-include](includes/footer-banner.md)]