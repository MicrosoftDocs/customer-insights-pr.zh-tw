---
title: 協力廠商 Enrichment Leadspace 的公司設定檔
description: 有關協力廠商 Leadspace 富集作用的一般資訊。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305192"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="dc067-103">使用 Leadspace 擴充公司設定檔 (預覽)</span><span class="sxs-lookup"><span data-stu-id="dc067-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="dc067-104">Leadspace 是一家提供 B2B 客戶資料平台的資料科學公司。</span><span class="sxs-lookup"><span data-stu-id="dc067-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="dc067-105">為客戶帶來統一客戶設定檔，讓各家公司可以擴充其資料。</span><span class="sxs-lookup"><span data-stu-id="dc067-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="dc067-106">擴充包括更多屬性，例如公司規模、位置、產業等等。</span><span class="sxs-lookup"><span data-stu-id="dc067-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dc067-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="dc067-107">Prerequisites</span></span>

<span data-ttu-id="dc067-108">若要設定 Leadspace，必須符合以下先決條件：</span><span class="sxs-lookup"><span data-stu-id="dc067-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dc067-109">您有一個有效的 Leadspace 授權。</span><span class="sxs-lookup"><span data-stu-id="dc067-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="dc067-110">您有公司的[統一客戶設定檔](customer-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="dc067-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="dc067-111">Leadspace 連接已由系統管理員設定，或者您有 [系統管理員](permissions.md#administrator)權限和「永久金鑰」(被稱為 **Leadspace 權杖**)。</span><span class="sxs-lookup"><span data-stu-id="dc067-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="dc067-112">如需產品的詳細資料，請直接聯繫 [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/)。</span><span class="sxs-lookup"><span data-stu-id="dc067-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="dc067-113">擴充設定</span><span class="sxs-lookup"><span data-stu-id="dc067-113">Configure the enrichment</span></span>

1. <span data-ttu-id="dc067-114">請在對象見解中前往 **資料** > **富集**。</span><span class="sxs-lookup"><span data-stu-id="dc067-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="dc067-115">在 Leadspace 圖格上選取 **擴充我的資料**，然後選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="dc067-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 圖格的螢幕擷取畫面。":::

1. <span data-ttu-id="dc067-117">從下拉式清單選取一個[連結](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="dc067-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="dc067-118">如果沒有可用的連接，請與系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="dc067-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="dc067-119">如果您是系統管理員，則可以選取 **新增連接** 接著選擇 **Leadspace** 來建立連接。</span><span class="sxs-lookup"><span data-stu-id="dc067-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="dc067-120">選取 **連接至 Leadspace** 以確認選取連接。</span><span class="sxs-lookup"><span data-stu-id="dc067-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="dc067-121">選取 **下一步**，然後選擇想要用 Leadspace 的公司資料擴充的 **客戶資料集**。</span><span class="sxs-lookup"><span data-stu-id="dc067-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="dc067-122">您可以選取 **客戶** 實體來擴充所有的客戶設定檔，或選取客戶細分實體僅擴充位於該客戶細分的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="dc067-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. <span data-ttu-id="dc067-124">選取 **下一步**，接著定義在整合個人資料中的欄位，這些欄位用來在 Leadspace 尋找符合的公司資料。</span><span class="sxs-lookup"><span data-stu-id="dc067-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="dc067-125">**公司名稱** 欄位是必要欄位。</span><span class="sxs-lookup"><span data-stu-id="dc067-125">The **Name of company** field is required.</span></span> <span data-ttu-id="dc067-126">為了獲得更高的準確性，可以新增多達兩個欄位，**公司網站** 和 **公司位置**。</span><span class="sxs-lookup"><span data-stu-id="dc067-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 欄位對應窗格。":::

1. <span data-ttu-id="dc067-128">請選取 **下一步**，完成欄位對應。</span><span class="sxs-lookup"><span data-stu-id="dc067-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="dc067-129">提供擴充的名稱，並在檢閱選擇後選取 **儲存擴充**。</span><span class="sxs-lookup"><span data-stu-id="dc067-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="dc067-130">設定 Leadspace 的連接</span><span class="sxs-lookup"><span data-stu-id="dc067-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="dc067-131">您必須是系統管理員才能設定連接。</span><span class="sxs-lookup"><span data-stu-id="dc067-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="dc067-132">在設定擴充時，請選取 \**新增連接\*\*\*或* 在 Leadspace 圖格上移至 **管理** > **連接** 並選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="dc067-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="dc067-133">選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="dc067-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="dc067-134">在 **顯示名稱** 方塊中輸入連接的名稱。</span><span class="sxs-lookup"><span data-stu-id="dc067-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="dc067-135">提供有效的 Leadspace 權杖。</span><span class="sxs-lookup"><span data-stu-id="dc067-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="dc067-136">檢閱並選取 **我同意**，提供您的 **資料隱私權和合規性** 許可。</span><span class="sxs-lookup"><span data-stu-id="dc067-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="dc067-137">選取 **驗證** 來驗證設定。</span><span class="sxs-lookup"><span data-stu-id="dc067-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="dc067-138">完成驗證之後，請選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="dc067-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 的連接設定頁面。":::

## <a name="enrichment-results"></a><span data-ttu-id="dc067-140">擴充結果</span><span class="sxs-lookup"><span data-stu-id="dc067-140">Enrichment results</span></span>

<span data-ttu-id="dc067-141">重新整理擴充內容之後，您可以在[我的擴充內容](enrichment-hub.md)中檢閱新近擴充的公司資料。</span><span class="sxs-lookup"><span data-stu-id="dc067-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="dc067-142">您可以找到上次更新的時間以及已擴充設定檔的數目。</span><span class="sxs-lookup"><span data-stu-id="dc067-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dc067-143">您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。</span><span class="sxs-lookup"><span data-stu-id="dc067-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="dc067-144">如需詳細資訊，請參閱 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)。</span><span class="sxs-lookup"><span data-stu-id="dc067-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="dc067-145">後續步驟</span><span class="sxs-lookup"><span data-stu-id="dc067-145">Next steps</span></span>

<span data-ttu-id="dc067-146">建立在您擴充的客戶資料之上。</span><span class="sxs-lookup"><span data-stu-id="dc067-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dc067-147">建立[客戶細分](segments.md)和 [量值 ](measures.md)，甚至 [匯出資料](export-destinations.md)，為您的客戶提供個人化的體驗。</span><span class="sxs-lookup"><span data-stu-id="dc067-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dc067-148">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="dc067-148">Data privacy and compliance</span></span>

<span data-ttu-id="dc067-149">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Leadspace 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="dc067-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dc067-150">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Leadspace 符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="dc067-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dc067-151">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="dc067-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dc067-152">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此擴充，不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="dc067-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
