---
title: 實體和資料集
description: 在實體頁面上檢視資料。
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 1e1abdf49a3c1fe6f9fdd2cf5353a7723454f47b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355288"
---
# <a name="entities-in-audience-insights"></a>對象見解中的實體

[設定資料來源](data-sources.md)之後，請移至 **實體** 頁面，評估所擷取資料的品質。 實體被視為資料集。 Dynamics 365 Customer Insights 的多重功能圍繞這些實體組建。 仔細檢閱它們可協助您驗證這些功能的輸出。

**實體** 頁面會列出實體，並包含下列資料行：

- **名稱**：資料實體的名稱。 如果實體名稱旁邊出現警告符號，表示無法順利載入該實體的資料。
- **來源**：擷取到實體的資料來源類型。
- **更新**：實體上次更新的時間。
- **狀態**：實體上次更新的詳細資料。

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>探索特定實體的資料

1. 請在對象見解中前往 **資料** > **實體**。
1. 在 **實體** 頁面中，選取一個實體來打開詳細資料頁面。  
1. 探索該實體中包含的不同欄位和記錄。

- **屬性** 索引標籤會被預設選取，並顯示用來檢閱所選實體詳細資料的表格，例如欄位名稱、資料類型和類型。 **類型** 欄會顯示 Common Data Model 關聯的類型，它們是由系統自動識別或由使用者[手動對應](map-entities.md)。 這些類型是語義類型，且可以與屬性的資料類型不同。 例如，下列的 *電子郵件* 欄位有資料類型 *文字*，但是 (語義的) Common Data Model 類型可能是 *電子郵件* 或 *EmailAddress*。

> [!div class="mx-imgBorder"]
> ![欄位表格。](media/data-manager-entities-fields.PNG "欄位表格")

> [!NOTE]
> 此頁面只會顯示您實體資料的範例。 若要查看完整資料集，請移至 **資料來源** 頁面，選取實體，選取 **編輯**，然後使用 Power Query 編輯器查看此實體的資料（如[資料來源](data-sources.md)中所述）。

若要進一步了解實體中擷取的資料，**摘要** 欄提供了一些重要的資料特徵，例如 null、遺失值、唯一值、計數和分佈（視何者適用於您的資料）。 選取圖表圖示以查看資料的摘要。

> [!div class="mx-imgBorder"]
> ![摘要符號。](media/data-manager-entities-summary.png "資料摘要表格")

- **資料** 索引標籤會顯示一個表格，其中列出有關實體中個別記錄的詳細資料。 列出的詳細資料會依實體的資料類型而定。

> [!div class="mx-imgBorder"]
> ![選取實體。](media/data-manager-entities-data.png "選取實體")

- **報表** 索引標籤（在某些實體可用）讓您可透過建立報表來實現資料的視覺化效果，並包含這些資料行：

  - **報表名稱**：報表的名稱。
  - **建立者**：建立實體的人員名稱。
  - **建立時間**：建立實體的日期與時間。
  - **編輯者**：修改實體的人員名稱。
  - **編輯時間**：修改實體的日期與時間。 

## <a name="entity-specific-information"></a>指定實體資訊

下列各節將對系統建立的實體提供相關資訊。

### <a name="corrupted-data-sources"></a>損毀的資料來源

從資料來源擷取來的欄位，可能包含損壞的資料。 損毀欄位的記錄會在系統建立的實體中顯示。 得知損毀的記錄，讓您能找出來源系統上要檢閱和更新的資料。 下次重新整理資料來源之後，已更正的記錄會擷取至 Customer Insights，並傳遞至下游處理程序。 

例如，'birthday' 資料行會將資料類型設定為 'date'。 一筆客戶記錄的生日輸入成 '01/01/19777'。 系統會將此記錄標記為已損毀。 某人現在到來源系統中把生日變更 '1977'。 自動重新整理資料來源之後，欄位現在會是有效的格式，而且該記錄將會從損毀實體中移除。 

移至 **資料** > **實體**，並在 **系統** 區段中尋找損毀實體。 損毀實體的結構描述名稱：'DataSourceName_EntityName_corrupt'。 選取已損壞的實體，找出個別記錄等級中所有損壞的欄位和原因。
> [!div class="mx-imgBorder"]
> ![損壞原因。](media/corruption-reason.png "損壞原因")

Customer Insights 仍然會處理損毀的記錄。 但是，當您使用整合資料時，可能會造成問題。

下列檢查會在擷取的資料上執行，以找出損毀的記錄： 

- 欄位的值與其資料行的資料類型不相符。
- 欄位包含的字元會造成資料行與預期的結構描述不相符。 例如：未正確格式化的引號、未跳脫引號或換行字元。
- 如果有 datetime/date/datetimeoffset 資料行，當其不符合標準 ISO 格式時，在模型中必須指定其格式。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
