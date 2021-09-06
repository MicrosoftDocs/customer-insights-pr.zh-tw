---
title: 建立和設定 Customer Insights 的付費授權
description: 取得並設定 Dynamics 365 Customer Insights 授權訂閱的步驟。
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034442"
---
# <a name="get-started-with-a-paid-subscription"></a>開始使用您的付費訂閱

本文說明在您的組織購買 Dynamics 365 Customer Insights 訂閱之後，如何建立新的環境。 如果您想要購買 Customer Insights，連絡方式列在 [Dynamics 365 Customer Insights 網站](https://dynamics.microsoft.com/ai/customer-insights/)。 

如果您要嘗試服務及功能，請參閱[設定試用環境](get-started-trial.md)。

## <a name="create-an-environment-in-an-existing-organization"></a>在現有的組織中建立環境

在購買 Customer Insights 的訂閱授權之後，Microsoft 365 租用戶的全域系統管理員會收到一封電子郵件，邀請他們建立環境。 若要開始使用，請前往 [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start)。 

Customer Insights 不是每位使用者授權，因此它不會顯示在授權區域中。 如果您正在 Microsoft 365 系統管理中心尋找授權，請移至 **您的產品**。 

> [!NOTE]
> 每個 Customer Insights 授權，組織可以建立 *兩種* 環境。 如果您的組織購買授權超過一次，請[與我們的支援小組聯繫](https://go.microsoft.com/fwlink/?linkid=2079641)，增加可用環境的數目。 如需容量和附加容量的詳細資訊，請下載 [Dynamics 365 授權指南](https://go.microsoft.com/fwlink/?LinkId=866544)。

若要建立環境：

1. 在 **建立環境** 對話方塊中，選取 **新增環境**。

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="建立新的 Customer Insights 環境的對話方塊。":::

   我們建議您從頭開始設定環境。 不過，如果您是試用環境的系統管理員或成員，則可以選擇 **現有環境中複製**，以[從其他環境複製資料](manage-environments.md#copy-the-environment-configuration)。 您會看到組織中所有可用環境的清單，您可以從此清單複製資料。

1. 提供下列詳細資料：
   - **名稱**：此環境的名稱。 如果您已複製現有環境，則欄位已填入資料，但是您可以變更此欄位。
   - **地區**：服務部署和託管所在的地區。
   - **類型**：選取要建立生產環境還是沙箱環境。 沙箱環境不允許排程資料重新整理，是為實作前階段和測試準備的。
   
1. 您可選擇性選取 **進階設定** 核取方塊：

   - **將所有資料儲存到**：指定要儲存 Customer Insights 所產生之輸出資料的位置。 您將有兩個選項：**Customer Insights 儲存體** (由 Customer Insights 團隊管理的 Azure Data Lake) 和 **Azure Data Lake Storage**(您自己 Azure Data Lake Storage)。 預設會選取 [Customer Insights 儲存空間] 選項。

     > [!NOTE]
     > 將資料儲存至 Azure Data Lake Storage，即表示您同意將資料傳送並儲存在相應的 Azure 儲存體帳戶的地理位置，這可能不同於將資料儲存在 Dynamics 365 Customer Insights 中的位置。 [在 Microsoft 信任中心深入了解。](https://www.microsoft.com/trust-center)
     >
     > 目前，從 Power BI 資料流程擷取的實體儲存在 Microsoft Dataverse 受管理的 Data Lake 中。 
     > 
     > 我們只支援在建立環境時選取相同 Azure 地區的 Azure Data Lake Storage 帳戶。 
     > 
     > 我們只支援已啟用階層命名空間的 Azure Data Lake Storage 帳戶。


   - 在 Azure Data Lake Storage 選項中，進行驗證可以在資源型選項和訂閱型選項之間選擇。 更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。 **容器** 的名稱無法變更，將會是 `customerinsights`。
   
   - 如果您要使用 [立即可用的模型](predictions-overview.md#out-of-box-models)，設定與 Microsoft Dataverse 共用資料，或啟用內部部署資料來源中的資料擷取，請在 **設定與 Microsoft Dataverse 共用資料並啟用其他功能** 下，提供 Microsoft Dataverse 環境 URL。 選取 **啟用資料共用** 與 Microsoft Dataverse Managed Data Lake 共用 Customer Insights 輸出資料。

     > [!NOTE]
     > - 當您將所有資料儲存到自己的 Azure Data Lake Storage ，目前不支援共用資料給 Microsoft Dataverse Managed Data Lake。
     > - 當您以 Microsoft Dataverse Managed Data Lake 啟用資料共用時，目前不支援[預測實體中缺少的值](predictions.md)。

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="啟用與 Microsoft Dataverse 共用資料的設定選項。":::

   當系統處理程序 (例如資料擷取) 完成時，系統會在您指定的儲存體帳戶中建立對應的資料夾。 會根據程序名稱建立資料檔案和 model.json 檔案並新增至資料夾。

   如果您建立多個 Customer Insights 環境並選擇從您的儲存體帳戶環境中儲存輸出實體，各資料夾將針對容器含有 ci_<environmentid> 每個環境分開建立。

1. 選取 **建立** 設定環境。 

## <a name="configure-an-environment"></a>設定環境

檢閱下列文章，可以協助您開始設定 Customer Insights。 

- [新增更多使用者並指派權限](permissions.md)。
- [擷取您的資料來源](data-sources.md)並以[資料整合程序](data-unification.md)執行資料，以取得[整合的客戶個人資料](customer-profiles.md)。
- [擴充整合客戶個人資料](enrichment-hub.md)或[執行預測模型](predictions-overview.md)。
- 建立[客戶細分](segments.md)來分組客戶和[量值](measures.md)檢閱 KPI。
- 在其他應用程式中設定[連接](connections.md)和[匯出](export-destinations.md)，以處理您的資料子集。
