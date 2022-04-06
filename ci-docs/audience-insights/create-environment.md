---
title: 在 Customer Insights 建立環境
description: 建立已授權的 Dynamics 365 Customer Insights 訂閱環境。
ms.date: 03/28/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: a538237322615f69f0a5cb43d394275bf79af00b
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491903"
---
# <a name="create-an-environment-in-audience-insights"></a>在對象見解建立環境

本文說明在您的組織購買 Dynamics 365 Customer Insights 訂閱之後，如何建立新的環境。 

每個 Customer Insights 授權，組織可以建立 *兩種* 環境。 如果貴組織購買多組授權，[請聯絡本公司支援團隊](https://go.microsoft.com/fwlink/?linkid=2079641)增加可用環境數目。 如需容量和附加容量的詳細資訊，請下載 [Dynamics 365 授權指南](https://go.microsoft.com/fwlink/?LinkId=866544)。

> [!NOTE]
> 如果您有意尋求試用服務，請參閱[設定試用環境](../trial-signup.md)。

## <a name="create-a-new-environment"></a>建立新環境

在購買 Customer Insights 的訂閱授權之後，Microsoft 365 租用戶的全域系統管理員會收到一封邀請他們建立環境的電子郵件。 若要開始使用，請前往 [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start)。 

引導式體驗幫助您按步就班蒐集新環境所需的全部資訊。 您需要對象見解的[系統管理員權限](permissions.md)建立或管理環境。

1. 請在對象見解中開啟環境選擇器及選取 **+ 新**。
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="選取環境選擇器。":::

1. 遵照下列各節概述的引導式體驗。

### <a name="step-1-provide-environment-information"></a>步驟 1：提供環境資訊

請在 **基本資訊** 步驟中選擇是否從頭建立環境或[從另一個環境複製資料](manage-environments.md#copy-the-environment-configuration)。

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="建立新的 Customer Insights 環境的對話方塊。":::

提供下列詳細資料：
   - **名稱**：此環境的名稱。 如果您已複製現有環境，則欄位已填入資料，但是您可以變更此欄位。
   - **選擇您的業務**：選擇新環境的主要對象。 您可以搭配個別消費者 (B 到 C) 或[業務帳戶](work-with-business-accounts.md) (B 到 B)。
   - **類型**：選取要建立生產環境還是沙箱環境。 沙箱環境不允許排程資料重新整理，是為實作前階段和測試準備的。 沙箱環境使用的主要對象與目前選取的生產環境相同。
   - **地區**：服務部署和託管所在的地區。

### <a name="step-2-configure-data-storage"></a>步驟 2：組態資料儲存體

請在 **資料儲存體** 步驟中選擇從對象見解儲存資料的位置。

您將有兩個選項：**Customer Insights 儲存體** (由 Customer Insights 團隊管理的 Azure 資料湖) 和 **Azure Data Lake Storage**(您自己 Azure Data Lake Storage)。 預設會選取 [Customer Insights 儲存空間] 選項。

:::image type="content" source="media/data-storage-environment.png" alt-text="選擇 Azure Data Lake Storage 儲存中的對象見解資料。":::

藉由儲存資料到 Azure Data Lake Storage，表示您同意資料將傳輸並儲存在 Azure 儲存體帳戶適當的地理位置。 此位置可能與 Dynamics 365 Customer Insights 內儲存資料的位置不同。 請在 [Microsoft 信任中心了解更多](https://www.microsoft.com/trust-center)。

> [!NOTE]
> Customer Insights 目前支援如下：
> - 從儲存在 Microsoft Dataverse 託管 Data Lake 的  Power BI 資料流程擷取實體。  
> - 建立環境時，從您選取的相同 Azure 區域的 Azure Data Lake Storage 帳戶。
> - 已啟用 *階層命名空間* 且是 Gen2 的 Azure Data Lake Storage 帳戶。 不支援 Azure Data Lake Gen1 storage 帳戶。

在 Azure Data Lake Storage 選項中，進行驗證可以在資源型選項和訂閱型選項之間選擇。 如需更多資訊，請參閱[使用 Azure 服務主體連接 Azure Data Lake Storage 帳戶](connect-service-principal.md)。 **容器** 名稱將是 `customerinsights` 且無法變更。

當系統處理如資料擷取完成時，系統會在您指定的儲存體帳戶建立對應的資料夾。 資料檔案和 *model.json* 檔案會根據處理名稱建立並新增到資料夾。

如果您建立 Customer Insights 多重環境並選擇將環境輸出實體儲存到您的儲存體帳戶，Customer Insights 會針對容器中每個 `ci_environmentID` 環境分開建立資料夾。

### <a name="step-3-connect-to-microsoft-dataverse"></a>步驟 3：連線到 Microsoft Dataverse
   
**Microsoft Dataverse** 步驟讓您連接 Customer Insights 和您的 Dataverse 環境。

提供您 Microsoft Dataverse的環境，讓您可以使用 Dataverse 來共用資料 (個人資料和見解) 給商務應用程式 (例如 Dynamics 365 Marketing 或 Power Apps 的模型導向應用程式)。 如果您沒有 Dataverse環境，請將此欄位保留空白，我們會為您佈建。

連接至 Dataverse 環境也讓您可以[使用 Power Platform 的資料流程和閘道從內部部署資料來源來擷取資料](data-sources.md#add-data-from-on-premises-data-sources)。 您也可以通過連接 Dataverse 環境來使用[立即可用的預測模型](predictions-overview.md?tabs=b2c#out-of-box-models)。

> [!IMPORTANT]
> 1. Customer Insights 與 Dataverse 必須位於相同的地區，才能啟用資料共用。
> 1. Dataverse 環境中必須有全域系統管理員角色。 確認此 [Dataverse 環境是否關聯](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment)到特定的安全性群組，並確定您已被新增至這些安全性群組。
> 1. 現有的 Customer Insights 環境尚未與該 Dataverse 環境相關聯。 了解如何[移除現有的 Dataverse 環境連接](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment)。

:::image type="content" source="media/dataverse-provisioning.png" alt-text="為全新實例自動啟用 Microsoft Dataverse 的資料共用。":::

有關啟用從 Azure Data Lake Storage 共用資料到 Microsoft Dataverse，如需詳細資訊，請參閱[連接至 Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse)。

Customer Insights 不支援的資料共用案例如下：
- 如果您啟用與 Dataverse 共享資料的功能，您就無法[在實體建立預測或遺漏的數值](predictions.md)。

### <a name="step-4-finalize-the-settings"></a>步驟 4：完成設定

請在 **評論** 步驟中巡遍所有指定的設定。 當一切看似完成時，請選取 **建立** 設定環境。 

您也可以稍候變更大部分的設定。 如需詳細資訊，請參閱[管理環境](manage-environments.md)。

## <a name="work-with-your-new-environment"></a>搭配您的新環境使用

請回顧下列文章幫助您開始組態 Customer Insights： 

- [新增更多使用者並指派權限](permissions.md)。
- [擷取您的資料來源](data-sources.md)並以[資料整合程序](data-unification.md)執行資料，以取得[整合的客戶個人資料](customer-profiles.md)。
- [擴充整合客戶個人資料](enrichment-hub.md)或[執行預測模型](predictions-overview.md)。
- [建立區段](segments.md)以便分組客戶和[測量](measures.md)評論 KPI。
- [設定連接](connections.md)和[匯出](export-destinations.md)，以處理您在其他應用程式的資料子集。
