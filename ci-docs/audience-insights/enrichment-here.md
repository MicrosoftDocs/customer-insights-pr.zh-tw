---
title: 以協力廠商 HERE Technologies 擴充進行擴充
description: 有關 HERE Technologies 協力廠商富集作用的一般資訊。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 00be15367001a5f4342d60bb284726ef7154d05c
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555297"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>HERE Technologies 客戶設定檔的富集作用 (預覽版)

HERE Technologies 是一間位置平台公司，提供以位置為中心的資料和服務。 您可以使用 HERE Technologies 的資料富集服務建立對您客戶位址正規化、緯度和經度擷取等更精確的位置瞭解。

## <a name="prerequisites"></a>先決條件

若要組態 HERE Technologies 富集作用，必須符合下列先決條件：

- 您已具備有效的 HERE Technologies 訂閱。 若要訂閱，您可以[在這裡註冊](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) 或直接 [聯絡 HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)。 [深入瞭解 HERE Technologies 的 Location Enrichment。](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- 有可用的 HERE 的 [連接](connections.md)*或*，或者您有[系統管理員](permissions.md#administrator)權限和 HERE Technologies API 金鑰。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**。 

1. 在 HERE Technologies 圖格上選取 **擴充我的資料**，然後選取 **開始使用**。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies 圖標。](media/HERE-tile.png "HERE Technologies 圖格")

1. 從下拉式清單選取一個[連結](connections.md)。 如果沒有可用的連接，請與系統管理員聯繫。 如果您是系統管理員，則可以選取 **新增連接** 來建立連接。 從下拉式清單中選擇 **HERE Technologies**。 

1. 選取 **連接至 HERE Technologies** 以確認選取連接。

1.  選取 **下一步**，然後選擇想要用 HERE Technologies 的位置資料擴充的 **客戶資料集**。 您可以選取 **客戶** 實體來擴充所有的客戶設定檔，或選取客戶細分實體僅擴充位於該客戶細分的客戶設定檔。

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="選擇客戶資料集的螢幕擷取畫面。":::

1. 選取是否要將欄位對應到主要和/或次要位址。 您可以分別指定欄位對應到兩個地址並且指定擴充個人資料給兩個地址。 例如，如果有家庭和商務地址。 選取 **下一步**。

1. 定義應使用您的哪些統一設定檔欄位，以尋找符合 HERE Technologies 的位置資料。 **街道 1** 和 **郵遞區號** 欄位是選取的主要和/或次要位址的必要欄位。 為了更高的符合準確性，可以新增更多欄位。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies 擴充設定頁面。](media/enrichment-HERE-configuration.png "HERE Technologies 富集組態頁面")

1. 請選取 **下一步**，完成欄位對應。

1. 提供擴充的名稱。 

1. 檢閱選擇之後，請選取 **儲存擴充**。

## <a name="configure-the-connection-for-here-technologies"></a>設定 HERE Technologies 的連接 

您必須是系統管理員才能設定連接。 在設定擴充時，請選取 **新增連接***或* 在 HERE Technologies 圖格上移至 **管理** > **連接** 並選取 **設定**。

1. 在 **顯示名稱** 方塊中輸入連接的名稱。

1. 提供有效的 HERE Technologies API 金鑰。

1. 檢閱並選取 **我同意**，提供您的 **資料隱私權和合規性** 許可。

1. 選取 **驗證** 來驗證設定。

1. 完成驗證之後，請選取 **儲存**。

   > [!div class="mx-imgBorder"]
   > ![HERE technologies 的連接設定頁面。](media/enrichment-HERE-connection.png "HERE technologies 的連接設定頁面")

## <a name="enrichment-results"></a>擴充結果

若要開始擴充程序，請從命令列中選取 **執行**。 您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。 處理時間將視您的客戶資料大小和 HERE Technologies 的 API 回應時間而定。

擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。 此外，您還會找到上次更新時間以及已擴充的設定檔數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

## <a name="next-steps"></a>後續步驟

建立在您擴充的客戶資料之上。 建立[客戶細分](segments.md)和 [量值 ](measures.md)，甚至 [匯出資料](export-destinations.md)，為您的客戶提供個人化的體驗。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 HERE Technologies 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 HERE Technologies 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此擴充，不再繼續使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
