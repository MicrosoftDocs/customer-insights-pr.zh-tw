---
title: 藉助協力廠商 HERE Technologies 的富集作用
description: 有關 HERE Technologies 協力廠商富集作用的一般資訊。
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668668"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>HERE Technologies 客戶設定檔的富集作用 (預覽版)

HERE Technologies 是一間位置平台公司，提供以位置為中心的資料和服務。 您可以使用 HERE Technologies 的資料富集服務建立對您客戶位址正規化、緯度和經度擷取等更精確的位置瞭解。

## <a name="prerequisites"></a>先決條件

若要組態 HERE Technologies 富集作用，必須符合下列先決條件：

- 您已具備有效的 HERE Technologies 訂閱。 若要訂閱，您可以 [在這裡註冊](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) 或直接 [聯絡 HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)。 [深入瞭解 HERE Technologies 的 Location Enrichment。](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- 您擁有 HERE Technologies API 金鑰。

- 您擁有 [系統管理員](permissions.md#administrator) 權限。

## <a name="configuration"></a>組態

1. 移至 **資料** > **擴充**。

1. 請在 HERE Technologies 圖格上選取 **富集我的資料**。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies 圖格](media/HERE-tile.png "HERE Technologies 圖格")

1. 輸入有效的 **HERE Technologies API 金鑰**。 選取 **我同意** 核取方塊，以檢閱 **資料隱私權和合規性** 並表示同意。 

1. 選取 **連接到 HERE** 確認這兩項輸入資料。

1. 選取 **新增資料** 並選擇是否要將欄位對應到主要和/或次要位址。 您可以為兩個位址指定欄位對應 (例如住宅和公司位址)，然後分別富集兩個位址的設定檔。 選取 **下一步**。

1. 定義應使用您的哪些統一設定檔欄位，以尋找符合 HERE Technologies 的位置資料。 **街道 1** 和 **郵遞區號** 欄位是選取的主要和/或次要位址的必要欄位。 為了更高的符合準確性，可以新增更多欄位。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies 富集組態頁面](media/enrichment-HERE-configuration.png "HERE Technologies 富集組態頁面")

1. 選取 **套用** 完成欄位對應。

## <a name="enrichment-results"></a>擴充結果

若要開始擴充程序，請從命令列中選取 **執行**。 您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。 處理時間將視您的客戶資料大小和 HERE Technologies 的 API 回應時間而定。

擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。 此外，您還會找到上次更新時間以及已擴充的設定檔數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

## <a name="next-steps"></a>後續步驟

建立在您擴充的客戶資料之上。 建立[客戶細分](segments.md)、[量值](measures.md)，甚至[匯出資料](export-destinations.md)，以便傳送個人化體驗給您的客戶。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 HERE Technologies 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 HERE Technologies 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此富集作用，以便不再繼續使用此功能。
