---
title: Použití zdrojů dat pro ingestaci dat
description: Naučte se, jak importovat data z různých zdrojů.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304688"
---
# <a name="data-sources-overview"></a><span data-ttu-id="14980-103">Přehled zdrojů dat</span><span class="sxs-lookup"><span data-stu-id="14980-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="14980-104">Funkce přehledů cílové skupiny v Dynamics 365 Customer Insights propojuje data ze široké sady zdrojů.</span><span class="sxs-lookup"><span data-stu-id="14980-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="14980-105">Připojení k zdroji dat se často označuje jako proces *příjmu dat*.</span><span class="sxs-lookup"><span data-stu-id="14980-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="14980-106">Po požití dat můžete [sjednotit](data-unification.md) a podniknout s tím kroky.</span><span class="sxs-lookup"><span data-stu-id="14980-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="14980-107">Přidat zdroj dat</span><span class="sxs-lookup"><span data-stu-id="14980-107">Add a data source</span></span>

<span data-ttu-id="14980-108">V závislosti na zvolené možnosti si přečtěte podrobné články o tom, jak přidat zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="14980-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="14980-109">Zdroj dat můžete přidat třemi hlavními způsoby:</span><span class="sxs-lookup"><span data-stu-id="14980-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="14980-110">Prostřednictvím desítek konektorů Power Query</span><span class="sxs-lookup"><span data-stu-id="14980-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="14980-111">Ze složky modelu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="14980-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="14980-112">Z vlastního jezera Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="14980-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="14980-113">Přidání dat z místních zdrojů dat</span><span class="sxs-lookup"><span data-stu-id="14980-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="14980-114">Příjem dat z místních zdrojů dat v cílové skupině přehledů je podporován na základě toků dat Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="14980-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="14980-115">Toky dat lze povolit v nástroji Customer Insights [poskytnutím adresy URL prostředí Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) při nastavování prostředí.</span><span class="sxs-lookup"><span data-stu-id="14980-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="14980-116">Zdroje dat, které se vytvoří po přidružení prostředí Dataverse k nástroji Customer Insights, budou používat [toky dat Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) ve výchozím stavu.</span><span class="sxs-lookup"><span data-stu-id="14980-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="14980-117">Datové toky podporují místní připojení pomocí datové brány.</span><span class="sxs-lookup"><span data-stu-id="14980-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="14980-118">Odeberte a znovu vytvořte zdroje dat, které existovaly před přidružením prostředí Dataverse k [použití místních bran dat](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="14980-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="14980-119">Datové brány z existujícího prostředí Power BI nebo Power Apps bude viditelné a můžete jej znovu použít ve službě Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="14980-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="14980-120">Na stránce zdroje dat jsou zobrazeny odkazy, na které chcete přejít v prostředí Microsoft Power Platform, kde můžete prohlížet a konfigurovat místní datové brány.</span><span class="sxs-lookup"><span data-stu-id="14980-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="14980-121">Zkontrolujte přijatá data</span><span class="sxs-lookup"><span data-stu-id="14980-121">Review ingested data</span></span>

<span data-ttu-id="14980-122">Uvidíte název každého přijatého zdroje dat, jeho stav a poslední čas, kdy byla data pro tento zdroj aktualizována.</span><span class="sxs-lookup"><span data-stu-id="14980-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="14980-123">Seznam zdrojů dat můžete seřadit podle každého sloupce.</span><span class="sxs-lookup"><span data-stu-id="14980-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="14980-124">![Přidaný zdroj dat](media/configure-data-datasource-added.png "Přidaný zdroj dat")</span><span class="sxs-lookup"><span data-stu-id="14980-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="14980-125">Stav</span><span class="sxs-lookup"><span data-stu-id="14980-125">Status</span></span>  |<span data-ttu-id="14980-126">Popis</span><span class="sxs-lookup"><span data-stu-id="14980-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="14980-127">Úspěch</span><span class="sxs-lookup"><span data-stu-id="14980-127">Successful</span></span>   |<span data-ttu-id="14980-128">Zdroj dat byl úspěšně ingestován, pokud je v sloupci **Aktualizováno** uveden čas.</span><span class="sxs-lookup"><span data-stu-id="14980-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="14980-129">Nezahájeno</span><span class="sxs-lookup"><span data-stu-id="14980-129">Not started</span></span>   |<span data-ttu-id="14980-130">Zdroj dat zatím nemá žádná ingestovaná data nebo je stále v režimu konceptu.</span><span class="sxs-lookup"><span data-stu-id="14980-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="14980-131">Probíhá aktualizace</span><span class="sxs-lookup"><span data-stu-id="14980-131">Refreshing</span></span>    |<span data-ttu-id="14980-132">Probíhá příjem dat.</span><span class="sxs-lookup"><span data-stu-id="14980-132">Data ingestion is in progress.</span></span> <span data-ttu-id="14980-133">Tuto operaci můžete zrušit výběrem **Přestat obnovovat** v sloupci **Akce**.</span><span class="sxs-lookup"><span data-stu-id="14980-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="14980-134">Zastavením aktualizace zdroje dat se vrátíte do posledního stavu obnovy.</span><span class="sxs-lookup"><span data-stu-id="14980-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="14980-135">Nezdařilo se</span><span class="sxs-lookup"><span data-stu-id="14980-135">Failed</span></span>     |<span data-ttu-id="14980-136">Při přijímání dat došlo k chybám.</span><span class="sxs-lookup"><span data-stu-id="14980-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="14980-137">Vyberte hodnotu ve sloupci **Stav** ve zdroji dat, chcete-li znát další podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="14980-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="14980-138">V podokně **Podrobnosti o průběhu** rozbalte **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="14980-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="14980-139">Volbou **Zobrazit podrobnosti** zobrazíte další informace o stavu aktualizace, včetně podrobností o chybách a následných aktualizacích procesu.</span><span class="sxs-lookup"><span data-stu-id="14980-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="14980-140">Načítání dat může nějakou dobu trvat.</span><span class="sxs-lookup"><span data-stu-id="14980-140">Loading data can take time.</span></span> <span data-ttu-id="14980-141">Po úspěšné aktualizaci lze přijatá data zkontrolovat na stránce **Entity**.</span><span class="sxs-lookup"><span data-stu-id="14980-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="14980-142">Další informace najdete v tématu [Entity](entities.md).</span><span class="sxs-lookup"><span data-stu-id="14980-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="14980-143">Aktualizace zdroje dat</span><span class="sxs-lookup"><span data-stu-id="14980-143">Refresh a data source</span></span>

<span data-ttu-id="14980-144">Zdroje dat lze aktualizovat podle automatického plánu nebo ručně na vyžádání.</span><span class="sxs-lookup"><span data-stu-id="14980-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="14980-145">Přejděte na **Správce** > **Systém** > [**Plán**](system.md#schedule-tab), ke nakonfigurujte naplánované aktualizace všech ingestovaných zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="14980-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="14980-146">Chcete-li aktualizovat zdroj dat na vyžádání, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="14980-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="14980-147">V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="14980-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="14980-148">Vyberte svislé tlačítko se třemi tečkami vedle zdroje dat, který chcete aktualizovat, a v rozevíracím seznamu vyberte **Aktualizovat**.</span><span class="sxs-lookup"><span data-stu-id="14980-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="14980-149">Zdroj dat je nyní spuštěn pro ruční aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="14980-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="14980-150">Aktualizací zdroj dat aktualizujete schéma entity i data pro všechny entity uvedené ve zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="14980-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="14980-151">Vyberte **Zastavit aktualizaci**, pokud chcete zrušit existující aktualizaci a zdroj dat se vrátí do svého posledního stavu aktualizace.</span><span class="sxs-lookup"><span data-stu-id="14980-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="14980-152">Odstranit datový zdroj</span><span class="sxs-lookup"><span data-stu-id="14980-152">Delete a data source</span></span>

1. <span data-ttu-id="14980-153">V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="14980-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="14980-154">Vyberte svislé tlačítko se třemi tečkami vedle zdroje dat, který chcete odebrat, a v rozevírací nabídce vyberte **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="14980-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="14980-155">Odstranění potvrďte.</span><span class="sxs-lookup"><span data-stu-id="14980-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
