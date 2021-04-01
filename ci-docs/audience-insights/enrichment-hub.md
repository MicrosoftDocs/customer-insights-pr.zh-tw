---
title: 富集統一的客戶設定檔
description: 使用功能富集您的客戶資料。
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597685"
---
# <a name="enrichment-for-customer-profiles-preview"></a>客戶設定檔擴充 (預覽)

使用 Microsoft 和其他合作夥伴等來源的資料來擴充您的客戶資料。

:::image type="content" source="media/enrichment-hub-page.png" alt-text="擴充中心頁面":::

請在對象見解中，前往 **資料** > **富集** 搭配富集選項處理。    
您必須有參與者或系統管理員權限，才能建立或編輯擴充內容。 如需詳細資訊，請參閱[權限](permissions.md)。

在 **探索** 索引標籤上，您可找到下列擴充內容：

- Microsoft Graph 所提供的[品牌](enrichment-microsoft-graph.md)
- Microsoft Graph 所提供的[興趣](enrichment-microsoft-graph.md)
- Leadspace 提供的 [公司資料](enrichment-leadspace.md)
- Experian 所提供的[人口統計資料](enrichment-experian.md)
- HERE Technologies 提供的 [位置資料](enrichment-here.md)
- 透過安全檔案傳輸通訊協定 (SFTP) 的 [自訂資料](enrichment-SFTP-custom-import.md)

在 **我的擴充內容** 索引標籤上，您可以查看您已設定的擴充內容，並編輯其屬性。

## <a name="manage-existing-enrichments"></a>管理現有的擴充內容

移至 **我的擴充內容** 以查看所有已設定的擴充內容。 每個擴充內容都表示為一列，其中包含有關擴充內容的其他資訊。

選取擴充內容以查看可用的選項。 或者，也可以選取清單項目上的省略符號 (...) 來查看選項。

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="用來管理擴充清單中擴充內容的選項":::

- **檢視** 包含擴充客戶設定檔數目的擴充內容詳細資料。
- **編輯** 擴充內容設定。
- **執行** 擴充以使用最新資料更新客戶設定檔。
- **停用** 現有擴充內容，使其不再隨每次排定的重新整理自動進行重新整理。 上次成功重新整理的資料仍可繼續使用。 **啟用** 非使用中擴充內容，以重新開始隨每次排定的重新整理進行自動重新整理。
- **刪除** 富集。

您可以選取清單中的擴充內容，一次執行或停用多項擴充。 檢視和編輯選項無法用來執行大量動作，僅適用於一次執行一項擴充。


[!INCLUDE[footer-include](../includes/footer-banner.md)]