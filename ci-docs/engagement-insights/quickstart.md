---
title: 快速入門產品簡介
description: 首次執行體驗 - 設定業務開發見解功能。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/05/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 95caaa1f67a7740328b67face00acaea65452eb0
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494447"
---
# <a name="first-run-experience"></a>首次執行體驗

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

業務開發見解是 Dynamics 365 Customer Insights 的一項功能，可讓您收集並衡量您網站上的客戶行為。 本文解釋如何註冊業務開發見解、設定工作區、新增成員和變更。

## <a name="sign-up-for-a-demo-of-engagement-insights"></a>註冊業務開發見解示範版

您必須要有一個有效的 Microsoft Azure Active Directory 使用者帳戶。 

1. 打開[業務開發見解](https://home.ci.ai.dynamics.com/app/engagement-insights) 網站。 

1. 使用您的工作或學校帳戶登入。

1. 選取您的地區，然後使用核取方塊，指出您是否想要透過電子郵件來接收最新消息和優惠。

1. 檢閱 **業務開發見解（預覽版）使用條款** 和 **隱私權聲明**，然後選取 **探索示範** 來接受它們。

1. 使用一組範例資料來探索產品。 

## <a name="set-up-your-first-workspace-in-engagement-insights"></a>在業務開發見解中設定您的第一個工作區

工作區是您儲存和管理事件與報表的方式。

要建立您的第一個工作區

1. 在業務開發見解中，選取 **連接您的資料** 以啟動精靈。 

:::image type="content" source="media/banner.png" alt-text=" Customer Insights 頁面，其中包含連接到您的資料按鈕。":::

2. 選擇您要在新工作區中衡量的活動類型。 目前只有 **網站活動** 可選用。 在未來的版本中，另外會有 **應用程式活動** 和 **裝置活動** 可選用。

1. 選取 **下一步** 以確認及建立工作區。

1. 將程式碼片段新增至您的網站，以開始在業務開發見解中接收資料。 您可以立即執行此步驟，也可以與您的網站管理員共用程式碼和指示。稍後若要尋找程式碼片段，請移至 **系統管理員** > **工作區** > **安裝指南**。

   > [!IMPORTANT]
   > 在程式碼於您的網站上執行之前，資料都不會顯示在工作區中。

1. 選取 **完成** 以打開新的工作區。 

## <a name="add-members-to-an-existing-workspace"></a>新增成員至現有的工作區

根據預設，只有建立工作區的人員可以存取該工作區。 您可以隨時將您組織內的其他使用者新增至現有的工作區。

:::image type="content" source="media/add-members.png" alt-text="新增成員按鈕上帶有標注的成員頁面。":::

1. 移至 **系統管理員** > **工作區** > **成員**。

2. 選取 **新增成員**。 使用 **成員** 方塊來加入組織中的其他人員。 您可以一次新增多名成員。

3. 選取要指派給新成員的 **角色**。 目前只有 **工作區系統管理員** 可以選用。 其他角色將會新增至未來的版本中。

4. 選取 **新增成員** 以確認。

若要從工作區移除成員，請在 **成員** 頁面的名稱旁邊選取 **...**，然後從下拉式功能表中選取 **刪除**。

## <a name="edit-a-workspace"></a>編輯工作區

您可以隨時編輯現有工作區的詳細資料。

:::image type="content" source="media/change-workspace-settings.png" alt-text="工作區名稱和描述上帶有標注的工作區設定頁面。":::

1. 移至 **系統管理員** > **工作區** > **設定**。

1. 變更工作區的 **名稱**。

1. 選取 **儲存** 套用變更。

## <a name="add-another-new-workspace"></a>新增另一個工作區

:::image type="content" source="media/workspace-switcher.png" alt-text="在導覽窗格及描述中帶有標注的 Customer insights 頁面。":::

您可以建立其他工作區來分類您的資料。

1. 在工作區選取器中，選取 **新增工作區**。

1. 輸入 **名稱** 並自選要不要加上 **描述**。

1. 選取 **建立**。

## <a name="switch-between-workspaces"></a>在不同工作區之間切換

若要在工作區間進行變更，請選取工作區切換器。 您也可以建立新的工作區，或選取 **網頁範例** 來查看報表，並使用範例資料來嘗試產品特色。 



[!INCLUDE[footer-include](../includes/footer-banner.md)]