---
title: 預測概觀
description: Dynamics 365 Customer Insights 應用程式所涵蓋預測案例和選項。
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610180"
---
# <a name="predictions-overview"></a>預測概觀

Dynamics 365 Customer Insights 隨附多種選項，可讓您利用 AI 和機器學習來預測資料。

## <a name="out-of-box-models"></a>立即可用的模型

開始使用預測資料最簡單的方法是預先定義模型，通常稱為立即可用模型。 他們只需要某些資料和結構，即可快速生成見解。 有下列模型可用：

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- [客戶存留期值](predict-customer-lifetime-value.md)：預測客戶在與公司的互動中可能的營收。
- [產品建議](predict-product-recommendation.md)：根據採購行為和具有類似購買模式的客戶，提出一組預測產品建議。
- [訂閱流失](predict-subscription-churn.md): 預測客戶是否有不再使用貴公司的訂閱產品或服務的風險。
- [交易流失](predict-transactional-churn.md)：預測個別客戶是否在特定時間範圍內不再購買您的產品或服務。
- [情感分析](sentiment-analysis.md)：分析客戶意見反應的情感，並找出經常提及的業務層面。

# <a name="business-accounts-b-to-b"></a>[商務客戶 (B 到 B)](#tab/b2b)

- [交易流失](predict-transactional-churn.md)：預測客戶帳號是否在特定時間範圍內不再購買您的產品或服務。

---

> [!TIP]
> 我們建議您定期使用更新過的資料來重新整理立即可用模型，以確保它們能準確地支援您的業務使用案例。 當系統擷取新的或更新的資料來源時，會對資料進行專門的重新整理。 但是，模型只會在此案例中重新評分，並繼續使用現有的訓練資料。
>
> 在設定時設定模型重新定型排程，就可以設定 **更新排程**。 模型將重新定型及重新評分此排程，且您可以隨時變更。

## <a name="azure-machine-learning-integration"></a>Azure Machine Learnings 整合

如果組織已根據 Azure Machine Learning 試驗來使用機器學習案例，則 Customer Insights 中的自訂模型功能可協助您掌握全貌。 建立工作流程，來協助您選擇想要建立見解的資料，並將結果對應至您的整合客戶個人資料。 如需詳細資訊，請參閱[自訂機器學習模型](custom-models.md)。

## <a name="manage-existing-predictions"></a>管理現有的預測

請移至 **智慧** > **預測** 頁面。 在 **我的預測** 索引標籤上，查看您所建立的預測、其預測類型、輸出實體名稱、狀態、上次編輯預測的時間，以及上次重新整理資料的時間。 您可以依據任何欄排序預測清單。

選取預測以查看可用的動作。

:::image type="content" source="media/predictions.png" alt-text="我的預測頁面。":::

- **編輯** 預測以變更其屬性。
- [**重新整理**](#refresh-a-prediction)預測來包括最新的資料。
- **查看** 預測詳細資料。
- [**輸入資料可用性報告**](#view-the-input-data-usability-report)，以查看錯誤、警告和建議。
- **刪除** 預測。

### <a name="refresh-a-prediction"></a>重新整理預測

預測可自動排程重新整理或依照需要手動重新整理。 若要手動重新整理所有預測，請選取 **重新整理全部**。 若要手動重新整理預測，請選取它並選取 **重新整理**。 若要 [排程自動重新整理](schedule-refresh.md)，請前往 **系統管理** > **系統** > **排程**。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>查看輸入資料可用性報表

輸入資料可用性報表提供錯誤和警告的整合檢視表，指出在您的立即可用的預測可能產生的錯誤和警告。 它也提供如何改善模型效能的建議。

在模型完成其定型程序之後，才可使用此報表。 它是單獨為每個模型建立的，不管是否成功完成定型。

在 **我的預測** 索引標籤上，請選取預測，並選擇 **輸入資料可用性報告**。 或從預測詳細資料檢視表中，選取 **輸入資料可用性報告**。

:::image type="content" source="media/input-data-usability-report.png" alt-text="輸入資料可用性報表範例，顯示內有錯誤、警告和建議的資料表。":::

這個報告包括：

- **名稱：** 錯誤、警告或建議的描述性名稱。
- **步驟：** 模型階段，定型或分數，參照資訊。
- **狀態：** 資訊的嚴重性 (錯誤、警告、建議)。
- **資料行名稱：** 需要修改來改善模型效能的實體內資料行。
- **實體名稱：** 需要修改來改善模型效能的實體名稱。
- **詳細資料：** 錯誤、警告或建議的詳細資料。

[!INCLUDE [footer-include](includes/footer-banner.md)]
