---
title: Power Automate 連接器 | Microsoft Docs
description: 在 Microsoft Power Automate 中從 Dynamics 365 Customer Insights 建立流程。
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268814"
---
# <a name="power-automate-connector-preview"></a>Power Automate 連接器 (預覽)

資料變更時觸發自動發生的特定事件，或直接在 [Power Automate](https://flow.microsoft.com/) 中管理更複雜的流程。

## <a name="power-automate-triggers"></a>Power Automate 觸發程序

使用觸發程序來建立雲端流程並自動化重複工作，例如通知或更多進階動作。 

- 當資料來源重新整理失敗時觸發。 
- 當資料來源重新整理成功時觸發。
- 在區段上越過閾值時觸發。 觸發程序受限在需要超過閾值以上。
- 在業務量值上越過閾值時觸發。 觸發程序限制為必須超過閾值以上。
- 當完成 (資料來源、區段、量值，...) 的完整重新整理時，會引發發射鍵。
- 在完成統整程序 (對應、比對、合併) 機重新整理時觸發。

[在 Power Automate 中設定您的觸發程序](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)。

## <a name="power-automate-actions"></a>Power Automate 動作
Power Automate 連接器提供可用觸發程序以外的動作。 如需詳細資訊，請參閱《[Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)》。

## <a name="create-a-power-automate-flow"></a>建立 Power Automate 流程

1. 在對象見解中，前往 **系統管理員** > **匯出目的地**。

1. 在 **Power Automate** 圖格中，選取 **設定**。

1. Power Automate 中的 Customer Insights 連結器 (preview) 開啟。 **登入** Power Automate。

1. 選擇其中一個可用的觸發程序，並在新流程中新增更多步驟。 如需詳細資訊，請參閱[在 Power Automate 中建立雲端工作流程](https://docs.microsoft.com/power-automate/get-started-logic-flow)。

如何使用流程的範例： 
- 若資料來源重新整理失敗，請將訊息張貼到 Microsoft Teams 頻道。 
- 達到客戶細分上的閾值時，將電子郵件傳送給資料負責人。



[!INCLUDE[footer-include](../includes/footer-banner.md)]