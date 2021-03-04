---
title: Power BI 連接器
description: 了解如何在 Power BI 中使用 Dynamics 365 Customer Insights 連接器。
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477078"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="1e9a0-103">適用於 Power BI 的連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="1e9a0-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="1e9a0-104">使用 Power BI Desktop 為您的資料建立視覺效果。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="1e9a0-105">利用您的統整客戶資料建立其他見解並建立報表。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e9a0-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="1e9a0-106">Prerequisites</span></span>

- <span data-ttu-id="1e9a0-107">您具有統一的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="1e9a0-108">最新版本的 [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) 已安裝在您的電腦上。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="1e9a0-109">[進一步了解 Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="1e9a0-110">設定 Power BI 的連接器</span><span class="sxs-lookup"><span data-stu-id="1e9a0-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="1e9a0-111">在 Power BI Desktop 中，選取 **檔案** > **取得資料**。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="1e9a0-112">選取 **顯示較多資訊** 並搜尋 **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="1e9a0-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="1e9a0-113">選取 **Connect**。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-113">Select **Connect**.</span></span>

1. <span data-ttu-id="1e9a0-114">使用與用於 Customer Insights 相同的組織帳戶 **登入**，並選取 **關係**。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1e9a0-115">您在此步驟中指出的帳戶，是用來從 Customer Insights 擷取資料，並不需要與您登入 Power BI 所用的帳戶相同。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="1e9a0-116">若要重設用於資料取得的帳戶，請打開 Power BI 並前往 **檔案** > **選項** > **設定** > **資料來源設定**。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="1e9a0-117">在資料來源清單中，選取 **Dynamics 365 Customer Insights 登入**，並選取 **清除權限**。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="1e9a0-118">在 **導覽器** 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="1e9a0-119">您會看到所有您有存取權的環境清單。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="1e9a0-120">展開環境並打開任何資料夾 (實體、量值、區段、富集群)。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="1e9a0-121">例如，開啟 **實體** 資料夾以查看所有您可匯入的實體。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="1e9a0-122">![Power BI 連接器導覽器](media/power-bi-navigator.png "Power BI 連接器導覽器")</span><span class="sxs-lookup"><span data-stu-id="1e9a0-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="1e9a0-123">選取要包含的實體旁邊的核取方塊並 **載入**。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="1e9a0-124">您可以從多個環境選取多個實體。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="1e9a0-125">載入實體時，您會看到載入對話方塊。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="1e9a0-126">一旦已經載入所有選取的實體之後，您就可以使用 Power BI 的功能視覺化資料。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="1e9a0-127">大型資料集</span><span class="sxs-lookup"><span data-stu-id="1e9a0-127">Large data sets</span></span>

<span data-ttu-id="1e9a0-128">Power BI 的 Customer Insights 連接器是設計來處理包含多達 1 百萬個客戶設定檔的資料集。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="1e9a0-129">匯入較大型資料集或許可行，但需要花費很長時間。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="1e9a0-130">此外，程序可能會因為 Power BI 的限制而發生逾時。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="1e9a0-131">如需詳細資訊，請參閱 [Power BI：對處理大型資料集的建議](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets)。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="1e9a0-132">使用資料的子集</span><span class="sxs-lookup"><span data-stu-id="1e9a0-132">Work with a subset of data</span></span>

<span data-ttu-id="1e9a0-133">考慮搭配您的資料子集合處理。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="1e9a0-134">例如您可以建立 [區段](segments.md) 而不是將所有客戶記錄匯出到 Power BI。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1e9a0-135">疑難排解​​</span><span class="sxs-lookup"><span data-stu-id="1e9a0-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="1e9a0-136">Customer Insights 環境沒有顯示在 Power BI 中</span><span class="sxs-lookup"><span data-stu-id="1e9a0-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="1e9a0-137">環境中的兩個相同實體在對象見解中定義了超過一個的[關聯](relationships.md)，則在 Power BI 連接器中無法使用該環境。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="1e9a0-138">您可以找出並移除重複的關聯。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="1e9a0-139">到您在 Power BI 遺失的環境，在對象見解中移至其 **資料** > **關聯**。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="1e9a0-140">找出重複的關聯：</span><span class="sxs-lookup"><span data-stu-id="1e9a0-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="1e9a0-141">檢查是否對相同的兩個實體定義了多個關聯。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="1e9a0-142">檢查是否有關聯建立在兩個同時包含在整合程序中的實體。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="1e9a0-143">在整合程序中包含的所有實體，都會被定義隱式關聯。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="1e9a0-144">移除任何已發現的重複關聯。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="1e9a0-145">移除重複的關聯之後，請再次嘗試設定 Power BI連接器。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="1e9a0-146">環境現在應該可以使用了。</span><span class="sxs-lookup"><span data-stu-id="1e9a0-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

