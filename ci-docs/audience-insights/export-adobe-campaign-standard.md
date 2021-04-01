---
title: 將 Customer Insights 資料匯出到 Adobe Campaign Standard
description: 瞭解如何在 Adobe Campaign Standard 中使用對象見解客戶細分。
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596305"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="6c5fe-103">在 Adobe Campaign Standard 中使用 Customer Insights 客戶細分 (預覽)</span><span class="sxs-lookup"><span data-stu-id="6c5fe-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="6c5fe-104">作為 Dynamics 365 Customer Insights 對象見解的使用者，您可能創建了多個客戶細分，鎖定相關對象來提高行銷廣告活動的效益。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="6c5fe-105">在 Adobe Experience Platform 和 Adobe Campaign Standard 之類的應用程式中使用對象見解的客戶細分，您需要遵循本文中概述的幾個步驟。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="本文概述步驟的流程圖。":::

## <a name="prerequisites"></a><span data-ttu-id="6c5fe-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="6c5fe-107">Prerequisites</span></span>

-   <span data-ttu-id="6c5fe-108">Dynamics 365 Customer Insights 授權</span><span class="sxs-lookup"><span data-stu-id="6c5fe-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="6c5fe-109">Adobe Campaign Standard 授權</span><span class="sxs-lookup"><span data-stu-id="6c5fe-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="6c5fe-110">Azure Blob 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="6c5fe-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="6c5fe-111">行銷活動概觀</span><span class="sxs-lookup"><span data-stu-id="6c5fe-111">Campaign Overview</span></span>

<span data-ttu-id="6c5fe-112">為了更好地了解如何使用 Adobe Experience Platform 中對象見解的客戶細分，先來看看一個虛構的行銷活動。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="6c5fe-113">假設貴公司在美國為客戶提供每月訂閱型的服務。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="6c5fe-114">您希望找出哪些客戶的訂閱是需要在未來八天內續訂但尚未續訂的。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="6c5fe-115">為了保留這些客戶，您希望使用 Adobe Campaign Standard 向他們發送電子郵件提供促銷優惠。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="6c5fe-116">在此範例中，我們希望執行一次促銷電子郵件的行銷活動。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="6c5fe-117">本文不涵蓋多次執行行銷活動的使用案例。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="6c5fe-118">但是，對象見解和 Adobe Campaign Standard 也可以設定為定期行銷活動案例運作。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="6c5fe-119">找出目標對象</span><span class="sxs-lookup"><span data-stu-id="6c5fe-119">Identify your target audience</span></span>

<span data-ttu-id="6c5fe-120">在我們的案例中，我們假設客戶的電子郵件位址包含在對象見解中，而他們的促銷偏好也已經完成分析，能找出該客戶細分的成員。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="6c5fe-121">[在對象見解中定義的客戶細分](segments.md)名稱為 **ChurnProneCustomers**，且您計畫向這些客戶發送電子郵件促銷。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="建立了 ChurnProneCustomers 客戶細分頁面的螢幕擷取畫面。":::

<span data-ttu-id="6c5fe-123">您要發送的優惠電子郵件將包含客戶的姓、名和訂閱結束日期。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="6c5fe-124">此信件通知客戶，如果他們在訂閱結束前續訂訂閱，他們將獲得折扣。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="6c5fe-125">匯出目標對象</span><span class="sxs-lookup"><span data-stu-id="6c5fe-125">Export your target audience</span></span>

<span data-ttu-id="6c5fe-126">找出目標對象後，我們可以設定從對象見解到 Azure Blob 儲存體帳戶的匯出。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="6c5fe-127">在對象見解中，前往 **系統管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6c5fe-128">在 **Adobe Campaign** 圖格中選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard 的設定圖格。":::

1. <span data-ttu-id="6c5fe-130">為這個新的匯出目的地提供 **顯示名稱**，然後輸入您希望客戶細分匯出到的 Azure Blob 儲存體帳戶其 **帳戶名稱**、**帳戶金鑰**、和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="儲存體帳戶設定的螢幕擷取畫面。"::: 

   - <span data-ttu-id="6c5fe-132">若要進一步了解如何尋找 Azure Blob 儲存體帳戶名稱及帳戶金鑰，請參閱 [管理 Azure 入口網站中的儲存體帳戶設定](/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="6c5fe-133">若要了解如何建立容器，請參閱[建立容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="6c5fe-134">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-134">Select **Next**.</span></span>

1. <span data-ttu-id="6c5fe-135">選擇您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="6c5fe-136">在這個例子中，它是 **ChurnProneCustomers**。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="客戶細分選擇使用者介面中已選擇 ChurnProneCustomers 客戶細分的螢幕擷取畫面。":::

1. <span data-ttu-id="6c5fe-138">選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-138">Select **Next**.</span></span>

1. <span data-ttu-id="6c5fe-139">現在，我們將對象見解客戶細分的 **來源** 欄位對應到 Adobe Campaign Standard 個人資料結構描述中的 **目標** 欄位名稱。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard 連接器的欄位對應。":::

   <span data-ttu-id="6c5fe-141">若要新增更多屬性，請選擇 **新增屬性**。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="6c5fe-142">目標名稱可以與來源欄位名稱不同，因此，如果兩個系統中的欄位名稱不相同，您仍可以對應對象見解的客戶細分輸出到 Adobe Campaign Standard。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6c5fe-143">電子郵件地址被當成識別欄位，但您可以使用對象見解客戶個人資料中的任何其他識別碼來對應資料到 Adobe Campaign Standard。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="6c5fe-144">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-144">Select **Save**.</span></span>

<span data-ttu-id="6c5fe-145">儲存匯出目的地後，您可以在 **管理** > **匯出** > **我的匯出目的地** 找到。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="醒目提示匯出清單和範例客戶細分的螢幕擷取畫面。":::

<span data-ttu-id="6c5fe-147">現在，您能[依需求匯出客戶細分](export-destinations.md#export-data-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="6c5fe-148">匯出也會與每個[排定的重新整理](system.md)一起執行。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6c5fe-149">確認客戶細分記錄的匯出數量在 Adobe Campaign Standard 授權限制內。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="6c5fe-150">匯出的資料儲存在前面設定的 Azure Blob 儲存體容器中。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="6c5fe-151">在您的容器中將自動建立下列資料夾路徑：</span><span class="sxs-lookup"><span data-stu-id="6c5fe-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="6c5fe-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="6c5fe-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="6c5fe-153">範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="6c5fe-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="6c5fe-154">設定 Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="6c5fe-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="6c5fe-155">匯出對象見解的客戶細分時，它包含您在上個步驟定義匯出目的地時選擇的資料行。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="6c5fe-156">此資料可用於[建立 Adobe Campaign Standard 中的個人資料](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="6c5fe-157">要使用 Adobe Campaign Standard 中的客戶細分，我們需要擴充 Adobe Campaign Standard 中的個人資料結構描述，容納兩個額外的欄位。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="6c5fe-158">瞭解在 Adobe Campaign Standard 中如何使用新欄位[擴充個人資料資源](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing)。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="6c5fe-159">在我們的範例中，這些欄位是 *客戶細分名稱和客戶細分日期 (可選)。*</span><span class="sxs-lookup"><span data-stu-id="6c5fe-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="6c5fe-160">我們將使用這些欄位在 Adobe Campaign Standard 中找出我們想要用在此活動的個人資料。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="6c5fe-161">如果除了要匯入的內容，Adobe Campaign Standard 中沒有其他記錄，您可以跳過此步驟。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="6c5fe-162">將資料匯入 Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="6c5fe-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="6c5fe-163">現在一切都準備好了，我們需要從對象見解匯入準備好的對象資料到 Adobe Campaign Standard，以建立個人資料。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="6c5fe-164">瞭解使用工作流程，[如何在 Adobe Campaign Standard 匯入個人資料](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="6c5fe-165">下圖中的匯入工作流程已設定為每 8 小時執行一次，並找出已匯出的對象見解客戶細分 (Azure Blob 儲存體中的 csv 檔案)。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="6c5fe-166">工作流程以指定的資料行順序擷取 csv 檔案內容。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="6c5fe-167">此工作流程已組建為能執行基本錯誤處理，及確保每個記錄有一個電子郵寄地址之後才在 Adobe Campaign Standard 將資料序列化。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="6c5fe-168">工作流程還能從檔名中擷取資料細分名稱，再更新插入 ACS 個人資料。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard 使用者介面中匯入工作流程的螢幕擷取畫面。":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="6c5fe-170">在 Adobe Campaign Standard 中擷取對象</span><span class="sxs-lookup"><span data-stu-id="6c5fe-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="6c5fe-171">當資料匯入 Adobe Campaign Standard，您可以 [建立工作流程](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data)以及根據 *客戶細分名稱* 和 *客戶細分日期* 對客戶[查詢](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data)，來選取為範例活動確認完成的個人資料。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="6c5fe-172">使用 Adobe Campaign Standard 建立和發送電子郵件</span><span class="sxs-lookup"><span data-stu-id="6c5fe-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="6c5fe-173">建立電子郵件內容，接著[測試並發送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text=" Adobe Campaign Standard 中包含續訂優惠的電子郵件範例。":::