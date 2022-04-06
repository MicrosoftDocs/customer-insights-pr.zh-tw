---
title: 建立和管理環境
description: 瞭解如何註冊服務及管理環境。
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491988"
---
# <a name="manage-environments"></a>管理環境

## <a name="switch-environments"></a>切換環境

選取頁面右上角的 **環境** 控制項，以變更環境。

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="螢幕擷取畫面，圖為切換環境的控制項。":::

系統管理員能夠[建立](create-environment.md)和管理環境。

## <a name="edit-an-existing-environment"></a>編輯現有環境

您可以編輯現有環境的部分詳細資料。

1.  在應用程式的標頭中選取 **環境** 選取器。

2.  選取 **編輯** 圖示。

3. 您可以在 **編輯環境** 方塊中更新環境設定。

如需環境設定的詳細資訊，請參閱[建立新環境](create-environment.md)。

## <a name="connect-to-microsoft-dataverse"></a>連線至 Microsoft Dataverse
   
**Microsoft Dataverse** 步驟讓您連接 Customer Insights 和您的 Dataverse 環境。 

提供您 Microsoft Dataverse的環境，讓您可以使用 Dataverse 來共用資料 (個人資料和見解) 給商務應用程式 (例如 Dynamics 365 Marketing 或 Power Apps 的模型導向應用程式)。

若要使用[開箱即用預測模型](predictions-overview.md#out-of-box-models)，請組態與 Dataverse 共用的資料。 或者您可以從內部部署資料來源擷取，提供貴組織管理的 Microsoft Dataverse 環境 URL。

選取資料共用核取方塊來啟用 Microsoft Dataverse 資料共用，會觸發資料來源和所有其他程序的一次完整重新整理。

> [!IMPORTANT]
> 1. Customer Insights 與 Dataverse 必須位於相同的地區，才能啟用資料共用。
> 1. Dataverse 環境中必須有全域系統管理員角色。 確認此 [Dataverse 環境是否關聯](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment)到特定的安全性群組，並確定您已被新增至這些安全性群組。
> 1. 現有的 Customer Insights 環境尚未與該 Dataverse 環境相關聯。 了解如何[移除現有的 Dataverse 環境連接](#remove-an-existing-connection-to-a-dataverse-environment)。

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="啟用與 Microsoft Dataverse 共用資料的設定選項。":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>啟用資料共用，從 Azure Data Lake Storage 到 Dataverse (預覽版)

如果您的環境已設定成使用 Azure Data Lake Storage 儲存 Customer Insights 資料，啟用對 Microsoft Dataverse 資料共用就需要額外設定。

1. 在您的 Azure 訂閱上建立兩個安全性群組 - 一個 **讀者** 安全性群組和一個 **參與者** 安全性群組，並將 Microsoft Dataverse 服務設定為兩個安全性群組的負責人。
2. 透過這些安全性群組，在您的儲存體帳戶的 CustomerInsights 容器上管理存取控制清單 (ACL)。 將 Microsoft Dataverse 服務和任何 Dataverse 型商務應用程式 (例如 Dynamics 365 Marketing) 新增至 **唯讀** 權限的 **讀者** 安全性群組。 *僅* 將 Customers Insights 應用程式新增至 **參與者** 安全性群組，才能授與能寫入設定檔和見解的 **讀取與寫入** 權限。
   
#### <a name="prerequisites"></a>先決條件

若要執行 PowerShell 腳本，必須匯入下列三個模組。 

1. 安裝[Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)的最新版本。
   1. 在您的 PC 上，按下鍵盤上的 Windows 鍵並搜尋 **Windows PowerShell，** 然後選取 **以系統管理員身分執行**。
   1. 請在打開的 PowerShell 視窗中輸入 `Install-Module AzureAD`。
2. 匯入三個模組。
    1. 在 Powershell 視窗中輸入 `Install-Module -Name Az.Accounts` 並執行下列步驟。 
    1. 重複 `Install-Module -Name Az.Resources` 和 `Install-Module -Name Az.Storage`。

#### <a name="configuration-steps"></a>設定步驟

1. 從我們工程師的 [GitHub 存放庫](https://github.com/trin-msft/byol)中下載兩個需要執行的 PowerShell 腳本。
    1. `CreateSecurityGroups.ps1`
       - 若要執行 PowerShell 腳本，需要擁有 *租用戶系統管理員* 權限。 
       - 此 PowerShell 腳本會在您的 Azure 訂閱上建立兩個安全性群組。 一個是讀者群組，另一個是投稿人群組，並以 Microsoft Dataverse 服務作為這兩個安全性群組的負責人。
       - 請提供包含您 Azure Data Lake Storage 的 Azure 訂閱識別碼，在 Windows PowerShell 中執行此 PowerShell 腳本。 在編輯器中打開 PowerShell 腳本，以查看其他資訊與實施的邏輯。
       - 儲存此腳本生成的兩個安全性群組識別碼值，因為我們會在 `ByolSetup.ps1`腳本中使用它們。
       
        > [!NOTE]
        > 建立安全性群組在您的租用戶上可能是停用的。 在這種案例中，需要手動設定，而且您的 Azure AD系統管理員必須 [啟用安全性群組建立](/azure/active-directory/enterprise-users/groups-self-service-management)。

    2. `ByolSetup.ps1`
        - 必須有儲存體帳戶/容器層級的 *儲存體 Blob 資料擁有者* 權限，才能執行此腳本，或者這個腳本將為您建立一個。 在成功執行腳本之後，您可以手動移除角色指派。
        - 此 PowerShell 腳本會為 Microsoft Dataverse 服務和任何 Dataverse 商務應用程式新增必要的 tole 型存取控制 (RBAC)。 對於使用 `CreateSecurityGroups.ps1` 腳本建立的安全性群組，它也會在 CustomerInsights 容器上更新存取控制清單 (ACL) 。 參與者群組將具有 *rwx* 權限，而讀者群組則僅擁有 *r-x* 權限。
        - 提供 Azure Data Lake Storage 的 Azure 訂閱識別碼、儲存體帳戶名稱、資源群組名稱和讀者及投稿人安全性群組識別碼值，在 Windows PowerShell 中執行此 PowerShell 腳本。 在編輯器中打開 PowerShell 腳本，以查看其他資訊與實施的邏輯。
        - 在成功執行腳本之後，複製輸出字串。 輸出字串形式如：`https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. 將從上方複製的輸出字串輸入至 Microsoft Dataverse 環境設定步驟的 **權限識別碼** 欄位。

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="啟用共用 Azure Data Lake Storage 資料到 Microsoft Dataverse 的設定選項。":::

Customer Insights 不支援的資料共用案例如下：
- 如果您啟用與 Dataverse 共享資料的功能，您就無法[在實體建立預測或遺漏的數值](predictions.md)。
- 如果您使用 Dataverse 來啟用資料共用，您將無法在 Customer Insights 環境中查看任何選擇性的 PowerBI 嵌入式報表。

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>移除現有的 Dataverse 環境連接

當連接至 Dataverse 環境時，**此 CDS 組織已連接至另一個 Customer Insights 執行個體中** 的錯誤訊息表示 Dataverse 該環境已在 Customer Insights 環境中使用。 作為 Dataverse 環境的全域系統管理員，您可以將現有的連接移除。 可能需要花費數個小時才能填入變更。

1. 請移至 [Power Apps](https://make.powerapps.com)。
1. 從環境下選擇器中選取環境。
1. 移至 **解決方案**
1. 解除安裝或刪除名為 **Dynamics 365 Customer Insights 客戶卡增益集 (Preview)** 的解決方案。

OR 

1. 請打開您的 Dataverse 環境。
1. 移至 **進階設定** > **解決方案**。
1. 解除安裝 **CustomerInsightsCustomerCard** 解決方案。

## <a name="copy-the-environment-configuration"></a>複製環境設定

作為系統管理員，您可以選擇在建立新的環境時，從現有的環境複製設定。 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="螢幕擷取畫面，圖為環境設定中的設定選項。":::

您會看到組織中所有可用環境的清單，您可以從此清單複製資料。

下列組態設定已複製，

- 內嵌/匯入的資料來源
- 資料統一 (對應、比對、合併) 設定
- 客戶細分
- 量值
- 關聯
- 活動
- 搜尋和篩選索引
- 匯出目的地
- 已排程的重新整理
- 擴充
- 模型管理
- 角色指派

## <a name="set-up-a-copied-environment"></a>設定複製的環境

當您複製環境設定時，*不會* 複製下列資料：

- 客戶設定檔。
- 資料來源認證。 您必須提供每個資料來源的認證，並手動重新整理資料來源。
- 取自 Common Data Model 資料夾和 Dataverse 託管資料湖的資料來源。 您必須使用與來源環境相同的名稱，手動建立這些資料來源。
- 用於匯出和擴充的連接秘密。 您必須重新驗證這些連接，然後重新啟動擴充和匯出。 

複製環境時，您會看到一則指示已建立新環境的確認訊息。 選取 **移至資料來源** 以查看資料來源清單。

所有的資料來源都會顯示 **需要認證** 狀態。 編輯資料來源，並輸入認證以進行重新整理。

:::image type="content" source="media/data-sources-copied.png" alt-text="已複製且需要驗證的資料來源清單。":::

重新整理資料來源之後，移至 **資料** > **統一**。 您會在此處找到來源環境的設定。 視需要編輯，或選取 **執行** 以開始進行資料統一處理程序，並建立統一的客戶實體。

資料統一完成時，移至 **測量** 和 **分段** 進行重新整理。

在重新啟動匯出和擴充之前，請移至 **系統管理員** > **連接**，重新驗證新環境中的連接。

## <a name="change-the-owner-of-an-environment"></a>變更環境負責人

雖然在 Customer Insights 可以有多個使用者擁有系統管理員權限，但是只有一個使用者是環境的負責人。 根據預設，這會是建立環境的系統管理員。 作為環境的系統管理員，您可以將擁有權指派給具有系統管理員權限的其他使用者。

1. 在應用程式的標頭中選取 **環境** 選取器。

1. 選取 **編輯** 圖示。

1. 在 **編輯環境** 方塊中，移至 **基本資訊** 步驟。

1. 在 **變更環境的負責人** 欄位中，選擇環境的新負責人。  

1. 選取 **檢閱及完成**，然後按一下 **更新** 來套用變更。 

## <a name="claim-ownership-of-an-environment"></a>宣告環境的擁有權

如果環境的負責人離開組織或其使用者帳戶已被刪除，則環境將沒有負責人。 具有系統管理員權限的使用者可以宣告擁有權，並成為新的負責人。 他們可以繼續擁有環境，或[將擁有權變更到其他系統管理員](#change-the-owner-of-an-environment)。 

若要宣告擁有權，請選取 **取得擁有權** 按鈕，當原始負責人離開組織時，會在 Customer Insights 中每個頁面的頂端顯示該按鈕。

## <a name="reset-an-existing-environment"></a>重設現有環境中

作為環境負責人，若要刪除所有設定並移除擷取資料，您可以將環境重設為空白狀態。

1.  在應用程式的標頭中選取 **環境** 選取器。 

2.  選取您要重設的環境，並選取省略號 (**...**)。 

3. 選擇 **重設** 選項。 

4.  若要確認刪除，請輸入環境名稱並選取 **重設**。

## <a name="delete-an-existing-environment"></a>刪除現有環境

作為環境的負責人，您可以刪除您管理的環境。

1.  在應用程式的標頭中選取 **環境** 選取器。

2.  選取您要重設的環境，並選取省略號 (**...**)。 

3. 選擇 **刪除** 選項。 

4.  若要確認刪除，請輸入環境名稱，然後選取 **刪除**。

> [!NOTE]
> 刪除環境並不會移除環境的 Dataverse 關聯。了解如何[移除現有的 Dataverse 環境連接](#remove-an-existing-connection-to-a-dataverse-environment)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
