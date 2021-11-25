---
title: 在對象見解中啟動客戶細分的同意規則
description: 在對象見解中連結同意資料並啟動同意檢查的步驟。
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753051"
---
# <a name="activate-consent-rules"></a>啟用同意規則

[同意中心 (預覽版)](../consent-management/overview.md)可讓您協調不同來源的同意資料。 您可以使用整合的 *同意* 實體套用預設同意檢查。 在同意資料匯入同意中心且設定匯入的同意資料的規則之後，*同意* 實體會自動同步處理至對象見解。

## <a name="enable-consent-checks"></a>啟用同意檢查

如果已將同意的資料匯入同意中心 (預覽版) 並設定規則，您可以在對象見解中啟用同意檢查。 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="對象見解設定中的同意索引標籤包含已啟動的同意資料。":::

1. 請在對象見解中前往 **管理員** > **系統**。

1. 選取 **同意 (預覽版)** 索引標籤。

1. 在 **啟動同意檢查** 區段中，對您要 **啟用** 的區域切換設定。

1. 選取 **允許覆寫預設同意規則** 核取方塊，移除在特定區段上強制執行的預設同意檢查。 

1. 在下拉式功能表中，選取您要允許覆寫的位置。     

1. 在將 **連結同意至客戶個人資料** 區段中，選取作為識別碼的屬性，以將同意資料連結至客戶資料。 這很可能是電話號碼或電子郵件地址。 

1. 選取 **儲存** 套用設定。

## <a name="disable-consent-checks"></a>停用同意檢查

若要停止使用對象見解中的同意資料，系統管理員必須更新對應的系統設定。

1. 請在對象見解中前往 **管理員** > **系統**。

1. 選取 **同意 (預覽版)** 索引標籤。

1. 在 **啟用同意檢查** 區段中，切換設定為 **關閉**。
