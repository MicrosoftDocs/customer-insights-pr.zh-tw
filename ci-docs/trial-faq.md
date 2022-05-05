---
title: 試用版常見問答集-Dynamics 365 Customer Insights
description: Customer Insights 試用版設定和管理相關的常見問題解決方案。 了解如何解決平台和應用程式特定的問題。
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 4a269a223efa08f71db09eef2ec9a8f8a077f7a7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641798"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Dynamics 365 Customer Insights 試用版常見問題

## <a name="sign-up"></a>註冊

### <a name="what-are-the-system-requirements-for-the-trial"></a>試用版的系統需求是什麼？

此應用程式是雲端型服務，儘管適用一些限制，但除了最新的網頁瀏覽器以外，不需要特殊軟體。 為了獲得最佳試用體驗，請避免在 incognito 模式存取試用網站，並選擇最靠近您的試用位置。 [了解更多有關 Web 應用程式需求。](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>如果沒有 Microsoft 365 租用戶，如何註冊試用版？

您可以輸入非工作電子郵件地址，我們會為您建立帳戶和租用戶。

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>我可以註冊多個 Dynamics 365 應用程式 (例如 Sales、Marketing 和 Customer Service) 嗎？

是的，您可以。 若要檢視所有可用的試用版，[請瀏覽試用中心頁面](https://dynamics.microsoft.com/dynamics-365-free-trial)。 您可以使用相同的電子郵件帳戶註冊不同的試用版。 但是，不可以在同一個試用網站上擁有多個應用程式。 每個試用版各在不同的組織和 URL 上。 試用資料無法跨應用程式共用。

## <a name="trial-app"></a>試用版應用程式

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>註冊後並未收到試用詳細資料電子郵件，我該怎麼做？

註冊試用版時，您會收到包含試用詳細資訊的電子郵件。 如果在收件匣中看不到此電子郵件，請檢查您的垃圾郵件資料夾。 或者，使用下列步驟存取您的應用程式：

1. 請前往試用網站並選取 **免費試用**。
1. 輸入您用來註冊試用版的電子郵件識別碼。 系統會將您重新導向至試用版應用程式。

### <a name="how-do-i-add-more-users-to-a-trial"></a>如何將更多使用者新增至試用版？

若要新增使用者，請使用試用版管理員帳戶前往 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。 依照[系統管理中心指引](/microsoft-365/admin/add-users/add-users)，將使用者新增至試用版授權限制。 如果您要新增的使用者已經有 Microsoft 365 帳戶，則將試用組織中適當的資訊安全角色指派給他們。如需詳細資訊，請參閱[指派資訊安全角色給使用者](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user)。

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>可以將多少使用者新增至我的試用環境？

您可以將不限數目的使用者新增至試用環境。

### <a name="how-do-i-reset-the-trial-environment"></a>如何重設試用環境？

您無法重設試用環境。 不過，您可以等待試用期結束，然後再次註冊新的試用。

## <a name="trial-expiration-and-extension"></a>試用期滿和延長

### <a name="how-do-i-extend-the-trial"></a>如何延長試用？

您可以直接在應用程式裡延伸試用版。 您可以延長試用期一次。

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>我可以將試用版轉換為付費授權嗎？

一般而言，當您升級至付費版本的 Customer Insights 時，我們建議使用您自己的資料開始重頭開始。 

或者，如果您只使用 Customer Insights，在購買 Customer Insights 時，您可以從試用環境複製您的資料。 您必須是 Customer Insights 試用版的系統管理員和 Microsoft 365 的租用戶的全域系統管理員，或您組織中的 Dynamics 365 系統管理員，才能將設定從試用環境遷移至付費環境。 

第一次登入付費 Customer Insights 執行個體之後，系統會要求您建立新的環境。 在此過程中，您可以選擇從現有的環境複製設定，並遷移大部分的設定。 如果您有上述權限，則試用環境將會顯示在此清單中。 如需詳細資訊，請參閱[複製環境設定](manage-environments.md#copy-the-environment-configuration)。

### <a name="what-are-the-trial-limits-and-quotas"></a>試用版限制和配額是什麼？

- 您無法使用 Azure Azure Data Lake Storage 帳戶在 Customer Insights 試用期間儲存輸出資料。 但是，您可以從 Data Lake storage 帳戶擷取資料。
- 開始使用 Customer Insights 試用版時，您最多可以儲存 3 GB 的資料到自動佈建的 Dataverse 環境。

## <a name="customer-insights-specific-questions"></a>Customer Insights 特定問題

### <a name="how-do-i-start-using-the-trial"></a>如何開始使用試用版？

註冊試用版後，您將到達應用程式的主畫面。 主畫面提供使用者指南和教學課程的連結。 若要了解更多資訊，請造訪試用版註冊頁面上，[其他資源](trial-signup.md#additional-resources)中的連結。

### <a name="what-features-are-available-in-the-trial"></a>試用版提供哪些功能?

試用版開放使用絕大部份的 Customer Insights 功能。

以下是 **不可用** 的功能： 
- 您無法建立使用自己的 Azure 資料湖儲存體帳戶的新環境。
- 您無法刪除試用環境。 

### <a name="how-long-does-the-trial-last"></a>試用版使用期間多久？

Customer Insights 試用版為期 30 天。 您可以在 23 天後登入您的試用環境時，延長試用版時間。

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>如何從試用版中移除範例資料？

您不能從試用版移除範例資料。
