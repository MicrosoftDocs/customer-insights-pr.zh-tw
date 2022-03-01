---
title: 匯出 Customer Insights 資料到 Dynamics 365 Sales
description: 了解如何設定與 Dynamics 365 Sales 的連接。
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268998"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Sales 的連接器 (預覽)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

使用您的客戶資料來建立行銷名單、追蹤工作流程，並透過 Dynamics 365 Sales 寄出促銷活動。

## <a name="prerequisite"></a>先決條件

1. 連絡人記錄必須存在於Dynamics 365 Sales 中，才能將客戶細分從 Customer Insights 匯出至 Sales。 瞭解如何[使用 Common Data Services 在 Dynamics 365 Sales 裡面](connect-power-query.md)內嵌連絡人。

   > [!NOTE]
   > 將客戶細分中從對象見解中匯出到 Sales，並不會在 Sales 的執行個體中建立新的連絡人記錄。 Sales 中的連絡人記錄必須內嵌在對象見解中，並作為資料來源使用。 他們也必須包含整合客戶實體中，才能客戶細分匯出前，先將客戶識別碼對應至連絡人的識別碼。

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]