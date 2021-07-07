---
title: 以 Experian 協力廠商擴充進行擴充
description: 關於 Experian協力廠商擴充的一般資訊。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309810"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="ae0af-103">利用 Experian 的人口統計資訊擴充客戶個人資料 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="ae0af-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="ae0af-104">Experian 是消費者和企業信用報告和行銷服務的全球領導者。</span><span class="sxs-lookup"><span data-stu-id="ae0af-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="ae0af-105">有了 Experian 資料擴充服務服務，您可以使用人口統計資料 (例如，家庭大小、收入和其他資訊) 來擴充您的客戶個人資料，以建立深入瞭解您的客戶。</span><span class="sxs-lookup"><span data-stu-id="ae0af-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ae0af-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="ae0af-106">Prerequisites</span></span>

<span data-ttu-id="ae0af-107">若要設定 Experian，必須符合以下先決條件：</span><span class="sxs-lookup"><span data-stu-id="ae0af-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ae0af-108">您必須擁有 Experian 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="ae0af-108">You have an active Experian subscription.</span></span> <span data-ttu-id="ae0af-109">若要取得訂閱，請直接[聯繫 Experian](https://www.experian.com/marketing-services/contact)。</span><span class="sxs-lookup"><span data-stu-id="ae0af-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="ae0af-110">[深入了解 Experian 資料擴充](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。</span><span class="sxs-lookup"><span data-stu-id="ae0af-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="ae0af-111">Experian 連接已由系統管理員設定，*或* 您擁有[系統管理員](permissions.md#administrator)權限。</span><span class="sxs-lookup"><span data-stu-id="ae0af-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="ae0af-112">您也需要 Experian 為您建立的支援 SSH 的安全傳輸 (ST) 帳戶的使用者識別碼、當事人識別碼和型號編號。</span><span class="sxs-lookup"><span data-stu-id="ae0af-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="ae0af-113">支援的國家/地區</span><span class="sxs-lookup"><span data-stu-id="ae0af-113">Supported countries/regions</span></span>

<span data-ttu-id="ae0af-114">目前我們僅在美國支援擴充客戶個人資料。</span><span class="sxs-lookup"><span data-stu-id="ae0af-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="ae0af-115">擴充設定</span><span class="sxs-lookup"><span data-stu-id="ae0af-115">Configure the enrichment</span></span>

1. <span data-ttu-id="ae0af-116">移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ae0af-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="ae0af-117">在 Experian 圖格上，選取 **擴充我的資料**。</span><span class="sxs-lookup"><span data-stu-id="ae0af-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ae0af-118">![Experian 圖標](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="ae0af-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="ae0af-119">從下拉式清單選取一個[連結](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0af-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="ae0af-120">如果沒有可用的連接，請與系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="ae0af-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="ae0af-121">如果您是系統管理員，則可以選取 **新增連接**，然從下拉式清單中選擇 Experian，來建立連接。</span><span class="sxs-lookup"><span data-stu-id="ae0af-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="ae0af-122">選取 **連接至 Experian** 來確認選取連接。</span><span class="sxs-lookup"><span data-stu-id="ae0af-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="ae0af-123">選取 **下一步**，然後選擇要以 Experian 人口統計資料擴充的 **客戶資料集**。</span><span class="sxs-lookup"><span data-stu-id="ae0af-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="ae0af-124">您可以選取 **客戶** 實體來擴充所有的客戶設定檔，或選取客戶細分實體僅擴充位於該客戶細分的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="ae0af-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. <span data-ttu-id="ae0af-126">選取 **下一步**，並定義應該使用的整合個人資料欄位類型，來在 Experian 中尋找符合的人口統計資料。</span><span class="sxs-lookup"><span data-stu-id="ae0af-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="ae0af-127">至少要有 **名稱和位址**、**電話** 或 **電子郵件** 中的一個欄位。</span><span class="sxs-lookup"><span data-stu-id="ae0af-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="ae0af-128">為了獲得更高的比對準確性，其他欄位最多可新增兩個。</span><span class="sxs-lookup"><span data-stu-id="ae0af-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="ae0af-129">這項選取將會影響在下一個步驟中可以存取的對應欄位。</span><span class="sxs-lookup"><span data-stu-id="ae0af-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="ae0af-130">傳送更多的金鑰識別碼屬性，Experian更容易會產生較佳的符合率。</span><span class="sxs-lookup"><span data-stu-id="ae0af-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="ae0af-131">請選取 **下一步**，開始欄位對應。</span><span class="sxs-lookup"><span data-stu-id="ae0af-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="ae0af-132">定義應該使用的整合個人資料欄位類型，來在 Experian 中尋找符合的人口統計資料。</span><span class="sxs-lookup"><span data-stu-id="ae0af-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="ae0af-133">必要欄位被標記。</span><span class="sxs-lookup"><span data-stu-id="ae0af-133">Required fields are marked.</span></span>

1. <span data-ttu-id="ae0af-134">提供擴充的名稱以及輸出實體的名稱。</span><span class="sxs-lookup"><span data-stu-id="ae0af-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="ae0af-135">檢閱選擇之後，請選取 **儲存擴充**。</span><span class="sxs-lookup"><span data-stu-id="ae0af-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="ae0af-136">設定 Experian 的連接</span><span class="sxs-lookup"><span data-stu-id="ae0af-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="ae0af-137">您必須是系統管理員才能設定連接。</span><span class="sxs-lookup"><span data-stu-id="ae0af-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="ae0af-138">在設定擴充時，請選取 **新增連接**，*或* 移至 **管理** > **連接**，並在 Experian 圖格上選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="ae0af-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="ae0af-139">選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="ae0af-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="ae0af-140">在 **顯示名稱** 方塊中輸入連接的名稱。</span><span class="sxs-lookup"><span data-stu-id="ae0af-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="ae0af-141">輸入您的 Experian 安全傳輸帳戶的有效使用者識別碼、當事人識別碼和型號編號。</span><span class="sxs-lookup"><span data-stu-id="ae0af-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="ae0af-142">檢閱並選取 **我同意**，提供您的 **資料隱私權和合規性** 許可。</span><span class="sxs-lookup"><span data-stu-id="ae0af-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="ae0af-143">選取 **驗證** 來驗證設定。</span><span class="sxs-lookup"><span data-stu-id="ae0af-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="ae0af-144">完成驗證之後，請選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="ae0af-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 連接設定窗格。":::

## <a name="enrichment-results"></a><span data-ttu-id="ae0af-146">擴充結果</span><span class="sxs-lookup"><span data-stu-id="ae0af-146">Enrichment results</span></span>

<span data-ttu-id="ae0af-147">若要開始擴充程序，請從命令列中選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="ae0af-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ae0af-148">您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。</span><span class="sxs-lookup"><span data-stu-id="ae0af-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ae0af-149">處理時間將視客戶資料大小和 Experian 為您的帳戶設定的擴充程序而定。</span><span class="sxs-lookup"><span data-stu-id="ae0af-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="ae0af-150">擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。</span><span class="sxs-lookup"><span data-stu-id="ae0af-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ae0af-151">此外，您還會找到上次更新時間以及已擴充的設定檔數目。</span><span class="sxs-lookup"><span data-stu-id="ae0af-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ae0af-152">您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。</span><span class="sxs-lookup"><span data-stu-id="ae0af-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae0af-153">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ae0af-153">Next steps</span></span>

<span data-ttu-id="ae0af-154">建立在您擴充的客戶資料之上。</span><span class="sxs-lookup"><span data-stu-id="ae0af-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ae0af-155">建立[客戶細分](segments.md)和 [量值 ](measures.md)，甚至 [匯出資料](export-destinations.md)，為您的客戶提供個人化的體驗。</span><span class="sxs-lookup"><span data-stu-id="ae0af-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ae0af-156">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="ae0af-156">Data privacy and compliance</span></span>

<span data-ttu-id="ae0af-157">當您啟用  Dynamics 365 Customer Insights 將資料傳輸到 Experian 時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在的敏感性資料 (例如個人資料)。</span><span class="sxs-lookup"><span data-stu-id="ae0af-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ae0af-158">Microsoft 將會依您的指示傳送這類資料，但是您必須負責確保 Experian 符合您可能會承擔的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="ae0af-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ae0af-159">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="ae0af-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ae0af-160">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此擴充，不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ae0af-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
