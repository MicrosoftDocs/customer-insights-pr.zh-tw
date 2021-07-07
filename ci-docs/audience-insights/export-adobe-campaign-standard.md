---
title: 將 Customer Insights 資料匯出到 Adobe Campaign Standard
description: 瞭解如何在 Adobe Campaign Standard 中使用對象見解客戶細分。
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305376"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="3ae9d-103">在 Adobe Campaign Standard 中使用 Customer Insights 客戶細分 (預覽)</span><span class="sxs-lookup"><span data-stu-id="3ae9d-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="3ae9d-104">對於 Dynamics 365 Customer Insights 中對象見解的使用者，您可能已建立了一些客戶細分來鎖定相關的對象，讓您的行銷廣告活動更有效率。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="3ae9d-105">在 Adobe Experience Platform 和 Adobe Campaign Standard 之類的應用程式中使用對象見解的客戶細分，您需要遵循本文中概述的幾個步驟。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="本文概述步驟的流程圖。":::

## <a name="prerequisites"></a><span data-ttu-id="3ae9d-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="3ae9d-107">Prerequisites</span></span>

-   <span data-ttu-id="3ae9d-108">Dynamics 365 Customer Insights 授權</span><span class="sxs-lookup"><span data-stu-id="3ae9d-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="3ae9d-109">Adobe Campaign Standard 授權</span><span class="sxs-lookup"><span data-stu-id="3ae9d-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="3ae9d-110">Azure Blob 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="3ae9d-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="3ae9d-111">行銷活動概觀</span><span class="sxs-lookup"><span data-stu-id="3ae9d-111">Campaign overview</span></span>

<span data-ttu-id="3ae9d-112">為了更好地了解如何使用 Adobe Experience Platform 中對象見解的客戶細分，先來看看一個虛構的行銷活動。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="3ae9d-113">假設貴公司在美國為客戶提供每月訂閱型的服務。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="3ae9d-114">您希望找出哪些客戶的訂閱是需要在未來八天內續訂但尚未續訂的。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="3ae9d-115">為了保留這些客戶，您希望使用 Adobe Campaign Standard 向他們發送電子郵件提供促銷優惠。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="3ae9d-116">在此範例中，我們希望執行一次促銷電子郵件的行銷活動。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="3ae9d-117">本文不涵蓋多次執行行銷活動的使用案例。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="3ae9d-118">但是，對象見解和 Adobe Campaign Standard 也可以設定為定期行銷活動案例運作。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="3ae9d-119">找出目標對象</span><span class="sxs-lookup"><span data-stu-id="3ae9d-119">Identify your target audience</span></span>

<span data-ttu-id="3ae9d-120">在我們的案例中，我們假設客戶的電子郵件位址包含在對象見解中，而他們的促銷偏好也已經完成分析，能找出該客戶細分的成員。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="3ae9d-121">[在對象見解中定義的客戶細分](segments.md)名稱為 **ChurnProneCustomers**，且您計畫向這些客戶發送電子郵件促銷。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="建立了 ChurnProneCustomers 客戶細分頁面的螢幕擷取畫面。":::

<span data-ttu-id="3ae9d-123">您要發送的優惠電子郵件將包含客戶的姓、名和訂閱結束日期。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="3ae9d-124">此信件通知客戶，如果他們在訂閱結束前續訂訂閱，他們將獲得折扣。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="3ae9d-125">匯出目標對象</span><span class="sxs-lookup"><span data-stu-id="3ae9d-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="3ae9d-126">設定連接</span><span class="sxs-lookup"><span data-stu-id="3ae9d-126">Configure a connection</span></span>

<span data-ttu-id="3ae9d-127">找出目標對象後，我們可以設定從對象見解到 Azure Blob 儲存體帳戶的匯出。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="3ae9d-128">在對象見解中，移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3ae9d-129">選取 **新增連接**，然後選擇 **Adobe Campaign** 來設定此連接，或在 **Adobe Campaign** 圖格中選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard 的設定圖格。":::

1. <span data-ttu-id="3ae9d-131">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3ae9d-132">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3ae9d-133">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3ae9d-134">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-134">Choose who can use this connection.</span></span> <span data-ttu-id="3ae9d-135">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3ae9d-136">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3ae9d-137">輸入要將客戶細分匯出到的 Azure Blob 儲存體帳戶其 **帳戶名稱**、**帳戶金鑰** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="儲存體帳戶設定的螢幕擷取畫面。"::: 

   - <span data-ttu-id="3ae9d-139">若要進一步了解如何尋找 Azure Blob 儲存體帳戶名稱及帳戶金鑰，請參閱 [管理 Azure 入口網站中的儲存體帳戶設定](/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="3ae9d-140">若要了解如何建立容器，請參閱[建立容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="3ae9d-141">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="3ae9d-142">設定匯出</span><span class="sxs-lookup"><span data-stu-id="3ae9d-142">Configure an export</span></span>

<span data-ttu-id="3ae9d-143">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3ae9d-144">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3ae9d-145">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3ae9d-146">若要建立新匯出，請選取 **新增匯出**。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="3ae9d-147">在 **匯出的連結** 欄位中，在 Adobe Campaign 區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="3ae9d-148">如果您沒有看到此區段名稱，則代表此類型中的連接沒有您可以使用的。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="3ae9d-149">選擇您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="3ae9d-150">在這個例子中，它是 **ChurnProneCustomers**。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="客戶細分選擇使用者介面中已選擇 ChurnProneCustomers 客戶細分的螢幕擷取畫面。":::

1. <span data-ttu-id="3ae9d-152">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-152">Select **Next**.</span></span>

1. <span data-ttu-id="3ae9d-153">現在，我們將對象見解客戶細分的 **來源** 欄位對應到 Adobe Campaign Standard 個人資料結構描述中的 **目標** 欄位名稱。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard 連接器的欄位對應。":::

   <span data-ttu-id="3ae9d-155">若要新增更多屬性，請選擇 **新增屬性**。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="3ae9d-156">目標名稱可以與來源欄位名稱不同，因此，如果兩個系統中的欄位名稱不相同，您仍可以對應對象見解的客戶細分輸出到 Adobe Campaign Standard。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3ae9d-157">電子郵件地址被當成識別欄位，但您可以使用對象見解客戶個人資料中的任何其他識別碼來對應資料到 Adobe Campaign Standard。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="3ae9d-158">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-158">Select **Save**.</span></span>

<span data-ttu-id="3ae9d-159">儲存匯出目的地之後，您會在 **資料** > **匯出** 中找到它 。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="3ae9d-160">現在，您能[依需求匯出客戶細分](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="3ae9d-161">匯出也會與每個[排定的重新整理](system.md)一起執行。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3ae9d-162">確認客戶細分記錄的匯出數量在 Adobe Campaign Standard 授權限制內。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="3ae9d-163">匯出的資料儲存在前面設定的 Azure Blob 儲存體容器中。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="3ae9d-164">在您的容器中將自動建立下列資料夾路徑：</span><span class="sxs-lookup"><span data-stu-id="3ae9d-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="3ae9d-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="3ae9d-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="3ae9d-166">範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="3ae9d-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="3ae9d-167">設定 Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="3ae9d-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="3ae9d-168">匯出對象見解的客戶細分時，它包含您在上個步驟定義匯出目的地時選擇的資料行。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="3ae9d-169">此資料可用於[建立 Adobe Campaign Standard 中的個人資料](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="3ae9d-170">要使用 Adobe Campaign Standard 中的客戶細分，我們需要擴充 Adobe Campaign Standard 中的個人資料結構描述，容納兩個額外的欄位。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="3ae9d-171">瞭解在 Adobe Campaign Standard 中如何使用新欄位[擴充個人資料資源](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing)。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="3ae9d-172">在我們的範例中，這些欄位是 *客戶細分名稱和客戶細分日期 (可選)*。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="3ae9d-173">我們將使用這些欄位在 Adobe Campaign Standard 中找出我們想要用在此活動的個人資料。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="3ae9d-174">如果除了要匯入的內容，Adobe Campaign Standard 中沒有其他記錄，您可以跳過此步驟。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="3ae9d-175">將資料匯入 Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="3ae9d-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="3ae9d-176">現在一切都準備好了，我們需要從對象見解匯入準備好的對象資料到 Adobe Campaign Standard，以建立個人資料。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="3ae9d-177">瞭解使用工作流程，[如何在 Adobe Campaign Standard 匯入個人資料](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="3ae9d-178">下面圖片中的匯入工作流程已設定為每 8 小時執行一次，並尋找匯出的對象見解客戶細分 (位於 Azure Blob 儲存體中的 csv 檔案)。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="3ae9d-179">工作流程以指定的資料行順序擷取 csv 檔案內容。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="3ae9d-180">此工作流程已組建為能執行基本錯誤處理，及確保每個記錄有一個電子郵寄地址之後才在 Adobe Campaign Standard 將資料序列化。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="3ae9d-181">工作流程也會在 upsert 至 Adobe Campaign Standard 個人資料之前，先從檔案名中提取客戶細分名稱。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard 使用者介面中匯入工作流程的螢幕擷取畫面。":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="3ae9d-183">在 Adobe Campaign Standard 中擷取對象</span><span class="sxs-lookup"><span data-stu-id="3ae9d-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="3ae9d-184">當資料匯入 Adobe Campaign Standard，您可以 [建立工作流程](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data)以及根據 *客戶細分名稱* 和 *客戶細分日期* 對客戶[查詢](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data)，來選取為範例活動確認完成的個人資料。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="3ae9d-185">使用 Adobe Campaign Standard 建立和發送電子郵件</span><span class="sxs-lookup"><span data-stu-id="3ae9d-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="3ae9d-186">建立電子郵件內容，接著[測試並發送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3ae9d-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text=" Adobe Campaign Standard 中包含續訂優惠的電子郵件範例。":::
