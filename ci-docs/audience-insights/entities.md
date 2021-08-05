---
title: 實體和資料集
description: 在實體頁面上檢視資料。
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: ac8b0671b20123091bef64e672fc53398fe8955a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "6553965"
---
# <a name="entities-in-audience-insights"></a>對象見解中的實體

[設定資料來源](data-sources.md)之後，請移至 **實體** 頁面，評估所擷取資料的品質。 實體被視為資料集。 Dynamics 365 Customer Insights 的多重功能圍繞這些實體組建。 仔細檢閱它們可協助您驗證這些功能的輸出。

**實體** 頁面會列出實體，並包含數欄：

- **名稱**：您的資料實體名稱。 如果實體名稱旁邊出現警告符號，表示無法順利載入該實體的資料。
- **來源**：擷取實體的資料來源類型
- **建立者**：建立實體的人員名稱
- **建立時間**：建立實體的日期與時間
- **更新者**：更新實體的人員名稱
- **上次更新日期**：上次更新實體的日期與時間
- **上次重新整理**：上次資料重新整理的日期與時間

## <a name="explore-a-specific-entitys-data"></a>探索特定實體的資料

選取一個實體，以探索該實體中包含的不同欄位和記錄。

> [!div class="mx-imgBorder"]
> ![選取實體。](media/data-manager-entities-data.png "選取實體")

- **資料** 索引標籤會顯示一個表格，其中列出有關實體中個別記錄的詳細資料。

> [!div class="mx-imgBorder"]
> ![欄位表格。](media/data-manager-entities-fields.PNG "欄位表格")

- **屬性** 索引標籤會被預設選取，並顯示用來檢閱所選實體詳細資料的表格，例如欄位名稱、資料類型和類型。 **類型** 欄會顯示 Common Data Model 關聯的類型，它們是由系統自動識別或由使用者[手動對應](map-entities.md)。 這些類型是語義類型，且可以與屬性的資料類型不同。 例如，下列的 *電子郵件* 欄位有資料類型 *文字*，但是 (語義的) Common Data Model 類型可能是 *電子郵件* 或 *EmailAddress*。

> [!NOTE]
> 這兩個表格只會顯示您實體之資料的範例。 若要查看完整資料集，請移至 **資料來源** 頁面，選取實體，選取 **編輯**，然後使用 Power Query 編輯器查看此實體的資料（如[資料來源](data-sources.md)中所述）。

若要進一步了解實體中擷取的資料，**摘要** 欄提供了一些重要的資料特徵，例如 null、遺失值、唯一值、計數和分佈（視何者適用於您的資料）。

選取圖表圖示以查看資料的摘要。

> [!div class="mx-imgBorder"]
> ![摘要符號。](media/data-manager-entities-summary.png "資料摘要表格")

## <a name="entity-specific-information"></a>指定實體資訊

下列各節將對系統建立的實體提供相關資訊。

### <a name="corrupted-data-sources"></a>損毀的資料來源

從資料來源擷取來的欄位，可能包含損壞的資料。 損毀欄位的記錄會在系統建立的實體中顯示。 得知損毀的記錄，讓您能找出來源系統上要檢閱和更新的資料。 下次重新整理資料來源之後，已更正的記錄會擷取至 Customer Insights，並傳遞至下游處理程序。 

例如，'birthday' 資料行會將資料類型設定為 'date'。 一筆客戶記錄的生日輸入成 '01/01/19777'。 系統會將此記錄標記為已損毀。 某人現在到來源系統中把生日變更 '1977'。 自動重新整理資料來源之後，欄位現在會是有效的格式，而且該記錄將會從損毀實體中移除。 

移至 **資料** > **實體**，並在 **系統** 區段中尋找損毀實體。 損毀實體的結構描述名稱：'DataSourceName_EntityName_corrupt'。

Customer Insights 仍然會處理損毀的記錄。 但是，當您使用整合資料時，可能會造成問題。

下列檢查會在擷取的資料上執行，以找出損毀的記錄： 

- 欄位的值與其資料行的資料類型不相符。
- 欄位包含的字元會造成資料行與預期的結構描述不相符。 例如：未正確格式化的引號、未跳脫引號或換行字元。
- 如果有 datetime/date/datetimeoffset 資料行，且不符合標準 ISO 格式，則必須在模型中指定其格式。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
