---
title: 使用 Azure Data Lake 帳戶連接至 Common Data Model 資料夾
description: 搭配使用 Azure Data Lake Storage 的 Common Data Model 資料處理。
ms.date: 07/27/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: e071bf9364b44a92d81c9ff2269ff4e8654010aa
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206989"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>在 Azure Data Lake Storage 中連線至資料

使用 Azure Data Lake Storage Gen2 帳戶將資料插入 Dynamics 365 Customer Insights。 資料擷取可以為全部或累加。

## <a name="prerequisites"></a>先決條件

- 資料擷取僅支援 Azure Data Lake Storage *Gen2* 帳戶。 您無法使用 Azure Data Storage Gen1 帳戶內嵌資料。

- Azure Data Lake Storage 帳戶必須已啟用[階層命名空間](/azure/storage/blobs/data-lake-storage-namespace)。 資料必須以階層式資料夾格式儲存，且格式中定義了根資料夾並包含每個實體的子資料夾。 子資料夾可以擁有完整資料或累加式資料資料夾。

- 若要以 Azure 服務主體驗證，請確定它已在您的租用戶中設定完成。 如需更多資訊，請參閱[使用 Azure 服務主體連接 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。

- 您想要連接和內嵌資料的 Azure Data Lake Storage，必須與 Dynamics 365 Customer Insights 環境位於相同的 Azure 區域。 不支援從不同 Azure 區域的 Data Lake 連接到 Common Data Model 資料夾。 若要知道環境的 Azure 區域，在 Customer Insights 請前往 **系統管理員** > **系統** > **關於**。

- 儲存在線上服務中的資料可能會儲存在跟 Dynamics 365 Customer Insights 處理或儲存資料不同的位置。 匯入或連接至儲存在線上服務的資料，即表示您同意可以將資料傳輸或儲存至 Dynamics 365 Customer Insights。 [在 Microsoft 信任中心深入了解](https://www.microsoft.com/trust-center)。

- 若要存取儲存體帳戶，Customer Insights 服務主體必須是下列其中一種角色。 如需詳細資訊，請參閱[將權限授與服務主體以存取儲存體帳戶](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account)。
  - 儲存體 Blob 資料讀者
  - 儲存體 Blob 負責人
  - 儲存體 Blob 資料參與者

- Data Lake Storage 中的資料應遵循的 Common Data Model 標準儲存，並使用 Common Data Model 資訊清單來表示資料檔案的結構描述 (*.csv* 或 .parquet)。 此資訊清單必須提供實體的詳細資料 (例如實體欄和資料類型) 以及資料檔案位置和檔案類型。 如需更多資訊，請前往 [Common Data Model 資訊清單](/common-data-model/sdk/manifest)。 如果此資訊清單不存在，則具備 Storage Blob 資料擁有者或儲存 Blob 資料參與者存取權限的管理使用者，可以在內嵌資料時定義結構描述。

## <a name="connect-to-azure-data-lake-storage"></a>連線至 Azure Data Lake Storage

1. 移至 **資料** > **資料來源**。

1. 選取 **新增資料來源**。

1. 選取 **Azure data lake storage**。

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="可用於輸入 Azure Data Lake 連接詳細資料的對話方塊。" lightbox="media/data_sources_ADLS.png":::

1. 輸入資料來源的 **名稱** 和 **說明** (選填)。 名稱是資料來源的唯一標識，用於下游程式中的參照，且無法變更。

1. 您可以選擇下列其中一種選項，以 **連接使用的儲存體**。 如需更多資訊，請參閱[使用 Azure 服務主體將 Customer Insights 連接到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。

   - **Azure 資源**：輸入 **資源識別碼**。或者，如果您想透過 Azure Private Link 從儲存體帳戶中內嵌資料，請選取 **啟用 Private Link**。 如需詳細資訊，請參閱[私人連結](security-overview.md#private-links-tab)。
   - **Azure 訂閱**：選取 **訂閱**，然後選取 **資源群組** 和 **儲存體帳戶**。 或者，如果您想透過 Azure Private Link 從儲存體帳戶中內嵌資料，請選取 **啟用 Private Link**。 如需詳細資訊，請參閱[私人連結](security-overview.md#private-links-tab)。
  
   > [!NOTE]
   > 在容器或儲存體帳戶上您需要擁有下列任一個角色，才能建立資料來源：
   >
   >  - [儲存體 Blob 資料讀者] 足以讀取儲存體帳戶，並將資料內嵌至 Customer Insights。 
   >  - 如果您想要直接在 Customer Insights 中編輯資訊清單檔案，則需要 [儲存體 Blob 資料參與者] 或 [儲存體 Blob 資料負責人]。  
  
1. 選擇包含資料和結構描述 (model.json or manifest.json 檔案) 的 **容器** 名稱，以從其中匯入資料，然後選取 **下一步**。
   > [!NOTE]
   > 所有關聯到環境中另一個資料來源的 model.json 或 manifest.json 檔案將不會顯示在清單中。 然而同一個 model.json 或 manifest.json 檔案可在多個環境中用在資料來源。

1. 若要建立新的結構描述，請移至[建立新的結構描述檔案](#create-a-new-schema-file)。

1. 若要使用現有的結構描述，請前往 model.json 或 manifest.cdm.json 檔案的資料夾。 您可以在目錄中搜尋檔案。

1. 請選取 json 檔案，然後選取 **下一步**。 顯示可用實體的清單

   :::image type="content" source="media/review-entities.png" alt-text="可選取實體清單的對話方塊":::

1. 選取您要納入的實體。

   :::image type="content" source="media/ADLS_required.png" alt-text="顯示對主索引鍵為必要項目的對話方塊":::

   > [!TIP]
   > 若要在 JSON 編輯介面中編輯實體，請選取實體，然後選取 **編輯結構描述檔案**。 進行變更並選取 **儲存**。

1. 如果選定的實體需要累加式擷取，則 **累加式重新整理** 下顯示 **必要**。 若要對每一個實體，請參閱[為 Azure Data Lake 資料來源設定累加式重新整理](incremental-refresh-data-sources.md)。

1. 對於尚未定義主索引鍵的選定實體，則會在 **主索引鍵** 下顯示 **必要**。 對每一個實體：
   1. 選取 **必要**。 **編輯實體** 面板隨即顯示。
   1. 選擇 **主索引鍵**。 主索引鍵是實體的唯一屬性。 若要讓屬性成為有效的主索引鍵，其中不能包含重複值、遺漏值或 Null 值。 字串、整數及 GUID 資料類型屬性均支援主索引鍵。
   1. 或者，變更分區模式。
   1. 選取 **關閉** 以儲存並關閉面板。

1. 為每個已包含實體，選取 **屬性** 的數量。 **管理屬性** 頁面隨即顯示。

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="可選取資料分析的對話方塊。":::

   1. 建立新的屬性、編輯或刪除現有的屬性。 您可以變更名稱、資料格式或新增語義類型。
   1. 若要啟用分析和其他功能，請選取整個實體或特定屬性的 **資料分析**。 根據預設，沒有實體會啟用於資料剖析。
   1. 選取 **完成**。

1. 選取 **儲存**。 **資料來源** 頁面會打開，顯示處於 **重新整理** 狀態中的新資料來源。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

載入資料可能需要花費一些時間。 成功重新整理之後，即可從 [**實體**](entities.md)頁面查看擷取的資料。

### <a name="create-a-new-schema-file"></a>建立新的結構描述檔案

1. 選取 **新增結構描述檔案**。

1. 輸入檔案名稱，然後選取 **儲存**。

1. 選取 **新增實體**。 **新增實體** 面板隨即顯示。

1. 輸入實體名稱，然後選擇 **資料檔案位置**。
   - **多個 .csv 或 .parquet 檔案**：瀏覽至根資料夾，選取模式類型，然後輸入運算式。
   - **單一 .csv 或 .parquet 檔案**：瀏覽至 .csv 或 .parquet 檔案位置，並選取該檔案。

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="可建立新實體的對話方塊，並醒目提示資料檔案位置。":::

1. 選取 **儲存**。

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="可定義或自動生成屬性的對話方塊。":::

1. 選取 **定義屬性** 以手動新增屬性，或選取 **自動生成屬性**。 若要定義屬性，請輸入名稱，並選取資料格式及語義類型 (選填)。 對於自動產生屬性：

   1. 自動生成屬性後，請選取 **檢閱屬性**。 **管理屬性** 頁面隨即顯示。

   1. 請確定每個屬性的資料格式都正確。

   1. 若要啟用分析和其他功能，請選取整個實體或特定屬性的 **資料分析**。 根據預設，沒有實體會啟用於資料剖析。

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="可選取資料分析的對話方塊。":::

   1. 選取 **完成**。 **選取實體** 頁面隨即顯示。

1. 繼續新增實體和屬性 (如果可行)。

1. 新增實體之後，選取 **包括** 在資料來源擷取中納入實體。

   :::image type="content" source="media/ADLS_required.png" alt-text="顯示對主索引鍵為必要項目的對話方塊":::

1. 如果選定的實體需要累加式擷取，則 **累加式重新整理** 下顯示 **必要**。 若要對每一個實體，請參閱[為 Azure Data Lake 資料來源設定累加式重新整理](incremental-refresh-data-sources.md)。

1. 對於尚未定義主索引鍵的選定實體，則會在 **主索引鍵** 下顯示 **必要**。 對每一個實體：
   1. 選取 **必要**。 **編輯實體** 面板隨即顯示。
   1. 選擇 **主索引鍵**。 主索引鍵是實體的唯一屬性。 若要讓屬性成為有效的主索引鍵，其中不能包含重複值、遺漏值或 Null 值。 字串、整數及 GUID 資料類型屬性均支援主索引鍵。
   1. 或者，變更分區模式。
   1. 選取 **關閉** 以儲存並關閉面板。

1. 選取 **儲存**。 **資料來源** 頁面會打開，顯示處於 **重新整理** 狀態中的新資料來源。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

載入資料可能需要花費一些時間。 成功重新整理之後，即可從 [**實體**](entities.md)頁面查看擷取的資料。

## <a name="edit-an-azure-data-lake-storage-data-source"></a>編輯 Azure Data Lake Storage 資料來源

您可以更新 *連接至使用的儲存體帳戶* 選項。 如需更多資訊，請參閱[使用 Azure 服務主體將 Customer Insights 連接到 Azure Data Lake Storage Gen2 帳戶](connect-service-principal.md)。 若要從儲存體帳戶連接至不同的容器，或變更帳戶名稱，請[建立新的資料來源連接](#connect-to-azure-data-lake-storage)。

1. 移至 **資料** > **資料來源**。

1. 在您想要更新的資料來源旁邊，選取 **編輯**。

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="可編輯 Azure Data Lake 資料來源的對話方塊。":::

1. 變更下列資訊：

   - **描述**
   - **連接您使用的儲存空間** 並連接資訊。 更新連接時，您無法變更 **容器** 資訊。
      > [!NOTE]
      > 必須把下列的其中一種角色指派給儲存體帳戶或容器：
        > - 儲存體 Blob 資料讀者
        > - 儲存體 Blob 負責人
        > - 儲存體 Blob 資料參與者

   - **啟用 Private Link** 如果您想透過 Azure Private Link 從儲存體帳戶中內嵌資料。 如需詳細資訊，請參閱[私人連結](security-overview.md#private-links-tab)。

1. 選取 **下一步**。
1. 變更下列：
   - 瀏覽至不同的 model.json 或 manifest.json 檔案位置，該檔案包含一組來自該容器的不同實體集。
   - 若要新增其他實體進行內嵌，請選取 **新增實體**。
   - 若要移除任何已選定的實體 (如果沒有任何相依性)，請選取該實體，然後 **刪除**。
      > [!IMPORTANT]
      > 如果現有的 model.json 或 manifest.json file檔案對實體集合有相依性，您將會看到錯誤訊息，且無法選取不同的 model.json 或 manifest.json 檔案。 在變更 model.json 或 manifest.json 檔案之前移除這些相依性，或以您要使用的 model.json 或 manifest.json 檔案建立新的資料來源來避免移除相依性。
   - 若要變更資料檔案位置或主索引鍵，請選取 **編輯**。
   - 若要變更累加式擷取資料，請參閱[為 Azure Data Lake 資料來源設定累加式重新整理](incremental-refresh-data-sources.md)。
   - 僅變更機構名稱，使其符合 .json 檔案中的實體名稱。

     > [!NOTE]
     > 在擷取之後，一律保持 Customer Insights 中的實體名稱與 model.json 或 manifest.json 文件中的實體名稱相同。 在每次系統重新整理期間，Customer Insights 會使用 model.json 或 manifest.json 驗證所有實體名稱。 如果在 Customer Insights 內部或外部變更實體名稱，則會發生錯誤，因為 Customer Insights 在 .json 文件中找不到新實體名稱。 如果意外變更已擷取的實體名稱，請在 Customer Insights 中編輯實體名稱，使其符合 .json 檔案中的名稱。

1. 選取 **屬性** 來新增或變更屬性，或啟用資料分析。 然後，選取 **完成**。

1. 按一下 **儲存** 以套用變更，並返回至 **資料來源** 頁面。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
