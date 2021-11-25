---
title: 現有區段的區段見解
description: 洞察現有區段，以查看異同處。
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1f90b0d18331584fce306da38bd31faea93ef97e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732302"
---
# <a name="segment-insights-preview"></a>客戶細分深入解析 (預覽)

探索關於現有客戶細分的其他資訊與深入解析。 找出兩個客戶細分的區別所在兩者的共同點。

## <a name="segment-overlap"></a>客戶細分重疊

客戶細分重疊分析會顯示兩個或更多客戶細分有哪些共同的客戶以及這些客戶的數量。 例如，經常客戶的客戶細分如何與包含對服務或產品滿意之客戶的客戶細分重疊。
您也可以分析特定屬性重疊變更的情況。

### <a name="run-an-overlap-analysis"></a>執行重疊分析

1. 移至 **客戶細分**，然後選取 **深入解析 (預覽)** 索引標籤。

1. 選取 **新增**，並選擇 **選擇深入解析類型** 窗格中的 **重疊** 選項。

1. 選擇感興趣的客戶細分，然後選取 **下一步**。

1. 或者，選擇一個或多個感興趣的欄位，以分析對每個可能欄位值的重疊，然後選取 **下一步**。

1. 提供重疊分析的名稱、選擇性顯示名稱以及描述。

1. 選取 **儲存** 以開始進行分析。 狀態從 [正在重新整理] 變更為 [成功] 時，重疊分析已準備就緒。

### <a name="view-and-optimize-an-overlap-analysis"></a>檢視和最佳化重疊分析

完成分析之後，在 **客戶細分** > **深入解析 (預覽)** 中尋找有關此深入解析的詳細資料。

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="客戶細分重疊深入解析詳細資料。":::

選取深入解析以查看分析結果：

- 與所選要進行分析的客戶細分重疊的成員數目。
- 包含在其中一個客戶細分中，但不在其餘客戶細分中成員的數目。
- 如果您在設定重疊分析時已選取欄位，則會在對應的索引標籤中找到這些欄位。 您可以使用篩選下拉式表單來選擇興趣的任何屬性層級，底部的資料表將顯示相應的資料。

## <a name="segment-differentiators"></a>客戶細分獨特性

客戶細分獨特性可協助您找出一個客戶細分與其餘客戶或與其他客戶細分的區別所在。 您只需選取一個客戶細分，系統就會找出區分所選客戶細分的設定檔案屬性及量值。

### <a name="run-a-differentiator-analysis"></a>執行獨特性分析

1. 移至 **客戶細分**，然後選取 **深入解析 (預覽)** 索引標籤。

1. 選取 **新增**，並選擇 **選擇深入解析類型** 窗格中的 **重疊** 選項。

1. 選擇要做為 **主要客戶細分** 進行分析的客戶細分做為，然後選取 **下一步**。

1. 選擇 **所有客戶** 或 **次要客戶細分** 來與主要客戶細分做比較，然後選取 **下一步**。

1. 或者，選擇一個或多個感興趣的欄位，將注意力集中在分析特定屬性，然後選取 **下一步**。

1. 提供重疊分析的名稱、選擇性顯示名稱以及描述。

1. 選取 **儲存** 以開始進行分析。 狀態從 [正在重新整理] 變更為 [成功] 時，重疊分析已準備就緒。

### <a name="view-and-optimize-a-differentiators-analysis"></a>檢視和最佳化獨特性分析

完成分析之後，在 **客戶細分** > **深入解析 (預覽)** 中尋找有關此深入解析的詳細資料。

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="客戶細分獨特性深入解析詳細資料。":::

選取深入解析以查看分析結果。 獨特性分析包含兩個索引標籤。 **屬性** 索引標籤列出視為獨特性的設定檔屬性。 **量值** 索引標籤會列出獨特性。 每個索引標籤都包含下列詳細資料：

- 獨特性的排名清單，依差異分數排序。
- 每個獨特性的 **差異分數**。 差異分數表示兩個客戶細分之間的屬性差異程度。 差異分數越高，兩個客戶細分之間屬性就越不同。 選取分數以開啟 **差異分數** 窗格，以及該屬性的值分佈。

## <a name="manage-segment-insights"></a>管理客戶細分深入解析

您可以從命令列對深入解析使用下列選項：

- **返回** 以返回深入解析清單
- **重新整理** 以重新執行分析
- **刪除** 以移除此深入解析


[!INCLUDE[footer-include](../includes/footer-banner.md)]
