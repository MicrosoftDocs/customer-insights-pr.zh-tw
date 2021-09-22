---
title: 角色和權限
description: 工作區成員的可用角色和權限概述。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036683"
---
# <a name="roles-and-permissions"></a>角色和權限

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

工作區是您儲存和管理事件與報表的方式。 成員是指可以存取工作區的使用者。 您可以指派成員至您的工作區，並定義其角色和權限。 系統管理員角色可管理工作區和環境，並為其他使用者設定參與見解。 參與者角色適用那些不需要設定參與見解，但想要建立自己的報表、漏斗圖或客戶細分的分析員。

## <a name="permissions"></a>權限
  
下列圖表標示每個角色的權限。 

| 權限 | 環境管理員 | 工作區管理員 | 環境投稿人 | 工作區投稿人 | 
|--|--|--|--|--|
| 建立環境（建立者會自動成為環境系統管理員） | X* | X* | X* | X* |  
| 設定環境（環境成員、刪除環境） | X |  |  |  |  
| 建立工作區 | X |  |  |  |  
| 設定工作區 (工作區成員，刪除工作區) | X | X |  |  |  
| 設定事件與精簡事件 | X | X | |  |  
| 查看工作區事件與精簡事件 | X | X | |  |  
| 查看工作區資源（報表、區段和計量）| X | X | X | X |  
| 建立自訂報表和漏斗圖 | X | X | X | X |  
| 建立基準計量和維度| X | X |  |  |  
| 建立客戶細分| X | X | X | X |  

*只可以在預覽中建立試用環境。 

## <a name="add-members"></a>新增成員

您可以新增和移除工作區與環境中的成員。 如需詳細資訊，請參閱[環境和工作區](manage-environments-workspaces.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
