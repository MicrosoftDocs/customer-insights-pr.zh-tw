---
title: 作法 - 建立新環境
description: 使用 Dynamics 365 Customer Insights 建立環境的步驟。
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 6dfaa09cd80498e9a4e4dea6a07ce6e9d29105e2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011535"
---
# <a name="how-to-create-a-new-environment"></a>作法：建立新環境

在[購買 Dynamics 365 Customer Insights 的訂閱授權](paid-license.md)之後，Microsoft 365 用戶的全域系統管理員會收到一封邀請他們建立環境的電子郵件。 若要開始使用，請前往 [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start)。 在此案例中，您可以直接前往[步驟 1：提供基本資訊](#step-1-provide-basic-information)。

在第一次建立環境之後，Microsoft 365 用戶的全域系統管理員可以[新增組織的使用者為系統管理員](permissions.md)。 日後，這些系統管理員就可以管理使用者和環境。 如果貴組織購買多份 Customer Insights 的授權，[請聯絡本公司支援團隊](https://go.microsoft.com/fwlink/?linkid=2079641)增加可用環境數目。 如需容量和附加元件容量的詳細資訊，請查閱 [Dynamics 365 授權指南](https://go.microsoft.com/fwlink/?LinkId=866544)。

> [!TIP]
> 如果您有意尋求試用服務，請參閱[設定試用環境](trial-signup.md)。

## <a name="prerequisites"></a>先決條件

您需要 Customer Insights 的[系統管理員權限](permissions.md)建立或管理環境。

## <a name="start-the-environment-creation-process"></a>開始環境建立程序

1. 打開環境選取器，然後選取 **+ 新增**。
  
   :::image type="content" source="media/environment-picker.png" alt-text="選取環境選擇器。":::

1. 遵循下列各節所列的引導式體驗，提供新環境所需的所有資訊。 如果您先前已設定環境，您也可以[複製設定](#copy-the-environment-configuration)。

## <a name="step-1-provide-basic-information"></a>步驟 1：提供基本資訊

請在 **基本資訊** 步驟中選擇是否從頭建立環境或[從另一個環境複製資料](#copy-the-environment-configuration)。

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="建立新的 Customer Insights 環境的對話方塊。":::

提供下列詳細資料：

- **名稱**：此環境的名稱。 如果您已複製現有環境，則欄位已填入資料，但是您可以變更此欄位。
- **選擇您的業務**：選擇新環境的主要對象。 您可以搭配個別消費者 (B 到 C) 或[業務帳戶](work-with-business-accounts.md) (B 到 B)。 如果您的組織主要與個人有業務往來 (例如零售商或咖啡店)，請選擇個人消費者。 如果您的主要對象是其他公司 (例如汽車製造商或造紙公司)，請選擇商務帳戶。
- **類型**：選取要建立生產環境還是沙箱環境。 沙箱環境不允許排程資料重新整理，是為實作前階段和測試準備的。 沙箱環境使用的主要對象與目前選取的生產環境相同。
- **地區**：服務部署和託管所在的地區。 若要[使用自己的 Azure Data Lake Storage 帳戶](own-data-lake-storage.md)或[連接至現有的 Microsoft Dataverse 組織](customer-insights-dataverse.md)，則 Customer Insights 環境必須位於相同的區域。

## <a name="step-2-configure-data-storage"></a>步驟 2：組態資料儲存體

請在 **資料儲存體** 步驟中選擇儲存 Customer Insights 資料的位置。

您可以選擇兩個選項：

- **Customer Insights 儲存空間**：資料儲存由 Customer Insights 團隊管理。 這是預設選項，除非您有在自己的儲存體帳戶中儲存資料的特定需求，否則建議使用此選項。
- **Azure Data Lake Storage**：指定您自己的 Azure Data Lake Storage 帳戶來儲存資料，讓您擁有儲存資料的完整控制權。 如需詳細資訊，請參閱[使用自己的 Azure Data Lake Storage 帳戶](own-data-lake-storage.md)。

:::image type="content" source="media/data-storage-environment.png" alt-text="選擇儲存資料的偏好選項。":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>步驟 3：連線到 Microsoft Dataverse

**Microsoft Dataverse** 步驟讓您連接 Customer Insights 和您的 Dataverse 環境。 與 Dataverse 共用資料，以便以 Dataverse 為基礎的商務應用程式搭配使用 (例如 Dynamics 365 Marketing 或 Power Apps 的模型導向應用程式)。


如果您沒有自己的 Dataverse 環境，請將此欄位保留空白，我們會為您建立一個。

如需詳細資訊，請參閱[在 Microsoft Dataverse 中使用 Customer Insights 資料](customer-insights-dataverse.md)。

:::image type="content" source="media/dataverse-provisioning.png" alt-text="為全新環境自動啟用 Microsoft Dataverse 的資料共用。":::

### <a name="step-4-finalize-the-settings"></a>步驟 4：完成設定

請在 **評論** 步驟中巡遍所有指定的設定。 當一切看似完成時，請選取 **建立** 設定環境。

您也可以稍候變更部分設定。 如需詳細資訊，請參閱[管理環境](manage-environments.md)。

## <a name="work-with-your-new-environment"></a>搭配您的新環境使用

請回顧下列文章幫助您開始組態 Customer Insights：

- [新增更多使用者並指派權限](permissions.md)。
- [擷取您的資料來源](data-sources.md)並以[資料整合程序](data-unification.md)執行資料，以取得[整合的客戶個人資料](customer-profiles.md)。
- [擴充整合客戶個人資料](enrichment-hub.md)或[執行預測模型](predictions-overview.md)。
- [建立區段](segments.md)以便分組客戶和[測量](measures.md)評論 KPI。
- [設定連接](connections.md)和[匯出](export-destinations.md)，以處理您在其他應用程式的資料子集。

## <a name="copy-the-environment-configuration"></a>複製環境設定

作為系統管理員，您可以選擇在建立新的環境時，從現有的環境複製設定。

:::image type="content" source="media/environment-settings-dialog.png" alt-text="螢幕擷取畫面，圖為環境設定中的設定選項。":::

您會看到組織中所有可用環境的清單，您可以從此清單複製資料。

下列組態設定已複製，

- 透過 Power Query 匯入的資料來源
- 資料整合設定
- 客戶細分
- 量值
- 關係
- 活動
- 搜尋和篩選索引
- 匯出
- 重新整理排程
- 擴充
- 預測模型
- 角色指派

## <a name="set-up-a-copied-environment"></a>設定複製的環境

當您複製環境設定時，必須完成一些額外步驟來確認認證：

- 客戶設定檔。 首先，請驗證和擷取資料來源，並執行資料統整以重新建立客戶設定檔。
- 資料來源認證。 您必須提供每個資料來源的認證，才能手動驗證和重新整理資料來源。
- 取自 Common Data Model 資料夾和 Dataverse 的資料來源。 您必須使用與來源環境中相同的名稱，手動建立這些資料來源。
- 用於匯出和擴充的連接秘密。 您必須重新驗證這些連接，然後重新啟動擴充和匯出。

當您建立已複製的環境時，會看到一則確認訊息。 選取 **移至資料來源** 以查看資料來源清單。

所有的資料來源都會顯示 **需要認證** 狀態。 編輯資料來源，並輸入認證以進行重新整理。

:::image type="content" source="media/data-sources-copied.png" alt-text="已複製且需要驗證的資料來源清單。":::

重新整理資料來源之後，移至 **資料** > **統一**。 您會在此處找到來源環境的設定。 視需要編輯，或選取 **執行** 以開始進行資料統一處理程序，並建立統一的客戶實體。

資料統一完成時，移至 **測量** 和 **分段** 進行重新整理。

在重新啟動匯出和擴充之前，請移至 **系統管理員** > **連接**，重新驗證新環境中的連接。

[!INCLUDE [footer-include](includes/footer-banner.md)]
