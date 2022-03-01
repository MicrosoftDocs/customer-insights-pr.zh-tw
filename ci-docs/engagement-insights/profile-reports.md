---
title: 啟用拆箱即用的設定檔報表
description: 如何建立根據性別、年齡、縣或原產地分組歸類的設定檔報表。
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033942"
---
# <a name="out-of-box-profile-reports"></a>拆箱即用的設定檔報表

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

報表是資料視覺效果的集合，可協助您瞭解使用者行為。 透過連接至 Customer Insights 對象見解，業務開發見解可以顯示報表，其中有統一的客戶設定檔相關資訊。 此報表包含您所擁有的設定檔數目，依性別、年齡和地理位置分組歸類。

## <a name="prerequisites"></a>先決條件

對象見解環境必須將資料儲存在客戶管理的 Azure Data Lake Storage 帳戶中。

如果您使用的是試用版對象見解功能或者是由 Customer Insights 管理的 data lake 環境，請[聯繫我們](https://go.microsoft.com/fwlink/?linkid=2145734) 以取得協助。  


## <a name="enable-the-customer-profile-report"></a>啟用客戶設定檔報表

環境管理員必須[建立連接至對象見解](configure-connections.md)。

指定連接詳細資料後，系統管理員可以將存取權授予組織中的其他人員以查看報表。 設定該連接的環境管理員自動擁有報表的存取權。 

完成連接之後，就可以在左導覽窗格中使用 **設定檔** 功能。 

- 若要查看報表，請移至 **探索** > **設定檔**。

**設定檔** 報表包含視覺效果，內容為所連接之客戶設定檔的性別、年齡及地理位置。

:::image type="content" source="media/customer-profiles.png" alt-text="客戶個人資料報表。":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]