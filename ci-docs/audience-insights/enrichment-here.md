---
title: 藉助協力廠商 HERE Technologies 的富集作用
description: 有關 HERE Technologies 協力廠商富集作用的一般資訊。
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269504"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="d6af4-103">HERE Technologies 客戶設定檔的富集作用 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="d6af4-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="d6af4-104">HERE Technologies 是一間位置平台公司，提供以位置為中心的資料和服務。</span><span class="sxs-lookup"><span data-stu-id="d6af4-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="d6af4-105">您可以使用 HERE Technologies 的資料富集服務建立對您客戶位址正規化、緯度和經度擷取等更精確的位置瞭解。</span><span class="sxs-lookup"><span data-stu-id="d6af4-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6af4-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="d6af4-106">Prerequisites</span></span>

<span data-ttu-id="d6af4-107">若要組態 HERE Technologies 富集作用，必須符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="d6af4-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d6af4-108">您已具備有效的 HERE Technologies 訂閱。</span><span class="sxs-lookup"><span data-stu-id="d6af4-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="d6af4-109">若要訂閱，您可以 [在這裡註冊](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) 或直接 [聯絡 HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)。</span><span class="sxs-lookup"><span data-stu-id="d6af4-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="d6af4-110">深入瞭解 HERE Technologies 的 Location Enrichment。</span><span class="sxs-lookup"><span data-stu-id="d6af4-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="d6af4-111">您擁有 HERE Technologies API 金鑰。</span><span class="sxs-lookup"><span data-stu-id="d6af4-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="d6af4-112">您擁有 [系統管理員](permissions.md#administrator) 權限。</span><span class="sxs-lookup"><span data-stu-id="d6af4-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="d6af4-113">組態</span><span class="sxs-lookup"><span data-stu-id="d6af4-113">Configuration</span></span>

1. <span data-ttu-id="d6af4-114">移至 **資料** > **擴充**。</span><span class="sxs-lookup"><span data-stu-id="d6af4-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="d6af4-115">請在 HERE Technologies 圖格上選取 **富集我的資料**。</span><span class="sxs-lookup"><span data-stu-id="d6af4-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6af4-116">![HERE Technologies 圖格](media/HERE-tile.png "HERE Technologies 圖格")</span><span class="sxs-lookup"><span data-stu-id="d6af4-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="d6af4-117">輸入有效的 **HERE Technologies API 金鑰**。</span><span class="sxs-lookup"><span data-stu-id="d6af4-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="d6af4-118">選取 **我同意** 核取方塊，以檢閱 **資料隱私權和合規性** 並表示同意。</span><span class="sxs-lookup"><span data-stu-id="d6af4-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="d6af4-119">選取 **連接到 HERE** 確認這兩項輸入資料。</span><span class="sxs-lookup"><span data-stu-id="d6af4-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="d6af4-120">選取 **新增資料**，然後選擇要用 HERE Technologies 中的位置資料擴充的 **客戶資料集**。</span><span class="sxs-lookup"><span data-stu-id="d6af4-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="d6af4-121">您可以選取 **客戶** 實體來擴充所有的客戶設定檔，或選取客戶細分實體僅擴充位於該客戶細分的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="d6af4-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. <span data-ttu-id="d6af4-123">選取是否要將欄位對應到主要和/或次要位址。</span><span class="sxs-lookup"><span data-stu-id="d6af4-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="d6af4-124">您可以為兩個位址指定欄位對應 (例如住宅和公司位址)，然後分別富集兩個位址的設定檔。</span><span class="sxs-lookup"><span data-stu-id="d6af4-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="d6af4-125">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="d6af4-125">Select **Next**.</span></span>

1. <span data-ttu-id="d6af4-126">定義應使用您的哪些統一設定檔欄位，以尋找符合 HERE Technologies 的位置資料。</span><span class="sxs-lookup"><span data-stu-id="d6af4-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="d6af4-127">**街道 1** 和 **郵遞區號** 欄位是選取的主要和/或次要位址的必要欄位。</span><span class="sxs-lookup"><span data-stu-id="d6af4-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="d6af4-128">為了更高的符合準確性，可以新增更多欄位。</span><span class="sxs-lookup"><span data-stu-id="d6af4-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6af4-129">![HERE Technologies 富集組態頁面](media/enrichment-HERE-configuration.png "HERE Technologies 富集組態頁面")</span><span class="sxs-lookup"><span data-stu-id="d6af4-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="d6af4-130">選取 **套用** 完成欄位對應。</span><span class="sxs-lookup"><span data-stu-id="d6af4-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="d6af4-131">擴充結果</span><span class="sxs-lookup"><span data-stu-id="d6af4-131">Enrichment results</span></span>

<span data-ttu-id="d6af4-132">若要開始擴充程序，請從命令列中選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="d6af4-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="d6af4-133">您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。</span><span class="sxs-lookup"><span data-stu-id="d6af4-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d6af4-134">處理時間將視您的客戶資料大小和 HERE Technologies 的 API 回應時間而定。</span><span class="sxs-lookup"><span data-stu-id="d6af4-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="d6af4-135">擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。</span><span class="sxs-lookup"><span data-stu-id="d6af4-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="d6af4-136">此外，您還會找到上次更新時間以及已擴充的設定檔數目。</span><span class="sxs-lookup"><span data-stu-id="d6af4-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d6af4-137">您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。</span><span class="sxs-lookup"><span data-stu-id="d6af4-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d6af4-138">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d6af4-138">Next steps</span></span>

<span data-ttu-id="d6af4-139">建立在您擴充的客戶資料之上。</span><span class="sxs-lookup"><span data-stu-id="d6af4-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d6af4-140">建立[客戶細分](segments.md)、[量值](measures.md)，甚至[匯出資料](export-destinations.md)，以便傳送個人化體驗給您的客戶。</span><span class="sxs-lookup"><span data-stu-id="d6af4-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d6af4-141">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="d6af4-141">Data privacy and compliance</span></span>

<span data-ttu-id="d6af4-142">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 HERE Technologies 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="d6af4-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d6af4-143">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 HERE Technologies 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="d6af4-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d6af4-144">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="d6af4-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d6af4-145">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此富集作用，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="d6af4-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]