---
title: 實體和實體路徑之間的關係
description: 從多個資料來源建立和管理實體之間的關係。
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405283"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="5fb22-103">實體間的關聯</span><span class="sxs-lookup"><span data-stu-id="5fb22-103">Relationships between entities</span></span>

<span data-ttu-id="5fb22-104">關聯可協助您連接實體，並在實體共用可從一個實體參考另一個實體的通用識別碼（外部索引鍵）時，產生資料圖形。</span><span class="sxs-lookup"><span data-stu-id="5fb22-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="5fb22-105">連接的實體可讓您依據多個資料來源來定義區段和量值。</span><span class="sxs-lookup"><span data-stu-id="5fb22-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="5fb22-106">關聯有兩種類型。</span><span class="sxs-lookup"><span data-stu-id="5fb22-106">There are two types of relationships.</span></span> <span data-ttu-id="5fb22-107">不可編輯的系統關聯（自動建立），以及由使用者建立和設定的自訂關聯。</span><span class="sxs-lookup"><span data-stu-id="5fb22-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="5fb22-108">在比對和合併程序期間，會根據智慧型比對，在幕後建立系統關聯。</span><span class="sxs-lookup"><span data-stu-id="5fb22-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="5fb22-109">這些關聯有助於將客戶設定檔記錄關聯至其他對應實體的記錄。</span><span class="sxs-lookup"><span data-stu-id="5fb22-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="5fb22-110">下圖顯示當客戶實體與其他實體比對以產生最終的客戶設定檔實體時，建立了三個系統關聯。</span><span class="sxs-lookup"><span data-stu-id="5fb22-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5fb22-111">![關聯建立](media/relationships-entities-merge.png "關聯建立")</span><span class="sxs-lookup"><span data-stu-id="5fb22-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="5fb22-112">***CustomerToContact* 關聯** 是在客戶實體與連絡人實體之間建立的。</span><span class="sxs-lookup"><span data-stu-id="5fb22-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="5fb22-113">客戶實體會取得與連絡人實體索引鍵欄位 **contactId** 相關的 **Contact_contactId** 索引鍵欄位。</span><span class="sxs-lookup"><span data-stu-id="5fb22-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="5fb22-114">**_CustomerToAccount_ 關聯** 是在客戶實體與帳戶實體之間建立的。</span><span class="sxs-lookup"><span data-stu-id="5fb22-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="5fb22-115">客戶實體會取得與帳戶實體索引鍵欄位 **accountId** 相關的 **Account_accountId** 索引鍵欄位。</span><span class="sxs-lookup"><span data-stu-id="5fb22-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="5fb22-116">**_CustomerToWebAccount_ 關聯** 是在客戶實體與 WebAccount 實體之間建立的。</span><span class="sxs-lookup"><span data-stu-id="5fb22-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="5fb22-117">客戶實體會取得與 WebAccount 實體索引鍵欄位 **webaccountId** 相關的 **WebAccount_webaccountId** 索引鍵欄位。</span><span class="sxs-lookup"><span data-stu-id="5fb22-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="5fb22-118">建立關聯</span><span class="sxs-lookup"><span data-stu-id="5fb22-118">Create a relationship</span></span>

<span data-ttu-id="5fb22-119">在 **關聯** 頁面上定義自訂關聯。</span><span class="sxs-lookup"><span data-stu-id="5fb22-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="5fb22-120">每個關聯均包含來源實體（保存外部索引鍵的實體）和目標實體（來源實體之外部索引鍵所指向的實體）。</span><span class="sxs-lookup"><span data-stu-id="5fb22-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="5fb22-121">請在對象見解中前往 **資料** > **關係**。</span><span class="sxs-lookup"><span data-stu-id="5fb22-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="5fb22-122">選取 **新增關聯**。</span><span class="sxs-lookup"><span data-stu-id="5fb22-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="5fb22-123">在 **新增關聯** 窗格上，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5fb22-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5fb22-124">![輸入關聯詳細資料](media/relationships-add.png "輸入關聯詳細資料")</span><span class="sxs-lookup"><span data-stu-id="5fb22-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="5fb22-125">**關聯名稱**：反映關聯用途的名稱（例如，**AccountWebLogs**）。</span><span class="sxs-lookup"><span data-stu-id="5fb22-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="5fb22-126">**描述**：關聯的描述。</span><span class="sxs-lookup"><span data-stu-id="5fb22-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="5fb22-127">**來源實體**：選取在關聯中用作來源的實體（例如，WebLog）。</span><span class="sxs-lookup"><span data-stu-id="5fb22-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="5fb22-128">**基數**：選取來源實體記錄的基數。</span><span class="sxs-lookup"><span data-stu-id="5fb22-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="5fb22-129">例如，「很多」表示多個 Weblog 記錄與一個 WebAccount 相關聯。</span><span class="sxs-lookup"><span data-stu-id="5fb22-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="5fb22-130">**來源索引鍵欄位**：這代表來源實體中的外部索引鍵欄位。</span><span class="sxs-lookup"><span data-stu-id="5fb22-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="5fb22-131">例如，WebLog 有 **accountId** 外部索引鍵欄位。</span><span class="sxs-lookup"><span data-stu-id="5fb22-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="5fb22-132">**目標實體**：選取在關聯中用作目標的實體（例如，WebAccount）。</span><span class="sxs-lookup"><span data-stu-id="5fb22-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="5fb22-133">**目標基數**：選取目標實體記錄的基數。</span><span class="sxs-lookup"><span data-stu-id="5fb22-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="5fb22-134">例如，「一個」表示多個 Weblog 記錄與一個 WebAccount 相關聯。</span><span class="sxs-lookup"><span data-stu-id="5fb22-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="5fb22-135">**目標索引鍵欄位**：此欄位表示目標實體的索引鍵欄位。</span><span class="sxs-lookup"><span data-stu-id="5fb22-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="5fb22-136">例如，WebAccount 有 **accountId** 索引鍵欄位。</span><span class="sxs-lookup"><span data-stu-id="5fb22-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="5fb22-137">只支援多對一或一對一關聯。</span><span class="sxs-lookup"><span data-stu-id="5fb22-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="5fb22-138">多對多關聯可使用兩個多對一關聯和連結實體（用於連接來源實體和目標實體的實體）來建立。</span><span class="sxs-lookup"><span data-stu-id="5fb22-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="5fb22-139">刪除關聯</span><span class="sxs-lookup"><span data-stu-id="5fb22-139">Delete a relationship</span></span>

1. <span data-ttu-id="5fb22-140">請在對象見解中前往 **資料** > **關係**。</span><span class="sxs-lookup"><span data-stu-id="5fb22-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="5fb22-141">選取您要刪除之關聯的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5fb22-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="5fb22-142">在 **關聯** 表格頂端選取 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="5fb22-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="5fb22-143">確認刪除。</span><span class="sxs-lookup"><span data-stu-id="5fb22-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="5fb22-144">後續步驟</span><span class="sxs-lookup"><span data-stu-id="5fb22-144">Next step</span></span>

<span data-ttu-id="5fb22-145">系統和自訂關聯是根據已不再分散的多個資料來源來建立區段。</span><span class="sxs-lookup"><span data-stu-id="5fb22-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="5fb22-146">如需詳細資訊，請參閱[區段](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="5fb22-146">For more information, see [Segments](segments.md).</span></span>
