---
title: 匯出 Customer Insights 資料到 Dynamics 365 Marketing
description: 了解如何設定與 Dynamics 365 Marketing 的連接。
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643763"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing 的連接器 (預覽)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

使用 [區段](segments.md) 產生行銷活動並使用 Dynamics 365 Marketing 聯絡特定族群的客戶。 如需詳細資訊，請參閱 [透過 Dynamics 365 Marketing 使用 Dynamics 365 Customer Insights 中的區段](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>先決條件

[從 Dynamics 365 Marketing 內嵌的 Common Data Service](connect-power-query.md) 連絡人記錄。

## <a name="configure-the-connector-for-marketing"></a>設定 Marketing 的連接器

1. 在對象見解中，前往 **系統管理員** > **匯出目的地**。

1. 在 **Dynamics 365 Marketing** 底下，選取 **設定**。

1. 在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。

1. 在 **伺服器位址** 欄位中輸入組織的 Marketing URL。

1. 在 **伺服器管理帳戶** 區段中，選取 **登入**，然後選擇 Dynamics 365 Marketing 帳戶。

1. 將客戶識別碼欄位對應到 Dynamics 365 連絡人識別碼。

1. 選取 **下一步**。

1. 選擇一個或多個客戶細分。

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。
