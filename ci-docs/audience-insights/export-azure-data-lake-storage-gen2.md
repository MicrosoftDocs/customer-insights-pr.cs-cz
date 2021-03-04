---
title: Export dat Customer Insights do Azure Data Lake Storage Gen2
description: Naučte se konfigurovat připojení k Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477171"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="fad90-103">Konektor pro Azure Data Lake Storage Gen2 (Preview)</span><span class="sxs-lookup"><span data-stu-id="fad90-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="fad90-104">Uchovávejte svá data Customer Insights ve službě Azure Data Lake Storage Gen2 nebo ji použijte k jejich přenosu do jiných aplikací.</span><span class="sxs-lookup"><span data-stu-id="fad90-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="fad90-105">Konfigurace konektoru pro Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="fad90-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="fad90-106">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="fad90-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fad90-107">Pod **Azure Data Lake Storage Gen2** vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="fad90-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="fad90-108">Zadejte rozpoznatelný název cíle do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="fad90-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="fad90-109">Zadejte **Název účtu**, **Klíč účtu** a **Kontejner** pro své úložiště Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="fad90-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="fad90-110">Chcete-li vědět, jak vytvořit účet úložiště pro použití se službou Azure Data Lake Storage Gen2, projděte si téma [Vytvoření účtu úložiště](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="fad90-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="fad90-111">Další informace, jak vyhledat název účtu úložiště Azure Data Lake Gen2 a klíč účtu, najdete v článku [Správa nastavení účtu úložiště v Azure Portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="fad90-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="fad90-112">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="fad90-112">Select **Next**.</span></span>

1. <span data-ttu-id="fad90-113">Zaškrtněte políčko vedle každé entity, kterou chcete exportovat do tohoto cíle.</span><span class="sxs-lookup"><span data-stu-id="fad90-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="fad90-114">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="fad90-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fad90-115">Export dat</span><span class="sxs-lookup"><span data-stu-id="fad90-115">Export the data</span></span>

<span data-ttu-id="fad90-116">Můžete [exportovat data na vyžádání](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fad90-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="fad90-117">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fad90-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
