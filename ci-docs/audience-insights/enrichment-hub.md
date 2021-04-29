---
title: 富集統一的客戶設定檔
description: 使用功能富集您的客戶資料。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895995"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="2f854-103">客戶設定檔擴充 (預覽)</span><span class="sxs-lookup"><span data-stu-id="2f854-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="2f854-104">使用 Microsoft 和其他合作夥伴等來源的資料來擴充您的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="2f854-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="擴充中心頁面":::

<span data-ttu-id="2f854-106">請在對象見解中，前往 **資料** > **富集** 搭配富集選項處理。</span><span class="sxs-lookup"><span data-stu-id="2f854-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="2f854-107">您必須有參與者或系統管理員權限，才能建立或編輯擴充內容。</span><span class="sxs-lookup"><span data-stu-id="2f854-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="2f854-108">如需詳細資訊，請參閱[權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="2f854-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="2f854-109">在 **探索** 索引標籤上，您可找到下列擴充內容：</span><span class="sxs-lookup"><span data-stu-id="2f854-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="2f854-110">[Brands](enrichment-microsoft.md) 由 Microsoft 提供</span><span class="sxs-lookup"><span data-stu-id="2f854-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="2f854-111">[Interests](enrichment-microsoft.md) 由 Microsoft 提供</span><span class="sxs-lookup"><span data-stu-id="2f854-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="2f854-112">Leadspace 提供的 [公司資料](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="2f854-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="2f854-113">Experian 所提供的[人口統計資料](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="2f854-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="2f854-114">HERE Technologies 提供的 [位置資料](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="2f854-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="2f854-115">透過安全檔案傳輸通訊協定 (SFTP) 的 [自訂資料](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="2f854-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="2f854-116">在 **我的擴充內容** 索引標籤上，您可以查看您已設定的擴充內容，並編輯其屬性。</span><span class="sxs-lookup"><span data-stu-id="2f854-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="2f854-117">管理現有的擴充內容</span><span class="sxs-lookup"><span data-stu-id="2f854-117">Manage existing enrichments</span></span>

<span data-ttu-id="2f854-118">移至 **我的擴充內容** 以查看所有已設定的擴充內容。</span><span class="sxs-lookup"><span data-stu-id="2f854-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="2f854-119">每個擴充內容都表示為一列，其中包含有關擴充內容的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="2f854-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="2f854-120">選取擴充內容以查看可用的選項。</span><span class="sxs-lookup"><span data-stu-id="2f854-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="2f854-121">您也可以選取清單上專案的省略號 (...) 來查看選項。</span><span class="sxs-lookup"><span data-stu-id="2f854-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="用來管理擴充清單中擴充內容的選項":::

- <span data-ttu-id="2f854-123">**檢視** 包含擴充客戶設定檔數目的擴充內容詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2f854-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="2f854-124">**編輯** 擴充內容設定。</span><span class="sxs-lookup"><span data-stu-id="2f854-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="2f854-125">**執行** 擴充以使用最新資料更新客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="2f854-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="2f854-126">**停用** 現有擴充內容，使其不再隨每次排定的重新整理自動進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="2f854-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="2f854-127">上次成功重新整理的資料仍可繼續使用。</span><span class="sxs-lookup"><span data-stu-id="2f854-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="2f854-128">**啟用** 非使用中擴充內容，以重新開始隨每次排定的重新整理進行自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="2f854-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="2f854-129">**刪除** 富集。</span><span class="sxs-lookup"><span data-stu-id="2f854-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="2f854-130">您可以選取清單中的擴充內容，一次執行或停用多項擴充。</span><span class="sxs-lookup"><span data-stu-id="2f854-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="2f854-131">檢視和編輯選項無法用來執行大量動作，僅適用於一次執行一項擴充。</span><span class="sxs-lookup"><span data-stu-id="2f854-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="2f854-132">擴充與連接</span><span class="sxs-lookup"><span data-stu-id="2f854-132">Enrichments and connections</span></span>

<span data-ttu-id="2f854-133">協力廠商擴充設定為要使用[連接](connections.md)，連結由系統管理員設定認證，並同意資料傳輸。</span><span class="sxs-lookup"><span data-stu-id="2f854-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="2f854-134">系統管理員和參與者都可以使用這些連接設定擴充。</span><span class="sxs-lookup"><span data-stu-id="2f854-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="2f854-135">多個相同類型的擴充</span><span class="sxs-lookup"><span data-stu-id="2f854-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="2f854-136">在擴充設定期間，會指定要擴充的實體，這可讓您擴充個人資料的子集。</span><span class="sxs-lookup"><span data-stu-id="2f854-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="2f854-137">例如，只擴充特定客戶細分的資料。</span><span class="sxs-lookup"><span data-stu-id="2f854-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="2f854-138">您可以設定數個相同類型的擴充，並重複使用相同的連接。</span><span class="sxs-lookup"><span data-stu-id="2f854-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="2f854-139">某些擴充將限制相同類型的擴充可建立的數量。</span><span class="sxs-lookup"><span data-stu-id="2f854-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="2f854-140">在 **擴充** 頁面上可以看到限制和目前使用的值 。</span><span class="sxs-lookup"><span data-stu-id="2f854-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
