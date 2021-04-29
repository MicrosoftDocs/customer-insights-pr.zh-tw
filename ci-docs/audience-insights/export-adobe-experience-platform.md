---
title: 將 Customer Insights 資料匯出到 Adobe Experience Platform
description: 了解如何在 Adobe Experience Platform 中使用對象見解客戶細分。
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760091"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="1f8ce-103">在 Adobe Experience Platform 中使用 Customer Insights 客戶細分 (預覽)</span><span class="sxs-lookup"><span data-stu-id="1f8ce-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="1f8ce-104">作為 Dynamics 365 Customer Insights 對象見解的使用者，您可能創建了多個客戶細分，鎖定相關對象來提高行銷廣告活動的效益。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="1f8ce-105">在 Adobe Experience Platform 和 Adobe Campaign Standard 之類的應用程式中使用對象見解的客戶細分，您需要遵循本文中概述的幾個步驟。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="本文概述步驟的流程圖。":::

## <a name="prerequisites"></a><span data-ttu-id="1f8ce-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="1f8ce-107">Prerequisites</span></span>

-   <span data-ttu-id="1f8ce-108">Dynamics 365 Customer Insights 授權</span><span class="sxs-lookup"><span data-stu-id="1f8ce-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="1f8ce-109">Adobe Experience Platform 權限</span><span class="sxs-lookup"><span data-stu-id="1f8ce-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="1f8ce-110">Adobe Campaign Standard 授權</span><span class="sxs-lookup"><span data-stu-id="1f8ce-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="1f8ce-111">Azure Blob 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="1f8ce-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="1f8ce-112">行銷活動概觀</span><span class="sxs-lookup"><span data-stu-id="1f8ce-112">Campaign Overview</span></span>

<span data-ttu-id="1f8ce-113">為了更好地了解如何使用 Adobe Experience Platform 中對象見解的客戶細分，先來看看一個虛構的行銷活動。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="1f8ce-114">假設貴公司在美國為客戶提供每月訂閱型的服務。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="1f8ce-115">您希望找出哪些客戶的訂閱是需要在未來八天內續訂但尚未續訂的。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="1f8ce-116">為了保留這些客戶，您希望使用 Adobe Experience Platform 向他們發送電子郵件提供促銷優惠。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="1f8ce-117">在此範例中，我們希望執行一次促銷電子郵件的行銷活動。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="1f8ce-118">本文不涵蓋多次執行行銷活動的使用案例。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="1f8ce-119">找出目標對象</span><span class="sxs-lookup"><span data-stu-id="1f8ce-119">Identify your target audience</span></span>

<span data-ttu-id="1f8ce-120">在我們的案例中，我們假設客戶的電子郵件位址包含在對象見解中，而他們的促銷偏好也已經完成分析，能找出該客戶細分的成員。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="1f8ce-121">[在對象見解中定義的客戶細分](segments.md)名稱為 **ChurnProneCustomers**，且您計畫向這些客戶發送電子郵件促銷。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="建立了 ChurnProneCustomers 客戶細分頁面的螢幕擷取畫面。":::

<span data-ttu-id="1f8ce-123">您要發送的優惠電子郵件將包含客戶的姓、名和訂閱結束日期。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="1f8ce-124">此信件通知客戶，如果他們在訂閱結束前續訂訂閱，他們將獲得折扣。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="1f8ce-125">匯出目標對象</span><span class="sxs-lookup"><span data-stu-id="1f8ce-125">Export your target audience</span></span>

<span data-ttu-id="1f8ce-126">找出目標對象後，我們可以設定從對象見解到 Azure Blob 儲存體帳戶的匯出。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="1f8ce-127">設定連接</span><span class="sxs-lookup"><span data-stu-id="1f8ce-127">Configure a connection</span></span>

1. <span data-ttu-id="1f8ce-128">移至 **管理** > **連接**。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1f8ce-129">選取 **新增連接**，然後選擇 **Azure blob 儲存體** 或在 **Azure Blob 儲存體** 圖格中選取 **設定**：</span><span class="sxs-lookup"><span data-stu-id="1f8ce-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob 儲存體的設定圖格。"::: <span data-ttu-id="1f8ce-131">若要設定連接：</span><span class="sxs-lookup"><span data-stu-id="1f8ce-131">to configure the connection.</span></span>

1. <span data-ttu-id="1f8ce-132">在 **顯示名稱** 中，給連接一個能夠辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1f8ce-133">連接的名稱與類型能說明此連接。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1f8ce-134">我們建議您選取可以說明此連接用途和目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1f8ce-135">選擇可使用此連接的人員。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-135">Choose who can use this connection.</span></span> <span data-ttu-id="1f8ce-136">如果您不採取任何動作，預設值將為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1f8ce-137">如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1f8ce-138">對客戶細分要匯出到的 Azure Blob 儲存體帳戶，輸入其 **帳戶名稱**、**帳戶金鑰** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="儲存體帳戶設定的螢幕擷取畫面。"::: 
   
    - <span data-ttu-id="1f8ce-140">若要進一步了解如何找到 Blob 儲存體帳戶名稱及帳戶金鑰，請參閱 [Azure 入口網站中的管理儲存體帳戶設定](/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="1f8ce-141">若要了解如何建立容器，請參閱[建立容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="1f8ce-142">選取 **儲存** 來完成連接。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="1f8ce-143">設定匯出</span><span class="sxs-lookup"><span data-stu-id="1f8ce-143">Configure an export</span></span>

<span data-ttu-id="1f8ce-144">若您擁有取此類型的連接的存取權，則可以設定此匯出。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1f8ce-145">如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1f8ce-146">移至 **資料** > **匯出**。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1f8ce-147">若要建立新匯出，請選取 **新增匯出**。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="1f8ce-148">在 **匯出的連結** 欄位中，在 Azure Blob 儲存體區段中選擇連接。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="1f8ce-149">如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1f8ce-150">選擇您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="1f8ce-151">在這個例子中，它是 **ChurnProneCustomers**。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="客戶細分選擇使用者介面中已選擇 ChurnProneCustomers 客戶細分的螢幕擷取畫面。":::

1. <span data-ttu-id="1f8ce-153">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-153">Select **Save**.</span></span>

<span data-ttu-id="1f8ce-154">儲存匯出目的地之後，您會在 **資料** > **匯出** 中找到它 。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="1f8ce-155">現在，您能[依需求匯出客戶細分](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="1f8ce-156">匯出也會與每個[排定的重新整理](system.md)一起執行。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1f8ce-157">確認客戶細分記錄的匯出數量在 Adobe Campaign Standard 授權限制內。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="1f8ce-158">匯出的資料儲存在前面設定的 Azure Blob 儲存體容器中。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="1f8ce-159">在您的容器中將自動建立下列資料夾路徑：</span><span class="sxs-lookup"><span data-stu-id="1f8ce-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="1f8ce-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="1f8ce-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="1f8ce-161">範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="1f8ce-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="1f8ce-162">匯出實體的 *model.json* 位於 *%ExportDestinationName%* 層級。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="1f8ce-163">範例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="1f8ce-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="1f8ce-164">在 Adobe Experience Platform 中定義體驗資料模型 (XDM)</span><span class="sxs-lookup"><span data-stu-id="1f8ce-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="1f8ce-165">在 Adobe Experience Platform 中使用對象見解的匯出資料之前，我們需要定義體驗資料模型結構描述，並[為即時客戶個人資料設定資料](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="1f8ce-166">了解 [XDM 是什麼](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)，並了解[結構描述組成的基本知識](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema)。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="1f8ce-167">匯入資料到 Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="1f8ce-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="1f8ce-168">現在一切都準備好了，我們需要從對象見解匯入準備好的對象資料到 Adobe Experience Platform，以建立個人資料。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="1f8ce-169">首先，[建立 Azure Blob 儲存體來源連接 ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="1f8ce-170">定義來源連接後，為雲端儲存空間批次連接[設定資料流程](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials)，從對象見解客戶細分輸出匯入 Adobe Experience Platform。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="1f8ce-171">在 Adobe Campaign Standard 建立對象</span><span class="sxs-lookup"><span data-stu-id="1f8ce-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="1f8ce-172">發送此行銷活動的電子郵件，我們將使用 Adobe Campaign Standard。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="1f8ce-173">將資料匯入 Adobe Experience Platform 後，我們需要使用 Adobe Experience Platform 中的資料在 Adobe Campaign Standard 中[建立對象](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="1f8ce-174">了解在 Adobe Campaign Standard 中如何[使用客戶細分建立工具](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment)以 Adobe Experience Platform 的資料定義對象。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="1f8ce-175">使用 Adobe Campaign Standard 建立和發送電子郵件</span><span class="sxs-lookup"><span data-stu-id="1f8ce-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="1f8ce-176">建立電子郵件內容，接著[測試並發送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1f8ce-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text=" Adobe Campaign Standard 中包含續訂優惠的電子郵件範例。":::
