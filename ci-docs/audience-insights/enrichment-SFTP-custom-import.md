---
title: SFTP 自訂匯入的富集
description: 有關SFTP 自訂匯入富集的一般資訊。
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269596"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="358d2-103">使用自訂資料富集客戶設定檔 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="358d2-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="358d2-104">安全檔案傳輸通訊協定 (SFTP) 自訂匯入功能可讓您匯入不需要透過資料統一處理的資料。</span><span class="sxs-lookup"><span data-stu-id="358d2-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="358d2-105">那是一種靈活、安全且容易帶入您的資料的方式。</span><span class="sxs-lookup"><span data-stu-id="358d2-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="358d2-106">SFTP 自訂匯入功能可以和 [SFTP 匯出](export-sftp.md) 功能搭配使用，讓您匯出富集所需的客戶設定檔資料。</span><span class="sxs-lookup"><span data-stu-id="358d2-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="358d2-107">接著資料可以處理、富集和 SFTP 自訂匯入，將富集後的資料帶回 Dynamics 365 Customer Insights 的對象見解功能。</span><span class="sxs-lookup"><span data-stu-id="358d2-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="358d2-108">先決條件</span><span class="sxs-lookup"><span data-stu-id="358d2-108">Prerequisites</span></span>

<span data-ttu-id="358d2-109">若要組態 SFTP 自訂匯入，您務必符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="358d2-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="358d2-110">您具備準備匯入資料的 SFTP 位置使用者憑證 (使用者名稱與密碼)。</span><span class="sxs-lookup"><span data-stu-id="358d2-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="358d2-111">您具有 STFP 主機的 URL 和連接埠號碼 (通常是 22)。</span><span class="sxs-lookup"><span data-stu-id="358d2-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="358d2-112">您具有將匯入 SFTP 主機的檔案名稱和位置。</span><span class="sxs-lookup"><span data-stu-id="358d2-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="358d2-113">目前有一個指定將匯入資料的結構描述 *model.json* 檔案。</span><span class="sxs-lookup"><span data-stu-id="358d2-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="358d2-114">此檔案必須和將匯入的檔案在同一個目錄中。</span><span class="sxs-lookup"><span data-stu-id="358d2-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="358d2-115">您具有 [系統管理員](permissions.md#administrator) 權限。</span><span class="sxs-lookup"><span data-stu-id="358d2-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="358d2-116">組態</span><span class="sxs-lookup"><span data-stu-id="358d2-116">Configuration</span></span>

1. <span data-ttu-id="358d2-117">移至 **資料** > **擴充**，然後選取 **探索** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="358d2-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="358d2-118">請在 **SFTP 自訂匯入圖格** 上選取 **富集我的資料**。</span><span class="sxs-lookup"><span data-stu-id="358d2-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="358d2-119">![SFTP 自訂匯入圖格](media/SFTP_Custom_Import_tile.png "SFTP 自訂匯入圖格")</span><span class="sxs-lookup"><span data-stu-id="358d2-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="358d2-120">選取 **開始使用** 並提供 SFTP 伺服器的憑證和位址。</span><span class="sxs-lookup"><span data-stu-id="358d2-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="358d2-121">例如，sftp://mysftpserver.com:22。</span><span class="sxs-lookup"><span data-stu-id="358d2-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="358d2-122">輸入包含不在根資料夾時，SFTP 伺服器上檔案資料和路徑的檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="358d2-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="358d2-123">選取 **連接到自訂匯入** 確認所有輸入資料。</span><span class="sxs-lookup"><span data-stu-id="358d2-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="358d2-124">![SFTP 自訂匯入組態飛出視窗](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP 自訂匯入組態飛出視窗")</span><span class="sxs-lookup"><span data-stu-id="358d2-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="358d2-125">定義欄位對應</span><span class="sxs-lookup"><span data-stu-id="358d2-125">Defining field mappings</span></span> 

<span data-ttu-id="358d2-126">包含將在 SFTP 伺服器上匯入檔案的目錄也必須包含 *model.json* 檔案。</span><span class="sxs-lookup"><span data-stu-id="358d2-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="358d2-127">此檔案定義用來匯入資料的結構描述。</span><span class="sxs-lookup"><span data-stu-id="358d2-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="358d2-128">結構描述必須使用 [Common Data Model](https://docs.microsoft.com/common-data-model/) 指定欄位對應。</span><span class="sxs-lookup"><span data-stu-id="358d2-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="358d2-129">model.json 檔案的簡易範例如下：</span><span class="sxs-lookup"><span data-stu-id="358d2-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="358d2-130">擴充結果</span><span class="sxs-lookup"><span data-stu-id="358d2-130">Enrichment results</span></span>

<span data-ttu-id="358d2-131">若要開始擴充程序，請從命令列中選取 **執行**。</span><span class="sxs-lookup"><span data-stu-id="358d2-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="358d2-132">您也可以讓系統在[排定的重新整理](system.md#schedule-tab)過程中自動執行擴充。</span><span class="sxs-lookup"><span data-stu-id="358d2-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="358d2-133">處理時間將視要匯入資料的大小和 SFTP 伺服器的連接而定。</span><span class="sxs-lookup"><span data-stu-id="358d2-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="358d2-134">富集流程完成後，您可以在 **我的富集群** 下方評論新匯入的自訂富集資料。</span><span class="sxs-lookup"><span data-stu-id="358d2-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="358d2-135">此外，您還會找到上次更新時間以及已擴充的設定檔數目。</span><span class="sxs-lookup"><span data-stu-id="358d2-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="358d2-136">您可以選取 **檢視擴充的資料** 來存取每個已擴充設定檔的詳細檢視表。</span><span class="sxs-lookup"><span data-stu-id="358d2-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="358d2-137">後續步驟</span><span class="sxs-lookup"><span data-stu-id="358d2-137">Next steps</span></span>

<span data-ttu-id="358d2-138">建立在您擴充的客戶資料之上。</span><span class="sxs-lookup"><span data-stu-id="358d2-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="358d2-139">建立 [區段](segments.md)、[量值](measures.md) 和 [匯出資料](export-destinations.md) 以便將個人化的經驗傳遞給您的客戶。</span><span class="sxs-lookup"><span data-stu-id="358d2-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]