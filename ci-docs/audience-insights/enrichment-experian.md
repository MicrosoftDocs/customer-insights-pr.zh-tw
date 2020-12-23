---
title: 藉助協力廠商 Enrichment Experian 的富集作用
description: 有關 Experian 協力廠商富集作用的一般資訊。
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668794"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>使用 Experian 提供的人口統計資料擴充客戶設定檔 (預覽)

Experian 是消費者與企業信用報告以及行銷服務的全球領導者。 有了 Experian 的資料擴充服務，您就可以透過人口統計資料 (例如家庭人數、收入及其他) 擴充您的客戶設定檔，加深對客戶的了解。

## <a name="prerequisites"></a>先決條件

若要設定 Experian，必須符合以下先決條件：

- 您擁有有效的 Experian 訂閱。 若要取得訂閱，請直接[與 Experian 連絡](https://www.experian.com/marketing-services/contact)。 [深入了解t Experian 資料擴充](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。
- 您具有 Experian 為您所建立啟用 SSH 之安全傳輸 (ST) 帳戶的使用者識別碼、當事人識別碼和模型編號。
- 您在對象見解中具備 [系統管理員](permissions.md#administrator) 權限。

## <a name="configuration"></a>組態

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 選取 Experian 圖標上的 **擴充我的資料**。

   > [!div class="mx-imgBorder"]
   > ![Experian 圖標](media/experian-tile.png "Experian 圖標")

1. 選取 **開始使用**，並輸入您的 Experian 安全傳輸帳戶的使用者識別碼、當事人識別碼和模型編號。 選取 **我同意** 核取方塊，以檢閱 **資料隱私權和合規性** 並表示同意。 選取 **套用** 以確認所有輸入。

## <a name="map-your-fields"></a>對應欄位

1. 選取 **新增資料**，然後從 **名稱和地址**、**電子郵件** 或 **電話** 選擇您的金鑰識別元以傳送至 Experian 進行身分識別解析。

   > [!TIP]
   > 傳送至 Experian 的金鑰識別元屬性愈多，可能產生的適配率愈高。

1. 選取 **下一步**，然後對應所選金鑰識別元欄位的統一客戶實體中的對應屬性。

1. 選取 **新增屬性**，以對應任何您要傳送至 Experian 的其他屬性。

1.  選取 **儲存** 來完成欄位對應。

   > [!div class="mx-imgBorder"]
   > ![Experian 欄位對應](media/experian-field-mapping.png "Experian 欄位對應")

## <a name="enrichment-results"></a>擴充結果

若要開始擴充程序，請從命令列中選取 **執行**。 您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。 處理時間取決於客戶資料的大小以及 Experian 為您帳戶設定的擴充程序。

擴充程序完成後，您可以在 **我的擴充內容** 底下查看新擴充的客戶設定檔資料。 此外，您還會找到上次更新時間以及已擴充的設定檔數目。

您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。

## <a name="next-steps"></a>後續步驟

建立在您擴充的客戶資料之上。 建立[客戶細分](segments.md)、[量值](measures.md)，甚至[匯出資料](export-destinations.md)，以便傳送個人化體驗給您的客戶。

## <a name="data-privacy-and-compliance"></a>資料隱私權與合規性

當您啟用 Dynamics 365 Customer Insights 將資料傳輸給 Experian 時，您允許在合規性邊界之外傳輸 Dynamics 365 Customer Insights 資料，包括潛在敏感性資料如個人資料。 Microsoft 將依據您的指示傳輸此資料，但您須負責確保 Experian 符合您可能應盡的任何隱私權或資訊安全義務。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 系統管理員可以隨時移除此富集作用，以便不再繼續使用此功能。
