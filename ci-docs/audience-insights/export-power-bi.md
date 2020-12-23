---
title: Power BI 連接器
description: 了解如何在 Power BI 中使用 Dynamics 365 Customer Insights 連接器。
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405242"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="7b432-103">適用於 Power BI 的連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="7b432-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="7b432-104">使用 Power BI Desktop 為您的資料建立視覺效果。</span><span class="sxs-lookup"><span data-stu-id="7b432-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="7b432-105">利用您的統整客戶資料建立其他見解並建立報表。</span><span class="sxs-lookup"><span data-stu-id="7b432-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7b432-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="7b432-106">Prerequisites</span></span>

- <span data-ttu-id="7b432-107">您具有統一的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="7b432-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="7b432-108">最新版本的 [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) 已安裝在您的電腦上。</span><span class="sxs-lookup"><span data-stu-id="7b432-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="7b432-109">[進一步了解 Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)。</span><span class="sxs-lookup"><span data-stu-id="7b432-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="7b432-110">設定 Power BI 的連接器</span><span class="sxs-lookup"><span data-stu-id="7b432-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="7b432-111">在 Power BI Desktop 中，選取 **檔案** > **取得資料**。</span><span class="sxs-lookup"><span data-stu-id="7b432-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="7b432-112">選取 **顯示較多資訊** 並搜尋 **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="7b432-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="7b432-113">選取結果並選取 **關係**。</span><span class="sxs-lookup"><span data-stu-id="7b432-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="7b432-114">使用與用於 Customer Insights 相同的組織帳戶 **登入**，並選取 **關係**。</span><span class="sxs-lookup"><span data-stu-id="7b432-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="7b432-115">您在此步驟中指出的帳戶，是用來從 Customer Insights 擷取資料，並不需要與您登入 Power BI 所用的帳戶相同。</span><span class="sxs-lookup"><span data-stu-id="7b432-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="7b432-116">若要重設用於資料取得的帳戶，請打開 Power BI 並前往 **檔案** > **選項** > **設定** > **資料來源設定**。</span><span class="sxs-lookup"><span data-stu-id="7b432-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="7b432-117">在資料來源清單中，選取 **Dynamics 365 Customer Insights 登入**，並選取 **清除權限**。</span><span class="sxs-lookup"><span data-stu-id="7b432-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="7b432-118">在 **導覽器** 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="7b432-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="7b432-119">您會看到所有您有存取權的環境清單。</span><span class="sxs-lookup"><span data-stu-id="7b432-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="7b432-120">展開環境並打開任何資料夾 (實體、量值、區段、富集群)。</span><span class="sxs-lookup"><span data-stu-id="7b432-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="7b432-121">例如，開啟 **實體** 資料夾以查看所有您可匯入的實體。</span><span class="sxs-lookup"><span data-stu-id="7b432-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="7b432-122">![Power BI 連接器導覽器](media/power-bi-navigator.png "Power BI 連接器導覽器")</span><span class="sxs-lookup"><span data-stu-id="7b432-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="7b432-123">選取要包含的實體旁邊的核取方塊並 **載入**。</span><span class="sxs-lookup"><span data-stu-id="7b432-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="7b432-124">您可以從多個環境選取多個實體。</span><span class="sxs-lookup"><span data-stu-id="7b432-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="7b432-125">載入實體時，您會看到載入對話方塊。</span><span class="sxs-lookup"><span data-stu-id="7b432-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="7b432-126">一旦已經載入所有選取的實體之後，您就可以使用 Power BI 的功能視覺化資料。</span><span class="sxs-lookup"><span data-stu-id="7b432-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="7b432-127">大型資料集</span><span class="sxs-lookup"><span data-stu-id="7b432-127">Large data sets</span></span>

<span data-ttu-id="7b432-128">Power BI 的 Customer Insights 連接器是設計來處理包含多達 1 百萬個客戶設定檔的資料集。</span><span class="sxs-lookup"><span data-stu-id="7b432-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="7b432-129">匯入較大型資料集或許可行，但需要花費很長時間。</span><span class="sxs-lookup"><span data-stu-id="7b432-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="7b432-130">此外，程序可能會因為 Power BI 的限制而發生逾時。</span><span class="sxs-lookup"><span data-stu-id="7b432-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="7b432-131">如需詳細資訊，請參閱 [Power BI：對處理大型資料集的建議](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets)。</span><span class="sxs-lookup"><span data-stu-id="7b432-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="7b432-132">使用資料的子集</span><span class="sxs-lookup"><span data-stu-id="7b432-132">Work with a subset of data</span></span>

<span data-ttu-id="7b432-133">考慮搭配您的資料子集合處理。</span><span class="sxs-lookup"><span data-stu-id="7b432-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="7b432-134">例如您可以建立 [區段](segments.md) 而不是將所有客戶記錄匯出到 Power BI。</span><span class="sxs-lookup"><span data-stu-id="7b432-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
