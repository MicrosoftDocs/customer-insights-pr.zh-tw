---
title: 資料整合概觀
description: 使用您的資料進行資料整合處理流程，建立整合客戶個人資料的單一資料集。
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139470"
---
# <a name="data-unification-overview"></a>資料整合概觀

[設定資料來源](data-sources.md) 之後，您可以統一資料。 資料整合可讓您將曾經不同的資料來源整合成單一主要資料集，並提供該資料的整合檢視表。 對於個別消費者 (B 到 C)，資料會是以個人為中心，而整合提供客戶的整合檢視表。 對於商務客戶 (B 到 B)，資料會是以客戶為中心，而整合提供客戶的整合檢視表。

資料可以在單一實體或多個實體上整合。 以下列順序執行整合：

1. [來源欄位](map-entities.md) (先前稱為對應)：在來源欄位步驟中，選取要包含在整合程序中的實體和欄位。 將欄位對應至說明欄位用途的一般語意類型。

1. [重複資料記錄](remove-duplicates.md) (先前屬於比對)：在重複資料記錄步驟中，可選擇定義規則，以從每個實體中移除重複的客戶記錄。

1. [比對條件](match-entities.md) (先前稱為比對)：在比對條件步驟中，定義比對實體間客戶記錄的規則。 當在兩個或多個實體中找到客戶時，會合併成單一記錄，其中包含每個實體的所有欄和資料。

1. [整合客戶欄位](merge-entities.md) (先前稱為合併)：在整合客戶欄位步驟中，決定應納入、排除或合併至整合客戶個人資料的來源欄位。  

1. [檢閱](review-unification.md)並建立整合個人資料。

在完成資料整合之後，您可以選擇：

- [設定實體之間的關聯](relationships.md)以建立複雜的客戶細分。
- [擴充資料](enrichment-hub.md)以深入了解您的客戶。
- 從一些內嵌的屬性 [定義活動](activities.md)。
- [組建量值](measures.md)以清楚瞭解客戶行為和業務績效。

[!INCLUDE [footer-include](includes/footer-banner.md)]
