---
title: 以協力廠商 HERE Technologies 擴充進行擴充
description: 有關 HERE Technologies 協力廠商富集作用的一般資訊。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305284"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="b6f60-103">HERE Technologies 客戶設定檔的富集作用 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="b6f60-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="b6f60-104">HERE Technologies 是一間位置平台公司，提供以位置為中心的資料和服務。</span><span class="sxs-lookup"><span data-stu-id="b6f60-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="b6f60-105">您可以使用 HERE Technologies 的資料富集服務建立對您客戶位址正規化、緯度和經度擷取等更精確的位置瞭解。</span><span class="sxs-lookup"><span data-stu-id="b6f60-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b6f60-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="b6f60-106">Prerequisites</span></span>

<span data-ttu-id="b6f60-107">若要組態 HERE Technologies 富集作用，必須符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="b6f60-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b6f60-108">您已具備有效的 HERE Technologies 訂閱。</span><span class="sxs-lookup"><span data-stu-id="b6f60-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="b6f60-109">若要訂閱，您可以[在這裡註冊](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) 或直接 [聯絡 HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)。</span><span class="sxs-lookup"><span data-stu-id="b6f60-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="b6f60-110">深入瞭解 HERE Technologies 的 Location Enrichment。</span><span class="sxs-lookup"><span data-stu-id="b6f60-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="b6f60-111">有可用的 HERE 的 [連接](connections.md)*或*，或者您有[系統管理員](permissions.md#administrator)權限和 HERE Technologies API 金鑰。</span><span class="sxs-lookup"><span data-stu-id="b6f60-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="b6f60-112">擴充設定</span><span class="sxs-lookup"><span data-stu-id="b6f60-112">Configure the enrichment</span></span>

1. <span data-ttu-id="b6f60-113">移至 **資料** > **擴充**。</span><span class="sxs-lookup"><span data-stu-id="b6f60-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="b6f60-114">在 HERE Technologies 圖格上選取 **擴充我的資料**，然後選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="b6f60-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b6f60-115">![HERE Technologies 圖格](media/HERE-tile.png "HERE Technologies 圖格")</span><span class="sxs-lookup"><span data-stu-id="b6f60-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="b6f60-116">從下拉式清單選取一個[連結](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="b6f60-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="b6f60-117">如果沒有可用的連接，請與系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="b6f60-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="b6f60-118">如果您是系統管理員，則可以選取 **新增連接** 來建立連接。</span><span class="sxs-lookup"><span data-stu-id="b6f60-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="b6f60-119">從下拉式清單中選擇 **HERE Technologies**。</span><span class="sxs-lookup"><span data-stu-id="b6f60-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="b6f60-120">選取 **連接至 HERE Technologies** 以確認選取連接。</span><span class="sxs-lookup"><span data-stu-id="b6f60-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="b6f60-121">選取 **下一步**，然後選擇想要用 HERE Technologies 的位置資料擴充的 **客戶資料集**。</span><span class="sxs-lookup"><span data-stu-id="b6f60-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="b6f60-122">您可以選取 **客戶** 實體來擴充所有的客戶設定檔，或選取客戶細分實體僅擴充位於該客戶細分的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="b6f60-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. <span data-ttu-id="b6f60-124">選取是否要將欄位對應到主要和/或次要位址。</span><span class="sxs-lookup"><span data-stu-id="b6f60-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="b6f60-125">您可以分別指定欄位對應到兩個地址並且指定擴充個人資料給兩個地址。</span><span class="sxs-lookup"><span data-stu-id="b6f60-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="b6f60-126">例如，如果有家庭和商務地址。</span><span class="sxs-lookup"><span data-stu-id="b6f60-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="b6f60-127">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="b6f60-127">Select **Next**.</span></span>

1. <span data-ttu-id="b6f60-128">定義應使用您的哪些統一設定檔欄位，以尋找符合 HERE Technologies 的位置資料。</span><span class="sxs-lookup"><span data-stu-id="b6f60-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="b6f60-129">**街道 1** 和 **郵遞區號** 欄位是選取的主要和/或次要位址的必要欄位。</span><span class="sxs-lookup"><span data-stu-id="b6f60-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="b6f60-130">為了更高的符合準確性，可以新增更多欄位。</span><span class="sxs-lookup"><span data-stu-id="b6f60-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b6f60-131">![HERE Technologies 富集組態頁面](media/enrichment-HERE-configuration.png "HERE Technologies 富集組態頁面")</span><span class="sxs-lookup"><span data-stu-id="b6f60-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="b6f60-132">請選取 **下一步**，完成欄位對應。</span><span class="sxs-lookup"><span data-stu-id="b6f60-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="b6f60-133">提供擴充的名稱。</span><span class="sxs-lookup"><span data-stu-id="b6f60-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="b6f60-134">檢閱選擇之後，請選取 **儲存擴充**。</span><span class="sxs-lookup"><span data-stu-id="b6f60-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="b6f60-135">設定 HERE Technologies 的連接</span><span class="sxs-lookup"><span data-stu-id="b6f60-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="b6f60-136">您必須是系統管理員才能設定連接。</span><span class="sxs-lookup"><span data-stu-id="b6f60-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="b6f60-137">在設定擴充時，請選取 \**新增連接\*\*\*或* 在 HERE Technologies 圖格上移至 **管理** > **連接** 並選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="b6f60-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="b6f60-138">在 **顯示名稱** 方塊中輸入連接的名稱。</span><span class="sxs-lookup"><span data-stu-id="b6f60-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="b6f60-139">提供有效的 HERE Technologies API 金鑰。</span><span class="sxs-lookup"><span data-stu-id="b6f60-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="b6f60-140">檢閱並選取 **我同意**，提供您的 **資料隱私權和合規性** 許可。</span><span class="sxs-lookup"><span data-stu-id="b6f60-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="b6f60-141">選取 **驗證** 來驗證設定。</span><span class="sxs-lookup"><span data-stu-id="b6f60-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="b6f60-142">完成驗證之後，請選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="b6f60-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b6f60-143">![HERE technologies 的連接設定頁面](media/enrichment-HERE-connection.png "HERE technologies 的連接設定頁面")</span><span class="sxs-lookup"><span data-stu-id="b6f60-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b6f60-144">擴充結果</span><span class="sxs-lookup"><span data-stu-id="b6f60-144">Enrichment results</span></span>

<span data-ttu-id="b6f60-145">若要開始擴充程序，請從命令列中選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="b6f60-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b6f60-146">您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。</span><span class="sxs-lookup"><span data-stu-id="b6f60-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b6f60-147">處理時間將視您的客戶資料大小和 HERE Technologies 的 API 回應時間而定。</span><span class="sxs-lookup"><span data-stu-id="b6f60-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="b6f60-148">擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。</span><span class="sxs-lookup"><span data-stu-id="b6f60-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="b6f60-149">此外，您還會找到上次更新時間以及已擴充的設定檔數目。</span><span class="sxs-lookup"><span data-stu-id="b6f60-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b6f60-150">您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。</span><span class="sxs-lookup"><span data-stu-id="b6f60-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b6f60-151">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b6f60-151">Next steps</span></span>

<span data-ttu-id="b6f60-152">建立在您擴充的客戶資料之上。</span><span class="sxs-lookup"><span data-stu-id="b6f60-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b6f60-153">建立[客戶細分](segments.md)和 [量值 ](measures.md)，甚至 [匯出資料](export-destinations.md)，為您的客戶提供個人化的體驗。</span><span class="sxs-lookup"><span data-stu-id="b6f60-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b6f60-154">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="b6f60-154">Data privacy and compliance</span></span>

<span data-ttu-id="b6f60-155">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 HERE Technologies 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="b6f60-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b6f60-156">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 HERE Technologies 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="b6f60-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b6f60-157">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="b6f60-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b6f60-158">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此擴充，不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b6f60-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
