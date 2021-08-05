---
title: 對應資料統整實體
description: 對應資料以建立統整的客戶設定檔。
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7fc05aca61d1136f620019ee82dc6937ea39d8e5
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555113"
---
# <a name="map-entities-and-attributes"></a>對應實體和屬性

**對應** 是對象見解的資料統整流程中第一個階段。 對應包含三個階段：

- *實體選取*：找出可組合的實體，可產生具有更完整客戶資訊的資料集。
- *屬性選取*：針對每個實體，識別想要在 *比對* 和 *合併* 階段中組合和調整的欄。 這些欄位稱為 *屬性*。
- *主索引鍵語意類型選擇*：對於每個實體，找出您要定義為該實體之主索引鍵的屬性，並針對每個屬性，找出最能準確描述該屬性的語意類型。

如需資料統合一般流程的詳細資訊，請參閱[統整](data-unification.md)。

## <a name="select-the-first-entities"></a>選取第一個實體

1. 請在對象見解中前往 **資料**  > **統整**  > **對應**。

2. 選擇 **選取實體** 以開始對應階段。

3. 選取要在 *比對* 和 *合併* 階段中使用的實體和屬性。 您可以從實體個別選取所需的屬性，或選取實體層級上的 **包括所有欄位** 核取方塊，以加入實體中的所有屬性。 我們建議至少選取兩個實體，才能受益於資料統合程序。

   > [!div class="mx-imgBorder"]
   > ![新增實體範例。](media/data-manager-configure-map-add-entities-example.png "新增實體範例")

   在此範例中，我們要新增 **eCommerceContacts** 及 **loyCustomers** 實體。 您可以選擇這些實體來衍生有關哪些線上商務客戶是忠誠度方案成員的見解。
   
   您可以在所有屬性與實體中搜尋關鍵字，以選取想要對應的必要屬性。
   
     > [!div class="mx-imgBorder"]
   > ![搜尋欄位範例。](media/data-manager-configure-map-search-fields-example.png "搜尋欄位範例")

4. 選取 **套用** 以確認您的選取。

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>選取屬性的主索引鍵與語意類型

選取實體之後，**對應** 頁面會列出選取的實體供您檢閱。 定義實體的主索引鍵，並在實體中識別屬性的語意類型。

- **主索引鍵**：選取一個屬性做為每個實體的主索引鍵。 若要讓屬性成為有效的主索引鍵，其中不能包含重複值、遺漏值或 Null 值。 字串、整數及 GUID 資料類型屬性支援做為主索引鍵，並且會顯示在欄位中，供您選取。

- **屬性語意類型**：屬性的類別，例如電子郵件地址或名稱。 若要使用 AI 模型進行語意智慧預測、節省時間並改善準確性，請將 **智慧對應** 設定為 **開啟**。 智慧對應會在 **類型** 欄位中反白顯示 AI 提供的語意建議。 如果將其設定為 **關閉**，您看到的會是我們的一般對應建議。 您可以從可用的選項清單選取任何語意類型，並覆寫建議的選取項目。

> [!div class="mx-imgBorder"]
> ![屬性類型和語義預測。](media/data-manager-configure-map-add-attributes-semantic-prediction.png "屬性類型和語意預測")

您也可以新增自訂實體類型。 選取該屬性的類型欄位，然後輸入自訂語意類型名稱。 如此一來，您也可以變更系統識別的屬性類型。

所有由系統自動識別語意類型的屬性，都會在 **檢閱對應欄位** 區段中分為群組。 檢閱這些屬性及其語意類型，因為資料統合的合併步驟會使用這些屬性來組合您的實體。

沒有自動對應至語意類型的屬性會在 **定義未對應欄位中的資料** 區段分為群組。 選取未對應屬性的語意類型欄位，或輸入您的自訂屬性類型名稱。

> [!div class="mx-imgBorder"]
> ![主索引鍵和屬性類型。](media/data-manager-configure-map-add-attributes.png "主索引鍵和屬性類型")

> [!NOTE]
> 一個欄位應該對應至語意類型 Person.FullName，以便填入客戶卡片中的客戶名稱。 否則，客戶卡片將會以未命名的方式顯示。 

## <a name="add-and-remove-attributes-and-entities"></a>新增和移除屬性及實體

1. 在 **統整** > **對應** 中，選取 **編輯欄位**。

2. 在 **編輯欄位** 窗格中，新增或移除屬性及實體。 使用搜尋或捲動方式，尋找並選取感興趣的屬性及實體。 如果屬性或實體已經相符，就無法加以移除。

   > [!div class="mx-imgBorder"]
   > ![新增或移除屬性。](media/configure-data-map-edit.png "新增或移除屬性")

3. 選取 **套用**。

## <a name="add-images-to-profiles"></a>將影像新增至設定檔

如果實體包含公開提供的設定檔影像或標誌的 URL，您可以將它們新增至統整的客戶設定檔。

選取實體，並尋找包含設定檔影像 URL 的欄位。 在 **類型** 輸入欄位中，手動輸入下列值： 
- 對於人員：Person.ProfileImage
- 對於組織：Organization.LogoImage

繼續執行統合步驟，並確定包含影像 URL 的屬性也已新增至[合併](merge-entities.md)步驟中。

## <a name="set-attributes-for-organizations"></a>設定組織的屬性

如果是組織 (預覽)，則屬性類型會對應至「Organization.Name」
> [!div class="mx-imgBorder"]
> ![主索引鍵和屬性類型 B2B](media/configure-data-map-edit-b2b.png "主索引鍵和屬性類型 B2B")

## <a name="next-step"></a>下一個步驟

在資料統合程序中，移至 **比對** 頁面。 造訪 [**比對**](match-entities.md)，了解此階段的相關資訊。

> [!TIP]
> 請查看下列影片：[開始使用：建立統整的客戶設定檔](https://youtu.be/oBfGEhucAxs)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]