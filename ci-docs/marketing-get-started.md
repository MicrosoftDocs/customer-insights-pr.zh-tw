---
title: 在 Dynamics 365 Marketing 中使用整合個人資料
description: 了解如何在 Dynamics 365 Marketing 中統整整合個人資料及客戶細分。
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054422"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>在 Dynamics 365 Marketing 中使用整合客戶設定檔

 [Dynamics 365 Marketing](/dynamics365/marketing/overview)提升客戶體驗，讓您在所有接觸點安排個人化旅程，以增強關聯並贏得忠誠度。 Dynamics 365 Marketing 應用程式與 Dynamics 365 Sales、 Dynamics 365 Customer Insights、Microsoft Teams 及其他產品徹底整合，可讓您使用資料和 AI 的力量做出更快更好的決策。

將 Customer Insights 資料與 Marketing 相連，您可以：

- 目標鎖定整合客戶個人資料和客戶細分。 這使您能夠接觸每個客戶，無論客戶的資料位置在哪。
- 基本動態內容 (如個人化權杖)，是來自電子郵件、簡訊和推播通知中，並由整合 Customer Insights 個人資料中擷取出的量值 (例如：忠誠度狀態、訂閱續訂日期、上層客戶或任何其它量值)。
- 將資料從 Marketing 載入至 Customer Insights 中，並將其與其他來源的客戶資料相結合。
- 套用 Customer Insights 資料清理、擴充和模糊比對等工具。

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>在即時行銷中使用擴充客戶設定檔

即時行銷允許您建立[自訂觸發程序](/dynamics365/marketing/real-time-marketing-custom-triggers)，藉由任何客戶動作啟動客戶旅程。 您的資料越個人化，您的旅程就越相關和個人化。 這就是結合Marketing 和 Customer Insights 會如此強大的原因。 您可以將任何來源的[資料進行整合](data-unification.md) ，然後使用它來推動超個人化的客戶旅程。

深入了解：[在即時行銷中使用 Customer Insights 個人資料和客戶細分](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>將整合的客戶細分與出站客戶旅程結合使用

Customer Insights 可讓您優化來自多個來源的資料，並將其合併到彙總客戶細分中。 [連接 Customer Insights 與出站行銷](export-dynamics365-marketing.md)，這些客戶細分將在客戶旅程設計器中自動顯示 *並* 自動更新。

瞭解更多資訊：[使用 Dynamics 365 Marketing 與 Dynamics 365 Customer Insights 客戶細分](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>從您的 Azure Data Lake Storage 提取資料

如果您想在 Marketing 中使用 Customer Insights 資料，則不受限於雲端儲存空間。 如果您已經準備好 Azure Data Lake Storage，則可以連接到 Customer Insights，然後與 Marketing 應用程式共用資料，就像使用雲端設定一樣。

瞭解更多資訊：[啟用 Azure Data Lake Storage 共用資料到 Dataverse](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
