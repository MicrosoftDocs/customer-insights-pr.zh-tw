---
title: 藉助協力廠商 Enrichment Experian 的富集作用
description: 有關 Experian 協力廠商富集作用的一般資訊。
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668794"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="ac6c7-103">使用 Experian 提供的人口統計資料擴充客戶設定檔 (預覽)</span><span class="sxs-lookup"><span data-stu-id="ac6c7-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="ac6c7-104">Experian 是消費者與企業信用報告以及行銷服務的全球領導者。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="ac6c7-105">有了 Experian 的資料擴充服務，您就可以透過人口統計資料 (例如家庭人數、收入及其他) 擴充您的客戶設定檔，加深對客戶的了解。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac6c7-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="ac6c7-106">Prerequisites</span></span>

<span data-ttu-id="ac6c7-107">若要設定 Experian，必須符合以下先決條件：</span><span class="sxs-lookup"><span data-stu-id="ac6c7-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ac6c7-108">您擁有有效的 Experian 訂閱。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-108">You have an active Experian subscription.</span></span> <span data-ttu-id="ac6c7-109">若要取得訂閱，請直接[與 Experian 連絡](https://www.experian.com/marketing-services/contact)。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="ac6c7-110">[深入了解t Experian 資料擴充](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="ac6c7-111">您具有 Experian 為您所建立啟用 SSH 之安全傳輸 (ST) 帳戶的使用者識別碼、當事人識別碼和模型編號。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="ac6c7-112">您在對象見解中具備 [系統管理員](permissions.md#administrator) 權限。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="ac6c7-113">組態</span><span class="sxs-lookup"><span data-stu-id="ac6c7-113">Configuration</span></span>

1. <span data-ttu-id="ac6c7-114">移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="ac6c7-115">選取 Experian 圖標上的 **擴充我的資料**。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac6c7-116">![Experian 圖標](media/experian-tile.png "Experian 圖標")</span><span class="sxs-lookup"><span data-stu-id="ac6c7-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="ac6c7-117">選取 **開始使用**，並輸入您的 Experian 安全傳輸帳戶的使用者識別碼、當事人識別碼和模型編號。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="ac6c7-118">選取 **我同意** 核取方塊，以檢閱 **資料隱私權和合規性** 並表示同意。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="ac6c7-119">選取 **套用** 以確認所有輸入。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="ac6c7-120">對應欄位</span><span class="sxs-lookup"><span data-stu-id="ac6c7-120">Map your fields</span></span>

1. <span data-ttu-id="ac6c7-121">選取 **新增資料**，然後從 **名稱和地址**、**電子郵件** 或 **電話** 選擇您的金鑰識別元以傳送至 Experian 進行身分識別解析。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="ac6c7-122">傳送至 Experian 的金鑰識別元屬性愈多，可能產生的適配率愈高。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="ac6c7-123">選取 **下一步**，然後對應所選金鑰識別元欄位的統一客戶實體中的對應屬性。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="ac6c7-124">選取 **新增屬性**，以對應任何您要傳送至 Experian 的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="ac6c7-125">選取 **儲存** 來完成欄位對應。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac6c7-126">![Experian 欄位對應](media/experian-field-mapping.png "Experian 欄位對應")</span><span class="sxs-lookup"><span data-stu-id="ac6c7-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ac6c7-127">擴充結果</span><span class="sxs-lookup"><span data-stu-id="ac6c7-127">Enrichment results</span></span>

<span data-ttu-id="ac6c7-128">若要開始擴充程序，請從命令列中選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ac6c7-129">您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ac6c7-130">處理時間取決於客戶資料的大小以及 Experian 為您帳戶設定的擴充程序。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="ac6c7-131">擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ac6c7-132">此外，您還會找到上次更新時間以及已擴充的設定檔數目。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ac6c7-133">您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ac6c7-134">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ac6c7-134">Next steps</span></span>

<span data-ttu-id="ac6c7-135">建立在您擴充的客戶資料之上。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ac6c7-136">建立[客戶細分](segments.md)、[量值](measures.md)，甚至[匯出資料](export-destinations.md)，以便傳送個人化體驗給您的客戶。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ac6c7-137">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="ac6c7-137">Data privacy and compliance</span></span>

<span data-ttu-id="ac6c7-138">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Experian 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ac6c7-139">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Experian 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ac6c7-140">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ac6c7-141">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此富集作用，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
