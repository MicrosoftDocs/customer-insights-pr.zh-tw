---
title: 利用來自 Microsoft Office 365 的資料擴充客戶設定檔 (預覽版)
description: 使用 Microsoft Office 的專有資料，以參與度資料擴充您的客戶設定檔。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055664"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>利用來自 Microsoft Office 365 的資料擴充客戶設定檔 (預覽版)

使用 Microsoft Office 365 中的資料，經由 Office 365 應用程式以參與度的見解來擴充客戶個人資料。 參與度由電子郵件和會議活動組成，並根據帳戶等級進行彙總。 例如，來自商務客戶的電子郵件數量或與該客戶的會議數量。 無法使用有關個別使用者的資料。

## <a name="supported-countries-or-regions"></a>支援的國家或地區

目前我們支援下列地區：英國、歐洲、北美洲。

## <a name="prerequisites"></a>先決條件

- 一個有效的 Office 365 雲端授權。
- 由[商務帳戶](work-with-business-accounts.md)建立的[整合客戶個人資料](customer-profiles.md)。
- 您的 Customer Insights 環境必須[附加 Microsoft Dataverse 組織](create-environment.md#step-3-connect-to-microsoft-dataverse)。
- [系統管理員](permissions.md#admin)權限。
- 您的 Office 365 租用戶系統管理員同意在 Dynamics 365 應用程式中使用 Office 365 資料以提供 **組織的深入解析**。

## <a name="configure-the-enrichment"></a>擴充設定

1. 移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。

1. 在 **帳戶參與** 磚中，選取 **擴充我的資料**。

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="帳戶參與度圖格。":::

1. 檢閱概覽，然後選擇 **下一步**。

1. 輸入您的組織中要彙總 Office 資料的電子郵件地址。 只有列出電子郵件地址的資料才會對相關通訊進行處理。 最佳的作法是使用電子郵件群組，例如，在 Office 365 中可管理的 *美國銷售團隊*。 群組中已解析並顯示的電子郵件地址數量。 電子郵件地址總數至少為 2 個，且不能超過 2500 個。

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="客戶參與度電子郵件地址。":::

1. 檢閱並選取 **我同意**，對[Office 365 租用戶系統管理員同意](#office-365-tenant-administrator-consent)提供您的同意。

1. 選取 **下一步**。

1. 選取 **連絡人資料集**，然後選擇要擴充的個人資料或客戶細分。 選取 **下一步**。

1. 對應連絡人電子郵件地址欄位，然後選取 **下一步**。

1. 提供擴充與 **輸出實體** 的 **名稱**。

1. 檢閱選擇之後，請選取 **儲存擴充**。

1. 選取 **關閉** 以返回至 **擴充** 頁面。

### <a name="office-365-tenant-administrator-consent"></a>Office 365 租用戶系統管理員同意

若要啟動擴充，必須有 Office 365 租用戶系統管理員的同意。 儲存擴充時，會傳送電子郵件給 Office 365 租用戶管理員，要求他們審查並同意允許 Dynamics 365 應用程式使用您的企業 Office 365 資料，以提供 **給組織的見解**。 Office 365 租用戶系統管理員也可以透過選取 **給組織的見解**，直接在其 Office 365 管理主控台中同意。

## <a name="running-the-enrichment-for-the-first-time"></a>第一次執行擴充

在第一次開始擴充時，取得 Office 365 租用戶系統管理員同意之後，就會開始從 Office 365 下載資料。 此程序需要一些時間。 第一次擴充的執行排程會有六小時的延遲。 擴充完成後，您可以在客戶參與度概覽頁面上看到資料涵蓋的天數。 在有較大的資料量時，請在幾天後再次執行擴充。 這可確保整個時間範圍的資料完成，那應該是一年的時間。

根據 Office 資料的大小而定，可能需要數小時才能完成擴充執行過程。

當您執行擴充時，Microsoft 將在 Office 365 合規性邊界中處理資料，以建立彙總見解，然後將這些見解新增至 Customer Insights 環境。 沒有在個人層級的資料（例如，任何電子郵件或行事曆邀請的主體）會讓 Customer Insights 使用者能夠使用。

選取 **執行** 開始進行擴充程序。

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>查看擴充結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]這是 *Office* 實體。 *Office_UserEntity* 包含在擴充設定期間選定的電子郵件地址的 Active Directory ID。

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="執行擴充程序之後的結果預覽。":::

所有資料都會彙總至客戶等級。 系統會計算參與度分數，範圍從 0 到 100，給每個客戶。 這項參與度分數提供了相對於其他客戶的電子郵件和會議，客戶參與度的綜合量值。 下列清單包含客戶參與度擴充提供的彙總資料：

| 資料​​                                                                              | 資料行名稱                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| 參與分數                                                                  |  EngagementScore                         |
| 客戶的電子郵件數量                                                       |  NoOfEmails_ToAccount                    |
| 來自客戶的電子郵件數量                                                     |  NoOfEmails_FromAccount                  |
| 客戶開始的會議數量                                           |  NoOfMeetings_FromAccount                |
| 您的組織開始的會議數量                                 |  NoOfMeetings_ToAccount                  |
| 組織中與客戶開會的成員數量                  |  NoOfContactsInvolved_Meetings           |
| 組織中與客戶以電子郵件交談的成員數量       |  NoOfContactsInvolved_Emails             |
| 客戶與您的組織開會的成員數量                  |  NoOfAccountContactsInvolved_Meetings    |
| 客戶與您的組織用電子郵件交談的成員數量       |  NoOfAccountContactsInvolved_Emails      |
| 參與度開始日期（資料中的第一個電子郵件或會議）                        |  EngagementStartDate                     |
| 最後一封電子郵件到目前的天數                                                             |  DaysSinceLastEmail                      |
| 最後一次會議到目前的天數                                                           |  DaysSinceLastMeeting                    |
| 會議的平均期間                                                      |  AverageDuration_Of_Meetings             |
| 客戶電子郵件的平均回覆期間                                    |  AverageDuration_Of_AccountEmailReplies  |
| 彙總開始日期                                                            |  AggregationStartDate                    |
| 彙總等級(年、月或星期)                                          |  AggregationLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>查看客戶卡片上的擴充資料

您也可以在單一客戶卡上查看客戶參與度。 移至 **客戶** 並選取客戶設定檔。 在客戶卡中，您會發現該客戶的參與度分數、去年彙總的所有電子郵件總數以及會議數量。 您也會尋找顯示電子郵件及會議歷史記錄的圖表。

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="包含擴充資料的客戶卡片。":::

## <a name="next-steps"></a>後續步驟

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
例如，客戶細分可以包含所有 *最後電子郵件到目前的天數* 和 *最後會議到目前的天數* 值超過 60 的客戶。 這樣的客戶細分包含停滯的客戶，您可以嘗試重新啟動。

[!INCLUDE [footer-include](includes/footer-banner.md)]
