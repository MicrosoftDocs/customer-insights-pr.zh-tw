---
title: 建立新環境
description: 在 Dynamics 365 Customer Insights 建立環境的步驟。
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304233"
---
# <a name="create-a-new-environment"></a>建立新環境

在[購買 Dynamics 365 Customer Insights 的訂閱授權](paid-license.md)之後，Microsoft 365 用戶的全域系統管理員會收到一封邀請他們建立環境的電子郵件。 若要開始使用，請前往 [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start)。 在此案例中，先從[步驟 1：提供基本資訊](#step-1-provide-basic-information)開始。

建立第一個環境之後，Microsoft 365 租用戶的全域系統管理員可以[將組織中的使用者新增為系統管理員](permissions.md)。 這些系統管理員接著就可以管理使用者和環境。 如果貴組織購買多份 Customer Insights 的授權，[請聯絡本公司支援團隊](https://go.microsoft.com/fwlink/?linkid=2079641)增加可用環境數目。 如需容量和附加元件容量的詳細資訊，請查閱 [Dynamics 365 授權指南](https://go.microsoft.com/fwlink/?LinkId=866544)。 一旦能夠建立其他環境，即移至[開始環境建立程序](#start-the-environment-creation-process)。

> [!TIP]
> 如果您有意尋求試用服務，請參閱[設定試用環境](trial-signup.md)。

## <a name="prerequisites"></a>先決條件

Customer Insights 中的[系統管理員權限](permissions.md)

## <a name="start-the-environment-creation-process"></a>開始環境建立程序

1. 打開環境選取器，然後選取 **+ 新增**。
  
   :::image type="content" source="media/environment-picker.png" alt-text="選取環境選擇器。":::

1. 遵循下列各節所列的引導式體驗，提供新環境所需的所有資訊。

## <a name="step-1-provide-basic-information"></a>步驟 1：提供基本資訊

1. 選擇您要從頭建立環境還是要從其他環境複製資料。 [從其他環境複製資料](#copy-the-environment-configuration)需要額外的步驟。

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="建立新的 Customer Insights 環境的對話方塊。":::

1. 提供下列詳細資料：

   - **名稱**：此環境的名稱。 如果您已複製現有環境，則欄位已填入資料，但是您可以變更此欄位。
   - **選擇您的業務**：新環境的主要對象：個別消費者 (B 到 C) 或[商務客戶](work-with-business-accounts.md) (B 到 B)。 如果您的組織主要與個人有業務往來 (例如零售商或咖啡店)，請選擇個人消費者。 如果您的主要對象是其他公司 (例如汽車製造商或造紙公司)，請選擇商務客戶。
   - **類型**：環境的類型：生產或沙箱。 沙箱環境不允許排程資料重新整理，是為實作前階段和測試準備的。 沙箱環境使用的主要對象與目前選取的生產環境相同。
   - **區域**：服務部署和託管所在的區域。 若要[使用自己的 Azure Data Lake Storage 帳戶](own-data-lake-storage.md)或[連接至現有的 Microsoft Dataverse 組織](customer-insights-dataverse.md)，則 Customer Insights 環境必須位於相同的區域。

1. 選取 **下一步**。

## <a name="step-2-configure-data-storage"></a>步驟 2：組態資料儲存體

1. 選擇是否要儲存 Customer Insights 資料：

   - **Customer Insights 儲存體**：自動管理資料儲存。 這是預設選項，除非您有在自己的儲存體帳戶中儲存資料的特定需求，否則建議使用此選項。
   - **Azure Data Lake Storage**：您自己用於儲存資料的 Azure Data Lake Storage 帳戶，讓您擁有儲存資料的完整控制權。 請依照[使用您自己的 Azure Data Lake Storage 帳戶](own-data-lake-storage.md)中的步驟操作。

   :::image type="content" source="media/data-storage-environment.png" alt-text="選擇儲存資料的偏好選項。":::

1. 選取 **下一步**。

## <a name="step-3-connect-to-microsoft-dataverse"></a>步驟 3：連線到 Microsoft Dataverse

如果您有 Dataverse 環境，請連接 Customer Insights。 與 Dataverse 共用資料，以便以 Dataverse 為基礎的商務應用程式搭配使用 (例如 Dynamics 365 Marketing 或 Power Apps 的模型導向應用程式)。

1. 請依照[在 Microsoft Dataverse 中使用 Customer Insights 資料](customer-insights-dataverse.md)中的步驟操作。

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="為全新環境自動啟用 Microsoft Dataverse 的資料共用。":::

1. 選取 **下一步**。

## <a name="step-4-finalize-the-settings"></a>步驟 4：完成設定

檢閱指定的設定。 當一切看似完成時，請選取 **建立** 設定環境。

若要在稍後變更部分設定，請參閱[管理環境 ](manage-environments.md)。

## <a name="work-with-your-new-environment"></a>搭配您的新環境使用

請回顧下列文章幫助您開始組態 Customer Insights：

- [新增更多使用者並指派權限](permissions.md)。
- [擷取您的資料來源](data-sources.md)並以[資料整合程序](data-unification.md)執行資料，以取得[整合的客戶設定檔](customer-profiles.md)。
- [擴充統一客戶設定檔](enrichment-hub.md)或[執行預測模型](predictions-overview.md)。
- [建立區段](segments.md)以便分組客戶和[測量](measures.md)評論 KPI。
- [設定連接](connections.md)和[匯出](export-destinations.md)，以處理您在其他應用程式的資料子集。

## <a name="copy-the-environment-configuration"></a>複製環境設定

身為管理員，如果選擇從現有環境複製設定，請從您組織中所有可用環境的清單選取。

:::image type="content" source="media/environment-settings-dialog.png" alt-text="螢幕擷取畫面，圖為環境設定中的設定選項。":::

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

### <a name="set-up-a-copied-environment"></a>設定複製的環境

複製環境設定時，確認訊息會在建立複製的環境後顯示。 執行下列步驟以確認認證。

1. 選取 **移至資料來源** 以查看資料來源清單。 所有的資料來源都會顯示 **需要認證** 狀態。

   :::image type="content" source="media/data-sources-copied.png" alt-text="已複製且需要驗證的資料來源清單。":::

1. 編輯資料來源，並輸入認證以進行重新整理。 來自 Common Data Model 資料夾和 Dataverse 的資料來源必須使用與來源環境中相同的名稱手動建立。

1. 重新整理資料來源之後，移至 **資料** > **整合**。 您會在此處找到來源環境的設定。 視需要編輯這些設定，或選取 **整合** > **整合客戶設定檔和相依性** 以開始進行資料整合程序，並建立整合客戶實體。

   > [!TIP]
   > 對於帳戶和連絡人，選取 **整合帳戶** > **整合設定檔和相依性**。

1. 資料整合完成時，移至 **量值** 和 **客戶細分** 以進行重新整理。

1. 移至 **管理員** > **連接**，重新驗證新環境中的連接。

1. 移至 **資料** > **擴充** 和 **資料** > **匯出** 以重新啟用這些連接。

[!INCLUDE [footer-include](includes/footer-banner.md)]
