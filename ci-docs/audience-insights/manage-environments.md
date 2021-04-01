---
title: 建立和管理環境
description: 瞭解如何註冊服務及管理環境。
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598283"
---
# <a name="manage-environments"></a>管理環境

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

本文章解釋如何建立新組織及佈建環境。

## <a name="sign-up-and-create-an-organization"></a>註冊和建立組織

1. 前往 [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) 網站。

2. 選取 **開始使用**。

3. 選擇您偏好的註冊案例，並選取對應的連結。

4. 接受條款及條件，然後選取 **繼續** 以開始建立組織。

5. 建立環境之後，就會重新導向至 [Customer Insights](https://home.ci.ai.dynamics.com)。

6. 使用示範環境來探索應用程式，或依照下一節中的步驟建立新環境。

7. 指定環境設定之後，選取 **建立**。

8. 待環境建立成功後，您即可登入。

## <a name="create-an-environment-in-an-existing-organization"></a>在現有的組織中建立環境

建立新環境的方式有兩種。 您可以指定全新的環境設定，也可以從現有環境複製一些組態設定。

若要建立環境：

1. 在應用程式的標頭中選取 **環境** 選取器。

1. 選取 **新增**。

   > [!div class="mx-imgBorder"]
   > ![環境設定](media/environment-settings-dialog.png)

1. 在 **建立新環境** 對話方塊中，選取 **新增環境**。

   如果您想要 [從目前的環境複製資料](#additional-considerations-for-copy-configuration-preview)，請選取 **從現有環境複製**。 您會看到組織中所有可用環境的清單，您可以從此清單複製資料。

1. 提供下列詳細資料：
   - **名稱**：此環境的名稱。 如果您已複製現有環境，則欄位已填入資料，但是您可以變更此欄位。
   - **地區**：服務部署和託管所在的地區。
   - **類型**：選取要建立生產環境還是沙箱環境。

2. 您可選擇性選取 **進階設定** 核取方塊：

   - **將所有資料儲存到**：指定要儲存 Customer Insights 所產生之輸出資料的位置。 您有兩個選項：**Customer Insights 儲存空間** (由 Customer Insights 團隊管理的 Azure Data Lake) 和 **Azure Data Lake Storage Gen2** (您自己的 Azure Data Lake Storage)。 預設會選取 [Customer Insights 儲存空間] 選項。

   > [!NOTE]
   > 將資料儲存至 Azure Data Lake Storage，即表示您同意將資料傳送並儲存在相應的 Azure 儲存體帳戶的地理位置，這可能不同於將資料儲存在 Dynamics 365 Customer Insights 中的位置。 [在 Microsoft 信任中心深入了解。](https://www.microsoft.com/trust-center)
   >
   > 目前，已擷取的實體永遠都是儲存在 Customer Insights 管理的 Data Lake 中。
   > 我們只在建立環境時從同一個 Azure 區域支援 Azure Data Lake Gen2 儲存體帳戶。
   > 我們只支援 Azure Data Lake Gen2 階層命名空間 (HNS) 啟用的儲存體帳戶。

   - Azure Data Lake Storage Gen2 選項方面，您可以在資源式選項和訂閱式選項之間選擇進行驗證。 更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。 **容器** 名稱無法變更，將為 "customerinsights"。
   
   - 如果您想要使用 [預測](predictions.md)或以 Microsoft Dataverse 設定共用資料給應用程式和解決方案，請在 **與 Microsoft Dataverse 資料共用的設定並啟用其他功能** 下，提供 Microsoft Dataverse 環境 URL。 選取 **啟用資料共用** 與 Microsoft Dataverse Managed Data Lake 共用 Customer Insights 輸出資料。

     > [!NOTE]
     > - 當您將所有資料儲存到自己的 Azure Data Lake Storage ，目前不支援共用資料給 Microsoft Dataverse Managed Data Lake。
     > - 當您啟用資料共用給 Microsoft Dataverse Managed Data Lake 時，目前不支援[實體中遺失值的預測](predictions.md)。

     > [!div class="mx-imgBorder"]
     > ![啟用與 Microsoft Dataverse 共用資料的組態選項](media/Datasharing-with-DataverseMDL.png)

   當您執行流程如資料內嵌或區段建立時，對應資料夾會在您上述指定的儲存體帳戶中建立。 資料檔案和 model.json 檔案會根據您執行的程序，建立並新增至各自的子資料夾。

   如果您建立多個 Customer Insights 環境並選擇從您的儲存體帳戶環境中儲存輸出實體，各資料夾將針對容器含有 ci_<environmentid> 每個環境分開建立。

### <a name="additional-considerations-for-copy-configuration-preview"></a>複製設定的其他考量 (預覽)

下列組態設定已複製，

- 功能設定
- 內嵌/匯入的資料來源
- 資料統一 (對應、比對、合併) 設定
- 客戶細分
- 量值
- 關聯
- 活動
- 搜尋和篩選索引
- 匯出目的地
- 已排程的重新整理
- 擴充內容
- 模型管理
- 角色指派

下列設定 *未* 複製：

- 客戶設定檔。
- 資料來源認證。 您必須提供每個資料來源的認證，並手動重新整理資料來源。
- Common Data Model 資料夾和 Common Data Service 受管理資料湖的資料來源。 您必須使用與來源環境相同的名稱，手動建立這些資料來源。

複製環境時，您會看到一則指示已建立新環境的確認訊息。 選取 **移至資料來源** 以查看資料來源清單。

所有的資料來源都會顯示 **需要認證** 狀態。 編輯資料來源，並輸入認證以進行重新整理。

> [!div class="mx-imgBorder"]
> ![資料來源已複製](media/data-sources-copied.png)

重新整理資料來源之後，移至 **資料** > **統一**。 您會在此處找到來源環境的設定。 視需要編輯，或選取 **執行** 以開始進行資料統一處理程序，並建立統一的客戶實體。

資料統一完成時，移至 **測量** 和 **分段** 進行重新整理。

## <a name="edit-an-existing-environment"></a>編輯現有環境

您可以編輯現有環境的部分詳細資料。

1.  在應用程式的標頭中選取 **環境** 選取器。

2.  選取 **編輯** 圖示。

3. 在 **編輯環境** 方塊中，您可以更新環境的 **顯示名稱**，但是不可以變更 **區域** 或 **類型**。

4. 如果環境設定為在 Azure Data Lake Storage Gen2 中儲存資料，您可以更新 **帳戶金鑰**。 不過，您無法變更 **帳戶名稱** 或 **容器** 名稱。

5. 或者您可以從帳戶金鑰式連接到資源式或訂閱式連接更新。 一旦升級，您就無法在更新後恢復到帳戶金鑰。 更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。 更新連接時，您無法變更 **容器** 資訊。

## <a name="reset-an-existing-environment"></a>重設現有環境中

作為管理員，如果您要刪除所有組態並移除內嵌的資料，您可以將環境重設為空白狀態。

1.  在應用程式的標頭中選取 **環境** 選取器。 

2.  選取您要重設的環境，並選取省略號 **...**。 

3. 選擇 **重設** 選項。 

4.  若要確認刪除，請輸入環境名稱並選取 **重設**。

## <a name="delete-an-existing-environment-available-only-for-admins"></a>刪除現有的環境 (只有系統管理員可以使用)

作為管理員，您可以刪除您所管理的環境。

1.  在應用程式的標頭中選取 **環境** 選取器。

2.  選取您要重設的環境，並選取省略號 **...**。 

3. 選擇 **刪除** 選項。 

4.  若要確認刪除，請輸入環境名稱，然後選取 **刪除**。


[!INCLUDE[footer-include](../includes/footer-banner.md)]