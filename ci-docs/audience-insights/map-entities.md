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
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595983"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="2d750-103">對應實體和屬性</span><span class="sxs-lookup"><span data-stu-id="2d750-103">Map entities and attributes</span></span>

<span data-ttu-id="2d750-104">**對應** 是對象見解的資料統整流程中第一個階段。</span><span class="sxs-lookup"><span data-stu-id="2d750-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="2d750-105">對應包含三個階段：</span><span class="sxs-lookup"><span data-stu-id="2d750-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="2d750-106">*實體選取*：找出可組合的實體，可產生具有更完整客戶資訊的資料集。</span><span class="sxs-lookup"><span data-stu-id="2d750-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="2d750-107">*屬性選取*：針對每個實體，識別想要在 *比對* 和 *合併* 階段中組合和調整的欄。</span><span class="sxs-lookup"><span data-stu-id="2d750-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="2d750-108">這些欄位稱為 *屬性*。</span><span class="sxs-lookup"><span data-stu-id="2d750-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="2d750-109">*主索引鍵語意類型選擇*：對於每個實體，找出您要定義為該實體之主索引鍵的屬性，並針對每個屬性，找出最能準確描述該屬性的語意類型。</span><span class="sxs-lookup"><span data-stu-id="2d750-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="2d750-110">如需資料統合一般流程的詳細資訊，請參閱[統整](data-unification.md)。</span><span class="sxs-lookup"><span data-stu-id="2d750-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="2d750-111">選取第一個實體</span><span class="sxs-lookup"><span data-stu-id="2d750-111">Select the first entities</span></span>

1. <span data-ttu-id="2d750-112">請在對象見解中前往 **資料**  > **統整**  > **對應**。</span><span class="sxs-lookup"><span data-stu-id="2d750-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="2d750-113">選擇 **選取實體** 以開始對應階段。</span><span class="sxs-lookup"><span data-stu-id="2d750-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="2d750-114">選取要在 *比對* 和 *合併* 階段中使用的實體和屬性。</span><span class="sxs-lookup"><span data-stu-id="2d750-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="2d750-115">您可以從實體個別選取所需的屬性，或選取實體層級上的 **包括所有欄位** 核取方塊，以加入實體中的所有屬性。</span><span class="sxs-lookup"><span data-stu-id="2d750-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="2d750-116">我們建議至少選取兩個實體，才能受益於資料統合程序。</span><span class="sxs-lookup"><span data-stu-id="2d750-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d750-117">![新增實體範例](media/data-manager-configure-map-add-entities-example.png "新增實體範例")</span><span class="sxs-lookup"><span data-stu-id="2d750-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="2d750-118">在此範例中，我們要新增 **eCommerceContacts** 及 **loyCustomers** 實體。</span><span class="sxs-lookup"><span data-stu-id="2d750-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="2d750-119">您可以選擇這些實體來衍生有關哪些線上商務客戶是忠誠度方案成員的見解。</span><span class="sxs-lookup"><span data-stu-id="2d750-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="2d750-120">您可以在所有屬性與實體中搜尋關鍵字，以選取想要對應的必要屬性。</span><span class="sxs-lookup"><span data-stu-id="2d750-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d750-121">![搜尋欄位範例](media/data-manager-configure-map-search-fields-example.png "搜尋欄位範例")</span><span class="sxs-lookup"><span data-stu-id="2d750-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="2d750-122">選取 **套用** 以確認您的選取。</span><span class="sxs-lookup"><span data-stu-id="2d750-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="2d750-123">選取屬性的主索引鍵與語意類型</span><span class="sxs-lookup"><span data-stu-id="2d750-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="2d750-124">選取實體之後，**對應** 頁面會列出選取的實體供您檢閱。</span><span class="sxs-lookup"><span data-stu-id="2d750-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="2d750-125">定義實體的主索引鍵，並在實體中識別屬性的語意類型。</span><span class="sxs-lookup"><span data-stu-id="2d750-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="2d750-126">**主索引鍵**：選取一個屬性做為每個實體的主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2d750-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="2d750-127">若要讓屬性成為有效的主索引鍵，其中不能包含重複值、遺漏值或 Null 值。</span><span class="sxs-lookup"><span data-stu-id="2d750-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="2d750-128">字串、整數及 GUID 資料類型屬性支援做為主索引鍵，並且會顯示在欄位中，供您選取。</span><span class="sxs-lookup"><span data-stu-id="2d750-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="2d750-129">**屬性語意類型**：屬性的類別，例如電子郵件地址或名稱。</span><span class="sxs-lookup"><span data-stu-id="2d750-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="2d750-130">若要使用 AI 模型進行語意智慧預測、節省時間並改善準確性，請將 **智慧對應** 設定為 **開啟**。</span><span class="sxs-lookup"><span data-stu-id="2d750-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="2d750-131">智慧對應會在 **類型** 欄位中反白顯示 AI 提供的語意建議。</span><span class="sxs-lookup"><span data-stu-id="2d750-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="2d750-132">如果將其設定為 **關閉**，您看到的會是我們的一般對應建議。</span><span class="sxs-lookup"><span data-stu-id="2d750-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="2d750-133">您可以從可用的選項清單選取任何語意類型，並覆寫建議的選取項目。</span><span class="sxs-lookup"><span data-stu-id="2d750-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2d750-134">![屬性類型和語意預測](media/data-manager-configure-map-add-attributes-semantic-prediction.png "屬性類型和語意預測")</span><span class="sxs-lookup"><span data-stu-id="2d750-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="2d750-135">您也可以新增自訂實體類型。</span><span class="sxs-lookup"><span data-stu-id="2d750-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="2d750-136">選取該屬性的類型欄位，然後輸入自訂語意類型名稱。</span><span class="sxs-lookup"><span data-stu-id="2d750-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="2d750-137">如此一來，您也可以變更系統識別的屬性類型。</span><span class="sxs-lookup"><span data-stu-id="2d750-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="2d750-138">所有由系統自動識別語意類型的屬性，都會在 **檢閱對應欄位** 區段中分為群組。</span><span class="sxs-lookup"><span data-stu-id="2d750-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="2d750-139">檢閱這些屬性及其語意類型，因為資料統合的合併步驟會使用這些屬性來組合您的實體。</span><span class="sxs-lookup"><span data-stu-id="2d750-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="2d750-140">沒有自動對應至語意類型的屬性會在 **定義未對應欄位中的資料** 區段分為群組。</span><span class="sxs-lookup"><span data-stu-id="2d750-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="2d750-141">選取未對應屬性的語意類型欄位，或輸入您的自訂屬性類型名稱。</span><span class="sxs-lookup"><span data-stu-id="2d750-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2d750-142">![主索引鍵和屬性類型](media/data-manager-configure-map-add-attributes.png "主索引鍵和屬性類型")</span><span class="sxs-lookup"><span data-stu-id="2d750-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="2d750-143">一個欄位應該對應至語意類型 Person.FullName，以便填入客戶卡片中的客戶名稱。</span><span class="sxs-lookup"><span data-stu-id="2d750-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="2d750-144">否則，客戶卡片將會以未命名的方式顯示。</span><span class="sxs-lookup"><span data-stu-id="2d750-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="2d750-145">新增和移除屬性及實體</span><span class="sxs-lookup"><span data-stu-id="2d750-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="2d750-146">在 **統整** > **對應** 中，選取 **編輯欄位**。</span><span class="sxs-lookup"><span data-stu-id="2d750-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="2d750-147">在 **編輯欄位** 窗格中，新增或移除屬性及實體。</span><span class="sxs-lookup"><span data-stu-id="2d750-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="2d750-148">使用搜尋或捲動方式，尋找並選取感興趣的屬性及實體。</span><span class="sxs-lookup"><span data-stu-id="2d750-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="2d750-149">如果屬性或實體已經相符，就無法加以移除。</span><span class="sxs-lookup"><span data-stu-id="2d750-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d750-150">![新增或移除屬性](media/configure-data-map-edit.png "新增或移除屬性")</span><span class="sxs-lookup"><span data-stu-id="2d750-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="2d750-151">選取 **套用**。</span><span class="sxs-lookup"><span data-stu-id="2d750-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="2d750-152">將影像新增至設定檔</span><span class="sxs-lookup"><span data-stu-id="2d750-152">Add images to profiles</span></span>

<span data-ttu-id="2d750-153">如果實體包含公開提供的設定檔影像或標誌的 URL，您可以將它們新增至統整的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="2d750-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="2d750-154">選取實體，並尋找包含設定檔影像 URL 的欄位。</span><span class="sxs-lookup"><span data-stu-id="2d750-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="2d750-155">在 **類型** 輸入欄位中，手動輸入下列值：</span><span class="sxs-lookup"><span data-stu-id="2d750-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="2d750-156">對於人員：Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="2d750-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="2d750-157">對於組織：Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="2d750-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="2d750-158">繼續執行統合步驟，並確定包含影像 URL 的屬性也已新增至[合併](merge-entities.md)步驟中。</span><span class="sxs-lookup"><span data-stu-id="2d750-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="2d750-159">設定組織的屬性</span><span class="sxs-lookup"><span data-stu-id="2d750-159">Set attributes for organizations</span></span>

<span data-ttu-id="2d750-160">如果是組織 (預覽)，則屬性類型會對應至「Organization.Name」</span><span class="sxs-lookup"><span data-stu-id="2d750-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="2d750-161">![主索引鍵和屬性類型 B2B](media/configure-data-map-edit-b2b.png "主索引鍵和屬性類型 B2B")</span><span class="sxs-lookup"><span data-stu-id="2d750-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="2d750-162">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2d750-162">Next step</span></span>

<span data-ttu-id="2d750-163">在資料統合程序中，移至 **比對** 頁面。</span><span class="sxs-lookup"><span data-stu-id="2d750-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="2d750-164">造訪 [**比對**](match-entities.md)，了解此階段的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2d750-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="2d750-165">請查看下列影片：[開始使用：建立統整的客戶設定檔](https://youtu.be/oBfGEhucAxs)。</span><span class="sxs-lookup"><span data-stu-id="2d750-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]