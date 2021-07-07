---
title: 使用 API
description: 使用 API 並瞭解限制。
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304732"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="b967e-103">搭配 Customer Insights API 處理</span><span class="sxs-lookup"><span data-stu-id="b967e-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="b967e-104">Dynamics 365 Customer Insights 提供 API，可根據 Customer Insights 中的資料建立您自己的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b967e-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b967e-105">這些 API 詳細資料會列在 [Customer Insights API 參考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)。</span><span class="sxs-lookup"><span data-stu-id="b967e-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="b967e-106">它們包含有關作業、參數和回應的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="b967e-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="b967e-107">本文說明如何存取 Customer Insights API、建立 Azure 應用程式註冊，以及開始使用可用的用戶端程式庫。</span><span class="sxs-lookup"><span data-stu-id="b967e-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="b967e-108">嘗試使用 Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="b967e-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="b967e-109">[登入](https://home.ci.ai.dynamics.com) Customer Insights。</span><span class="sxs-lookup"><span data-stu-id="b967e-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="b967e-110">如果您尚未訂閱，請 [註冊試用版的 Customer Insights](https://aka.ms/tryci)。</span><span class="sxs-lookup"><span data-stu-id="b967e-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="b967e-111">若要在您的 Customer Insights 環境中啟用 API，請前往 **系統管理** > **權限**。</span><span class="sxs-lookup"><span data-stu-id="b967e-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="b967e-112">您必須具備系統管理員權限才能執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b967e-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="b967e-113">前往 **API** 索引標籤，然後選取 **啟用** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="b967e-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="b967e-114">啟用 API 會為您的執行個體建立 API 要求使用的主要和次要訂閱金鑰。</span><span class="sxs-lookup"><span data-stu-id="b967e-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="b967e-115">您可以選取 **系統管理** > **權限** > **APIs** 的 **重新產生主要** 或 **重新產生次要** 重新產生金鑰。</span><span class="sxs-lookup"><span data-stu-id="b967e-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text=" 啟用 Customer Insights API":::

1. <span data-ttu-id="b967e-117">選取 **探索我們的 API**[試用 API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)。</span><span class="sxs-lookup"><span data-stu-id="b967e-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="b967e-118">選擇 API 作業並選取 **嘗試**。</span><span class="sxs-lookup"><span data-stu-id="b967e-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="b967e-119">在側邊窗格中，將 **授權** 下拉式功能表中的值設為 **隱含**。</span><span class="sxs-lookup"><span data-stu-id="b967e-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="b967e-120">`Authorization` 標頭會以持有人權杖的方式新增。</span><span class="sxs-lookup"><span data-stu-id="b967e-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="b967e-121">將會自動填入您的訂閱金鑰。</span><span class="sxs-lookup"><span data-stu-id="b967e-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="b967e-122">或者新增所有必要的查詢參數。</span><span class="sxs-lookup"><span data-stu-id="b967e-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="b967e-123">滾動到側窗格底端後選取 **傳送**。</span><span class="sxs-lookup"><span data-stu-id="b967e-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="b967e-124">HTTP 回應將很快在下方出現。</span><span class="sxs-lookup"><span data-stu-id="b967e-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="如何測試 API。":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="b967e-126">在 Azure 入口網站建立新的應用程式註冊</span><span class="sxs-lookup"><span data-stu-id="b967e-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="b967e-127">這些步驟可協助您使用委派權限在 Azure 應用程式中開始使用 Customer Insights API。</span><span class="sxs-lookup"><span data-stu-id="b967e-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="b967e-128">請務必先完成[開始使用工作階段](#get-started-trying-the-customer-insights-apis)。</span><span class="sxs-lookup"><span data-stu-id="b967e-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="b967e-129">使用可存取 Customer Insights 資料的帳戶登入 [Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="b967e-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="b967e-130">選取左邊的 **應用程式註冊**。</span><span class="sxs-lookup"><span data-stu-id="b967e-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="b967e-131">選取 **新增註冊** 提供應用程式名稱並選擇帳戶類型。</span><span class="sxs-lookup"><span data-stu-id="b967e-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="b967e-132">或者新增重新導向 URL。</span><span class="sxs-lookup"><span data-stu-id="b967e-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="b967e-133">http://localhost 可足以用來開發本機電腦上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b967e-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="b967e-134">在您的新應用程式註冊上前往 **API 權限**。</span><span class="sxs-lookup"><span data-stu-id="b967e-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="如何在應用程式註冊中設定 API 權限。":::

1. <span data-ttu-id="b967e-136">選取 **新增權限** 並選取側窗格中的 **Customer Insights**。</span><span class="sxs-lookup"><span data-stu-id="b967e-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="b967e-137">在 **權限類型** 中，選取 **委派權限**，然後選取 **user_impersonation** 權限。</span><span class="sxs-lookup"><span data-stu-id="b967e-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="b967e-138">選取 **新增權限**。</span><span class="sxs-lookup"><span data-stu-id="b967e-138">Select **Add permissions**.</span></span> <span data-ttu-id="b967e-139">如果您需要在無使用者登入時存取 API，請查看 [伺服器對伺服器應用程式權限](#server-to-server-application-permissions) 區。</span><span class="sxs-lookup"><span data-stu-id="b967e-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="b967e-140">選取 **授與系統管理員同意...** 完成應用程式註冊。</span><span class="sxs-lookup"><span data-stu-id="b967e-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="b967e-141">您可以使用此應用程式註冊的應用程式/用戶端 ID 註冊 Microsoft 驗證程式庫（MSAL）取得持有人權杖，將您的要求傳送給 API。</span><span class="sxs-lookup"><span data-stu-id="b967e-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="如何授與管理員同意。":::

<span data-ttu-id="b967e-143">如需 MSAL 詳細資訊，請見 [Microsoft 驗證程式庫（MSAL）總覽](/azure/active-directory/develop/msal-overview)。</span><span class="sxs-lookup"><span data-stu-id="b967e-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="b967e-144">如需有關 Azure 中的應用程式註冊的詳細資訊，請參閱[註冊應用程式](/azure/active-directory/develop/quickstart-register-app.md#register-an-application)。</span><span class="sxs-lookup"><span data-stu-id="b967e-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="b967e-145">如需在用戶端程式庫中使用 API 的更多資訊，請參閱[Customer Insights 用戶端程式庫](#customer-insights-client-libraries)。</span><span class="sxs-lookup"><span data-stu-id="b967e-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="b967e-146">伺服器到伺服器應用程式權限</span><span class="sxs-lookup"><span data-stu-id="b967e-146">Server-to-server application permissions</span></span>

<span data-ttu-id="b967e-147">[應用程式註冊區](#create-a-new-app-registration-in-the-azure-portal) 概述如何註冊要求使用者登入驗證的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b967e-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="b967e-148">瞭解如何建立不需要使用者互動並可在伺服器上執行的應用程式註冊。</span><span class="sxs-lookup"><span data-stu-id="b967e-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="b967e-149">在 Azure 入口網站中您的應用程式註冊上，前往 **API 權限**。</span><span class="sxs-lookup"><span data-stu-id="b967e-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="b967e-150">選取 **新增權限**。</span><span class="sxs-lookup"><span data-stu-id="b967e-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="b967e-151">選取 **我的組織使用的 API** 索引標籤，然後從清單中選擇 **Dynamics 365 AI for Customer Insights**。</span><span class="sxs-lookup"><span data-stu-id="b967e-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="b967e-152">在 **權限類型** 中，選取 **應用程式權限**，然後選取 **CustomerInsights.Api.All** 權限。</span><span class="sxs-lookup"><span data-stu-id="b967e-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="b967e-153">選取 **新增權限**。</span><span class="sxs-lookup"><span data-stu-id="b967e-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="b967e-154">返回 **API 權限** 進行應用程式註冊。</span><span class="sxs-lookup"><span data-stu-id="b967e-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="b967e-155">選取 **授與系統管理員同意...** 完成應用程式註冊。</span><span class="sxs-lookup"><span data-stu-id="b967e-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="如何授與管理員同意。":::

1. <span data-ttu-id="b967e-157">若要總結，我們必須將應用程式註冊名稱新增為 Customer Insights 使用者。</span><span class="sxs-lookup"><span data-stu-id="b967e-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="b967e-158">打開 Customer insights，前往 **管理員** > **權限** 並選取 **新增使用者**。</span><span class="sxs-lookup"><span data-stu-id="b967e-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="b967e-159">搜尋您的應用程式註冊名稱，從搜尋結果選取它，然後選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="b967e-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="b967e-160">Customer Insights 用戶端程式庫</span><span class="sxs-lookup"><span data-stu-id="b967e-160">Customer Insights client libraries</span></span>

<span data-ttu-id="b967e-161">本節幫助您開始使用可用於 Customer Insights API 的用戶端程式庫。</span><span class="sxs-lookup"><span data-stu-id="b967e-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="b967e-162">您可以在 [Customer Insights GitHub 頁面](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries)上找到所有的程式庫來原始程式碼和範例應用程式。</span><span class="sxs-lookup"><span data-stu-id="b967e-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="b967e-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="b967e-163">C# NuGet</span></span>

<span data-ttu-id="b967e-164">瞭解如何開始從 NuGet.org 使用 C# 用戶端程式庫。如需更多有關 NuGet 套裝軟體的詳細資訊，請見 [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/)。</span><span class="sxs-lookup"><span data-stu-id="b967e-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="b967e-165">目前此套裝軟體鎖定 netstandard 2.0 和 netcoreapp 2.0 框架為目標。</span><span class="sxs-lookup"><span data-stu-id="b967e-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="b967e-166">將 C# 用戶端程式庫新增到 C# 專案</span><span class="sxs-lookup"><span data-stu-id="b967e-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="b967e-167">在 Visual Studio 中打開您的專案的 **NuGet 套裝程式管理員**。</span><span class="sxs-lookup"><span data-stu-id="b967e-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="b967e-168">搜尋 **Microsoft.Dynamics.CustomerInsights.Api**。</span><span class="sxs-lookup"><span data-stu-id="b967e-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="b967e-169">選取 **安裝**，以便將套裝程式新增到專案。</span><span class="sxs-lookup"><span data-stu-id="b967e-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="b967e-170">或者在 **NuGet 套裝程式管理員主控台** 中執行此命令：`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="b967e-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text=" 將 NuGet 套裝程式新增到 Visual Studio 專案":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="b967e-172">使用 C# 用戶端程式庫</span><span class="sxs-lookup"><span data-stu-id="b967e-172">Use the C# client library</span></span>

1. <span data-ttu-id="b967e-173">使用 [Microsoft 驗證程式庫 (MSAL)](/azure/active-directory/develop/msal-overview) 取得 `AccessToken` 使用現有的 [Azure 應用程式註冊](#create-a-new-app-registration-in-the-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="b967e-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="b967e-174">一旦成功驗證並獲取權杖後，請建構新的或使用現有 `HttpClient`，連同附加的 **DefaultRequestHeaders "授權"** 設定為 **持有人 <access token>** 及 **Ocp-Apim-Subscription-Key** 設定為源自您的 Customer Insights 環境 [**訂閱金鑰**](#get-started-trying-the-customer-insights-apis)。</span><span class="sxs-lookup"><span data-stu-id="b967e-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="b967e-175">請適時重設 **授權** 標頭。</span><span class="sxs-lookup"><span data-stu-id="b967e-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="b967e-176">例如當權杖到期時。</span><span class="sxs-lookup"><span data-stu-id="b967e-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="b967e-177">將此 `HttpClient` 傳遞到 `CustomerInsights` 用戶端的建構過程。</span><span class="sxs-lookup"><span data-stu-id="b967e-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient 範例":::

1. <span data-ttu-id="b967e-179">讓用戶端與「擴充方法」呼叫—例如，`GetAllInstancesAsync`。</span><span class="sxs-lookup"><span data-stu-id="b967e-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="b967e-180">如果偏好存取基礎 `Microsoft.Rest.HttpOperationResponse`，請使用「HTTP 訊息方法」—例如 `GetAllInstancesWithHttpMessagesAsync`。</span><span class="sxs-lookup"><span data-stu-id="b967e-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="b967e-181">回應類型將很有可能是 `object`，因為方法會傳回多種類型 (例如，`IList<InstanceInfo>` 和 `ApiErrorResult`)。</span><span class="sxs-lookup"><span data-stu-id="b967e-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="b967e-182">若要檢查傳回類型，您可以將物件安全轉換成 [API 詳細資料頁面](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) 上指定的回應類型。</span><span class="sxs-lookup"><span data-stu-id="b967e-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="b967e-183">如果需要更多要求資訊，請使用 **HTTP 訊息方法** 存取原始回應物件。</span><span class="sxs-lookup"><span data-stu-id="b967e-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="b967e-184">NodeJS 套件</span><span class="sxs-lookup"><span data-stu-id="b967e-184">NodeJS package</span></span>

<span data-ttu-id="b967e-185">可透過 NPM 使用 NodeJS 用戶端程式庫：https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="b967e-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="b967e-186">Python 套件</span><span class="sxs-lookup"><span data-stu-id="b967e-186">Python package</span></span>

<span data-ttu-id="b967e-187">可透過 PyPi 使用 Python 用戶端程式庫：https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="b967e-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
