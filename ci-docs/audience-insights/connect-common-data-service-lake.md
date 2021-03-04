---
title: 連接到 Common Data Service 管理湖中的實體
description: 從 Common Data Service 受管理的資料湖匯入資料。
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267796"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="fe902-103">連線至 Common Data Service 受管理資料湖中的資料</span><span class="sxs-lookup"><span data-stu-id="fe902-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="fe902-104">本文提供有關現有 Dynamics 365 客戶如何在 Common Data Service 受管理的資料湖中快速連接至其分析實體的資訊。</span><span class="sxs-lookup"><span data-stu-id="fe902-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="fe902-105">您必須是 Common Data Service 組織的系統管理員，才能繼續執行並查看受管理的資料湖中提供的實體清單。</span><span class="sxs-lookup"><span data-stu-id="fe902-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="fe902-106">重要考量</span><span class="sxs-lookup"><span data-stu-id="fe902-106">Important considerations</span></span>

<span data-ttu-id="fe902-107">儲存在線上服務 (例如 Azure Data Lake Storage) 的資料可能會儲存在與處理資料所在位置不同的位置或儲存在 Dynamics 365 Customer Insights 中。</span><span class="sxs-lookup"><span data-stu-id="fe902-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="fe902-108">匯入或連接至儲存在線上服務的資料，即表示您同意可以將資料傳輸或儲存至 Dynamics 365 Customer Insights。 [在 Microsoft 信任中心深入了解。](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="fe902-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="fe902-109">連接至 Common Data Service 受管理的資料湖</span><span class="sxs-lookup"><span data-stu-id="fe902-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="fe902-110">在對象見解中，前往 **資料** > **資料來源**。</span><span class="sxs-lookup"><span data-stu-id="fe902-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="fe902-111">選取 **新增資料來源**。</span><span class="sxs-lookup"><span data-stu-id="fe902-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="fe902-112">選取 **連接至 Common Data Service**，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="fe902-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="fe902-113">輸入資料來源的 **名稱**，然後選取 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="fe902-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="fe902-114">命名方針：</span><span class="sxs-lookup"><span data-stu-id="fe902-114">Name guidelines:</span></span> 
   - <span data-ttu-id="fe902-115">名稱必須以字母開頭。</span><span class="sxs-lookup"><span data-stu-id="fe902-115">Start with a letter.</span></span>
   - <span data-ttu-id="fe902-116">只能使用字母和數字。</span><span class="sxs-lookup"><span data-stu-id="fe902-116">Use letters and numbers only.</span></span> <span data-ttu-id="fe902-117">不可以使用空格和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="fe902-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="fe902-118">接受 3 到 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="fe902-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="fe902-119">提供 Common Data Service 組織的 **伺服器位址**，並選取 **登入**。</span><span class="sxs-lookup"><span data-stu-id="fe902-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fe902-120">![用來輸入 Common Data Service 伺服器位址的對話方塊](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="fe902-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="fe902-121">從可用清單選取要內嵌的實體。</span><span class="sxs-lookup"><span data-stu-id="fe902-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="fe902-122">如果已選取一些實體，則其他 Dynamics 365 應用程式 (例如 Dynamics 365 Sales Insights 或 Customer Service Insights) 可能會使用這些實體。</span><span class="sxs-lookup"><span data-stu-id="fe902-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="fe902-123">您無法變更此選取項目。</span><span class="sxs-lookup"><span data-stu-id="fe902-123">You can't change the selection.</span></span> <span data-ttu-id="fe902-124">建立資料來源之後，就可以使用這些實體。</span><span class="sxs-lookup"><span data-stu-id="fe902-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fe902-125">![顯示 Common Data Service 組織中實體清單的對話方塊](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="fe902-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="fe902-126">儲存您的選取項目，開始將選取的實體同步處理至 Common Data Service 受管理的資料湖。</span><span class="sxs-lookup"><span data-stu-id="fe902-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="fe902-127">您會在 **資料來源** 頁面上找到最近新增的連接。</span><span class="sxs-lookup"><span data-stu-id="fe902-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="fe902-128">這會排入佇列等待重新整理，並在同步處理所有實體之前，將實體計數顯示為 0。</span><span class="sxs-lookup"><span data-stu-id="fe902-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="fe902-129">只有一個環境的資料來源可同時使用同一個 Common Data Service 管理湖。</span><span class="sxs-lookup"><span data-stu-id="fe902-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="fe902-130">編輯 Common Data Service 受管理的資料湖資料來源</span><span class="sxs-lookup"><span data-stu-id="fe902-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="fe902-131">只有在建立資料來源之後，才可以編輯實體選取項目。</span><span class="sxs-lookup"><span data-stu-id="fe902-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="fe902-132">例如，如果已將其他實體新增至 Common Data Service，但您也想要將這些實體匯入時。</span><span class="sxs-lookup"><span data-stu-id="fe902-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="fe902-133">若要連接至不同的 Common Data Service，請[建立新的資料來源](#connect-to-a-common-data-service-managed-lake)。</span><span class="sxs-lookup"><span data-stu-id="fe902-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="fe902-134">在對象見解中，前往 **資料** > **資料來源**。</span><span class="sxs-lookup"><span data-stu-id="fe902-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="fe902-135">在您想要更新的資料來源旁邊，選取省略符號。</span><span class="sxs-lookup"><span data-stu-id="fe902-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="fe902-136">從清單中選取 **編輯** 選項。</span><span class="sxs-lookup"><span data-stu-id="fe902-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="fe902-137">從可用實體清單選取額外實體，然後選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="fe902-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]