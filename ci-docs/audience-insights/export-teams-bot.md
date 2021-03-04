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
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267942"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="d0192-103">Dynamics 365 Customer Insights 團隊機器人 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="d0192-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="d0192-104">連接 Microsoft Teams 讓機器人查閱 Teams 通道中的統一客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="d0192-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d0192-105">![顯示客戶記錄的 Teams 機器人](media/teams-bot.png "顯示客戶記錄的 Teams 機器人")</span><span class="sxs-lookup"><span data-stu-id="d0192-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0192-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="d0192-106">Prerequisites</span></span>

<span data-ttu-id="d0192-107">若要安裝並設定機器人，必須符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="d0192-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d0192-108">至少有一個[新增的資料來源 ](data-sources.md)。</span><span class="sxs-lookup"><span data-stu-id="d0192-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="d0192-109">[統一程序](data-unification.md)已完成。</span><span class="sxs-lookup"><span data-stu-id="d0192-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="d0192-110">欄位已新增至[搜尋和篩選索引](search-filter-index.md)。</span><span class="sxs-lookup"><span data-stu-id="d0192-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="d0192-111">Customer Insights 和 Teams 位於相同的組織中。</span><span class="sxs-lookup"><span data-stu-id="d0192-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="d0192-112">設定機器人</span><span class="sxs-lookup"><span data-stu-id="d0192-112">Configure the bot</span></span>

1. <span data-ttu-id="d0192-113">在對象見解中，前往 **系統管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="d0192-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="d0192-114">在 Microsoft Teams 圖標中，選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="d0192-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="d0192-115">系統會將您重新導向至 Teams 中的 **應用程式** 區域。</span><span class="sxs-lookup"><span data-stu-id="d0192-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="d0192-116">您也可以開啟 Teams 並選取左下角的 **應用程式**，或是直接[從 AppSource 中取得](https://go.microsoft.com/fwlink/?linkid=2124104)。</span><span class="sxs-lookup"><span data-stu-id="d0192-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="d0192-117">搜尋 **Customer Insights** 並選取此應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0192-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="d0192-118">選取 **新增**。</span><span class="sxs-lookup"><span data-stu-id="d0192-118">Select **Add**.</span></span>
1. <span data-ttu-id="d0192-119">在 Teams 中登入 Customer Insights 之後，您會看到歡迎訊息，並且可以開始使用。</span><span class="sxs-lookup"><span data-stu-id="d0192-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="d0192-120">您可以使用機器人執行的作業</span><span class="sxs-lookup"><span data-stu-id="d0192-120">Things you can do with the bot</span></span>

<span data-ttu-id="d0192-121">機器人提供對統一客戶設定檔的查詢功能。</span><span class="sxs-lookup"><span data-stu-id="d0192-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="d0192-122">輸入 **搜尋** 並在後面接著名稱、電子郵件地址，或任何其他在新增至搜尋及篩選索引之統一客戶設定檔中的欄位。</span><span class="sxs-lookup"><span data-stu-id="d0192-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="d0192-123">您會從產生的客戶設定檔中取得最多 15 個欄位。</span><span class="sxs-lookup"><span data-stu-id="d0192-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="d0192-124">有多個相符項目時，會傳回可讓您選取設定檔的結果清單。</span><span class="sxs-lookup"><span data-stu-id="d0192-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="d0192-125">您可在雙引號中加入搜尋字詞，以查詢完全相符的項目。</span><span class="sxs-lookup"><span data-stu-id="d0192-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="d0192-126">如果貴組織在同一個組織維護多個 Customer Insights 環境，您可以輸入 **switchinstance** 選擇將您要連接機器人的環境。</span><span class="sxs-lookup"><span data-stu-id="d0192-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="d0192-127">輸入 **說明**，以查看機器人的可用命令清單。</span><span class="sxs-lookup"><span data-stu-id="d0192-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]