---
title: 安裝和組態客戶卡片增益集
description: 安裝及設定 Dynamics 365 Customer Insights 客戶卡片增益集。
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268034"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="7c702-103">客戶卡片增益集 (預覽)</span><span class="sxs-lookup"><span data-stu-id="7c702-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7c702-104">直接在 Dynamics 365 應用程式中取得您客戶的 360 度視圖。</span><span class="sxs-lookup"><span data-stu-id="7c702-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="7c702-105">透過客戶卡片增益集查看人口統計、見解及活動時間表。</span><span class="sxs-lookup"><span data-stu-id="7c702-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7c702-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="7c702-106">Prerequisites</span></span>

- <span data-ttu-id="7c702-107">已啟用整合介面的 Dynamics 365 應用程式 (例如銷售中心或客戶服務中心) 9.0 版及更新版本。</span><span class="sxs-lookup"><span data-stu-id="7c702-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="7c702-108">[從使用 Common Data Service](connect-power-query.md) 的 Dynamics 365 應用程式內嵌的客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="7c702-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="7c702-109">客戶卡片增益集使用者在對象見解中必須 [新增為使用者](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="7c702-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="7c702-110">[組態的搜尋和篩選功能](search-filter-index.md)。</span><span class="sxs-lookup"><span data-stu-id="7c702-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="7c702-111">人口統計控制項：在統整的客戶設定檔中可以使用人口統計欄位 (如年齡或性別)。</span><span class="sxs-lookup"><span data-stu-id="7c702-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="7c702-112">擴充控制項：需要將使用中[擴充內容](enrichment-hub.md)套用至客戶設定檔。</span><span class="sxs-lookup"><span data-stu-id="7c702-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="7c702-113">智慧控制項：需要使用 Azure Machine Learning ([預測](predictions.md) 或 [自訂模型](custom-models.md)) 產生的資料</span><span class="sxs-lookup"><span data-stu-id="7c702-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="7c702-114">量值控制項：需要 [組態的量值](measures.md)。</span><span class="sxs-lookup"><span data-stu-id="7c702-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="7c702-115">時間表控制項：需要 [已組態的活動](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="7c702-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="7c702-116">安裝客戶卡片增益集</span><span class="sxs-lookup"><span data-stu-id="7c702-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="7c702-117">客戶卡片增益集是 Dynamics 365 中 Customer Engagement 應用程式的解決方案。</span><span class="sxs-lookup"><span data-stu-id="7c702-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="7c702-118">若要安裝此解決方案，請移至 AppSource 並搜尋 **Dynamics Customer 卡片**。</span><span class="sxs-lookup"><span data-stu-id="7c702-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="7c702-119">選取 [AppSource 上的客戶卡片增益集](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)，然後選取 **立即取得**。</span><span class="sxs-lookup"><span data-stu-id="7c702-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="7c702-120">您可能必須使用 Dynamics 365 應用程式的系統管理員認證登入，才能安裝解決方案。</span><span class="sxs-lookup"><span data-stu-id="7c702-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="7c702-121">若要將解決方案安裝到您的環境，可能需要花費一些時間。</span><span class="sxs-lookup"><span data-stu-id="7c702-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="7c702-122">設定客戶卡片增益集</span><span class="sxs-lookup"><span data-stu-id="7c702-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="7c702-123">以系統管理員身分，移至 Dynamics 365 中的 **設定** 區段，然後選取 **解決方案**。</span><span class="sxs-lookup"><span data-stu-id="7c702-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="7c702-124">選取 **Dynamics 365 Customer Insights 客戶卡片增益集 (預覽)** 解決方案的 **顯示名稱** 連結。</span><span class="sxs-lookup"><span data-stu-id="7c702-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c702-125">![選取顯示名稱](media/select-display-name.png "選取顯示名稱")</span><span class="sxs-lookup"><span data-stu-id="7c702-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="7c702-126">選取 **登入**，然後輸入您用來設定 Customer Insights 的管理帳戶憑證。</span><span class="sxs-lookup"><span data-stu-id="7c702-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7c702-127">請檢查當您選取 **登入** 按鈕時，瀏覽器快顯封鎖程式不會封鎖驗證視窗。</span><span class="sxs-lookup"><span data-stu-id="7c702-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="7c702-128">選取您要擷取資料的環境。</span><span class="sxs-lookup"><span data-stu-id="7c702-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="7c702-129">定義對應 Dynamics 365 應用程式記錄的欄位。</span><span class="sxs-lookup"><span data-stu-id="7c702-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="7c702-130">若要對應連絡人，請選取客戶實體中符合您的連絡人實體的識別碼欄位。</span><span class="sxs-lookup"><span data-stu-id="7c702-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="7c702-131">若要對應帳戶，請選取客戶實體中符合您的帳戶實體的識別碼欄位。</span><span class="sxs-lookup"><span data-stu-id="7c702-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c702-132">![連絡人識別碼欄位](media/contact-id-field.png "連絡人識別碼欄位")</span><span class="sxs-lookup"><span data-stu-id="7c702-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="7c702-133">選取 **儲存設定** 以儲存設定。</span><span class="sxs-lookup"><span data-stu-id="7c702-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="7c702-134">接下來，您必須指派 Dynamics 365 中的資訊安全角色，才能讓使用者自訂並查看客戶卡片。</span><span class="sxs-lookup"><span data-stu-id="7c702-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="7c702-135">在 Dynamics 365 中，移至 **設定** > **安全性** > **使用者**。</span><span class="sxs-lookup"><span data-stu-id="7c702-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="7c702-136">選取要編輯使用者角色的使用者，並選取 **管理角色**。</span><span class="sxs-lookup"><span data-stu-id="7c702-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="7c702-137">將 **Customer Insights 卡片自訂員** 角色指派給要為整個組織自訂卡片顯示內容的使用者。</span><span class="sxs-lookup"><span data-stu-id="7c702-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="7c702-138">新增客戶卡片控制項到表單</span><span class="sxs-lookup"><span data-stu-id="7c702-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="7c702-139">若要將客戶卡片控制項新增至您的連絡人表單，請移至 Dynamics 365 中的 **設定** > **自訂**。</span><span class="sxs-lookup"><span data-stu-id="7c702-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="7c702-140">選取 **自訂系統**。</span><span class="sxs-lookup"><span data-stu-id="7c702-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="7c702-141">瀏覽至 **連絡人** 實體，展開它，然後選取 **表單**。</span><span class="sxs-lookup"><span data-stu-id="7c702-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="7c702-142">選取您要新增客戶卡片控制項的連絡人表單。</span><span class="sxs-lookup"><span data-stu-id="7c702-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7c702-143">![選取連絡人表單](media/contact-active-forms.png "選取連絡人表單")</span><span class="sxs-lookup"><span data-stu-id="7c702-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="7c702-144">若要新增控制項，請在表單編輯器中，將 **欄位總管** 中的任何欄位拖曳至要您希望控制項出現的位置。</span><span class="sxs-lookup"><span data-stu-id="7c702-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="7c702-145">選取表單上您剛新增的欄位，然後選取 **變更屬性**。</span><span class="sxs-lookup"><span data-stu-id="7c702-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="7c702-146">移至 **控制項** 索引標籤，然後選取 **新增控制項**。</span><span class="sxs-lookup"><span data-stu-id="7c702-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="7c702-147">選擇其中一個可用的自訂控制項，然後選取 **新增**。</span><span class="sxs-lookup"><span data-stu-id="7c702-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="7c702-148">在 **欄位屬性** 對話方塊中，清除 **顯示表單的標籤** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7c702-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="7c702-149">選取控制項的 **Web** 選項。</span><span class="sxs-lookup"><span data-stu-id="7c702-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="7c702-150">對於擴充控制項，您可以設定 **enrichmentType** 欄位，以選取要顯示的擴充內容類型。</span><span class="sxs-lookup"><span data-stu-id="7c702-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="7c702-151">為每個擴充類型新增擴充控制項。</span><span class="sxs-lookup"><span data-stu-id="7c702-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="7c702-152">選取 **儲存** 和 **發佈** 以發佈更新的連絡人表單。</span><span class="sxs-lookup"><span data-stu-id="7c702-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="7c702-153">移至發行的連絡人表單。</span><span class="sxs-lookup"><span data-stu-id="7c702-153">Go to the published contact form.</span></span> <span data-ttu-id="7c702-154">您會看到最新新增的控制項。</span><span class="sxs-lookup"><span data-stu-id="7c702-154">You'll see the newly added control.</span></span> <span data-ttu-id="7c702-155">您可能需要在第一次使用時登入。</span><span class="sxs-lookup"><span data-stu-id="7c702-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="7c702-156">若要自訂想要在自訂控制項上顯示的內容，請在右上角選取編輯按鈕。</span><span class="sxs-lookup"><span data-stu-id="7c702-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="7c702-157">升級客戶卡片增益集</span><span class="sxs-lookup"><span data-stu-id="7c702-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="7c702-158">客戶卡片增益集不會自動升級。</span><span class="sxs-lookup"><span data-stu-id="7c702-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="7c702-159">若要升級為最新版本，請在已安裝增益集的 Dynamics 365 應用程式中執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="7c702-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="7c702-160">在 Dynamics 365 應用程式中，移至 **設定** > **自訂**，然後選取 **解決方案**。</span><span class="sxs-lookup"><span data-stu-id="7c702-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="7c702-161">在增益集表格中尋找 **CustomerInsightsCustomerCard**，並選取該資料列。</span><span class="sxs-lookup"><span data-stu-id="7c702-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="7c702-162">在動作列中選取 **套用解決方案升級**。</span><span class="sxs-lookup"><span data-stu-id="7c702-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="在 Dynamics 365 應用程式的自訂區域中升級解決方案":::

1. <span data-ttu-id="7c702-164">開始升級程序之後，會顯示載入指標直到升級完成。</span><span class="sxs-lookup"><span data-stu-id="7c702-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="7c702-165">如果不存在可更新的版本，會出現升級錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7c702-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]