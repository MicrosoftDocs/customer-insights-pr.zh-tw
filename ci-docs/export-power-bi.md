---
title: Power BI 連接器 (預覽)
description: 了解如何在 Power BI 中使用 Dynamics 365 Customer Insights 連接器。
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 72daf6d4ef3b6afb8049c622b57e7ec44762fb21
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051259"
---
# <a name="power-bi-connector-preview"></a>Power BI 連接器 (預覽)

使用 Microsoft Power BI Desktop 為您的資料建立視覺效果。 利用您的統整客戶資料建立其他見解並建立報表。

## <a name="prerequisites"></a>先決條件

- 您具有統一的客戶設定檔。
- 最新版本的 [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/)已安裝在您的電腦上。 [進一步了解 Power BI Desktop](/power-bi/desktop-what-is-desktop)。

## <a name="configure-the-connector-for-power-bi"></a>設定 Power BI 的連接器

1. 在 Power BI Desktop 中，選取 **檔案** > **取得資料**。

1. 選取 **顯示較多資訊** 並搜尋 **Dynamics 365 Customer Insights**

1. 選取 **Connect**。

1. 使用與用於 Customer Insights 相同的組織帳戶 **登入**，並選取 **關係**。
   > [!NOTE]
   > 您在此步驟中指出的帳戶，是用來從 Customer Insights 擷取資料，並不需要與您登入 Power BI 所用的帳戶相同。 若要重設用於資料取得的帳戶，請打開 Power BI 並前往 **檔案** > **選項** > **設定** > **資料來源設定**。 在資料來源清單中，選取 **Dynamics 365 Customer Insights 登入**，並選取 **清除權限**。  

1. 在 **導覽器** 對話方塊中。 您會看到所有您有存取權的環境清單。 展開環境並打開任何資料夾 (實體、量值、區段、富集群)。 例如，開啟 **實體** 資料夾以查看所有您可匯入的實體。

   ![Power BI 連接器導覽器。](media/power-bi-navigator.png "Power BI 連接器導覽器")

1. 選取要包含的實體旁邊的核取方塊並 **載入**。 您可以從多個環境選取多個實體。

1. 載入實體時，您會看到載入對話方塊。 一旦已經載入所有選取的實體之後，您就可以使用 Power BI 的功能視覺化資料。

## <a name="large-data-sets"></a>大型資料集

Power BI 的 Customer Insights 連接器是設計來處理包含多達 1 百萬個客戶設定檔的資料集。 匯入較大型資料集或許可行，但需要花費很長時間。 此外，程序可能會因為 Power BI 的限制而發生逾時。 如需詳細資訊，請參閱 [Power BI：對處理大型資料集的建議](/power-bi/admin/service-premium-what-is#large-datasets)。 

### <a name="work-with-a-subset-of-data"></a>使用資料的子集

考慮搭配您的資料子集合處理。 例如您可以建立 [區段](segments.md) 而不是將所有客戶記錄匯出到 Power BI。

## <a name="troubleshooting"></a>疑難排解​​

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights 環境沒有顯示在 Power BI 中

在 Customer Insights 兩個相同實體之間定義了超過一個的[關係](relationships.md)，其所在的環境於 Power BI 連接器中無法使用。

您可以找出並移除重複的關聯。

1. 在 Power BI 中遺失的環境中，前往 **資料** > **關係**。
2. 找出重複的關聯：
   - 檢查是否對相同的兩個實體定義了多個關聯。
   - 檢查是否有關聯建立在兩個同時包含在整合程序中的實體。 在整合程序中包含的所有實體，都會被定義隱式關聯。
3. 移除任何已發現的重複關聯。

移除重複的關聯之後，請再次嘗試設定 Power BI連接器。 環境現在應該可以使用了。

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>在 Power BI Desktop 中載入實體時，日期欄位發生錯誤

載入實體中包含如 MM/DD/YYYY 日期格式的欄位時，可能會發生錯誤，因為與地區設定格式不相符。 當 Power BI Desktop 檔案設為非英文 (美國) 的其他地區設定時，就會發生此不相符現象，因為 Customer Insights 中的日期欄位會儲存為 US 格式。

Power BI Desktop 檔案有單一地區設定，在檢索資料時套用。 要讓這些日期欄位可以正確解譯，請設定.BPI 檔案的地區設定為英文 (美國)。 [了解如何變更 Power BI Desktop 檔案的地區設定](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
