---
title: 富集統一的客戶設定檔
description: 使用功能富集您的客戶資料。
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: d12c0a9dd65d31f9ae8a9cafeafab2767d57893e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555251"
---
# <a name="enrichment-for-customer-profiles-preview"></a>客戶設定檔擴充 (預覽)

使用 Microsoft 和其他合作夥伴等來源的資料來擴充您的客戶資料。

:::image type="content" source="media/enrichment-hub-page.png" alt-text="擴充中心頁面。":::

請在對象見解中，前往 **資料** > **富集** 搭配富集選項處理。  

您必須有參與者或系統管理員權限，才能建立或編輯擴充內容。 如需詳細資訊，請參閱[權限](permissions.md)。

在 **探索** 索引標籤上，您可找到下列擴充內容：

- [Brands](enrichment-microsoft.md) 由 Microsoft 提供
- [Interests](enrichment-microsoft.md) 由 Microsoft 提供
- Microsoft 提供的[增強地址](enrichment-enhanced-addresses.md)
- Leadspace 提供的 [公司資料](enrichment-leadspace.md)
- 由 Experian 提供的[人口統計](enrichment-experian.md)
- HERE Technologies 提供的 [位置資料](enrichment-here.md)
- 透過安全檔案傳輸通訊協定 (SFTP) 的 [自訂資料](enrichment-SFTP-custom-import.md)

在 **我的擴充內容** 索引標籤上，您可以查看您已設定的擴充內容，並編輯其屬性。

## <a name="manage-existing-enrichments"></a>管理現有的擴充內容

移至 **我的擴充** 索引標籤，以查看所有設定好的擴充。 每個擴充內容都表示為一列，其中包含有關擴充內容的其他資訊。

選取擴充以查看可用的選項。 您也可以選取清單上專案的省略號 (...) 來查看選項。 如果您已設定數個擴充，則可以使用搜尋方塊快速尋找。

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="擴充清單中用來管理擴充內容的選項。":::

- **檢視** 包含擴充客戶設定檔數目的擴充內容詳細資料。
- **編輯** 擴充內容設定。
- **執行** 擴充以使用最新資料更新客戶設定檔。
- **停用** 現有擴充內容，使其不再隨每次排定的重新整理自動進行重新整理。 上次成功重新整理的資料仍可繼續使用。 **啟用** 非使用中擴充內容，以重新開始隨每次排定的重新整理進行自動重新整理。
- **刪除** 擴充。

要一次執行或停用多個擴充，請在清單中選取它們。 查看和編輯選項無法以批次動作使用。 一次只能進行一個。

## <a name="enrichments-and-connections"></a>擴充與連接

協力廠商擴充設定為要使用[連接](connections.md)，連結由系統管理員設定認證，並同意資料傳輸。 系統管理員和參與者都可以使用這些連接設定擴充。  

## <a name="multiple-enrichments-of-the-same-type"></a>多個相同類型的擴充

在擴充設定期間，會指定要擴充的實體，這可讓您擴充個人資料的子集。 例如，只擴充特定客戶細分的資料。 您可以設定數個相同類型的擴充，並重複使用相同的連接。 某些擴充將限制相同類型的擴充可建立的數量。 在 **擴充** 頁面上可以看到限制和目前使用的值 。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
