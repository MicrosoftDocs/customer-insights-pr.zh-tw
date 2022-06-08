---
title: 富集統一的客戶設定檔
description: 使用功能富集您的客戶資料。
ms.date: 03/29/2022
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
ms.openlocfilehash: abc1b6af80e8854ee3bc930453634ef67376c4af
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800595"
---
# <a name="enrichment-for-customer-profiles-preview"></a>客戶設定檔擴充 (預覽)

使用 Microsoft 和其他合作夥伴等來源的資料來擴充您的客戶資料。

:::image type="content" source="media/enrichment-hub-page.png" alt-text="擴充中心頁面。":::

請移至 **資料** > **擴充** 來使用擴充選項。  

您必須有參與者或系統管理員權限，才能建立或編輯擴充內容。 如需詳細資訊，請參閱[權限](permissions.md)。

您將會在 **探索** 索引標籤上發現所有支援的擴充選項。

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- [Brands](enrichment-microsoft.md) 由 Microsoft 提供
- [Interests](enrichment-microsoft.md) 由 Microsoft 提供
- Microsoft 提供的[增強地址](enrichment-enhanced-addresses.md) 
- 由 Experian 提供的[人口統計](enrichment-experian.md)
- 透過安全檔案傳輸通訊協定 (SFTP) 的 [自訂資料](enrichment-SFTP-custom-import.md) 
- 由 Microsoft 提供的 [Azure 地圖服務](enrichment-azure-maps.md)
- HERE Technologies 提供的 [位置資料](enrichment-here.md) 
- 由 LiveRamp AbiliTec 提供的[身分識別](enrichment-liveramp.md)

# <a name="business-accounts-b-to-b"></a>[商務帳戶 (B2B)](#tab/b2b)

- Leadspace 提供的 [公司資料](enrichment-leadspace.md)
- Microsoft 提供的[增強地址](enrichment-enhanced-addresses.md) 
- Microsoft 提供的[增強型公司資料](enrichment-enhanced-company-data.md)
- HERE Technologies 提供的 [位置資料](enrichment-here.md) 
- 透過安全檔案傳輸通訊協定 (SFTP) 的 [自訂資料](enrichment-SFTP-custom-import.md) 
- 由 Microsoft 提供的 [Azure 地圖服務](enrichment-azure-maps.md)
- Dun&Bradstreet 提供的[公司資料](enrichment-dnb.md)
- Microsoft 提供的[客戶參與度資料](enrichment-office.md)

---

在 **我的擴充內容** 索引標籤上，您可以查看您已設定的擴充內容，並編輯其屬性。

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

在擴充設定期間，會指定要擴充的實體，這可讓您擴充個人資料的子集。 例如，只擴充特定客戶細分的資料。 您可以設定數個相同類型的擴充，並重複使用相同的連接。 某些擴充將限制相同類型的擴充可建立的數量。 在 **擴充** 頁面上可以看到限制和目前使用的值 。

## <a name="enrich-data-sources-before-unification"></a>在整合之前擴充資料來源

在資料整合處理之前，先擴充您的客戶資料，以提升資料比對的成果。 如需詳細資訊，請參閱[資料來源擴充](data-sources-enrichment.md)。

## <a name="see-the-progress-of-the-enrichment-process"></a>查看擴充程序的進度

在重新整理時或重新整理完成後，您都可以查看擴充程序詳細資料，包括其狀態和潛在問題。 瞭解哪些程序包含在擴充的重新整理中，以及執行該程序所花費的時間。 擴充狀態支援 Experian、Leadspace、HERE Technologies、SFTP 匯入以及 Azure 地圖服務。

查看擴充的狀態

1. 移至 **資料** > **擴充**。 
1. 在 **我的擴充** 索引標籤中，選取擴充的狀態以打開側邊窗格。 
1. 在 **進度詳細資料** 窗格中，展開 **擴充** 區段。 
1. 在您想要查看進度的擴充底下，選取 **查看詳細資料**。 
1. 在 **工作詳細資料** 窗格中，選取 **顯示詳細資料**，以查看包含在擴充更新的程序及其狀態。 

## <a name="enrichment-results"></a>擴充結果

完成擴充後，您可以檢閱擴充結果。

1. 移至 **資料** > **擴充**。 
1. 選取需要更多資訊的擴充

所有的擴充都會顯示基本資訊，例如擴充個人資料的數量、生成擴充實體的預覽，以及隨時間完成擴充的個人資料數量。 如果有的話，**已擴充欄位的客戶數** 可讓您鑽研到每個擴充的欄位。

:::image type="content" source="media/enrichments-results.png" alt-text="擴充結果頁面。":::

某些擴充也會顯示擴充類型的特定資訊。 如需詳細資訊，請參閱相關擴充文件。


[!INCLUDE [footer-include](includes/footer-banner.md)]
