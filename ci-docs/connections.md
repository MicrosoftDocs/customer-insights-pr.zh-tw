---
title: 連接 (預覽版) 概觀
description: 從 Customer Insights 連接到其他服務。
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245501"
---
# <a name="connections-preview-overview"></a>連接 (預覽版) 概觀

連接是與 Customer Insights 啟用資料共用的關鍵。 每個連接都會對特定服務建立資料共用。 使用連接來進行[設定協力廠商擴充](enrichment-hub.md)和[設定匯出](export-destinations.md)。 同一個連接可以多次使用。 例如，一個對 Dynamics 365 Marketing 的連結可用於多個匯出，而另一個對 Leadspace 的連接可以用來進行多個擴充。

## <a name="export-connections"></a>匯出連接

只有系統管理員能夠設定新的連接，但是系統管理員也能將[存取權授予給參與者](#allow-contributors-to-use-a-connection-for-exports)，讓他們使用現有連接。 系統管理員控制資料的流向，參與者定義符合其需求的酬載和頻率。

## <a name="enrichment-connections"></a>擴充連接

只有系統管理員才可以設定新的連接，但是建立好的連接都可供系統管理員和參與者使用。 系統管理員能管理認證並同意資料傳輸。 系統管理員和參與者都可以使用這些連接進行擴充。

## <a name="add-a-new-connection"></a>新增連接

### <a name="prerequisites"></a>先決條件

- [系統管理員權限](permissions.md)
- 其他 Microsoft 服務 (如果有的話) 位於相同的組織中

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇要建立的連接類型。 或者，請前往 **探索** 索引標籤並選取連接磚上的 **設定**。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 輸入必要的詳細資料。 確切的欄位會視您要連接的服務而定。 若要了解連接類型的詳細資料，請參考目標服務的相關文章。

1. 如果您 [使用自己的金鑰保存庫](use-azure-key-vault.md)儲存祕密，請使用 **金鑰保存庫** 並從清單選擇祕密。

1. 請檢閱資料隱私權和合規性，並選取 **我同意**。

1. 選取 **儲存** 來建立連結。

### <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸至協力廠商或其他 Microsoft 產品時，您允許傳輸資料到 Dynamics 365 Customer Insights 合規性邊界之外，包括潛在的敏感性資料 (例如個人資料)。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保協力廠商符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 管理員可以隨時移除此連線，不再繼續使用該功能。

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>允許參與者使用匯出連接

設定或編輯匯出連接時，選擇允許哪些使用者使用此連接以定義[匯出](export-destinations.md)。 根據預設，具有系統管理員角色的使用者可以使用連接。 變更 **選取能使用此連接的人員** 設定，並允許具備參與者角色的使用者使用此連接。

- 參與者無法查看或編輯該連接。 在建立匯出時，他們只能看到顯示名稱及其類型。
- 透過共用連接，您可以讓參與者使用連接。 當參與者設定匯出時，會看到共用的連接。 他們可以管理使用此特定連接的每個匯出。
- 您可以保留參與者已定義的匯出，並變更此設定。

## <a name="manage-existing-connections"></a>管理現有的連接

1. 移至 **管理** > **連接**。

1. 選取 **擴充** 或 **匯出** 索引標籤，以查看擴充或匯出連接的清單、連接類型、建立的時間以及可存取的使用者。 您可以依據任一欄排序連接清單。

1. 選取連接來查看可用的動作。

   - **編輯** 連接。
   - [**移除**](#remove-a-connection)連接。

### <a name="remove-a-connection"></a>移除連接

如果擴充或匯出正在使用預計移除的連接，您必須先中斷它們的連結或移除它們。 移除對話方塊將引導您到相關的擴充或匯出。

> [!TIP]
> 停用環境則中斷連結的匯出會變成停用。 您可以在[擴充](enrichment-hub.md)或[匯出](export-destinations.md)頁面上新增另一個連接給它們，以重新啟動。

1. 移至 **管理** > **連接**。

1. 選取 **擴充** 或 **匯出** 索引標籤。

1. 選取您要移除的連接。

1. 從下拉式功能表中選取 **移除**。 確認對話方塊隨即出現。

   1. 如果有擴充或匯出使用此連接，請選取按鈕，以查看正在使用此連接的功能。
      - **匯出：** 選擇 **移除** 匯出或 **中斷連接**。 中斷連接將保留匯出設定，但除非匯出中新增另一個連接，否則不會執行。
      - **擴充：** 選擇 **刪除** 或 **停用** 擴充。
   1. 當連接不再有其他相依性時，請回到 **管理** > **連結**，然後嘗試再次移除該連接。

1. 請選取 **刪除**，來確認刪除。

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>請借助您自己的金鑰保存庫管理的祕密設定連接

某些連接需要像 API 金鑰或密碼之類的祕密。 某些連接支援儲存在您自己金鑰保存庫的祕密。 了解更多支援的連接及在如何在[金鑰保存庫上設定 Customer Insights](use-azure-key-vault.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
