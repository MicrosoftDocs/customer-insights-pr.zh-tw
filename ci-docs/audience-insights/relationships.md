---
title: 實體和實體路徑之間的關係
description: 從多個資料來源建立和管理實體之間的關係。
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171154"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="b680a-103">實體間的關聯</span><span class="sxs-lookup"><span data-stu-id="b680a-103">Relationships between entities</span></span>

<span data-ttu-id="b680a-104">當實體共用一般識別碼 (外部索引鍵) 時，關聯會連接實體並定義資料圖形。</span><span class="sxs-lookup"><span data-stu-id="b680a-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="b680a-105">此外部索引鍵可以從一個實體參照到另一個實體。</span><span class="sxs-lookup"><span data-stu-id="b680a-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="b680a-106">連接的實體依據多個資料來源來啟用客戶細分和量值定義。</span><span class="sxs-lookup"><span data-stu-id="b680a-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="b680a-107">有三種類型的關聯：</span><span class="sxs-lookup"><span data-stu-id="b680a-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="b680a-108">不可編輯的系統關聯，是在資料整合程序中由系統建立的</span><span class="sxs-lookup"><span data-stu-id="b680a-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="b680a-109">不可編緝的繼承關聯，是內嵌資料來源時自動建立的</span><span class="sxs-lookup"><span data-stu-id="b680a-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="b680a-110">可編輯的自訂關聯，由使用者建立和設定</span><span class="sxs-lookup"><span data-stu-id="b680a-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="b680a-111">不可編輯的系統關聯</span><span class="sxs-lookup"><span data-stu-id="b680a-111">Non-editable system relationships</span></span>

<span data-ttu-id="b680a-112">在資料整合時，會根據智慧比對自動建立系統關聯。</span><span class="sxs-lookup"><span data-stu-id="b680a-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="b680a-113">這些關聯有助於將客戶個人資料記錄關聯至其他對應記錄。</span><span class="sxs-lookup"><span data-stu-id="b680a-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="b680a-114">以下圖表將圖示三種系統型關聯的建立。</span><span class="sxs-lookup"><span data-stu-id="b680a-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="b680a-115">客戶實體與其他實體比對，以產生整合的的 *客戶* 實體。</span><span class="sxs-lookup"><span data-stu-id="b680a-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="具有三個 1-n 關聯的客戶實體關聯路徑圖表。":::

- <span data-ttu-id="b680a-117">***CustomerToContact* 關聯** 是在 *客戶* 實體與 *連絡人* 實體之間建立的。</span><span class="sxs-lookup"><span data-stu-id="b680a-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="b680a-118">*客戶* 實體會取得 **Contact_contactID** 索引鍵欄位，來關聯 *連絡人* 實體索引鍵欄位 **contactID** 。</span><span class="sxs-lookup"><span data-stu-id="b680a-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="b680a-119">***CustomerToAccount* 關聯** 是在 *客戶* 實體與 *帳戶* 實體之間建立的。</span><span class="sxs-lookup"><span data-stu-id="b680a-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="b680a-120">*客戶* 實體會取得 **Account_accountID** 索引鍵欄位，來關聯 *帳戶* 實體索引鍵欄位 **accountID**。</span><span class="sxs-lookup"><span data-stu-id="b680a-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="b680a-121">***CustomerToWebAccount* 關聯** 是在 *客戶* 實體與 *WebAccount* 實體之間建立的。</span><span class="sxs-lookup"><span data-stu-id="b680a-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="b680a-122">*客戶* 實體會取得 **WebAccount_webaccountID** 索引鍵欄位，並關連到 *WebAccount* 實體索引鍵欄位 **webaccountID**。</span><span class="sxs-lookup"><span data-stu-id="b680a-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="b680a-123">不可編輯的繼承關聯</span><span class="sxs-lookup"><span data-stu-id="b680a-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="b680a-124">資料擷取程序進行時，系統會檢查資料來源的現有關聯。</span><span class="sxs-lookup"><span data-stu-id="b680a-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="b680a-125">如果不存在任何關聯，系統會自動建立這些關聯。</span><span class="sxs-lookup"><span data-stu-id="b680a-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="b680a-126">這些關聯也用在下游程序中。</span><span class="sxs-lookup"><span data-stu-id="b680a-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="b680a-127">建立自訂關聯</span><span class="sxs-lookup"><span data-stu-id="b680a-127">Create a custom relationship</span></span>

<span data-ttu-id="b680a-128">關聯是由包含外部索引鍵的 *來源實體* 和來源實體的外部索引鍵指向的 *目標實體* 組成。</span><span class="sxs-lookup"><span data-stu-id="b680a-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="b680a-129">請在對象見解中前往 **資料** > **關係**。</span><span class="sxs-lookup"><span data-stu-id="b680a-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="b680a-130">選取 **新增關聯**。</span><span class="sxs-lookup"><span data-stu-id="b680a-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="b680a-131">在 **新增關聯** 窗格上，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="b680a-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="具有空白輸入欄位的新關聯側邊窗格。":::

   - <span data-ttu-id="b680a-133">**關聯名稱**：反映關聯用途的名稱。</span><span class="sxs-lookup"><span data-stu-id="b680a-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="b680a-134">範例：CustomerToSupportCase。</span><span class="sxs-lookup"><span data-stu-id="b680a-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="b680a-135">**描述**：關聯的描述。</span><span class="sxs-lookup"><span data-stu-id="b680a-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="b680a-136">**來源實體**：在關聯中作為來源的實體。</span><span class="sxs-lookup"><span data-stu-id="b680a-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="b680a-137">範例：SupportCase。</span><span class="sxs-lookup"><span data-stu-id="b680a-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="b680a-138">**目標實體**：在關聯中作為目標的實體。</span><span class="sxs-lookup"><span data-stu-id="b680a-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="b680a-139">範例：客戶。</span><span class="sxs-lookup"><span data-stu-id="b680a-139">Example: Customer.</span></span>
   - <span data-ttu-id="b680a-140">**來源基數**：指定來源實體的基數。</span><span class="sxs-lookup"><span data-stu-id="b680a-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="b680a-141">基數說明集合中可能的元素數目。</span><span class="sxs-lookup"><span data-stu-id="b680a-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="b680a-142">它總是與目標基數有關。</span><span class="sxs-lookup"><span data-stu-id="b680a-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="b680a-143">您可以選擇 **一** 和 **多個**。</span><span class="sxs-lookup"><span data-stu-id="b680a-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="b680a-144">只支援多對一或一對一關聯。</span><span class="sxs-lookup"><span data-stu-id="b680a-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="b680a-145">多對一：多個來源記錄可以關連到一個目標記錄。</span><span class="sxs-lookup"><span data-stu-id="b680a-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="b680a-146">範例：來自單一客戶的多個支援案例。</span><span class="sxs-lookup"><span data-stu-id="b680a-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="b680a-147">一對一：單一來源記錄關連到一個目標記錄。</span><span class="sxs-lookup"><span data-stu-id="b680a-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="b680a-148">範例：一位客戶的一個忠誠度識別碼。</span><span class="sxs-lookup"><span data-stu-id="b680a-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="b680a-149">多對多關聯可以使用兩個多對一關聯和一個連結實體 (連入來源實體和目標實體) 來建立。</span><span class="sxs-lookup"><span data-stu-id="b680a-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="b680a-150">**目標基數**：選取目標實體記錄的基數。</span><span class="sxs-lookup"><span data-stu-id="b680a-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="b680a-151">**來源索引鍵欄位**：來源實體中的外部索引鍵欄位。</span><span class="sxs-lookup"><span data-stu-id="b680a-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="b680a-152">範例：SupportCase 可以使用 CaseID 作為外部索引鍵欄位。</span><span class="sxs-lookup"><span data-stu-id="b680a-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="b680a-153">**目標索引鍵欄位**：欄位表示目標實體的索引鍵欄位。</span><span class="sxs-lookup"><span data-stu-id="b680a-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="b680a-154">範例客戶可以使用 **CustomerID** 索引鍵鍵欄位。</span><span class="sxs-lookup"><span data-stu-id="b680a-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="b680a-155">選取 **儲存** 以建立自訂關聯。</span><span class="sxs-lookup"><span data-stu-id="b680a-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="b680a-156">檢視關聯性</span><span class="sxs-lookup"><span data-stu-id="b680a-156">View relationships</span></span>

<span data-ttu-id="b680a-157">關聯頁面會列出已建立的所有關聯。</span><span class="sxs-lookup"><span data-stu-id="b680a-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="b680a-158">每一列代表一個關聯，裡面也包含有關來源實體、目標實體和基數的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b680a-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="在關聯頁面的動作欄中的關聯和選項清單。":::

<span data-ttu-id="b680a-160">此頁面對現有與新關聯提供一組選項：</span><span class="sxs-lookup"><span data-stu-id="b680a-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="b680a-161">**新增關聯**：[建立自訂關聯](#create-a-custom-relationship)。</span><span class="sxs-lookup"><span data-stu-id="b680a-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="b680a-162">**視覺化檢視**：[探索關聯視覺化檢視](#explore-the-relationship-visualizer)，以查看現有關聯及其基數的網狀圖表。</span><span class="sxs-lookup"><span data-stu-id="b680a-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="b680a-163">**依...篩選**：選擇要在清單中顯示的關聯類型。</span><span class="sxs-lookup"><span data-stu-id="b680a-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="b680a-164">**搜尋關聯**：在關聯的屬性上使用文字型搜尋。</span><span class="sxs-lookup"><span data-stu-id="b680a-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="b680a-165">探索關聯視覺化檢視</span><span class="sxs-lookup"><span data-stu-id="b680a-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="b680a-166">視覺化檢視顯示網狀圖表，表示在連接實體間的現有關聯及其基數。</span><span class="sxs-lookup"><span data-stu-id="b680a-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="b680a-167">若要自訂檢視表，您可以透過在畫布上拖動方塊來變更位置。</span><span class="sxs-lookup"><span data-stu-id="b680a-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="關聯視覺化檢視的螢幕擷取畫面，圖上為相關實體間連接的網狀圖表。":::

<span data-ttu-id="b680a-169">可用的選項：</span><span class="sxs-lookup"><span data-stu-id="b680a-169">Available options:</span></span> 
- <span data-ttu-id="b680a-170">**匯出成影像**：將目前的檢視表儲存為影像檔。</span><span class="sxs-lookup"><span data-stu-id="b680a-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="b680a-171">**變更為橫向/垂直版面配置**：變更實體與關聯的對齊方式。</span><span class="sxs-lookup"><span data-stu-id="b680a-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="b680a-172">**編輯**：在編輯窗格中更新自訂關聯的屬性，並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="b680a-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="b680a-173">管理現有關聯</span><span class="sxs-lookup"><span data-stu-id="b680a-173">Manage existing relationships</span></span> 

<span data-ttu-id="b680a-174">在關聯頁面上，每個關聯都是以資料列顯示。</span><span class="sxs-lookup"><span data-stu-id="b680a-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="b680a-175">選取關聯，然後選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="b680a-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="b680a-176">**編輯**：在編輯窗格中更新自訂關聯的屬性，並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="b680a-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="b680a-177">**刪除**：刪除自訂關聯。</span><span class="sxs-lookup"><span data-stu-id="b680a-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="b680a-178">**查看**：查看系統-建立和繼承的關聯。</span><span class="sxs-lookup"><span data-stu-id="b680a-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="b680a-179">下一個步驟</span><span class="sxs-lookup"><span data-stu-id="b680a-179">Next step</span></span>

<span data-ttu-id="b680a-180">因為多個資料來源不再孤立，系統和自訂關聯可以用來[建立客戶細分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="b680a-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
