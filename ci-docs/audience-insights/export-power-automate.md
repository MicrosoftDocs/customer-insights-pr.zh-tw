---
title: Power Automate 連接器 | Microsoft Docs
description: 在 Microsoft Power Automate 中從 Dynamics 365 Customer Insights 建立流程。
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405237"
---
# <a name="power-automate-connector-preview"></a>Power Automate 連接器 (預覽)

資料變更時觸發自動發生的特定事件，或直接在 [Power Automate](https://flow.microsoft.com/) 中管理更複雜的流程。

## <a name="power-automate-triggers"></a>Power Automate 觸發程序

您可以使用各種允許您建立流程的觸發程序來自動化重複性工作，例如通知或其他進階動作。 

- 當資料來源重新整理失敗時觸發。 
- 當資料來源重新整理成功時觸發。
- 在區段上越過閾值時觸發。 觸發程序受限在需要超過閾值以上。
- 在業務量值上越過閾值時觸發。 觸發程序限制為必須超過閾值以上。
- 當完成 (資料來源、區段、量值，...) 的完整重新整理時，會引發發射鍵。
- 在完成統整程序 (對應、比對、合併) 機重新整理時觸發。

[在 Power Automate 中設定您的觸發程序](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)。

## <a name="power-automate-actions"></a>Power Automate 動作
Power Automate 連接器提供可用觸發程序以外的動作。 如需詳細資訊，請參閱《[Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)》。

## <a name="create-a-power-automate-flow-in-audience-insights"></a>在對象見解中建立 Power Automate 流程

1. 請在對象見解中前往 **管理員** > **系統**。

1. 在 **系統** 頁面上，選取 **狀態** 索引標籤。

1. 在 **資料來源** 區段中，選取 **流程**，然後從下拉式清單中選取 **建立流程**。
   > [!div class="mx-imgBorder"]
   > ![顯示建立流程動作的 Power Automate 連接器](media/power-automate-connector-create-flow.png "顯示建立流程動作的 Power Automate 連接器")

1. 在 Power Automate 中，選取其中一個可用的觸發程序，以建立您喜歡的流程。 如果您正在建立第一個流程，則必須先使用 Power Automate 連接器進行驗證。
