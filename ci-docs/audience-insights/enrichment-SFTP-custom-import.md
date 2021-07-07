---
title: SFTP 自訂匯入的富集
description: 有關SFTP 自訂匯入富集的一般資訊。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304640"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="4c2c3-103">使用自訂資料富集客戶設定檔 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="4c2c3-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="4c2c3-104">安全檔案傳輸通訊協定 (SFTP) 自訂匯入功能可讓您匯入不需要透過資料統一處理的資料。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="4c2c3-105">那是一種靈活、安全且容易帶入您的資料的方式。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="4c2c3-106">SFTP 自訂匯入功能可以和 [SFTP 匯出](export-sftp.md) 功能搭配使用，讓您匯出富集所需的客戶設定檔資料。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="4c2c3-107">然後可以處理和擴充資料，並使用 SFTP 自訂匯入將擴充後的資料帶回 Dynamics 365 Customer Insights 的對象見解功能。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c2c3-108">先決條件</span><span class="sxs-lookup"><span data-stu-id="4c2c3-108">Prerequisites</span></span>

<span data-ttu-id="4c2c3-109">若要組態 SFTP 自訂匯入，您務必符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="4c2c3-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4c2c3-110">您擁有將在 SFTP 主機上匯入的檔案名稱和位置 (路徑)。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="4c2c3-111">檔案 *model.json*，會為要匯入的資料指定 [Common Data Model 結構描述](/common-data-model/)。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="4c2c3-112">此檔案必須和將匯入的檔案在同一個目錄中。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="4c2c3-113">SFTP 連接已由系統管理員設定，*或* 您擁有[系統管理員](permissions.md#administrator)權限。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="4c2c3-114">您會需要 SFTP 位置的使用者認證、URL 及連接埠號碼，該 SFTP 位置是匯入資料的所在處。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="4c2c3-115">設定匯入</span><span class="sxs-lookup"><span data-stu-id="4c2c3-115">Configure the import</span></span>

1. <span data-ttu-id="4c2c3-116">移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="4c2c3-117">在 **SFTP 自訂匯入圖格** 上選取 **擴充我的資料**，然後選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP 自訂匯入圖格。":::

1. <span data-ttu-id="4c2c3-119">從下拉式清單選取一個[連結](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="4c2c3-120">如果沒有可用的連接，請與系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="4c2c3-121">如果您是系統管理員，則可以選取 **新增連接**，然從下拉式清單中選擇 **SFTP 自訂匯入**，來建立連接。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="4c2c3-122">選取 **連接至自訂匯入** 以確認選取的連接。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="4c2c3-123">選取 **下一步**，然後輸入您要匯入的資料檔案的 **路徑** 和 **檔案名**。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="輸入資料位置時的螢幕擷取畫面。":::

1. <span data-ttu-id="4c2c3-125">選取 **下一步** 並提供擴充的名稱以及輸出實體的名稱。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="4c2c3-126">檢閱選擇之後，請選取 **儲存擴充**。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="4c2c3-127">為 SFTP 自訂匯入設定連接</span><span class="sxs-lookup"><span data-stu-id="4c2c3-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="4c2c3-128">您必須是系統管理員才能設定連接。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="4c2c3-129">在設定擴充時，請選取 \**新增連接\*\*\*或* 在自訂匯入圖格上移至 **管理** > **連接** 並選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="4c2c3-130">在 **顯示名稱** 方塊中輸入連接的名稱。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="4c2c3-131">輸入匯入的資料駐留的 SFTP 伺服器其有效的使用者名、密碼及主機 URL。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="4c2c3-132">選取 **我同意** 核取方塊，以檢閱 **資料隱私權和合規性** 並表示同意。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="4c2c3-133">選取 **驗證** 來驗證設定。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="4c2c3-134">驗證完成後，您可以選取 **儲存** 來儲存連接。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c2c3-135">![Experian 連接設定頁面](media/enrichment-SFTP-connection.png "Experian 連接設定頁面")</span><span class="sxs-lookup"><span data-stu-id="4c2c3-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="4c2c3-136">定義欄位對應</span><span class="sxs-lookup"><span data-stu-id="4c2c3-136">Defining field mappings</span></span> 

<span data-ttu-id="4c2c3-137">包含將在 SFTP 伺服器上匯入檔案的目錄也必須包含 *model.json* 檔案。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="4c2c3-138">此檔案定義用來匯入資料的結構描述。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="4c2c3-139">結構描述必須使用 [Common Data Model](/common-data-model/) 來指定欄位對應。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="4c2c3-140">model.json 檔案的簡易範例如下：</span><span class="sxs-lookup"><span data-stu-id="4c2c3-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="4c2c3-141">擴充結果</span><span class="sxs-lookup"><span data-stu-id="4c2c3-141">Enrichment results</span></span>

<span data-ttu-id="4c2c3-142">若要開始擴充程序，請從命令列中選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4c2c3-143">您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4c2c3-144">處理時間將視要匯入資料的大小和 SFTP 伺服器的連接而定。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="4c2c3-145">富集流程完成後，您可以在 **我的富集群** 下方評論新匯入的自訂富集資料。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="4c2c3-146">此外，您還會找到上次更新時間以及已擴充的設定檔數目。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4c2c3-147">您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4c2c3-148">後續步驟</span><span class="sxs-lookup"><span data-stu-id="4c2c3-148">Next steps</span></span>

<span data-ttu-id="4c2c3-149">建立在您擴充的客戶資料之上。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4c2c3-150">建立[客戶細分](segments.md)和[量值](measures.md)，和[匯出資料](export-destinations.md)，為您的客戶提供個人化的體驗。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
