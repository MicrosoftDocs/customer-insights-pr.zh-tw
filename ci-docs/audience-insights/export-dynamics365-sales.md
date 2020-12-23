---
title: 匯出 Customer Insights 資料到 Dynamics 365 Sales
description: 了解如何設定與 Dynamics 365 Sales 的連接。
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643808"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Sales 的連接器 (預覽)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

使用您的客戶資料來建立行銷名單、追蹤工作流程，並透過 Dynamics 365 Sales 寄出促銷活動。

## <a name="prerequisite"></a>先決條件

[從 Dynamics 365 Sales 內嵌使用 Common Data Service](connect-power-query.md) 的連絡人記錄。

## <a name="configure-the-connector-for-sales"></a>設定 Sales 的連接器

1. 在對象見解中，前往 **系統管理員** > **匯出目的地**。

1. 在 **Dynamics 365 Sales** 底下，選取 **設定**。

1. 在 **顯示名稱** 欄位中，為匯出目的地提供可辨識的名稱。

1. 在 **伺服器位址** 欄位中輸入組織的 Sales URL。

1. 在 **伺服器管理帳戶** 區段中，選取 **登入**，然後選擇 Dynamics 365 Sales 帳戶。

1. 將客戶識別碼欄位對應到 Dynamics 365 連絡人識別碼。

1. 選取 **下一步**。

1. 選擇一個或多個客戶細分。

1. 選取 **儲存**。

## <a name="export-the-data"></a>匯出資料

您可以[視需要匯出資料](export-destinations.md)。 匯出也會與每個[排定的重新整理](system.md#schedule-tab)一起執行。
