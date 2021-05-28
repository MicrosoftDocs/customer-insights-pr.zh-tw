---
title: Dynamics 365 應用程式的客戶卡片增益集
description: 以此增益集顯示位於 Dynamics 365 應用程式中的對象見解資料。
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059578"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="1d502-103">客戶卡片增益集 (預覽)</span><span class="sxs-lookup"><span data-stu-id="1d502-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1d502-104">直接在 Dynamics 365 應用程式中取得您客戶的 360 度視圖。</span><span class="sxs-lookup"><span data-stu-id="1d502-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="1d502-105">在可支援的 Dynamics 365 應用程式中安裝客戶卡片增益集，您可以選擇顯示人口統計資訊、見解及活動時間軸。</span><span class="sxs-lookup"><span data-stu-id="1d502-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="1d502-106">增益集將從 Customer Insights 擷取資料，對被連接的 Dynamics 365 應用程式，不會影響其中的資料。</span><span class="sxs-lookup"><span data-stu-id="1d502-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1d502-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="1d502-107">Prerequisites</span></span>

- <span data-ttu-id="1d502-108">增益集只適用在 Dynamics 365 模型導向應用程式 (例如 Sales 或 Customer Service)，版本 9.0 或更新的版本。</span><span class="sxs-lookup"><span data-stu-id="1d502-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="1d502-109">為了讓您的 Dynamics 365 資料對應至對象見解客戶個人資料，這些資料需要 [從 Dynamics 365 應用程式使用 Common Data Service 連接器進行內嵌](connect-power-query.md)。</span><span class="sxs-lookup"><span data-stu-id="1d502-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="1d502-110">客戶卡片增益集的 Dynamics 365 使用者全部都必須[新增為](permissions.md)對象見解的使用者，才能查看資料。</span><span class="sxs-lookup"><span data-stu-id="1d502-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="1d502-111">在對象見解中必要有[完成設定的搜尋和篩選功能](search-filter-index.md)才能查詢用來作業的資料。</span><span class="sxs-lookup"><span data-stu-id="1d502-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="1d502-112">每個增益集控制項都依賴對象見解中的特定資料：</span><span class="sxs-lookup"><span data-stu-id="1d502-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="1d502-113">量值控制項：需要 [組態的量值](measures.md)。</span><span class="sxs-lookup"><span data-stu-id="1d502-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="1d502-114">智慧控制項：需要使用[預測](predictions.md)或[自訂模型](custom-models.md)生成資料。</span><span class="sxs-lookup"><span data-stu-id="1d502-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="1d502-115">人口統計控制項：在統整的客戶設定檔中可以使用人口統計欄位 (如年齡或性別)。</span><span class="sxs-lookup"><span data-stu-id="1d502-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="1d502-116">擴充控制項：需要將使用中[擴充內容](enrichment-hub.md)套用至客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="1d502-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="1d502-117">時間表控制項：需要 [已組態的活動](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="1d502-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="1d502-118">安裝客戶卡片增益集</span><span class="sxs-lookup"><span data-stu-id="1d502-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="1d502-119">客戶卡片增益集是 Dynamics 365 中 Customer Engagement 應用程式的解決方案。</span><span class="sxs-lookup"><span data-stu-id="1d502-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="1d502-120">若要安裝此解決方案，請移至 AppSource 並搜尋 **Dynamics Customer 卡片**。</span><span class="sxs-lookup"><span data-stu-id="1d502-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="1d502-121">選取 [AppSource 上的客戶卡片增益集](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)，然後選取 **立即取得**。</span><span class="sxs-lookup"><span data-stu-id="1d502-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="1d502-122">您可能必須使用 Dynamics 365 應用程式的系統管理員認證登入，才能安裝解決方案。</span><span class="sxs-lookup"><span data-stu-id="1d502-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="1d502-123">若要將解決方案安裝到您的環境，可能需要花費一些時間。</span><span class="sxs-lookup"><span data-stu-id="1d502-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="1d502-124">設定客戶卡片增益集</span><span class="sxs-lookup"><span data-stu-id="1d502-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="1d502-125">以系統管理員身分，移至 Dynamics 365 中的 **設定** 區段，然後選取 **解決方案**。</span><span class="sxs-lookup"><span data-stu-id="1d502-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="1d502-126">選取 **Dynamics 365 Customer Insights 客戶卡片增益集 (預覽)** 解決方案的 **顯示名稱** 連結。</span><span class="sxs-lookup"><span data-stu-id="1d502-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1d502-127">![選取顯示名稱](media/select-display-name.png "選取顯示名稱")</span><span class="sxs-lookup"><span data-stu-id="1d502-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="1d502-128">選取 **登入**，然後輸入您用來設定 Customer Insights 的管理帳戶憑證。</span><span class="sxs-lookup"><span data-stu-id="1d502-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1d502-129">請檢查當您選取 **登入** 按鈕時，瀏覽器快顯封鎖程式不會封鎖驗證視窗。</span><span class="sxs-lookup"><span data-stu-id="1d502-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="1d502-130">選取您要從中提取資料的 Customer Insights 環境。</span><span class="sxs-lookup"><span data-stu-id="1d502-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="1d502-131">在 Dynamics 365 應用程式中定義記錄對欄位的對應。</span><span class="sxs-lookup"><span data-stu-id="1d502-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="1d502-132">視 Customer Insights 中的資料而定，您可以選擇對應下列選項：</span><span class="sxs-lookup"><span data-stu-id="1d502-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="1d502-133">若要對應連絡人，請選取客戶實體中符合您的連絡人實體的識別碼欄位。</span><span class="sxs-lookup"><span data-stu-id="1d502-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="1d502-134">若要對應帳戶，請選取客戶實體中符合您的帳戶實體的識別碼欄位。</span><span class="sxs-lookup"><span data-stu-id="1d502-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1d502-135">![連絡人識別碼欄位](media/contact-id-field.png "連絡人識別碼欄位")</span><span class="sxs-lookup"><span data-stu-id="1d502-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="1d502-136">選取 **儲存設定** 以儲存設定。</span><span class="sxs-lookup"><span data-stu-id="1d502-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="1d502-137">接下來，您必須指派 Dynamics 365 中的資訊安全角色，才能讓使用者自訂並查看客戶卡片。</span><span class="sxs-lookup"><span data-stu-id="1d502-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="1d502-138">在 Dynamics 365 中，移至 **設定** > **安全性** > **使用者**。</span><span class="sxs-lookup"><span data-stu-id="1d502-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="1d502-139">選取要編輯使用者角色的使用者，並選取 **管理角色**。</span><span class="sxs-lookup"><span data-stu-id="1d502-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="1d502-140">將 **Customer Insights 卡片自訂員** 角色指派給要為整個組織自訂卡片顯示內容的使用者。</span><span class="sxs-lookup"><span data-stu-id="1d502-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="1d502-141">新增客戶卡片控制項到表單</span><span class="sxs-lookup"><span data-stu-id="1d502-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="1d502-142">若要將客戶卡片控制項新增至您的連絡人表單，請移至 Dynamics 365 中的 **設定** > **自訂**。</span><span class="sxs-lookup"><span data-stu-id="1d502-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="1d502-143">選取 **自訂系統**。</span><span class="sxs-lookup"><span data-stu-id="1d502-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="1d502-144">瀏覽至 **連絡人** 實體，展開它，然後選取 **表單**。</span><span class="sxs-lookup"><span data-stu-id="1d502-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="1d502-145">選取您要新增客戶卡片控制項的連絡人表單。</span><span class="sxs-lookup"><span data-stu-id="1d502-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1d502-146">![選取連絡人表單](media/contact-active-forms.png "選取連絡人表單")</span><span class="sxs-lookup"><span data-stu-id="1d502-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="1d502-147">若要新增控制項，請在表單編輯器中，將 **欄位總管** 中的任何欄位拖曳至要您希望控制項出現的位置。</span><span class="sxs-lookup"><span data-stu-id="1d502-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="1d502-148">選取表單上您剛新增的欄位，然後選取 **變更屬性**。</span><span class="sxs-lookup"><span data-stu-id="1d502-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="1d502-149">移至 **控制項** 索引標籤，然後選取 **新增控制項**。</span><span class="sxs-lookup"><span data-stu-id="1d502-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="1d502-150">選擇其中一個可用的自訂控制項，然後選取 **新增**。</span><span class="sxs-lookup"><span data-stu-id="1d502-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="1d502-151">在 **欄位屬性** 對話方塊中，清除 **顯示表單的標籤** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1d502-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="1d502-152">選取控制項的 **Web** 選項。</span><span class="sxs-lookup"><span data-stu-id="1d502-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="1d502-153">對於擴充控制項，您可以設定 **enrichmentType** 欄位，以選取要顯示的擴充內容類型。</span><span class="sxs-lookup"><span data-stu-id="1d502-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="1d502-154">為每個擴充類型新增擴充控制項。</span><span class="sxs-lookup"><span data-stu-id="1d502-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="1d502-155">選取 **儲存** 和 **發佈** 以發佈更新的連絡人表單。</span><span class="sxs-lookup"><span data-stu-id="1d502-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="1d502-156">移至發行的連絡人表單。</span><span class="sxs-lookup"><span data-stu-id="1d502-156">Go to the published contact form.</span></span> <span data-ttu-id="1d502-157">您會看到最新新增的控制項。</span><span class="sxs-lookup"><span data-stu-id="1d502-157">You'll see the newly added control.</span></span> <span data-ttu-id="1d502-158">您可能需要在第一次使用時登入。</span><span class="sxs-lookup"><span data-stu-id="1d502-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="1d502-159">若要自訂想要在自訂控制項上顯示的內容，請在右上角選取編輯按鈕。</span><span class="sxs-lookup"><span data-stu-id="1d502-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="1d502-160">升級客戶卡片增益集</span><span class="sxs-lookup"><span data-stu-id="1d502-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="1d502-161">客戶卡片增益集不會自動升級。</span><span class="sxs-lookup"><span data-stu-id="1d502-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="1d502-162">若要升級為最新版本，請在已安裝增益集的 Dynamics 365 應用程式中執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="1d502-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="1d502-163">在 Dynamics 365 應用程式中，移至 **設定** > **自訂**，然後選取 **解決方案**。</span><span class="sxs-lookup"><span data-stu-id="1d502-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="1d502-164">在增益集表格中尋找 **CustomerInsightsCustomerCard**，並選取該資料列。</span><span class="sxs-lookup"><span data-stu-id="1d502-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="1d502-165">在動作列中選取 **套用解決方案升級**。</span><span class="sxs-lookup"><span data-stu-id="1d502-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="在 Dynamics 365 應用程式的自訂區域中升級解決方案":::

1. <span data-ttu-id="1d502-167">開始升級程序之後，會顯示載入指標直到升級完成。</span><span class="sxs-lookup"><span data-stu-id="1d502-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="1d502-168">如果不存在可更新的版本，會出現升級錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="1d502-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
