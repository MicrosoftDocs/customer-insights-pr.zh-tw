---
title: 協力廠商 Enrichment Leadspace 的公司設定檔
description: 有關協力廠商 Leadspace 富集作用的一般資訊。
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668713"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="991ca-103">使用 Leadspace 擴充公司設定檔 (預覽)</span><span class="sxs-lookup"><span data-stu-id="991ca-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="991ca-104">Leadspace 是一家提供 B2B 客戶資料平台的資料科學公司。</span><span class="sxs-lookup"><span data-stu-id="991ca-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="991ca-105">為客戶帶來統一客戶設定檔，讓各家公司可以擴充其資料。</span><span class="sxs-lookup"><span data-stu-id="991ca-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="991ca-106">富集群包括其他屬性如公司大小、地點、產業及其他。</span><span class="sxs-lookup"><span data-stu-id="991ca-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="991ca-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="991ca-107">Prerequisites</span></span>

<span data-ttu-id="991ca-108">若要設定 Leadspace，必須符合以下先決條件：</span><span class="sxs-lookup"><span data-stu-id="991ca-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="991ca-109">您具備有效的 Leadspace 授權和「永久金鑰」 (以下簡稱 **Leadspace 權杖**)。</span><span class="sxs-lookup"><span data-stu-id="991ca-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="991ca-110">直接連絡 [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/)，以取得其產品的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="991ca-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="991ca-111">您擁有 [系統管理員](permissions.md#administrator) 權限。</span><span class="sxs-lookup"><span data-stu-id="991ca-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="991ca-112">您有公司的[統一客戶設定檔](customer-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="991ca-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="991ca-113">組態</span><span class="sxs-lookup"><span data-stu-id="991ca-113">Configuration</span></span>

1. <span data-ttu-id="991ca-114">請在對象見解中前往 **資料** > **富集**。</span><span class="sxs-lookup"><span data-stu-id="991ca-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="991ca-115">選取 Leadspace 圖標上的 **擴充我的資料**。</span><span class="sxs-lookup"><span data-stu-id="991ca-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 圖格的螢幕擷取畫面。":::

1. <span data-ttu-id="991ca-117">選取 **開始使用** 然後輸入有效的 **Leadspace 權杖** (永久金鑰)。</span><span class="sxs-lookup"><span data-stu-id="991ca-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="991ca-118">選取 **我同意** 核取方塊，以檢閱 **資料隱私權和合規性** 並表示同意。</span><span class="sxs-lookup"><span data-stu-id="991ca-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="991ca-119">選取 **連接到 Leadspace** 確認這兩項輸入資料。</span><span class="sxs-lookup"><span data-stu-id="991ca-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="991ca-120">選取 **對應資料** 然後定義應使用統一設定檔中的欄位，以便尋找符合 Leadspace 的公司資料。</span><span class="sxs-lookup"><span data-stu-id="991ca-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="991ca-121">**公司名稱** 欄位是必要欄位。</span><span class="sxs-lookup"><span data-stu-id="991ca-121">The **Name of company** field is required.</span></span> <span data-ttu-id="991ca-122">為了獲得更高的準確性，可以新增多達兩個欄位，**公司網站** 和 **公司位置**。</span><span class="sxs-lookup"><span data-stu-id="991ca-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 欄位對應窗格。":::
   
1. <span data-ttu-id="991ca-124">選取 **套用** 完成欄位對應。</span><span class="sxs-lookup"><span data-stu-id="991ca-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="991ca-125">選取 **執行** 以擴充公司設定檔。</span><span class="sxs-lookup"><span data-stu-id="991ca-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="991ca-126">富集花費的時間視統一的客戶設定檔數量而定。</span><span class="sxs-lookup"><span data-stu-id="991ca-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="991ca-127">擴充結果</span><span class="sxs-lookup"><span data-stu-id="991ca-127">Enrichment results</span></span>

<span data-ttu-id="991ca-128">重新整理擴充內容之後，您可以在[我的擴充內容](enrichment-hub.md)中檢閱新近擴充的公司資料。</span><span class="sxs-lookup"><span data-stu-id="991ca-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="991ca-129">您可以找到上次更新的時間以及已擴充設定檔的數目。</span><span class="sxs-lookup"><span data-stu-id="991ca-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="991ca-130">您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。</span><span class="sxs-lookup"><span data-stu-id="991ca-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="991ca-131">如需詳細資訊，請參閱 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)。</span><span class="sxs-lookup"><span data-stu-id="991ca-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="991ca-132">後續步驟</span><span class="sxs-lookup"><span data-stu-id="991ca-132">Next steps</span></span>

<span data-ttu-id="991ca-133">建立在您擴充的客戶資料之上。</span><span class="sxs-lookup"><span data-stu-id="991ca-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="991ca-134">建立[客戶細分](segments.md)、[量值](measures.md)，甚至[匯出資料](export-destinations.md)，以便傳送個人化體驗給您的客戶。</span><span class="sxs-lookup"><span data-stu-id="991ca-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="991ca-135">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="991ca-135">Data privacy and compliance</span></span>

<span data-ttu-id="991ca-136">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Leadspace 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="991ca-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="991ca-137">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Leadspace 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="991ca-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="991ca-138">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="991ca-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="991ca-139">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此富集作用，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="991ca-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>