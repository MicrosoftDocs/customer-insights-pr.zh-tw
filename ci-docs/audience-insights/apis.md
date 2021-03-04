---
title: 使用 API
description: 使用 API 並瞭解限制。
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267514"
---
# <a name="work-with-customer-insights-apis"></a>搭配 Customer Insights API 處理

Dynamics 365 Customer Insights 提供 API，根據您在 Customer Insights 中的資料建立您自己的應用程式。

> [!IMPORTANT]
> 這些 API 詳細資料會列在 [Customer Insights API 參考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)。 它們包含有關作業、參數和回應的其他資訊。

本文章引導您存取 Customer Insights API、建立 Azure 應用程式註冊功能並協助您開始使用可用的用戶端程式庫。

## <a name="get-started-trying-the-customer-insights-apis"></a>嘗試使用 Customer Insights API

1. [登入](https://home.ci.ai.dynamics.com) Customer Insights。 如果您尚未訂閱，請 [註冊試用版的 Customer Insights](https://aka.ms/tryci)。

1. 若要在您的 Customer Insights 環境中啟用 API，請前往 **系統管理** > **權限**。 您必須具備系統管理員權限才能執行此動作。

1. 前往 **API** 索引標籤，然後選取 **啟用** 按鈕。    
   啟用 API 會為您的執行個體建立 API 要求使用的主要和次要訂閱金鑰。 您可以選取 **系統管理** > **權限** > **APIs** 的 **重新產生主要** 或 **重新產生次要** 重新產生金鑰。

   :::image type="content" source="media/enable-apis.gif" alt-text=" 啟用 Customer Insights API":::

1. 選取 **探索我們的 API** 試用 API。

1. 選擇 API 作業並選取 **嘗試**。

1. 在側面窗格中將 **授權** 下拉式功能表中的值設為 **隱性**。 `Authorization` 標頭與新增的持有人權杖一起使用。 將會自動填入您的訂閱金鑰。
  
1. 或者新增所有必要的查詢參數。

1. 滾動到側窗格底端後選取 **傳送**。

HTTP 回應將很快在下方出現。

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>在 Azure 入口網站建立新的應用程式註冊

這些步驟可幫助您開始在使用委派權限的 Azure 應用程式中使用 Customer Insights API。 請確定先完成 [開始使用區](#get-started-trying-the-customer-insights-apis)。

1. 使用可存取 Customer Insights 資料的帳戶登入 [Azure 入口網站](https://portal.azure.com)。

1. 選取左邊的 **應用程式註冊**。

1. 選取 **新增註冊** 提供應用程式名稱並選擇帳戶類型。
   或者新增重新導向 URL。 http://localhost 可足以用來開發本機電腦上的應用程式。

1. 在您的新應用程式註冊上前往 **API 權限**。

1. 選取 **新增權限** 並選取側窗格中的 **Customer Insights**。

1. **權限類型** 方面，請選取 **委派權限** 並選取 **使用者模擬** 權限。

1. 選取 **新增權限**。 如果您需要在無使用者登入時存取 API，請查看 [伺服器對伺服器應用程式權限](#server-to-server-application-permissions) 區。

1. 選取 **授與系統管理員同意...** 完成應用程式註冊。

您可以使用此應用程式註冊的應用程式/用戶端 ID 註冊 Microsoft 驗證程式庫（MSAL）取得持有人權杖，將您的要求傳送給 API。

如需 MSAL 詳細資訊，請見 [Microsoft 驗證程式庫（MSAL）總覽](https://docs.microsoft.com/azure/active-directory/develop/msal-overview)。

如需有關 Azure 中的應用程式註冊詳細資訊，請見 [新 Azure 入口網站應用程式註冊體驗](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide)。

如需使用 API（我們的用戶端程式庫）資訊，請見 [Customer Insights 用戶端程式庫](#customer-insights-client-libraries)。

### <a name="server-to-server-application-permissions"></a>伺服器到伺服器應用程式權限

[應用程式註冊區](#create-a-new-app-registration-in-the-azure-portal) 概述如何註冊要求使用者登入驗證的應用程式。 瞭解如何建立不需要使用者互動並可在伺服器上執行的應用程式註冊。

1. 在 Azure 入口網站中您的應用程式註冊上，前往 **API 權限**。

1. 選取 **新增權限** 並選取側窗格中的 **Customer Insights**。

1. **權限類型** 方面，請選取 **應用程式權限** 並選取 **CustomerInsights.Api.All** 權限。

1. 選取 **新增權限**。

1. 若要對此應用程式權限給予系統管理員同意，您必須新增服務主體。

   1. 安裝 Azure Active Directory (AD) PowerShell 模組：`Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. 連線到您的 AD 帳戶: `Connect-AzureAD -TenantId <your tenant id>`。 您可以在 **總覽** > **Azure Active Directory** 上找到您的租用戶 ID。
   1. 執行下列命令新增 Azure AD 服務主體：`New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` 與 Customer Insights API 應用程式相關的 AppId 參數。

   :::image type="content" source="media/azureAD-service-principal.png" alt-text=" 服務主體範例":::

1. 返回 **API 權限** 進行應用程式註冊。

1. 選取 **授與系統管理員同意...** 完成應用程式註冊。

1. 若要總結，我們必須將應用程式註冊名稱新增為 Customer Insights 使用者。    
   打開 Customer insights，前往 **管理員** > **權限** 並選取 **新增使用者**。

1. 搜尋您的應用程式註冊名稱，從搜尋結果選取它，然後選取 **儲存**。

## <a name="customer-insights-client-libraries"></a>Customer Insights 用戶端程式庫

本節幫助您開始使用可用於 Customer Insights API 的用戶端程式庫。

### <a name="c-nuget"></a>C# NuGet

瞭解如何開始從 NuGet.org 使用 C# 用戶端程式庫。如需更多有關 NuGet 套裝軟體的詳細資訊，請見 [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/)。 目前此套裝軟體鎖定 netstandard 2.0 和 netcoreapp 2.0 框架為目標。

#### <a name="add-the-c-client-library-to-a-c-project"></a>將 C# 用戶端程式庫新增到 C# 專案

1. 在 Visual Studio 中打開您的專案的 **NuGet 套裝程式管理員**。

1. 搜尋 **Microsoft.Dynamics.CustomerInsights.Api**。

1. 選取 **安裝**，以便將套裝程式新增到專案。
   或者在 **NuGet 套裝程式管理員主控台** 中執行此命令：`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text=" 將 NuGet 套裝程式新增到 Visual Studio 專案":::

#### <a name="use-the-c-client-library"></a>使用 C# 用戶端程式庫

1. 使用 [Microsoft 驗證程式庫 (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) 取得 `AccessToken` 使用現有的 [Azure 應用程式註冊](#create-a-new-app-registration-in-the-azure-portal)。

1. 一旦成功驗證並獲取權杖後，請建構新的或使用現有 `HttpClient`，連同附加的 **DefaultRequestHeaders "授權"** 設定為 **持有人 <access token>** 及 **Ocp-Apim-Subscription-Key** 設定為源自您的 Customer Insights 環境 [**訂閱金鑰**](#get-started-trying-the-customer-insights-apis)。    
   請適時重設 **授權** 標頭。 例如當權杖到期時。

1. 將此 `HttpClient` 傳遞到 `CustomerInsights` 用戶端的建構過程。

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient 範例":::

1. 讓用戶端與「擴充方法」通話，例如，`GetAllInstancesAsync`。 如果您偏愛存取基礎 `Microsoft.Rest.HttpOperationResponse`，請使用「HTTP 訊息方法」，例如 `GetAllInstancesWithHttpMessagesAsync`。

1. 回應類型將很有可能是 `object`，因為方法會傳回多種類型 (例如，`IList<InstanceInfo>` 和 `ApiErrorResult`)。 若要檢查傳回類型，您可以將物件安全轉換成 [API 詳細資料頁面](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) 上指定的回應類型。    
   如果需要更多要求資訊，請使用 **HTTP 訊息方法** 存取原始回應物件。


[!INCLUDE[footer-include](../includes/footer-banner.md)]