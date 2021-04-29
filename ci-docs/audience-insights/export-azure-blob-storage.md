---
title: Export dat Customer Insights do služby Azure Blob Storage
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Blob Storage.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760181"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="31506-103">Export seznamu segmentů a dalších dat do služby Azure Blob Storage (náhled)</span><span class="sxs-lookup"><span data-stu-id="31506-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="31506-104">Uložte si data Customer Insights do služby Azure Blob Storage nebo je použijte k přenosu dat do jiných aplikací.</span><span class="sxs-lookup"><span data-stu-id="31506-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="31506-105">Nastavení propojení s Blob Storage</span><span class="sxs-lookup"><span data-stu-id="31506-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="31506-106">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="31506-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="31506-107">Vyberte **Přidat připojení** a zvolte **Azure Blob Storage** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="31506-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="31506-108">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="31506-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="31506-109">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="31506-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="31506-110">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="31506-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="31506-111">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="31506-111">Choose who can use this connection.</span></span> <span data-ttu-id="31506-112">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="31506-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="31506-113">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="31506-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="31506-114">Zadejte **jméno obchodního vztahu**, **klíč obchodního vztahu** a **kontejner** pro účet Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="31506-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="31506-115">Další informace o vyhledání účtu Blob Storage a klíči účtu najdete v tématu [Správa nastavení účtu úložiště na webu Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="31506-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="31506-116">Informace o tom, jak vytvořit kontejner, viz [Vytvoření kontejneru](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="31506-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="31506-117">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="31506-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="31506-118">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="31506-118">Configure an export</span></span>

<span data-ttu-id="31506-119">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="31506-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="31506-120">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="31506-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="31506-121">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="31506-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="31506-122">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="31506-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="31506-123">V poli **propojení pro export** vyberte propojení z části Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="31506-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="31506-124">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="31506-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="31506-125">Zaškrtněte políčko vedle každé entity, kterou chcete exportovat do tohoto cíle.</span><span class="sxs-lookup"><span data-stu-id="31506-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="31506-126">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="31506-126">Select **Save**.</span></span>

<span data-ttu-id="31506-127">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="31506-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="31506-128">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="31506-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="31506-129">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="31506-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="31506-130">Exportovaná data jsou uložena v kontejneru úložiště Blob Storage, který jste nakonfigurovali.</span><span class="sxs-lookup"><span data-stu-id="31506-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="31506-131">Ve vašem kontejneru se automaticky vytvoří následující cesty ke složkám:</span><span class="sxs-lookup"><span data-stu-id="31506-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="31506-132">Pro zdrojové entity a entity generované systémem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="31506-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="31506-133">Příklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="31506-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="31506-134">Model.json pro exportované entity bude mít úroveň %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="31506-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="31506-135">Příklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="31506-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
