---
title: Power Automate 連接器 (預覽版) | Microsoft Docs
description: 在 Dynamics 365 Customer Insights 中建立 Microsoft Power Automate 的流程。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196108"
---
# <a name="power-automate-connector-preview"></a>Power Automate 連接器 (預覽)

資料變更時觸發自動發生的特定事件，或直接在 [Microsoft Power Automate](https://flow.microsoft.com/) 中管理更複雜的流程。

## <a name="known-limitations"></a>已知限制

- 60 秒最多可以執行 100 個呼叫。 使用 [$skip 參數](/connectors/customerinsights/#get-items-from-an-entity)，多次呼叫 API 端點。

## <a name="power-automate-triggers"></a>Power Automate 觸發程序

使用觸發程序來建立雲端流程並自動化重複工作，例如通知或更多進階動作。 在以下情況下使用觸發程序：

- 資料來源重新整理失敗。
- 資料來源重新整理成功。
- 在區段上越過閾值。 觸發程序受限在需要超過閾值以上。
- 在業務量值上越過閾值。 此處僅顯示缺少維度的業務量值。 觸發程序受限在需要超過閾值以上。
- 完整的排程重新整理完成時。 此觸發程序不適用於手動啟動的重新整理。
- 統一流程的重新整理完成時。

[在 Power Automate 中設定您的觸發程序。](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate 動作

Power Automate 連接器提供可用觸發程序以外的動作。 如需詳細資訊，請參閱《[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)》。

## <a name="create-a-power-automate-flow"></a>建立 Power Automate 流程

1. 移至 **管理** > **連接**。

1. 在 **Power Automate** 圖格中，選取 **設定**。

1. Power Automate 中的 Customer Insights 連結器 (preview) 開啟。 **登入** Power Automate。

1. 選擇其中一個可用的觸發程序，並在新流程中新增更多步驟。 如需詳細資訊，請參閱[在 Power Automate 中建立雲端工作流程](/power-automate/get-started-logic-flow)。

如何使用流程的範例： 
- 若資料來源重新整理失敗，請將訊息張貼到 Microsoft Teams 頻道。 
- 達到客戶細分上的閾值時，將電子郵件傳送給資料負責人。

[!INCLUDE [footer-include](includes/footer-banner.md)]
