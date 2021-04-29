---
title: 藉助協力廠商 Enrichment Experian 的富集作用
description: 有關 Experian 協力廠商富集作用的一般資訊。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896363"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="4b139-103">使用 Experian 提供的人口統計資料擴充客戶設定檔 (預覽)</span><span class="sxs-lookup"><span data-stu-id="4b139-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="4b139-104">Experian 是消費者與企業信用報告以及行銷服務的全球領導者。</span><span class="sxs-lookup"><span data-stu-id="4b139-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="4b139-105">有了 Experian 的資料擴充服務，您就可以透過人口統計資料 (例如家庭人數、收入及其他) 擴充您的客戶設定檔，加深對客戶的了解。</span><span class="sxs-lookup"><span data-stu-id="4b139-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4b139-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="4b139-106">Prerequisites</span></span>

<span data-ttu-id="4b139-107">若要設定 Experian，必須符合以下先決條件：</span><span class="sxs-lookup"><span data-stu-id="4b139-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4b139-108">您擁有有效的 Experian 訂閱。</span><span class="sxs-lookup"><span data-stu-id="4b139-108">You have an active Experian subscription.</span></span> <span data-ttu-id="4b139-109">若要取得訂閱，請直接[與 Experian 連絡](https://www.experian.com/marketing-services/contact)。</span><span class="sxs-lookup"><span data-stu-id="4b139-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="4b139-110">[深入了解t Experian 資料擴充](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。</span><span class="sxs-lookup"><span data-stu-id="4b139-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="4b139-111">Experian 連接已由系統管理員設定，*或* 您擁有[系統管理員](permissions.md#administrator)權限。</span><span class="sxs-lookup"><span data-stu-id="4b139-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="4b139-112">您也需要啟用 SSH 的安全傳輸 (ST) 帳戶的使用識別碼、合作對象識別碼和模型編碼，該帳戶是由 Experian 所建立的。</span><span class="sxs-lookup"><span data-stu-id="4b139-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="4b139-113">擴充設定</span><span class="sxs-lookup"><span data-stu-id="4b139-113">Configure the enrichment</span></span>

1. <span data-ttu-id="4b139-114">移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4b139-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="4b139-115">選取 Experian 圖標上的 **擴充我的資料**。</span><span class="sxs-lookup"><span data-stu-id="4b139-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4b139-116">![Experian 圖標](media/experian-tile.png "Experian 圖標")</span><span class="sxs-lookup"><span data-stu-id="4b139-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="4b139-117">在下拉式清單中選取一個[連接](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="4b139-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="4b139-118">如果沒有可用的連接，請與系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="4b139-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="4b139-119">如果您是系統管理員，則可以選取 **新增連接**，並從下拉式清單中選擇 Experian 來建立連接。</span><span class="sxs-lookup"><span data-stu-id="4b139-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="4b139-120">選取 **連接至 Experian** 以確認選取連接。</span><span class="sxs-lookup"><span data-stu-id="4b139-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="4b139-121">選取 **下一步**，然後選擇想要用 Experian 的人口統計資料擴充的 **客戶資料集**。</span><span class="sxs-lookup"><span data-stu-id="4b139-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="4b139-122">您可以選取 **客戶** 實體來擴充所有的客戶設定檔，或選取客戶細分實體僅擴充位於該客戶細分的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="4b139-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. <span data-ttu-id="4b139-124">選取 **下一步**，接著定義在整合個人資料中的欄位類型，該類型用來在 Experian 尋找符合的人口統計資料。</span><span class="sxs-lookup"><span data-stu-id="4b139-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="4b139-125">至少要有 **名稱和位址**、**電話** 或 **電子郵件** 中的一個欄位。</span><span class="sxs-lookup"><span data-stu-id="4b139-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="4b139-126">為了獲得更高的比對準確性，其他欄位最多可新增兩個。</span><span class="sxs-lookup"><span data-stu-id="4b139-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="4b139-127">這項選取將會影響在下一個步驟中可以存取的對應欄位。</span><span class="sxs-lookup"><span data-stu-id="4b139-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="4b139-128">傳送至 Experian 的金鑰識別元屬性愈多，可能產生的適配率愈高。</span><span class="sxs-lookup"><span data-stu-id="4b139-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="4b139-129">請選取 **下一步**，開始欄位對應。</span><span class="sxs-lookup"><span data-stu-id="4b139-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="4b139-130">定義在整合個人資料中的欄位類型，該欄位用來在 Experian 尋找符合的人口統計資料。</span><span class="sxs-lookup"><span data-stu-id="4b139-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="4b139-131">必要欄位被標記。</span><span class="sxs-lookup"><span data-stu-id="4b139-131">Required fields are marked.</span></span>

1. <span data-ttu-id="4b139-132">提供擴充的名稱以及輸出實體的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b139-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="4b139-133">檢閱選擇之後，請選取 **儲存擴充**。</span><span class="sxs-lookup"><span data-stu-id="4b139-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="4b139-134">設定 Experian 的連接</span><span class="sxs-lookup"><span data-stu-id="4b139-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="4b139-135">您必須是系統管理員才能設定連接。</span><span class="sxs-lookup"><span data-stu-id="4b139-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="4b139-136">在設定擴充時，請選取 \**新增連接\*\*\*或* 在 Experian 圖格上移至 **管理** > **連接** 並選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="4b139-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="4b139-137">選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="4b139-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="4b139-138">在 **顯示名稱** 方塊中輸入連接的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b139-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="4b139-139">為您的 Experian 安全傳輸帳戶輸入有效的使用者識別碼、合作對象識別碼和模型編號。</span><span class="sxs-lookup"><span data-stu-id="4b139-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="4b139-140">檢閱 **資料隱私權和合規性** 並選取 **我同意** 的核取方塊，表示同意</span><span class="sxs-lookup"><span data-stu-id="4b139-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="4b139-141">選取 **驗證** 來驗證設定。</span><span class="sxs-lookup"><span data-stu-id="4b139-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="4b139-142">完成驗證之後，請選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="4b139-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 連接設定窗格。":::

## <a name="enrichment-results"></a><span data-ttu-id="4b139-144">擴充結果</span><span class="sxs-lookup"><span data-stu-id="4b139-144">Enrichment results</span></span>

<span data-ttu-id="4b139-145">若要開始擴充程序，請從命令列中選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="4b139-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4b139-146">您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。</span><span class="sxs-lookup"><span data-stu-id="4b139-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4b139-147">處理時間取決於客戶資料的大小以及 Experian 為您帳戶設定的擴充程序。</span><span class="sxs-lookup"><span data-stu-id="4b139-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="4b139-148">擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。</span><span class="sxs-lookup"><span data-stu-id="4b139-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="4b139-149">此外，您還會找到上次更新時間以及已擴充的設定檔數目。</span><span class="sxs-lookup"><span data-stu-id="4b139-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4b139-150">您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。</span><span class="sxs-lookup"><span data-stu-id="4b139-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4b139-151">後續步驟</span><span class="sxs-lookup"><span data-stu-id="4b139-151">Next steps</span></span>

<span data-ttu-id="4b139-152">建立在您擴充的客戶資料之上。</span><span class="sxs-lookup"><span data-stu-id="4b139-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4b139-153">建立[客戶細分](segments.md)、[量值](measures.md)，甚至[匯出資料](export-destinations.md)，以便傳送個人化體驗給您的客戶。</span><span class="sxs-lookup"><span data-stu-id="4b139-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4b139-154">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="4b139-154">Data privacy and compliance</span></span>

<span data-ttu-id="4b139-155">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Experian 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="4b139-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4b139-156">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Experian 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="4b139-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4b139-157">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="4b139-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4b139-158">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此富集作用，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="4b139-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
