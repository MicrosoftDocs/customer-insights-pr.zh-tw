---
title: 匯出目的地
description: 匯出資料和管理匯出目的地。
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643853"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="12ca0-103">匯出目的地 (預覽)</span><span class="sxs-lookup"><span data-stu-id="12ca0-103">Export destinations (preview)</span></span>

<span data-ttu-id="12ca0-104">**匯出目的地** 頁面會顯示所有您已設定要匯出到的位置。</span><span class="sxs-lookup"><span data-stu-id="12ca0-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="12ca0-105">您也可以加入新的匯出目的地。</span><span class="sxs-lookup"><span data-stu-id="12ca0-105">You can also add new destinations for export.</span></span> <span data-ttu-id="12ca0-106">此外它顯示匯出目前可用的選項。</span><span class="sxs-lookup"><span data-stu-id="12ca0-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="12ca0-107">取得快速概觀、描述，並了解每個擴充性選項可用來執行的工作。</span><span class="sxs-lookup"><span data-stu-id="12ca0-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="12ca0-108">將統一的設定檔、量值及區段匯出至與您的業務相關的支援應用程式。</span><span class="sxs-lookup"><span data-stu-id="12ca0-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="12ca0-109">移至 **管理** > **匯出目的地**，尋找下列擴充性選項：</span><span class="sxs-lookup"><span data-stu-id="12ca0-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="12ca0-110">Dynamics 365 Customer 卡片增益集</span><span class="sxs-lookup"><span data-stu-id="12ca0-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="12ca0-111">Facebook 廣告管理員連接器</span><span class="sxs-lookup"><span data-stu-id="12ca0-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="12ca0-112">Power Automate 連接器</span><span class="sxs-lookup"><span data-stu-id="12ca0-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="12ca0-113">Power Apps 連接器</span><span class="sxs-lookup"><span data-stu-id="12ca0-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="12ca0-114">Power BI 連接器</span><span class="sxs-lookup"><span data-stu-id="12ca0-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="12ca0-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="12ca0-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="12ca0-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="12ca0-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="12ca0-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="12ca0-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="12ca0-118">Azure Blob 儲存體</span><span class="sxs-lookup"><span data-stu-id="12ca0-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="12ca0-119">LiveRamp &reg; 連接器</span><span class="sxs-lookup"><span data-stu-id="12ca0-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="12ca0-120">Microsoft Teams 的機器人</span><span class="sxs-lookup"><span data-stu-id="12ca0-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="12ca0-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="12ca0-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="12ca0-122">Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="12ca0-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="12ca0-123">新增匯出目的地</span><span class="sxs-lookup"><span data-stu-id="12ca0-123">Add a new export destination</span></span>

<span data-ttu-id="12ca0-124">若要新增匯出目的地，您具有 [系統管理員權限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="12ca0-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="12ca0-125">如果您匯出至 Microsoft 服務，我們會假設這兩個服務都位於相同的組織中。</span><span class="sxs-lookup"><span data-stu-id="12ca0-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="12ca0-126">移至 **管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="12ca0-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="12ca0-127">切換至 **我的匯出目的地** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="12ca0-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="12ca0-128">選取 **新增目的地** 以建立新的匯出目的地。</span><span class="sxs-lookup"><span data-stu-id="12ca0-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="12ca0-129">在 **新增目的地** 窗格中，從下拉式清單選取匯出目的地的 **類型**。</span><span class="sxs-lookup"><span data-stu-id="12ca0-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="12ca0-130">提供必要詳細資料，並選取 **下一步** 以建立匯出目的地。</span><span class="sxs-lookup"><span data-stu-id="12ca0-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="12ca0-131">您也可以在 **探索** 索引標籤中選取圖標上的 **設定**。</span><span class="sxs-lookup"><span data-stu-id="12ca0-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="12ca0-132">檢視匯出目的地</span><span class="sxs-lookup"><span data-stu-id="12ca0-132">View Export destinations</span></span>

<span data-ttu-id="12ca0-133">建立匯出目的地之後，您會在 **我的匯出目的地** 索引標籤的表格中找到這些目的地。此表格有三個欄：</span><span class="sxs-lookup"><span data-stu-id="12ca0-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="12ca0-134">**顯示名稱**：建立目的地時輸入的名稱。</span><span class="sxs-lookup"><span data-stu-id="12ca0-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="12ca0-135">**類型**：建立目的地時所設定的匯出目的地類型。</span><span class="sxs-lookup"><span data-stu-id="12ca0-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="12ca0-136">**建立日期**：目的地建立日期。</span><span class="sxs-lookup"><span data-stu-id="12ca0-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="12ca0-137">編輯匯出目的地</span><span class="sxs-lookup"><span data-stu-id="12ca0-137">Edit an export destination</span></span>

1. <span data-ttu-id="12ca0-138">選取所要編輯之匯出目的地的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="12ca0-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="12ca0-139">![垂直省略符號](media/export-destinations-page-ellipsis.png "垂直省略符號")</span><span class="sxs-lookup"><span data-stu-id="12ca0-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="12ca0-140">從下拉式功能表中選取 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="12ca0-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="12ca0-141">變更需要更新的值，然後選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="12ca0-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="12ca0-142">視需要匯出資料</span><span class="sxs-lookup"><span data-stu-id="12ca0-142">Export data on demand</span></span>

<span data-ttu-id="12ca0-143">為匯出目的地設定連接器之後，匯出將會隨每個[排定的重新整理](system.md#schedule-tab)執行。</span><span class="sxs-lookup"><span data-stu-id="12ca0-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="12ca0-144">若要匯出資料，而不等待排定的重新整理，請在 **管理** > **匯出目的地** 上移至 **我的匯出目的地** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="12ca0-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="12ca0-145">![垂直省略符號](media/export-destinations-page-ellipsis.png "垂直省略符號")</span><span class="sxs-lookup"><span data-stu-id="12ca0-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="12ca0-146">選取清單上方的 **匯出**，同時執行對所有匯出目的地的匯出。</span><span class="sxs-lookup"><span data-stu-id="12ca0-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="12ca0-147">選取清單項目後的省略符號 (...)，然後選擇 **匯出** 選項，針對單一匯出目的地執行匯出。</span><span class="sxs-lookup"><span data-stu-id="12ca0-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="12ca0-148">移除匯出目的地</span><span class="sxs-lookup"><span data-stu-id="12ca0-148">Remove an Export destination</span></span>

<span data-ttu-id="12ca0-149">若要移除匯出目的地，請從主要 **匯出目的地** 頁面開始。</span><span class="sxs-lookup"><span data-stu-id="12ca0-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="12ca0-150">選取要移除之匯出目的地的垂直省略符號。</span><span class="sxs-lookup"><span data-stu-id="12ca0-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="12ca0-151">![垂直省略符號](media/export-destinations-page-ellipsis.png "垂直省略符號")</span><span class="sxs-lookup"><span data-stu-id="12ca0-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="12ca0-152">從下拉式功能表中選取 **移除**。</span><span class="sxs-lookup"><span data-stu-id="12ca0-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="12ca0-153">在確認畫面上選取 **移除** 以確認移除。</span><span class="sxs-lookup"><span data-stu-id="12ca0-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
