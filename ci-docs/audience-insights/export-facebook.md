---
title: 匯出 Customer Insights 資料到 Facebook Ads Manager
description: 了解如何設定與 Facebook 廣告管理員的連接。
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643673"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="dcca8-103">適用於 Facebook 廣告管理員的連接器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="dcca8-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="dcca8-104">將統一客戶設定檔的區段匯出至 Facebook 廣告管理員，以建立 Facebook 和 Instagram 上的行銷活動。</span><span class="sxs-lookup"><span data-stu-id="dcca8-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dcca8-105">先決條件</span><span class="sxs-lookup"><span data-stu-id="dcca8-105">Prerequisites</span></span>

- <span data-ttu-id="dcca8-106">您必須具有包括 [**Facebook 商業帳戶**](https://business.facebook.com/) 的 [**Facebook 廣告帳戶**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)。</span><span class="sxs-lookup"><span data-stu-id="dcca8-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="dcca8-107">您在 [**Facebook 廣告帳戶**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) 上必須是管理員身份。</span><span class="sxs-lookup"><span data-stu-id="dcca8-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="dcca8-108">連接至 Facebook 廣告管理員</span><span class="sxs-lookup"><span data-stu-id="dcca8-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="dcca8-109">移至 **管理員** > **匯出目的地**。</span><span class="sxs-lookup"><span data-stu-id="dcca8-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dcca8-110">在 **Facebook 廣告管理員** 底下，選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="dcca8-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="dcca8-111">在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。</span><span class="sxs-lookup"><span data-stu-id="dcca8-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="dcca8-112">選取 **繼續使用 Facebook** 登入您的 Facebook 廣告帳戶。</span><span class="sxs-lookup"><span data-stu-id="dcca8-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="dcca8-113">使用 Facebook 驗證之後，允許 **ads_management** 權限。</span><span class="sxs-lookup"><span data-stu-id="dcca8-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="dcca8-114">選取您要使用的 **Facebook 廣告帳戶**。</span><span class="sxs-lookup"><span data-stu-id="dcca8-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="dcca8-115">從下拉式清單選取 **現有的自訂對象**，或建立 **新的自訂對象**。</span><span class="sxs-lookup"><span data-stu-id="dcca8-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="dcca8-116">如需詳細資訊，請參閱 [**Facebook 廣告管理員中的對象**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)。</span><span class="sxs-lookup"><span data-stu-id="dcca8-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="dcca8-117">選取 **我同意** 以確認 **資料隱私權與合規性**。</span><span class="sxs-lookup"><span data-stu-id="dcca8-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dcca8-118">選取 **下一步** 以設定匯出。</span><span class="sxs-lookup"><span data-stu-id="dcca8-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="dcca8-119">設定連接器</span><span class="sxs-lookup"><span data-stu-id="dcca8-119">Configure the connector</span></span>

1. <span data-ttu-id="dcca8-120">在 **選擇金鑰識別元欄位** 中，選取要傳送給 Facebook 廣告管理員的 **電子郵件**、**姓名和地址** 或 **電話**。</span><span class="sxs-lookup"><span data-stu-id="dcca8-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="dcca8-121">從您的統一客戶實體中對應所選金鑰識別元的相應屬性。</span><span class="sxs-lookup"><span data-stu-id="dcca8-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="dcca8-122">[提示] 如果您選取 **電子郵件** 做為金鑰識別元，則最有可能找到有相符項目。</span><span class="sxs-lookup"><span data-stu-id="dcca8-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="dcca8-123">新增其他識別元可能會改善比對情況。</span><span class="sxs-lookup"><span data-stu-id="dcca8-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="dcca8-124">選取 **新增屬性** 以對應要傳送至 Facebook 廣告管理員的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="dcca8-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="dcca8-125">Facebook 廣告管理員中的屬性將會對應至下列使用者易記的名稱：**FN** = **名字**、**LN** = **姓氏**、**FI** = **名字首字母**、**PHONE** = **電話**、**GEN** = **性別**、**DOB** = **出生日期**、**ST** = **縣/市**、**CT** = **市/鎮**、**ZIP** = **郵遞區號**、**COUNTRY** = **國家/地區**</span><span class="sxs-lookup"><span data-stu-id="dcca8-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="dcca8-126">選取您要匯出的客戶細分。</span><span class="sxs-lookup"><span data-stu-id="dcca8-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="dcca8-127">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="dcca8-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dcca8-128">匯出資料</span><span class="sxs-lookup"><span data-stu-id="dcca8-128">Export the data</span></span>

<span data-ttu-id="dcca8-129">您可以[視需要匯出資料](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="dcca8-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="dcca8-130">匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。</span><span class="sxs-lookup"><span data-stu-id="dcca8-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dcca8-131">資料隱私權與合規性</span><span class="sxs-lookup"><span data-stu-id="dcca8-131">Data privacy and compliance</span></span>

<span data-ttu-id="dcca8-132">當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Facebook Ads Manager 時，您允許在 Dynamics 365 Customer Insights 合規性邊界之外傳輸資料，包括潛在敏感性資料如個人資料。</span><span class="sxs-lookup"><span data-stu-id="dcca8-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dcca8-133">Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Facebook 廣告符合您可能應盡的任何隱私權或資訊安全義務。</span><span class="sxs-lookup"><span data-stu-id="dcca8-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="dcca8-134">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="dcca8-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dcca8-135">您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此匯出目的地，以便不再繼續使用此功能。</span><span class="sxs-lookup"><span data-stu-id="dcca8-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
