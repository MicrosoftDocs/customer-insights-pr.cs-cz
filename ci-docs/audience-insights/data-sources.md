---
title: Použití zdrojů dat pro ingestaci dat
description: Naučte se, jak importovat data z různých zdrojů.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643945"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="667d8-103">Přehled o zdrojích dat</span><span class="sxs-lookup"><span data-stu-id="667d8-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="667d8-104">Funkce přehledů cílové skupiny v Dynamics 365 Customer Insights propojuje data ze široké sady zdrojů.</span><span class="sxs-lookup"><span data-stu-id="667d8-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="667d8-105">Připojení k zdroji dat se často označuje jako proces *příjmu dat*.</span><span class="sxs-lookup"><span data-stu-id="667d8-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="667d8-106">Po požití dat můžete [sjednotit](data-unification.md) a podniknout s tím kroky.</span><span class="sxs-lookup"><span data-stu-id="667d8-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="667d8-107">Přidat zdroj dat</span><span class="sxs-lookup"><span data-stu-id="667d8-107">Add a data source</span></span>

<span data-ttu-id="667d8-108">V závislosti na zvolené možnosti si přečtěte podrobné články o tom, jak přidat zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="667d8-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="667d8-109">Zdroj dat můžete přidat třemi hlavními způsoby:</span><span class="sxs-lookup"><span data-stu-id="667d8-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="667d8-110">Prostřednictvím desítek konektorů Power Query</span><span class="sxs-lookup"><span data-stu-id="667d8-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="667d8-111">Ze složky modelu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="667d8-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="667d8-112">Z vlastního jezera Common Data Service</span><span class="sxs-lookup"><span data-stu-id="667d8-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="667d8-113">Data z místních datových zdrojů zatím nemůžete přidat.</span><span class="sxs-lookup"><span data-stu-id="667d8-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="667d8-114">Zkontrolujte přijatá data</span><span class="sxs-lookup"><span data-stu-id="667d8-114">Review ingested data</span></span>

<span data-ttu-id="667d8-115">Uvidíte název každého přijatého zdroje dat, jeho stav a poslední čas, kdy byla data pro tento zdroj aktualizována.</span><span class="sxs-lookup"><span data-stu-id="667d8-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="667d8-116">Seznam zdrojů dat můžete seřadit podle každého sloupce.</span><span class="sxs-lookup"><span data-stu-id="667d8-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="667d8-117">![Přidaný zdroj dat](media/configure-data-datasource-added.png "Přidaný zdroj dat")</span><span class="sxs-lookup"><span data-stu-id="667d8-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="667d8-118">Stav</span><span class="sxs-lookup"><span data-stu-id="667d8-118">Status</span></span>  |<span data-ttu-id="667d8-119">Popis</span><span class="sxs-lookup"><span data-stu-id="667d8-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="667d8-120">Úspěch</span><span class="sxs-lookup"><span data-stu-id="667d8-120">Successful</span></span>   |<span data-ttu-id="667d8-121">Zdroj dat byl úspěšně ingestován, pokud je v sloupci **Aktualizováno** uveden čas.</span><span class="sxs-lookup"><span data-stu-id="667d8-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="667d8-122">Nezahájeno</span><span class="sxs-lookup"><span data-stu-id="667d8-122">Not started</span></span>   |<span data-ttu-id="667d8-123">Zdroj dat zatím nemá žádná ingestovaná data nebo je stále v režimu konceptu.</span><span class="sxs-lookup"><span data-stu-id="667d8-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="667d8-124">Probíhá aktualizace</span><span class="sxs-lookup"><span data-stu-id="667d8-124">Refreshing</span></span>    |<span data-ttu-id="667d8-125">Probíhá příjem dat.</span><span class="sxs-lookup"><span data-stu-id="667d8-125">Data ingestion is in progress.</span></span> <span data-ttu-id="667d8-126">Tuto operaci můžete zrušit výběrem **Přestat obnovovat** v sloupci **Akce**.</span><span class="sxs-lookup"><span data-stu-id="667d8-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="667d8-127">Zastavením aktualizace zdroje dat se vrátíte do posledního stavu obnovy.</span><span class="sxs-lookup"><span data-stu-id="667d8-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="667d8-128">Nepovedlo se.</span><span class="sxs-lookup"><span data-stu-id="667d8-128">Failed</span></span>     |<span data-ttu-id="667d8-129">Při přijímání dat došlo k chybám.</span><span class="sxs-lookup"><span data-stu-id="667d8-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="667d8-130">Volbou **Aktualizovat stav** zkontrolujte další podrobnosti o stavu aktualizace, včetně podrobností o chybách a následných aktualizacích procesu.</span><span class="sxs-lookup"><span data-stu-id="667d8-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="667d8-131">Načtení dat může chvíli trvat.</span><span class="sxs-lookup"><span data-stu-id="667d8-131">Loading data can take some time.</span></span> <span data-ttu-id="667d8-132">Po úspěšné aktualizaci lze přijatá data zkontrolovat na stránce **Entity**.</span><span class="sxs-lookup"><span data-stu-id="667d8-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="667d8-133">Další informace najdete v tématu [Entity](entities.md).</span><span class="sxs-lookup"><span data-stu-id="667d8-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="667d8-134">Aktualizace zdroje dat</span><span class="sxs-lookup"><span data-stu-id="667d8-134">Refresh a data source</span></span>

<span data-ttu-id="667d8-135">Zdroje dat lze aktualizovat podle automatického plánu nebo ručně na vyžádání.</span><span class="sxs-lookup"><span data-stu-id="667d8-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="667d8-136">Přejděte na **Správce** > **Systém** > [**Plán**](system.md#schedule-tab), ke nakonfigurujte naplánované aktualizace všech ingestovaných zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="667d8-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="667d8-137">Chcete-li aktualizovat zdroj dat na vyžádání, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="667d8-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="667d8-138">V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**</span><span class="sxs-lookup"><span data-stu-id="667d8-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="667d8-139">Vyberte svislé tři tečky vedle zdroje dat, který chcete aktualizovat, a vyberte **Aktualizovat** z rozevíracího seznamu.</span><span class="sxs-lookup"><span data-stu-id="667d8-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="667d8-140">Zdroj dat je nyní spuštěn pro ruční aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="667d8-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="667d8-141">Aktualizací zdroje dat aktualizujete jak schéma entity, tak i data pro všechny entity zadané ve zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="667d8-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="667d8-142">Vyberte **Zastavit aktualizaci**, pokud chcete zrušit existující aktualizaci a zdroj dat se vrátí do svého posledního stavu aktualizace.</span><span class="sxs-lookup"><span data-stu-id="667d8-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="667d8-143">Odstranit datový zdroj</span><span class="sxs-lookup"><span data-stu-id="667d8-143">Delete a data source</span></span>

1. <span data-ttu-id="667d8-144">V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="667d8-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="667d8-145">Vyberte vertikální tři tečky vedle zdroje dat, který chcete odebrat, a vyberte **Odstranit** z rozbalovací nabídky.</span><span class="sxs-lookup"><span data-stu-id="667d8-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="667d8-146">Odstranění potvrďte.</span><span class="sxs-lookup"><span data-stu-id="667d8-146">Confirm your deletion.</span></span>
