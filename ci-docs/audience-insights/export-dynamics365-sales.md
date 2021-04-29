---
title: 匯出 Customer Insights 資料到 Dynamics 365 Sales
description: 了解如何設定連接並匯出至 Dynamics 365 Sales。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759581"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>在 Dynamics 365 Sales 中使用客戶細分 (預覽版)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

使用您的客戶資料來建立行銷名單、追蹤工作流程，並透過 Dynamics 365 Sales 寄出促銷活動。

## <a name="prerequisite-for-connection"></a>連接的先決條件

1. 連絡人記錄必須存在於Dynamics 365 Sales 中，才能將客戶細分從 Customer Insights 匯出至 Sales。 瞭解如何[使用 Common Data Services 在 Dynamics 365 Sales 裡面](connect-power-query.md)內嵌連絡人。

   > [!NOTE]
   > 將客戶細分中從對象見解中匯出到 Sales，並不會在 Sales 的執行個體中建立新的連絡人記錄。 Sales 中的連絡人記錄必須內嵌在對象見解中，並作為資料來源使用。 他們也必須包含整合客戶實體中，才能客戶細分匯出前，先將客戶識別碼對應至連絡人的識別碼。

## <a name="set-up-the-connection-to-sales"></a>設定與 Sales 的連線

1. 移至 **管理** > **連接**。

1. 選取 **新增連接**，然後選擇 **Dynamics 365 Sales** 來設定連接。

1. 在 **顯示名稱** 中，給連接一個能夠辨識的名稱。 連接的名稱與類型能說明此連接。 我們建議您選取可以說明此連接用途和目標的名稱。

1. 選擇可使用此連接的人員。 如果您不採取任何動作，預設值將為系統管理員。 如需詳細資訊，請參閱[允許參與者使用匯出的連接](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 在 **伺服器位址** 欄位中輸入組織的 Sales URL。

1. 在 **伺服器管理帳戶** 區段中，選取 **登入**，然後選擇 Dynamics 365 Sales 帳戶。

1. 將客戶識別碼欄位對應到 Dynamics 365 連絡人識別碼。

1. 選取 **儲存** 來完成連接。 

## <a name="configure-an-export"></a>設定匯出

若您擁有取此類型的連接的存取權，則可以設定此匯出。 如需詳細資訊，請參閱[設定匯出所需的權限](export-destinations.md#set-up-a-new-export)。

1. 移至 **資料** > **匯出**。

1. 若要建立新的匯出，請選取 **新增目的地**。

1. 在 **匯出的連結** 欄位中，在 Dynamics 365 Sales 區段中選擇連接。 如果您看不到此區段名稱，代表沒有此類型的連接可供您使用。

1. 選擇一個或多個客戶細分。

1. 選取 **儲存**

儲存匯出並不會立即執行匯出。

每次[排定重新整理](system.md#schedule-tab)會一起執行匯出。 您也可以依[需求匯出資料](export-destinations.md#run-exports-on-demand)。 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
