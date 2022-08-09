---
title: 資料來源擴充 (預覽版)
description: 在進行資料整合程序前，擴充資料來源。
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207173"
---
# <a name="enrichment-for-data-sources-preview"></a>資料來源擴充 (預覽版)

使用來自 Microsoft 和其他合作夥伴等來源的資料，在資料整合前擴充您的客戶資料。 資料來源擴充協助產生更高的資料完整性與品質，當您整合資料後，可取得更好的結果。 例如，使用正常化和標準格式來處理位址，提升比對結果的品質。 如需支援的擴充清單，請參閱[支援的資料來源擴充選項](#supported-data-source-enrichments)。

## <a name="enrich-a-data-source"></a>擴充資料來源

您必須具備參與者或系統管理員[權限](permissions.md)，才能建立或編輯擴充。  

1. 請前往 **資料** > **整合**。 選取您要擴充的實體，並選取一個屬性作為實體的[主索引鍵](map-entities.md#select-primary-key-and-semantic-type-for-attributes)。

1. 移至 **資料** > **資料來源**。

1. 請在您要擴充的資料來源旁邊，選取垂直省略符號 (&vellip;)，接著選取 **擴充**。

   :::image type="content" source="media/data_sources_enrich.png" alt-text="已醒目提示「擴充」的資料來源頁面":::

   **探索** 索引標籤會顯示[受支援的資料來源擴充選項](#supported-data-source-enrichments)。

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="資料來源擴充頁面。":::

1. 選取 **擴充我的資料**，以設定資料來源擴充。 隨即自動填入輸出實體名稱。

## <a name="supported-data-source-enrichments"></a>受支援的資料來源擴充

下列擴充目前可供資料來源使用。 檢閱擴充的詳細步驟，了解如何設定它。

- [增強型地址](enrichment-enhanced-addresses.md)
- [增強公司資料](enrichment-enhanced-company-data.md)
- [取自 LiveRamp 的身分識別資料](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>管理現有的資料來源擴充

移至 **資料** > **擴充**。 在 **我的擴充** 索引標籤中，查看設定好的擴充、它們的狀態、要更新的客戶數，以及上次重新整理資料的時間。 您可以用任何欄來排序擴充清單，或是使用搜尋方塊尋找您要管理的擴充。

選取擴充以查看可用的選項。 您也可以選取清單項目上的垂直省略符號 (&vellip;) 來查看選項。

您可以查看、編輯、執行或刪除資料來源擴充。 如需更多資訊，請參閱[管理現有擴充](enrichment-hub.md#manage-existing-enrichments)。
