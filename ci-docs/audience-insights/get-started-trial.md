---
title: 建立和設定 Customer Insights 的試用版
description: 取得並設定 Dynamics 365 Customer Insights 試用訂閱的步驟。
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f038dedd369ac9e623146b66528efa87c47a8c23769037d8709fa9b804a0b723
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035405"
---
# <a name="set-up-a-trial-environment"></a>設定試用環境 

Dynamics 365 Customer Insights 試用版能讓您檢閱核心功能，並深入了解多種功能。 試用訂閱會在過期後被刪除。 試用環境由成為試用環境系統管理員的個別使用者建立。 他們可以邀請更多使用者到試用中並且設定各種功能。

## <a name="create-a-trial-environment"></a>建立試用環境

您可以在[試用註冊頁面](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights)上註冊試用。 

1. 選擇 **註冊免費試用** 選項，然後選取 **立即註冊**。

1. 提供您的工作或學校電子郵件地址，並提供您的個人資訊，接著選取 **開始使用**。

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="註冊試用執行個體的對話方塊":::

1. 檢閱條款及條件，然後選取 **繼續** 表示確認。

1. 提供您的新環境的 **名稱**。 

1. 設定環境 **類型** 為 **試用版**。

1. 在 **選取產業示範** 欄位中，您可以選擇特定產業的資料集。 您也可以稍後[變更為產業示範](#use-industry-specific-demo-data-sets-in-audience-insights)，並從預設資料集開始。

1. 選擇您的環境的 **區域**。

1. 或者，如果您是 Dynamics 365 組織的系統管理員：選取 **進階設定**，並提供您的組織的 URL，來使用預測功能 (例如客戶流失預測)。 

1. 選取 **建立**。 

需要幾一小段時間才能完成環境安裝。 完成後，您會被重導向至示範環境或您在上述步驟中所選取的產業示範。 您現在可以探索具有唯讀示範資料的應用程式。 若要將您自己的資料新增至環境，請參閱[在自己的環境中建立特定案例的示範資料](#create-scenario-specific-demo-data-in-your-own-environment)。

:::image type="content" source="media/trial-environment.png" alt-text="新建試用環境的螢幕擷取畫面。":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>在對象見解中使用特定產業的示範資料集

連接實際資料來源是使用 Customer Insights 能力的重要步驟之一。 若要嘗試功能而不影響您自己的資料，您可以選擇使用特定產業的示範資料。 下列產業提供數種示範資料集： 

-   汽車
-   銀行
-   消費性商品
-   政府
-   醫療
-   旅遊服務
-   保險
-   製造業
-   專業服務
-   零售業

### <a name="see-industry-specific-demo-data-in-trials"></a>在試用版中查看特定產業的示範資料

如需為特定產業或案例量身定制資訊的唯讀版本 Customer Insights，請從示範環境開始。 
 
1.  在對象見解中，在環境選取器中選擇 **示範** 環境。

2.  在 **首頁** 上，從精選產業示範下拉式功能表中選擇一個選項。

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="選擇試用環境的產業。":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>在自己的環境中建立特定案例的示範資料

系統管理員，請在應用程式標頭選取環境選取器建立新環境。 在新環境中，您可以根據需求來設定自己的資料來源，接著設定應用程式。 

1.  在對象見解中，前往 **資料** > **資料來源**。

2.  若要匯入您自己的資料來源，請移至[資料擷取指南](data-sources.md)。     
   如果您想使用可讓您嘗試資料擷取的範例資料，則可以在環境中擷取產業示範資料。 請選擇 **由 Datahub 匯入** 選項，並執行下列步驟。

3.  選取符合您的案例的產業卡片。 

4.  檢閱並選擇是否更新資料來源的建議名稱。 

5.  選取 **下一步** 以擷取範例資料。 

您現在可以使用擷取的資料，為您的案例自訂 Customer Insights。 若要查看專門擷取示範資料的環境，請在環境選取器中選擇 **<Industry> 示範** 選項。

## <a name="limitations-in-trials"></a>試用版限制

- 試用版預設會有 30 天的使用時間。 不過，在第 23 天後，如果您登入試用版，則可以進行延長。
- 在試用期間，您無法使用自己的 Azure Data Lake storage 帳戶，來儲存輸出資料。 但是，您可以從 Data Lake storage 帳戶擷取資料。
- 啟動 Customer Insights 試用版會自動佈建 Dataverse 環境，在其中您最多可以儲存最多 3 GB 的資料。

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>從試用版複製資料到付費訂閱

一般而言，當您升級至付費版本的 Customer Insights 時，我們建議使用您自己的資料開始重頭開始。 

當您購買 Customer Insights，您也可以從試用環境複製資料。 您必須是 Customer Insights 試用版的系統管理員，以及組織中的 Microsoft 365 租用戶的全域系統管理員，或是 Dynamics 365 系統管理員，才能將試用環境設定遷移至付費環境。 

第一次登入付費 Customer Insights 執行個體之後，系統會要求您建立新的環境。 在此過程中，您可以選擇從現有的環境複製設定，並遷移大部分的設定。 如果您有上述權限，則試用環境將會顯示在此清單中。 如需詳細資訊，請參閱[複製環境設定](manage-environments.md#copy-the-environment-configuration)。

## <a name="next-steps"></a>後續步驟

檢閱下列文章，可以協助您開始設定 Customer Insights。 

- [新增更多使用者並指派權限](permissions.md)。
- [擷取您的資料來源](data-sources.md)並以[資料整合程序](data-unification.md)執行資料，以取得[整合的客戶個人資料](customer-profiles.md)。
- [擴充整合客戶個人資料](enrichment-hub.md)或[執行預測模型](predictions-overview.md)。
- 建立[客戶細分](segments.md)來分組客戶和[量值](measures.md)檢閱 KPI。
- 在其他應用程式中設定[連接](connections.md)和[匯出](export-destinations.md)，以處理您的資料子集。