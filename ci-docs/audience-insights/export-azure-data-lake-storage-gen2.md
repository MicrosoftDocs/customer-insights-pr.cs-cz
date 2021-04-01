---
title: Export dat Customer Insights do Azure Data Lake Storage Gen2
description: Naučte se konfigurovat připojení k Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596629"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="569d6-103">Konektor pro Azure Data Lake Storage Gen2 (Preview)</span><span class="sxs-lookup"><span data-stu-id="569d6-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="569d6-104">Uchovávejte svá data Customer Insights ve službě Azure Data Lake Storage Gen2 nebo ji použijte k jejich přenosu do jiných aplikací.</span><span class="sxs-lookup"><span data-stu-id="569d6-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="569d6-105">Konfigurace konektoru pro Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="569d6-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="569d6-106">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="569d6-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="569d6-107">Pod **Azure Data Lake Storage Gen2** vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="569d6-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="569d6-108">Zadejte rozpoznatelný název cíle do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="569d6-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="569d6-109">Zadejte **Název účtu**, **Klíč účtu** a **Kontejner** pro své úložiště Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="569d6-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="569d6-110">Chcete-li vědět, jak vytvořit účet úložiště pro použití se službou Azure Data Lake Storage Gen2, projděte si téma [Vytvoření účtu úložiště](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="569d6-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="569d6-111">Další informace, jak vyhledat název účtu úložiště Azure Data Lake Gen2 a klíč účtu, najdete v článku [Správa nastavení účtu úložiště v Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="569d6-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="569d6-112">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="569d6-112">Select **Next**.</span></span>

1. <span data-ttu-id="569d6-113">Zaškrtněte políčko vedle každé entity, kterou chcete exportovat do tohoto cíle.</span><span class="sxs-lookup"><span data-stu-id="569d6-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="569d6-114">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="569d6-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="569d6-115">Export dat</span><span class="sxs-lookup"><span data-stu-id="569d6-115">Export the data</span></span>

<span data-ttu-id="569d6-116">Můžete [exportovat data na vyžádání](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="569d6-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="569d6-117">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="569d6-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>