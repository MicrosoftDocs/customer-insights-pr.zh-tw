---
title: 對象見解中的首頁
description: 開始在首頁上探索應用程式。
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405267"
---
# <a name="create-a-new-environment"></a>建立新環境

## <a name="create-a-trial-environment"></a>建立試用環境

您可以在[試用註冊頁面](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights)上註冊試用。 

> [!NOTE]
> 試用會在 30 天後過期。

1. 選擇 **註冊免費試用** 選項，然後選取 **立即註冊**。

1. 提供您的公司或學校電子郵件地址，告訴我們更多有關您個人的資訊，然後選取 **下一步**。

1. 提供您的新環境的 **名稱**。 

1. 選取試用類型。

1. 選擇您的環境的 **區域**。

1. (選擇性) 如果是 Dynamics 365 組織的系統管理員：選取 **進階設定**，並提供您的組織的 URL，以便使用像客戶流失這樣的預測功能。

1. 選取 **建立**。 

建立環境之後，您會看到 **示範** 環境，讓您使用虛構資料探索應用程式。 您可以變更範例資料，以符合您的行業。 選取標題中的 **設定** 圖示，然後選取 **示範設定**。 此外，您還可以變更視覺佈景主題。 

您可[切換至此環境](#change-between-environments) (進行註冊程序時所建立的環境)，以使用您自己的資料。

## <a name="create-a-new-production-or-sandbox-environment"></a>建立新的生產或沙箱環境

在您的環境中，選取標題中的 **設定** 圖示，然後選取 **新增環境**。

依照您[建立試用環境](#create-a-trial-environment)時的步驟操作。 選取 **進階設定** 時，您會看到可用來將資料儲存在您自己的 Azure Data Lake 中的其他選項。 提供您的帳戶名稱及帳戶金鑰，以建立與 Azure Data Lake 的連接。 根據預設，資料會儲存在 Customer Insights 管理的資料湖中。

> [!IMPORTANT]
> 將資料儲存至您的 Azure Data Lake Storage，即表示您同意將資料傳送並儲存在相應的 Azure 儲存體帳戶的地理位置，這可能不同於將資料儲存於 Dynamics 365 Customer Insights 中的位置。 [在 Microsoft 信任中心深入了解。](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>探索首頁

您可以在下列 URL 上 [存取您的 Customer Insights 環境](https://home.ci.ai.dynamics.com/)：[https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/)。
此 **首頁** 頁面顯示用於追蹤業務健全狀況的客戶群和關鍵計量概觀。

> [!div class="mx-imgBorder"] 
> ![首頁上的見解](media/home-page-insights.png "首頁上的見解")

在 **最新客戶細分** 底下，您可以根據您定義的人口統計、行為或交易屬性來查看客戶群組。 [建立區段](segments.md)可協助您更明確地設定商務活動目標。

**最新量值** 會顯示包含[量值](measures.md)的圖標。 量值是您已定義的關鍵效能指標 (KPI)。 例如，平均客戶流失可能性或每個客戶平均線上消費。

**最新擴充** 區段會列出最近完成的擴充執行結果。 擴充會新增關於您的客戶群的資訊。 例如，了解他們喜好的興趣和品牌。 完成[對應](map-entities.md)、[比對](match-entities.md)和[合併](merge-entities.md)階段之後，可以使用[擴充](enrichment-microsoft-graph.md)功能將此資訊解除鎖定。

## <a name="change-between-environments"></a>在環境之間進行變更

安裝並設定[資料來源](data-sources.md)之後，您就會想要從示範環境切換至實際環境。 使用產生環境可讓您使用您自己的客戶資料。 選取頁面右上角的 **環境** 控制項，以變更環境。

> [!div class="mx-imgBorder"] 
> ![切換環境](media/home-page-environment-switcher.png "切換環境")

系統管理員可以建立和管理[多個環境 ](manage-environments.md)。 例如，如果您的組織跨國營運，而您需要以不同的方式隔離資料與見解時，維護多個環境可能會很有用。

## <a name="next-step"></a>後續步驟

若要在首頁查看您自己的見解，必須先[新增資料來源](data-sources.md)，然後[統整](data-unification.md)資料以建立客戶設定檔。
