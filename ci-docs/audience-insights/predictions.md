---
title: 使用預測完成部分資料
description: 使用預測填滿未完成的客戶資料。
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595891"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="65224-103">透過預測完成部分資料</span><span class="sxs-lookup"><span data-stu-id="65224-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="65224-104">預測可讓您輕鬆建立預測值，以增強您對客戶的了解。</span><span class="sxs-lookup"><span data-stu-id="65224-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="65224-105">您可以在 **智慧** > **預測** 頁面上選取 **我的預測** 查看您已在觀眾見解其他部分中組態的預測，並允許進一步自訂它們。</span><span class="sxs-lookup"><span data-stu-id="65224-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="65224-106">如果您的環境使用 Azure Data Lake Gen 2 儲存體，您無法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="65224-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="65224-107">預測功能使用自動方法來評估資料，並根據該資料進行預測，因此具有用作剖析方法的能力，因為這個術語是由一般資料保護規定 (「GDPR」) 所定義。</span><span class="sxs-lookup"><span data-stu-id="65224-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="65224-108">若客戶使用此功能來處理資料，可能會受到 GDPR 或其他法律或法規的制約。</span><span class="sxs-lookup"><span data-stu-id="65224-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="65224-109">您負責確保您對 Dynamics 365 Customer Insights 的使用，包括預測、符合所有適用法律和規定，包括隱私權、個人資料、生物資料、資料保護和通訊機密性相關法律。</span><span class="sxs-lookup"><span data-stu-id="65224-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="65224-110">先決條件</span><span class="sxs-lookup"><span data-stu-id="65224-110">Prerequisites</span></span>

<span data-ttu-id="65224-111">在您的組織可以使用預測功能之前，必須符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="65224-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="65224-112">貴組織有 [在 Common Data Service](/ai-builder/build-model#prerequisites) 中設定的執行個體，它和 Customer Insights 位於同一個組織。</span><span class="sxs-lookup"><span data-stu-id="65224-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="65224-113">您的環境會附加到您的 Common Data Service 執行個體。</span><span class="sxs-lookup"><span data-stu-id="65224-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="65224-114">如果您要 [建立新的環境](manage-environments.md)，請在 **建立環境** 對話方塊中加以設定，然後選取 **進階**。</span><span class="sxs-lookup"><span data-stu-id="65224-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="65224-115">如果您已建立環境，請移至其設定並選取 **進階**。</span><span class="sxs-lookup"><span data-stu-id="65224-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="65224-116">或者在 **使用預測** 區段中輸入您要附加環境的 Common Data Service 執行個體 URL。</span><span class="sxs-lookup"><span data-stu-id="65224-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="65224-117">在客戶實體中建立預測</span><span class="sxs-lookup"><span data-stu-id="65224-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="65224-118">請在對象見解中前往 **資料** > **實體**。</span><span class="sxs-lookup"><span data-stu-id="65224-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="65224-119">選取 **客戶** 實體。</span><span class="sxs-lookup"><span data-stu-id="65224-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="65224-120">在 **Customer: CustomerInsights** 實體中，選取 **欄位** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="65224-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="65224-121">尋找想要預測值的屬性名稱，然後在 **摘要** 欄中選取 **概觀** 圖示。</span><span class="sxs-lookup"><span data-stu-id="65224-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65224-122">![概觀圖示](media/intelligence-overviewicon.png "概觀圖示")</span><span class="sxs-lookup"><span data-stu-id="65224-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="65224-123">如果您的屬性缺少很多值，請選取 **預測遺失值**，繼續預測。</span><span class="sxs-lookup"><span data-stu-id="65224-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65224-124">![顯示預測遺失值按鈕的概觀狀態](media/intelligence-overviewpredictmissingvalues.png "顯示預測遺失值按鈕的概觀狀態")</span><span class="sxs-lookup"><span data-stu-id="65224-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="65224-125">提供預測結果的 **顯示名稱** 和 **輸出實體名稱**。</span><span class="sxs-lookup"><span data-stu-id="65224-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="65224-126">預先填入的選項清單將顯示可將值對應至預測類別的位置。</span><span class="sxs-lookup"><span data-stu-id="65224-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="65224-127">在此案例中，您的類別選項只有 0 或 1，因為這些選項對應至預測的 true/false 或二進位性質。</span><span class="sxs-lookup"><span data-stu-id="65224-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="65224-128">在 [類別] 欄中，將您想要在最終預測中分類為 "0" 的欄位值對應至 "0"，然後將您想要在最終預測中分類為 "1" 的項目對應至 "1"。</span><span class="sxs-lookup"><span data-stu-id="65224-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65224-129">![顯示對應的欄位值至類別的範例](media/intelligence-categorymapping.png "顯示對應的欄位值至類別的範例")</span><span class="sxs-lookup"><span data-stu-id="65224-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="65224-130">選取 **完成**，預測將會得到處理。</span><span class="sxs-lookup"><span data-stu-id="65224-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="65224-131">處理工作需要花費一些時間，視資料的大小和複雜度而定。</span><span class="sxs-lookup"><span data-stu-id="65224-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="65224-132">根據您所建立之預測的 **輸出實體名稱**，在新實體中提供結果。</span><span class="sxs-lookup"><span data-stu-id="65224-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="65224-133">建立區段時建立預測</span><span class="sxs-lookup"><span data-stu-id="65224-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="65224-134">建立區段時，也可以預測特定屬性的遺失值。</span><span class="sxs-lookup"><span data-stu-id="65224-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="65224-135">特別是，當您根據統整的客戶實體或 Customer_Measure 實體快速建立區段時。</span><span class="sxs-lookup"><span data-stu-id="65224-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="65224-136">在此流程中，您可以選擇要據以建立區段的特定屬性，例如客戶滿意度或購買金額。</span><span class="sxs-lookup"><span data-stu-id="65224-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="65224-137">建立區段時，系統會建議針對此屬性預測任何遺失值的方法。</span><span class="sxs-lookup"><span data-stu-id="65224-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="65224-138">請在觀眾見解中前往 **區段** 並選取 **設定檔** 圖格。</span><span class="sxs-lookup"><span data-stu-id="65224-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="65224-139">選擇要在上建立區段的 **欄位**，並選取 **運算子**，然後選取 **檢閱**。</span><span class="sxs-lookup"><span data-stu-id="65224-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="65224-140">提供區段的 **名稱** 和 **顯示名稱**。</span><span class="sxs-lookup"><span data-stu-id="65224-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="65224-141">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="65224-141">Select **Save**.</span></span>

5. <span data-ttu-id="65224-142">如果您建立的區段在來源欄位中有不完整的資料，您可以選擇預測遺失的值。</span><span class="sxs-lookup"><span data-stu-id="65224-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65224-143">![預測按鈕](media/segments-predictoption.png "預測按鈕")</span><span class="sxs-lookup"><span data-stu-id="65224-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="65224-144">提供預測結果的 **顯示名稱** 和 **輸出實體名稱**。</span><span class="sxs-lookup"><span data-stu-id="65224-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="65224-145">選取 **完成**。</span><span class="sxs-lookup"><span data-stu-id="65224-145">Select **Done**.</span></span> <span data-ttu-id="65224-146">您的預測很快會在新的實體中產生，此實體具有您為 **輸出實體名稱** 所提供的名稱。</span><span class="sxs-lookup"><span data-stu-id="65224-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="65224-147">檢視預測</span><span class="sxs-lookup"><span data-stu-id="65224-147">View a prediction</span></span>

1. <span data-ttu-id="65224-148">請在對象見解中前往 **智慧**  > **預測**  > **我的預測**。</span><span class="sxs-lookup"><span data-stu-id="65224-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="65224-149">選取您要檢閱的預測。</span><span class="sxs-lookup"><span data-stu-id="65224-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="65224-150">在 **動作** 欄中選取省略符號，然後選擇 **檢視**。</span><span class="sxs-lookup"><span data-stu-id="65224-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="65224-151">您將會在預測的檢視表中看到數個資料點。</span><span class="sxs-lookup"><span data-stu-id="65224-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65224-152">![預測頁面](media/intelligence-predictionsviewpage.png "預測頁面")</span><span class="sxs-lookup"><span data-stu-id="65224-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="65224-153">**預測值** 顯示您在欄位值對應至類別階段所建立的對應。</span><span class="sxs-lookup"><span data-stu-id="65224-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="65224-154">這些值是資料集中已對應至特定類別的值。</span><span class="sxs-lookup"><span data-stu-id="65224-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="65224-155">-**主要影響因素** 是資料集中的因素，最有可能影響對應至特定類別之欄位值的預測信賴度。</span><span class="sxs-lookup"><span data-stu-id="65224-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="65224-156">**效能** 表示預測的效果。</span><span class="sxs-lookup"><span data-stu-id="65224-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="65224-157">選取連結以了解詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="65224-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="65224-158">**預覽** 會顯示您預測的輸出資料集樣本，以及預測值的可能性或信賴度，其中 0 是不確定，1 則是確定。</span><span class="sxs-lookup"><span data-stu-id="65224-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="65224-159">更新預測</span><span class="sxs-lookup"><span data-stu-id="65224-159">Update a prediction</span></span>

1. <span data-ttu-id="65224-160">請在對象見解中前往 **智慧**  > **預測**  > **我的預測**。</span><span class="sxs-lookup"><span data-stu-id="65224-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="65224-161">選取要更新的預測，然後選取 **更新** 圖示。</span><span class="sxs-lookup"><span data-stu-id="65224-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="65224-162">預測將會排程進行處理。</span><span class="sxs-lookup"><span data-stu-id="65224-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="65224-163">您可以在 **預測** 頁面的 **已更新** 欄中查看其上次更新的時間。</span><span class="sxs-lookup"><span data-stu-id="65224-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="65224-164">編輯預測</span><span class="sxs-lookup"><span data-stu-id="65224-164">Edit a prediction</span></span>

<span data-ttu-id="65224-165">建立預測之後，您可以在 AI Builder 中自訂模型，以增加模型的有效性。</span><span class="sxs-lookup"><span data-stu-id="65224-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="65224-166">請在對象見解中前往 **智慧**  > **預測**  > **我的預測**。</span><span class="sxs-lookup"><span data-stu-id="65224-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="65224-167">選取您想編輯的預測。</span><span class="sxs-lookup"><span data-stu-id="65224-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="65224-168">在 **動作** 欄中選取省略符號，然後選擇 **檢視**。</span><span class="sxs-lookup"><span data-stu-id="65224-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="65224-169">選取 **在 AI Builder 中自訂**。</span><span class="sxs-lookup"><span data-stu-id="65224-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="65224-170">在 AI Builder 中更新您的模型。</span><span class="sxs-lookup"><span data-stu-id="65224-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="65224-171">[深入了解如何在 AI Builder 中管理模型](/ai-builder/manage-model#retrain-and-republish-existing-models)。</span><span class="sxs-lookup"><span data-stu-id="65224-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="65224-172">下次執行預測時，會使用您所建立的更新模型。</span><span class="sxs-lookup"><span data-stu-id="65224-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="65224-173">在 AI Builder 建立的新模型不會顯示在觀眾見解中，除非模型是從上列體驗建立。</span><span class="sxs-lookup"><span data-stu-id="65224-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="65224-174">移除預測</span><span class="sxs-lookup"><span data-stu-id="65224-174">Remove a prediction</span></span>

1. <span data-ttu-id="65224-175">請在對象見解中前往 **智慧**  > **預測**  > **我的預測**。</span><span class="sxs-lookup"><span data-stu-id="65224-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="65224-176">選取您要刪除的預測。</span><span class="sxs-lookup"><span data-stu-id="65224-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="65224-177">在 **動作** 欄中選取省略符號，然後選擇 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="65224-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="65224-178">確認刪除。</span><span class="sxs-lookup"><span data-stu-id="65224-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="65224-179">疑難排解​​</span><span class="sxs-lookup"><span data-stu-id="65224-179">Troubleshooting</span></span>

<span data-ttu-id="65224-180">如果由於發生錯誤而無法完成附加 Common Data Service 程序，則可以嘗試手動完成程序。</span><span class="sxs-lookup"><span data-stu-id="65224-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="65224-181">在附加程序中有兩個已知問題：</span><span class="sxs-lookup"><span data-stu-id="65224-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="65224-182">Customer 卡片增益集解決方案並未安裝。</span><span class="sxs-lookup"><span data-stu-id="65224-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="65224-183">完成 [安裝和設定解決方案](customer-card-add-in.md)的指示。</span><span class="sxs-lookup"><span data-stu-id="65224-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="65224-184">應用程式權限並未授予。</span><span class="sxs-lookup"><span data-stu-id="65224-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="65224-185">移至 [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="65224-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="65224-186">選取 **環境**。</span><span class="sxs-lookup"><span data-stu-id="65224-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="65224-187">選取您要新增權限的環境旁邊的省略符號，並選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="65224-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="65224-188">展開 **使用者 + 權限**，然後選取 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="65224-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="65224-189">選取 **+ 新增**，然後選取 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="65224-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="65224-190">選取 **應用程式使用者**（如果尚未選取），並輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="65224-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="65224-191">**使用者名稱：**cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="65224-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="65224-192">**應用程式識別碼：** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="65224-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="65224-193">**名字：** Customer</span><span class="sxs-lookup"><span data-stu-id="65224-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="65224-194">**姓氏**：Insights</span><span class="sxs-lookup"><span data-stu-id="65224-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="65224-195">**主要電子郵件：**cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="65224-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="65224-196">選取 **儲存後關閉**。</span><span class="sxs-lookup"><span data-stu-id="65224-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="65224-197">選取您剛建立的使用者。</span><span class="sxs-lookup"><span data-stu-id="65224-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="65224-198">在上方功能表列中選取 **管理角色**。</span><span class="sxs-lookup"><span data-stu-id="65224-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="65224-199">選取 **系統系統管理員**，然後選取 **確定**。</span><span class="sxs-lookup"><span data-stu-id="65224-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]