---
title: 管理環境
description: 了解如何以系統管理員的身分來管理現有的 Customer Insights 環境。
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588802"
---
# <a name="manage-environments"></a>管理環境

系統管理員可以[建立](create-environment.md)和管理環境。 他們可以變更現有環境中的某些設定。 業務、類型、地區、儲存選項和 Dataverse 設定可在建立環境之後進行修正。 如果您想要變更這些設定，請[重設環境](#reset-an-existing-environment-preview)或[建立新的環境](create-environment.md)。

## <a name="edit-an-existing-environment"></a>編輯現有環境

編輯現有環境的詳細資料 (例如名稱)，或設定預設環境。

1. 在應用程式的標頭中選取 **環境** 選取器。

1. 選取 **編輯** 圖示。

   :::image type="content" source="media/edit-environment.png" alt-text="用來編輯環境設定的圖示。":::

1. 在 **編輯環境** 窗格中，更新環境設定。

1. 選取 **檢閱及完成**，然後按一下 **更新** 來套用變更。

## <a name="change-the-owner-of-an-environment"></a>變更環境負責人

多個使用者可以擁有系統管理員權限，但是只有一個使用者是環境的負責人。 根據預設，這會是建立環境的系統管理員。 身為環境的管理員，您可以將擁有權指派給其他具有管理員權限的使用者。

1. 在應用程式的標頭中選取 **環境** 選取器。

1. 選取 **編輯** 圖示。

1. 在 **編輯環境** 窗格中，移至 **基本資訊** 步驟。

1. 在 **變更環境的負責人** 欄位中，選擇環境的新負責人。  

1. 選取 **檢閱及完成**，然後按一下 **更新** 來套用變更。

## <a name="claim-ownership-of-an-environment"></a>宣告環境的擁有權

如果負責人的使用者帳戶遭到刪除或停權，則環境將沒有負責人。 任何管理使用者都可以宣告擁有權，並成為新的擁有者。 擁有者管理員可以繼續擁有環境，或[將擁有權變更至其他管理員](#change-the-owner-of-an-environment)。

若要宣告擁有權，請選取 **取得擁有權** 按鈕，當原始負責人離開組織時，會在 Customer Insights 中每個頁面的頂端顯示該按鈕。

## <a name="reset-an-existing-environment-preview"></a>重設現有的環境 (預覽版)

身為環境擁有者，若要刪除所有設定並移除擷取的資料，請將環境重設為空白狀態。

1. 在應用程式的標頭中選取 **環境** 選取器。

1. 選取您要重設的環境，並選取垂直省略符號 (&vellip;)。

1. 選擇 **重設 (預覽版)**。

   :::image type="content" source="media/reset-environment.png" alt-text="用來重設環境的控制項。":::

1. 選擇是否要重設整個環境、資料來源以外的所有項目，或是已在統一客戶設定檔之上設定的任何項目。

1. 若要確認，請輸入環境名稱並選取 **重設**。

## <a name="delete-an-existing-environment"></a>刪除現有環境

身為環境的擁有者，您可以將其刪除。

> [!IMPORTANT]
> 刪除環境並不會移除 Dataverse 環境的連接。 如果您打算日後將相同的 Dataverse 環境連接至新的 Customer Insights 環境，則必須[移除與 Dataverse 環境的這個連接](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment)。

1. 在應用程式的標頭中選取 **環境** 選取器。

1. 選取您要刪除的環境，並選取垂直省略符號 (&vellip;)。 

1. 選擇 **刪除**。

   :::image type="content" source="media/delete-environment.png" alt-text="用來刪除環境的控制項。":::

1. 若要確認刪除，請輸入環境名稱，然後選取 **刪除**。

[!INCLUDE [footer-include](includes/footer-banner.md)]
