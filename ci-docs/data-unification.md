---
title: 建立客戶的整合檢視表
description: 使用您的資料巡遍資料統一處理流程，以便建立帳戶或客戶設定檔的單一主要資料集。
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304417"
---
# <a name="data-unification-overview"></a>資料整合概觀

[設定資料來源](data-sources.md) 之後，您可以統一資料。 資料整合可讓您將曾經不同的資料來源整合成單一主要資料集，並提供該資料的整合檢視表。

對於個別消費者 (B 到 C)，資料會是以個人為中心，而整合提供客戶的整合檢視表。 對於商務客戶 (B 到 B)，資料會是以客戶為中心，而整合提供客戶的整合檢視表。 [連絡人整合 (預覽版)](data-unification-contacts.md) 可讓這些帳戶的連絡人個別與帳戶進行整合並建立關聯。

資料可以在單一實體或多個實體上整合。

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

此整合程序會對應資料來源中的客戶資料、移除重複資料、比對不同實體的資料，以及建立統一設定檔。 以下列順序執行整合：

1. [來源欄位](map-entities.md) (先前稱為對應)：在來源欄位步驟中，選取要包含在整合程序中的實體和欄位。 將欄位對應至說明欄位用途的一般語意類型。

1. [重複資料記錄](remove-duplicates.md) (先前屬於比對)：在重複資料記錄步驟中，可選擇定義規則，以從每個實體中移除重複的客戶記錄。

1. [比對條件](match-entities.md) (先前稱為比對)：在比對條件步驟中，定義比對實體間客戶記錄的規則。 當在兩個或多個實體中找到客戶時，會合併成單一記錄，其中包含每個實體的所有欄和資料。

1. [整合客戶欄位](merge-entities.md) (先前稱為合併)：在整合客戶欄位步驟中，決定應納入、排除或合併至統一客戶設定檔的來源欄位。  

1. [檢閱](review-unification.md)並建立統一設定檔。

# <a name="business-accounts-b-to-b"></a>[商務客戶 (B 到 B)](#tab/b2b)

此整合程序會對應資料來源中的帳戶資料、移除重複資料、比對不同實體的資料，以及建立統一設定檔。 以下列順序執行整合：

1. [來源欄位](map-entities.md) (先前稱為對應)：在來源欄位步驟中，選取要包含在整合帳戶程序中的實體和欄位。 將欄位對應至說明欄位用途的一般語意類型。

1. [重複資料記錄](remove-duplicates.md) (先前屬於比對)：在重複資料記錄步驟中，可選擇定義規則，以從每個實體中移除重複的客戶記錄。

1. [比對條件](match-entities.md) (先前稱為比對)：在比對條件步驟中，定義比對實體間客戶記錄的規則。 在兩個或多個實體中找到客戶時，會合併成單一記錄，其中包含每個實體的所有資料行和資料。

1. [整合客戶欄位](merge-entities.md) (先前稱為合併)：在整合客戶欄位步驟中，決定應納入、排除或合併至統一客戶設定檔的來源欄位。  

1. [檢閱](review-unification.md)並建立統一設定檔。

整合帳戶之後，您可以選擇性地為這些帳戶[整合連絡人 (預覽版)](data-unification-contacts.md)，並將整合的連絡人連結至整合的帳戶。

---

完成資料整合之後，您可以選擇：

- [設定實體之間的關聯](relationships.md)以建立複雜的客戶細分。
- [擴充資料](enrichment-hub.md)以深入了解您的客戶。
- 從一些內嵌的屬性 [定義活動](activities.md)。
- [組建量值](measures.md)以清楚瞭解客戶行為和業務績效。

[!INCLUDE [footer-include](includes/footer-banner.md)]
