---
title: 富集統一的客戶設定檔
description: 使用功能富集您的客戶資料。
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667084"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="f8814-103">客戶設定檔擴充 (預覽)</span><span class="sxs-lookup"><span data-stu-id="f8814-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="f8814-104">使用 Microsoft 和其他合作夥伴等來源的資料來擴充您的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="f8814-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="擴充中心頁面":::

<span data-ttu-id="f8814-106">請在對象見解中，前往 **資料** > **富集** 搭配富集選項處理。</span><span class="sxs-lookup"><span data-stu-id="f8814-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="f8814-107">您必須有參與者或系統管理員權限，才能建立或編輯擴充內容。</span><span class="sxs-lookup"><span data-stu-id="f8814-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="f8814-108">如需詳細資訊，請參閱[權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f8814-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="f8814-109">在 **探索** 索引標籤上，您可找到下列擴充內容：</span><span class="sxs-lookup"><span data-stu-id="f8814-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="f8814-110">Microsoft Graph 所提供的[品牌](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="f8814-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="f8814-111">Microsoft Graph 所提供的[興趣](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="f8814-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="f8814-112">Leadspace 提供的 [公司資料](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="f8814-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="f8814-113">Experian 所提供的[人口統計資料](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="f8814-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="f8814-114">HERE Technologies 提供的 [位置資料](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="f8814-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="f8814-115">透過安全檔案傳輸通訊協定 (SFTP) 的 [自訂資料](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="f8814-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="f8814-116">在 **我的擴充內容** 索引標籤上，您可以查看您已設定的擴充內容，並編輯其屬性。</span><span class="sxs-lookup"><span data-stu-id="f8814-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="f8814-117">管理現有的擴充內容</span><span class="sxs-lookup"><span data-stu-id="f8814-117">Manage existing enrichments</span></span>

<span data-ttu-id="f8814-118">移至 **我的擴充內容** 以查看所有已設定的擴充內容。</span><span class="sxs-lookup"><span data-stu-id="f8814-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="f8814-119">每個擴充內容都表示為一列，其中包含有關擴充內容的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="f8814-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="f8814-120">選取擴充內容以查看可用的選項。</span><span class="sxs-lookup"><span data-stu-id="f8814-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="f8814-121">或者，也可以選取清單項目上的省略符號 (...) 來查看選項。</span><span class="sxs-lookup"><span data-stu-id="f8814-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="用來管理擴充清單中擴充內容的選項":::

- <span data-ttu-id="f8814-123">**檢視** 包含擴充客戶設定檔數目的擴充內容詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f8814-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="f8814-124">**編輯** 擴充內容設定。</span><span class="sxs-lookup"><span data-stu-id="f8814-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="f8814-125">**執行** 擴充以使用最新資料更新客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="f8814-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="f8814-126">**停用** 現有擴充內容，使其不再隨每次排定的重新整理自動進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="f8814-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="f8814-127">上次成功重新整理的資料仍可繼續使用。</span><span class="sxs-lookup"><span data-stu-id="f8814-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="f8814-128">**啟用** 非使用中擴充內容，以重新開始隨每次排定的重新整理進行自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="f8814-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="f8814-129">**刪除** 富集。</span><span class="sxs-lookup"><span data-stu-id="f8814-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="f8814-130">您可以選取清單中的擴充內容，一次執行或停用多項擴充。</span><span class="sxs-lookup"><span data-stu-id="f8814-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="f8814-131">檢視和編輯選項無法用來執行大量動作，僅適用於一次執行一項擴充。</span><span class="sxs-lookup"><span data-stu-id="f8814-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
