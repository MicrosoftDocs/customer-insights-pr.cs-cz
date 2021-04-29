---
title: Export dat Customer Insights do Azure Data Lake Storage Gen2
description: Naučte se konfigurovat připojení k Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760043"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="17d72-103">Nastavení propojení řešení s aplikacemi Azure Data Lake Storage Gen2 (preview)</span><span class="sxs-lookup"><span data-stu-id="17d72-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="17d72-104">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="17d72-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="17d72-105">Vyberte **Přidat připojení** a zvolte **Azure Data Lake Gen 2** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="17d72-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="17d72-106">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="17d72-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="17d72-107">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="17d72-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="17d72-108">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="17d72-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="17d72-109">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="17d72-109">Choose who can use this connection.</span></span> <span data-ttu-id="17d72-110">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="17d72-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="17d72-111">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="17d72-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="17d72-112">Zadejte **Název účtu**, **Klíč účtu** a **Kontejner** pro své úložiště Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="17d72-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="17d72-113">Chcete-li vědět, jak vytvořit účet úložiště pro použití se službou Azure Data Lake Storage Gen2, projděte si téma [Vytvoření účtu úložiště](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="17d72-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="17d72-114">Další informace o názvu účtu úložiště Azure Data Lake Gen2 a klíči účtu najdete v tématu [Správa nastavení účtu úložiště na webu Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="17d72-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="17d72-115">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="17d72-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="17d72-116">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="17d72-116">Configure an export</span></span>

<span data-ttu-id="17d72-117">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="17d72-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="17d72-118">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="17d72-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="17d72-119">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="17d72-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="17d72-120">Pokud chcete vytvořit nový export, vyberte **Přidat export**.</span><span class="sxs-lookup"><span data-stu-id="17d72-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="17d72-121">V poli **propojení pro export** vyberte propojení v části **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="17d72-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="17d72-122">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="17d72-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="17d72-123">Zaškrtněte políčko vedle každé entity, kterou chcete exportovat do tohoto cíle.</span><span class="sxs-lookup"><span data-stu-id="17d72-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="17d72-124">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="17d72-124">Select **Save**.</span></span>

<span data-ttu-id="17d72-125">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="17d72-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="17d72-126">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="17d72-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="17d72-127">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="17d72-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="17d72-128">Exportovaná data jsou uložena v kontejneru úložiště Azure Data Lake Gen 2, který jste nakonfigurovali.</span><span class="sxs-lookup"><span data-stu-id="17d72-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
