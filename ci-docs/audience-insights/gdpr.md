---
title: 符合 GDPR 的資料主體權利 (DSR) 要求 | Microsoft Docs
description: 回應資料主旨對 Dynamics 365 Customer Insights 對象見解能力的要求。
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268676"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="6bef2-103">符合 GDPR 的資料主體權利 (DSR) 要求</span><span class="sxs-lookup"><span data-stu-id="6bef2-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="6bef2-104">回應 GDPR 資料主旨刪除對 Dynamics 365 Customer Insights 對象見解能力的要求</span><span class="sxs-lookup"><span data-stu-id="6bef2-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="6bef2-105">從組織的客戶資料移除個人資料的「刪除權」是一般資料保護規定 (GDPR) 中的一項重要保護。</span><span class="sxs-lookup"><span data-stu-id="6bef2-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="6bef2-106">移除個人資料包括移除所有個人資料以及系統產生的日誌，但不包括稽核記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="6bef2-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="6bef2-107">管理資料主體刪除要求</span><span class="sxs-lookup"><span data-stu-id="6bef2-107">Manage data subject delete requests</span></span>

<span data-ttu-id="6bef2-108">對象見解提供下列產品內經驗，以刪除特定顧客或使用者的個人資料：</span><span class="sxs-lookup"><span data-stu-id="6bef2-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="6bef2-109">**管理客戶資料的刪除要求**：Customer Insights 中的客戶資料擷取自 Customer Insights 之外的原始資料來源。</span><span class="sxs-lookup"><span data-stu-id="6bef2-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="6bef2-110">所有的 GDPR 刪除要求都必須在原始資料來源中執行。</span><span class="sxs-lookup"><span data-stu-id="6bef2-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="6bef2-111">**管理 Customer Insights 使用者資料的刪除要求**：使用者資料透過 Customer Insights 建立。</span><span class="sxs-lookup"><span data-stu-id="6bef2-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="6bef2-112">所有的 GDPR 刪除要求都必須在 Customer Insights 中執行。</span><span class="sxs-lookup"><span data-stu-id="6bef2-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="6bef2-113">管理客戶資料的刪除要求</span><span class="sxs-lookup"><span data-stu-id="6bef2-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="6bef2-114">Customer Insights 管理員可以依照下列步驟移除已在資料來源中刪除的客戶資料：</span><span class="sxs-lookup"><span data-stu-id="6bef2-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="6bef2-115">登入 Dynamics 365 Customer Insights。</span><span class="sxs-lookup"><span data-stu-id="6bef2-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="6bef2-116">在對象見解中，前往 **資料** > **資料來源**</span><span class="sxs-lookup"><span data-stu-id="6bef2-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="6bef2-117">對於清單中每個包含已刪除之客戶資料的資料來源：</span><span class="sxs-lookup"><span data-stu-id="6bef2-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="6bef2-118">選取 (...)，然後選取 **重新整理**。</span><span class="sxs-lookup"><span data-stu-id="6bef2-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="6bef2-119">檢查 **狀態** 下的資料來源狀態。</span><span class="sxs-lookup"><span data-stu-id="6bef2-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="6bef2-120">核取記號表示已成功地進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="6bef2-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="6bef2-121">警告三角形表示發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6bef2-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="6bef2-122">如果顯示警告三角形，請聯繫 D365CI@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="6bef2-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6bef2-123">![處理客戶資料的 GDPR 刪除要求](media/gdpr-data-sources.png "處理客戶資料的 GDPR 刪除要求")</span><span class="sxs-lookup"><span data-stu-id="6bef2-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="6bef2-124">管理對使用者資料的刪除要求</span><span class="sxs-lookup"><span data-stu-id="6bef2-124">Manage delete requests for user data</span></span>

<span data-ttu-id="6bef2-125">Customer Insights 管理員可以依照下列步驟來刪除 Customer Insights 使用者資料：</span><span class="sxs-lookup"><span data-stu-id="6bef2-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="6bef2-126">登入 Dynamics 365 Customer Insights。</span><span class="sxs-lookup"><span data-stu-id="6bef2-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="6bef2-127">在對象見解中，前往 **管理員** > **權限**。</span><span class="sxs-lookup"><span data-stu-id="6bef2-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="6bef2-128">選取您要刪除之使用者的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6bef2-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="6bef2-129">選取 **移除**。</span><span class="sxs-lookup"><span data-stu-id="6bef2-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6bef2-130">![處理 GDPR 對使用者資料的刪除要求](media/gdpr-permissions.png "處理 GDPR 對使用者資料的刪除要求")</span><span class="sxs-lookup"><span data-stu-id="6bef2-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="6bef2-131">回應 GDPR 資料主旨匯出要求</span><span class="sxs-lookup"><span data-stu-id="6bef2-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="6bef2-132">我們致力於讓您符合一般資料保護規定 (GDPR) 的規範，因此我們開發了可協助您進行準備的文件。</span><span class="sxs-lookup"><span data-stu-id="6bef2-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="6bef2-133">本文件描述當您使用對象見解時，您可以馬上採用以支援 GDPR 合規性的步驟。</span><span class="sxs-lookup"><span data-stu-id="6bef2-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="6bef2-134">管理匯出和檢視要求</span><span class="sxs-lookup"><span data-stu-id="6bef2-134">Manage export and view requests</span></span>

<span data-ttu-id="6bef2-135">「資料可攜權」讓資料主體可要求其個人資料的電子格式 (「結構化、通用、機器可讀取及可互通的格式」) 複本，以便傳送至另一個資料控制器。</span><span class="sxs-lookup"><span data-stu-id="6bef2-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="6bef2-136">匯出客戶資料 (用戶管理員)</span><span class="sxs-lookup"><span data-stu-id="6bef2-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="6bef2-137">用戶管理員可遵循下列步驟來匯出資料：</span><span class="sxs-lookup"><span data-stu-id="6bef2-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="6bef2-138">傳送電子郵件至 D365CI@microsoft.com，在要求中指定客戶的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6bef2-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="6bef2-139">Customer Insights 團隊會傳送電子郵件給已註冊的租用戶管理員電子郵件地址，要求確認匯出資料。</span><span class="sxs-lookup"><span data-stu-id="6bef2-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="6bef2-140">認可匯出所要求之客戶資料的確認。</span><span class="sxs-lookup"><span data-stu-id="6bef2-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="6bef2-141">透過用戶管理員電子郵件地址接收匯出的資料。</span><span class="sxs-lookup"><span data-stu-id="6bef2-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="6bef2-142">匯出使用者資料 (租用戶管理員)</span><span class="sxs-lookup"><span data-stu-id="6bef2-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="6bef2-143">傳送電子郵件至 D365CI@microsoft.com，在要求中指定使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6bef2-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="6bef2-144">Customer Insights 團隊會傳送電子郵件給已註冊的租用戶管理員電子郵件地址，要求確認匯出資料。</span><span class="sxs-lookup"><span data-stu-id="6bef2-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="6bef2-145">認可匯出所要求之使用者資料的確認。</span><span class="sxs-lookup"><span data-stu-id="6bef2-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="6bef2-146">透過用戶管理員電子郵件地址接收匯出的資料。</span><span class="sxs-lookup"><span data-stu-id="6bef2-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]