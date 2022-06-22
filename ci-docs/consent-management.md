---
title: 使用客戶同意
description: 若要在 Customer Insights 中遵守客戶的同意喜好設定，請匯入同意資料。
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947492"
---
# <a name="use-customer-consent"></a>使用客戶同意

資料保護和隱私權法規讓每個人有權管理組織如何使用自身資料。 此類規章的範例如下：歐盟的一般資料保護規定或加州消費者隱私權法案。 基於這些法規，使用者能選擇不允許個人資料被收集、被處理或共用給協力廠商。  

客戶可以選擇對特定表單撤銷或拒絕給予同意。 他們也可能要求您將他們的個人資料從收集、儲存、使用或銷售中移出。 遵守所有客戶的同意內容和隱私權喜好設定，是至關重要的。  

Dynamics 365 Customer Insights 可以匯入客戶的喜好設定並將其儲存為整合客戶個人資料中的一部分，協助您遵守客戶的要求。

如果同意資料與客戶個人資料分開儲存，請[將您的同意資料新增為新的資料來源](#import-and-unify-consent-data)。 包含同意資料的資料來源會新增至資料整合程序。 成功將同意資訊與客戶個人資料整合後，就會產生包含同意資訊的整合客戶個人資料。 對於內含同意資訊的客戶個人資料，請直接前往[使用同意資料](#use-consent-data)區段。

## <a name="prerequisites"></a>先決條件

在來源資料中，下列資訊必須可以使用，才能整合同意資料與其他客戶個人資料：

- 其他索引鍵，可用來將同意資訊對應至 Customer Insights 中的使用者個人資料。 例如，電子郵件地址或電話號碼。
- 同意值，用來判斷客戶同意的狀態。

請考慮新增下列 *選填* 資訊：

- 當客戶要求變更時，用來更新同意狀態的主索引鍵。
- 同意類型 (如果處理客戶資訊的方式不只一個)。
- 同意日期，或其他任何與同意案例相關的資料類型。

內含多個同意選項的簡單同意資料庫其範例表格：

|同意識別碼 (主索引鍵)   |電子郵件 (其他索引鍵)  |同意選項  |同意值  |
|---------|---------|---------|---------|
|7    |  holly@contoso.com       |  電子報       |  False       |
|2    |  holly@contoso.com       |  產品更新       |  True       |
|3    |  frank@contoso.com       |  電子報       | True        |
|4    |  frank@contoso.com       |  產品更新       |  False       |

## <a name="import-and-unify-consent-data"></a>匯入並整合同意資料

同意資料匯入 Customer Insights 的方式，可以採用與其他資料來源相同的方式。 如需受支援資料的來源及匯入方式的詳細資訊，請參閱[資料來源概述](data-sources.md)。

如需整合資料來源的詳細資訊，請參閱[資料整合概述](data-unification.md)。

## <a name="use-consent-data"></a>使用同意資料

一旦同意資料成為您的整合客戶個人資料的一部分，您就可以在 Customer Insights 中使用它。 例如，建立客戶細分時，設定規則以確保遵守客戶的隱私權和資料保護喜好設定。 使用支援同意喜好設定的規則，即可根據個人資料屬性從客戶細分中排除使用者。 將規則新增到客戶細分，以排除沒有同意的客戶個人資料。

參照上述範例表格，客戶細分可包含此規則：`Consent option=Newsletter & Consent value=True`。 此設定會產生一個遵守喜好設定的客戶細分，並可用來傳送電子報。

如需建立客戶細分的詳細資訊，請參閱[建立客戶細分](segment-builder.md)。

建立客戶細分之後，您可以使用其中任一個[匯出選項](export-destinations.md)在其他應用程式中使用客戶細分。

## <a name="ensure-updated-consent-status"></a>確保同意狀態已更新

務必要將客戶的同意狀態保持更新。 在 Customer Insights 中排程的重新整理永遠會匯入資料來源的最新狀態。 此資訊接著進行資料整合處理和並產生更新後的客戶個人資料。 這些更新後的個人資料會用來重新整理客戶細分，確保您使用的是最新的資訊。

換言之，請確認匯入至 Customer Insights 的來源資料永遠是最新資訊。

如需詳細資訊，請參閱[手動重新整理客戶細分](segments.md#refresh-segments)或[設定排程的重新整理](system.md#schedule-tab)。
