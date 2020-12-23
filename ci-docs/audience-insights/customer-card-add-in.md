---
title: 安裝和組態客戶卡片增益集
description: 安裝及設定 Dynamics 365 Customer Insights 客戶卡片增益集。
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644033"
---
# <a name="customer-card-add-in-preview"></a>客戶卡片增益集 (預覽)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

直接在 Dynamics 365 應用程式中取得您客戶的 360 度視圖。 透過客戶卡片增益集查看人口統計、見解及活動時間表。

## <a name="prerequisites"></a>先決條件

- 已啟用整合介面的 Dynamics 365 應用程式 (例如銷售中心或客戶服務中心) 9.0 版及更新版本。
- [從使用 Common Data Service](connect-power-query.md) 的 Dynamics 365 應用程式內嵌的客戶設定檔。
- 客戶卡片增益集使用者在對象見解中必須 [新增為使用者](permissions.md)。
- [組態的搜尋和篩選功能](search-filter-index.md)。
- 人口統計控制項：如年齡或性別的人口統計欄位可在統一客戶設定檔中使用。
- 擴充控制項：需要將使用中[擴充內容](enrichment-hub.md)套用至客戶設定檔。
- 智慧控制項：需要使用 Azure Machine Learning ([預測](predictions.md) 或 [自訂模型](custom-models.md)) 產生的資料
- 量值控制項：需要 [組態的量值](measures.md)。
- 時間表控制項：需要 [已組態的活動](activities.md)。

## <a name="install-the-customer-card-add-in"></a>安裝客戶卡片增益集

客戶卡片增益集是 Dynamics 365 中 Customer Engagement 應用程式的解決方案。 若要安裝此解決方案，請移至 AppSource 並搜尋 **Dynamics Customer 卡片**。 選取 [AppSource 上的客戶卡片增益集](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)，然後選取 **立即取得**。

您可能必須使用 Dynamics 365 應用程式的系統管理員認證登入，才能安裝解決方案。

若要將解決方案安裝到您的環境，可能需要花費一些時間。

## <a name="configure-the-customer-card-add-in"></a>設定客戶卡片增益集

1. 以系統管理員身分，移至 Dynamics 365 中的 **設定** 區段，然後選取 **解決方案**。

1. 選取 **Dynamics 365 Customer Insights 客戶卡片增益集 (預覽)** 解決方案的 **顯示名稱** 連結。

   > [!div class="mx-imgBorder"]
   > ![選取顯示名稱](media/select-display-name.png "選取顯示名稱")

1. 選取 **登入**，然後輸入您用來設定 Customer Insights 的管理帳戶憑證。

   > [!NOTE]
   > 請檢查當您選取 **登入** 按鈕時，瀏覽器快顯封鎖程式不會封鎖驗證視窗。

1. 選取您要擷取資料的環境。

1. 定義對應 Dynamics 365 應用程式記錄的欄位。
   - 若要對應連絡人，請選取客戶實體中符合您的連絡人實體的識別碼欄位。
   - 若要對應帳戶，請選取客戶實體中符合您的帳戶實體的識別碼欄位。

   > [!div class="mx-imgBorder"]
   > ![連絡人識別碼欄位](media/contact-id-field.png "連絡人識別碼欄位")

1. 選取 **儲存設定** 以儲存設定。

1. 接下來，您必須指派 Dynamics 365 中的資訊安全角色，才能讓使用者自訂並查看客戶卡片。 在 Dynamics 365 中，移至 **設定** > **安全性** > **使用者**。 選取要編輯使用者角色的使用者，並選取 **管理角色**。

1. 將 **Customer Insights 卡片自訂員** 角色指派給要為整個組織自訂卡片顯示內容的使用者。

## <a name="add-customer-card-controls-to-forms"></a>新增客戶卡片控制項到表單
  
1. 若要將客戶卡片控制項新增至您的連絡人表單，請移至 Dynamics 365 中的 **設定** > **自訂**。

1. 選取 **自訂系統**。

1. 瀏覽至 **連絡人** 實體，展開它，然後選取 **表單**。

1. 選取您要新增客戶卡片控制項的連絡人表單。

    > [!div class="mx-imgBorder"]
    > ![選取連絡人表單](media/contact-active-forms.png "選取連絡人表單")

1. 若要新增控制項，請在表單編輯器中，將 **欄位總管** 中的任何欄位拖曳至要您希望控制項出現的位置。

1. 選取表單上您剛新增的欄位，然後選取 **變更屬性**。

1. 移至 **控制項** 索引標籤，然後選取 **新增控制項**。 選擇其中一個可用的自訂控制項，然後選取 **新增**。

1. 在 **欄位屬性** 對話方塊中，清除 **顯示表單的標籤** 核取方塊。

1. 選取控制項的 **Web** 選項。 對於擴充控制項，您可以設定 **enrichmentType** 欄位，以選取要顯示的擴充內容類型。 您必須為每個擴充內容類型個別新增不同的擴充控制項。

1. 選取 **儲存** 和 **發佈** 以發佈更新的連絡人表單。

1. 移至發行的連絡人表單。 您會看到最新新增的控制項。 您可能需要在第一次使用時登入。

1. 若要自訂想要在自訂控制項上顯示的內容，請在右上角選取編輯按鈕。
