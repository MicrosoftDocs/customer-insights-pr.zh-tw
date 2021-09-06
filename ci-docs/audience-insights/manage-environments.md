---
title: 建立和管理環境
description: 瞭解如何註冊服務及管理環境。
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034167"
---
# <a name="manage-environments"></a>管理環境

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>切換環境

選取頁面右上角的 **環境** 控制項，以變更環境。

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="螢幕擷取畫面，圖為切換環境的控制項。":::

系統管理員能夠[建立](get-started-paid.md)和管理環境。

## <a name="edit-an-existing-environment"></a>編輯現有環境

您可以編輯現有環境的部分詳細資料。

1.  在應用程式的標頭中選取 **環境** 選取器。

2.  選取 **編輯** 圖示。

3. 在 **編輯環境** 方塊中，您可以更新環境的 **顯示名稱**，但是不可以變更 **區域** 或 **類型**。

4. 如果環境設定要在 Azure Data Lake Storage 中儲存資料，您可以更新 **帳戶金鑰**。 不過，您無法變更 **帳戶名稱** 或 **容器** 名稱。

5. 或者您可以將帳戶金鑰型連接更新到資源型或訂閱型連接。 一旦升級，您就無法在更新後恢復到帳戶金鑰。 更多資訊請見 [使用 Azure 服務主體連接對象見解到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。 更新連接時，您無法變更 **容器** 資訊。

6. 或者，您可以在 **設定與 Microsoft Dataverse 共用資料並啟用其他功能** 下，提供 Microsoft Dataverse 環境 URL。 這些功能包含運用 Microsoft Dataverse 與應用程式和解決方案共用資料、從內部部署資料來源擷取資料、或使用[預測](predictions.md)。 選取 **啟用資料共用** 與 Microsoft Dataverse Managed Data Lake 共用 Customer Insights 輸出資料。

   > [!NOTE]
   > - 當您將所有資料儲存到自己的 Azure Data Lake Storage ，目前不支援共用資料給 Microsoft Dataverse Managed Data Lake。
   > - 當啟用與 Microsoft Dataverse 受管理的 Data Lake 共用資料時，目前不支援對象見解(如果在環境中啟用的話) 中的 PowerBI 嵌入式報表和[預測缺失的值](predictions.md)。

   啟用與 Microsoft Dataverse 的資料共用後，將對資料來源和其他程序開始一次完整的重新整理。 如果程序目前正在執行，您看不到用來啟用與 Microsoft Dataverse 共用資料的選項。 等待這些程序完成，或者取消它們以啟用資料共用。 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="啟用與 Microsoft Dataverse 共用資料的設定選項。":::
   
   當您執行流程如資料內嵌或區段建立時，對應資料夾會在您上述指定的儲存體帳戶中建立。 根據您執行的程序，會建立資料檔案和 model.json 並新增至各自的子資料夾。

## <a name="copy-the-environment-configuration"></a>複製環境設定

當您建立新的環境時，您可以選擇從現有的環境複製設定。 

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

*不會* 複製下列資料：

- 客戶設定檔。
- 資料來源認證。 您必須提供每個資料來源的認證，並手動重新整理資料來源。
- 來自 Common Data Model 資料夾和 Dataverse 受管理的 Data Lake 的資料來源。 您必須使用與來源環境相同的名稱，手動建立這些資料來源。

複製環境時，您會看到一則指示已建立新環境的確認訊息。 選取 **移至資料來源** 以查看資料來源清單。

所有的資料來源都會顯示 **需要認證** 狀態。 編輯資料來源，並輸入認證以進行重新整理。

:::image type="content" source="media/data-sources-copied.png" alt-text="已複製且需要驗證的資料來源清單。":::

重新整理資料來源之後，移至 **資料** > **統一**。 您會在此處找到來源環境的設定。 視需要編輯，或選取 **執行** 以開始進行資料統一處理程序，並建立統一的客戶實體。

資料統一完成時，移至 **測量** 和 **分段** 進行重新整理。

## <a name="reset-an-existing-environment"></a>重設現有環境中

作為管理員，如果您要刪除所有組態並移除內嵌的資料，您可以將環境重設為空白狀態。

1.  在應用程式的標頭中選取 **環境** 選取器。 

2.  選取您要重設的環境，並選取省略號 (**...**)。 

3. 選擇 **重設** 選項。 

4.  若要確認刪除，請輸入環境名稱並選取 **重設**。

## <a name="delete-an-existing-environment"></a>刪除現有環境

作為管理員，您可以刪除您所管理的環境。

1.  在應用程式的標頭中選取 **環境** 選取器。

2.  選取您要重設的環境，並選取省略號 (**...**)。 

3. 選擇 **刪除** 選項。 

4.  若要確認刪除，請輸入環境名稱，然後選取 **刪除**。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
