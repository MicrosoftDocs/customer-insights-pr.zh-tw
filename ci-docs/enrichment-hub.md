---
title: 富集統一的客戶設定檔
description: 使用功能富集您的客戶資料。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954031"
---
# <a name="enrichment-for-customer-profiles-preview"></a>客戶設定檔擴充 (預覽)

使用 Microsoft 和其他合作夥伴等來源的資料來擴充您的客戶資料。

:::image type="content" source="media/enrichment-hub-page.png" alt-text="擴充中心頁面。":::

請移至 **資料** > **擴充** 來使用擴充選項。  

您必須有參與者或系統管理員權限，才能建立或編輯擴充內容。 如需詳細資訊，請參閱[權限](permissions.md)。

您將會在 **探索** 索引標籤上發現所有支援的擴充選項。

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- 由 LiveRamp AbiliTec 提供的 [AbiliTec 身分識別](enrichment-liveramp.md)
- [Brands](enrichment-microsoft.md) 由 Microsoft 提供
- 由 Experian 提供的[人口統計](enrichment-experian.md)
- Microsoft 提供的[增強地址](enrichment-enhanced-addresses.md)
- [Interests](enrichment-microsoft.md) 由 Microsoft 提供
- Microsoft Azure 地圖服務提供的[位置資料](enrichment-azure-maps.md)
- HERE Technologies 提供的 [位置資料](enrichment-here.md)
- 透過安全檔案傳輸通訊協定 (SFTP) 的 [SFTP 自訂資料](enrichment-SFTP-custom-import.md)

# <a name="business-accounts-b-to-b"></a>[商務帳戶 (B2B)](#tab/b2b)

- Microsoft 提供的[客戶參與度資料](enrichment-office.md)
- Dun&Bradstreet 提供的[公司資料](enrichment-dnb.md)
- Leadspace 提供的 [公司資料](enrichment-leadspace.md)
- Microsoft 提供的[增強地址](enrichment-enhanced-addresses.md)
- Microsoft 提供的[增強型公司資料](enrichment-enhanced-company-data.md)
- Microsoft Azure 地圖服務提供的[位置資料](enrichment-azure-maps.md)
- HERE Technologies 提供的 [位置資料](enrichment-here.md)
- 透過安全檔案傳輸通訊協定 (SFTP) 的 [SFTP 自訂資料](enrichment-SFTP-custom-import.md)

---

在 **我的擴充內容** 索引標籤上，您可以查看您已設定的擴充內容，並編輯其屬性。 您也可以從擴充建立[客戶細分](segments.md)或[量值](measures.md)。

## <a name="manage-existing-enrichments"></a>管理現有的擴充內容

移至 **我的擴充** 索引標籤，以查看所有設定好的擴充。 每個擴充內容都表示為一列，其中包含有關擴充內容的其他資訊。

選取擴充以查看可用的選項。 您也可以選取清單項目上的垂直省略符號 (&vellip;) 來查看選項。 如果您已設定數個擴充，則可以使用搜尋方塊快速尋找。

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="擴充清單中用來管理擴充內容的選項。":::

- **檢視** 包含擴充客戶設定檔數目的擴充內容詳細資料。
- **編輯** 擴充內容設定。
- **執行** 擴充以使用最新資料更新客戶設定檔。
- **停用** 現有擴充內容，使其不再隨每次排定的重新整理自動進行重新整理。 上次成功重新整理的資料仍可繼續使用。 **啟用** 非使用中擴充內容，以重新開始隨每次排定的重新整理進行自動重新整理。
- **刪除** 擴充。

要一次執行或停用多個擴充，請在清單中選取它們。 查看和編輯選項無法以批次動作使用。 一次只能進行一個。

## <a name="enrichments-and-connections"></a>擴充與連接

協力廠商擴充設定為要使用[連接](connections.md)，連結由系統管理員設定認證，並同意資料傳輸。 系統管理員和參與者可以使用連線組態擴充。  

## <a name="multiple-enrichments-of-the-same-type"></a>多個相同類型的擴充

在擴充設定期間，會指定要擴充的實體，這可讓您擴充個人資料的子集。 例如，只擴充特定客戶細分的資料。 您可以設定數個相同類型的擴充，並重複使用相同的連接。 某些擴充將限制相同類型的擴充可建立的數量。 在 **擴充** 頁面的 **探索** 索引標籤上，可以在每個磚上看到限制和目前用途。

## <a name="enrich-data-sources-before-unification"></a>在整合之前擴充資料來源

在資料整合處理之前，先擴充您的客戶資料，以提升資料比對的成果。 如需詳細資訊，請參閱[資料來源擴充](data-sources-enrichment.md)。

## <a name="run-or-refresh-enrichments"></a>執行或重新整理擴充

1. 選取 **執行** 開始進行擴充程序。 或者，您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。 處理時間視客戶資料的大小而定。

1. 又或者，[查看擴充程序的進度](#see-the-progress-of-the-enrichment-process)。

1. 擴充程序完成後，請前往 **我的擴充** 以檢閱最新擴充的客戶個人資料、上次更新的時間以及擴充個人資料的數量。

1. 選取擴充以查看其[擴充結果](#enrichment-results)。

### <a name="see-the-progress-of-the-enrichment-process"></a>查看擴充程序的進度

在重新整理時或重新整理完成後，您都可以查看擴充程序詳細資料，包括其狀態和潛在問題。 瞭解哪些程序包含在擴充的重新整理中，以及執行該程序所花費的時間。 擴充狀態支援 Experian、Leadspace、HERE Technologies、SFTP 匯入以及 Azure 地圖服務。

1. 移至 **資料** > **擴充**。
1. 在 **我的擴充** 索引標籤中，選取擴充狀態將打開側邊窗格。
1. 在 **進度詳細資料** 窗格中，展開 **擴充** 區段。
1. 在您想要查看進度的擴充底下，選取 **查看詳細資料**。
1. 在 **工作詳細資料** 窗格中，選取 **顯示詳細資料**，以查看包含在擴充更新的程序及其狀態。

## <a name="enrichment-results"></a>擴充結果

完成擴充後，檢閱擴充結果。

1. 移至 **資料** > **擴充**。
1. 在 **我的擴充** 索引標籤中，選取擴充以了解相關資訊。

所有的擴充都會顯示基本資訊，例如擴充個人資料的數量，以及隨時間完成擴充的個人資料數量。 **預覽已擴充的客戶個人資料** 磚顯示已生成擴充實體的範例。 若要查看更詳細的檢視表，選取 **查看更多**，並選取 **資料** 索引標籤。

:::image type="content" source="media/enrichments-results.png" alt-text="擴充結果頁面。":::

如果有的話，**已擴充欄位的客戶數** 可讓您鑽研到每個擴充的欄位。

某些擴充也會顯示擴充類型的特定資訊。 如需詳細資訊，請參閱相關文件。

[!INCLUDE [footer-include](includes/footer-banner.md)]
