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
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049384"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="70b78-103">對象見解中的實體</span><span class="sxs-lookup"><span data-stu-id="70b78-103">Entities in audience insights</span></span>

<span data-ttu-id="70b78-104">[設定資料來源](data-sources.md)之後，請移至 **實體** 頁面，評估所擷取資料的品質。</span><span class="sxs-lookup"><span data-stu-id="70b78-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="70b78-105">實體被視為資料集。</span><span class="sxs-lookup"><span data-stu-id="70b78-105">Entities are considered datasets.</span></span> <span data-ttu-id="70b78-106">Dynamics 365 Customer Insights 的多重功能圍繞這些實體組建。</span><span class="sxs-lookup"><span data-stu-id="70b78-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="70b78-107">仔細檢閱它們可協助您驗證這些功能的輸出。</span><span class="sxs-lookup"><span data-stu-id="70b78-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="70b78-108">**實體** 頁面會列出實體，並包含數欄：</span><span class="sxs-lookup"><span data-stu-id="70b78-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="70b78-109">**名稱**：您的資料實體名稱。</span><span class="sxs-lookup"><span data-stu-id="70b78-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="70b78-110">如果實體名稱旁邊出現警告符號，表示無法順利載入該實體的資料。</span><span class="sxs-lookup"><span data-stu-id="70b78-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="70b78-111">**來源**：擷取實體的資料來源類型</span><span class="sxs-lookup"><span data-stu-id="70b78-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="70b78-112">**建立者**：建立實體的人員名稱</span><span class="sxs-lookup"><span data-stu-id="70b78-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="70b78-113">**建立時間**：建立實體的日期與時間</span><span class="sxs-lookup"><span data-stu-id="70b78-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="70b78-114">**更新者**：更新實體的人員名稱</span><span class="sxs-lookup"><span data-stu-id="70b78-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="70b78-115">**上次更新日期**：上次更新實體的日期與時間</span><span class="sxs-lookup"><span data-stu-id="70b78-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="70b78-116">**上次重新整理**：上次資料重新整理的日期與時間</span><span class="sxs-lookup"><span data-stu-id="70b78-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="70b78-117">探索特定實體的資料</span><span class="sxs-lookup"><span data-stu-id="70b78-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="70b78-118">選取一個實體，以探索該實體中包含的不同欄位和記錄。</span><span class="sxs-lookup"><span data-stu-id="70b78-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="70b78-119">![選取實體](media/data-manager-entities-data.png "選取實體")</span><span class="sxs-lookup"><span data-stu-id="70b78-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="70b78-120">**資料** 索引標籤會顯示一個表格，其中列出有關實體中個別記錄的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="70b78-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="70b78-121">![欄位表格](media/data-manager-entities-fields.PNG "欄位表格")</span><span class="sxs-lookup"><span data-stu-id="70b78-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="70b78-122">**屬性** 索引標籤會被預設選取，並顯示用來檢閱所選實體詳細資料的表格，例如欄位名稱、資料類型和類型。</span><span class="sxs-lookup"><span data-stu-id="70b78-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="70b78-123">**類型** 欄會顯示 Common Data Model 關聯的類型，它們是由系統自動識別或由使用者[手動對應](map-entities.md)。</span><span class="sxs-lookup"><span data-stu-id="70b78-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="70b78-124">這些語意類型可以不同於屬性的資料類型，例如，下列的欄位 *電子郵件* 有資料類型 *文字*，但是其 (語意) Common Data Model 類型可能是 *電子郵件* 或 *EmailAddress*。</span><span class="sxs-lookup"><span data-stu-id="70b78-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="70b78-125">這兩個表格只會顯示您實體之資料的範例。</span><span class="sxs-lookup"><span data-stu-id="70b78-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="70b78-126">若要查看完整資料集，請移至 **資料來源** 頁面，選取實體，選取 **編輯**，然後使用 Power Query 編輯器查看此實體的資料（如[資料來源](data-sources.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="70b78-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="70b78-127">若要進一步了解實體中擷取的資料，**摘要** 欄提供了一些重要的資料特徵，例如 null、遺失值、唯一值、計數和分佈（視何者適用於您的資料）。</span><span class="sxs-lookup"><span data-stu-id="70b78-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="70b78-128">選取圖表圖示以查看資料的摘要。</span><span class="sxs-lookup"><span data-stu-id="70b78-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="70b78-129">![摘要符號](media/data-manager-entities-summary.png "資料摘要表格")</span><span class="sxs-lookup"><span data-stu-id="70b78-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="70b78-130">後續步驟</span><span class="sxs-lookup"><span data-stu-id="70b78-130">Next step</span></span>

<span data-ttu-id="70b78-131">若要了解如何 *對應*、*比對* 和 *合併* 擷取的資料，請參閱[統整](data-unification.md)主題。</span><span class="sxs-lookup"><span data-stu-id="70b78-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
