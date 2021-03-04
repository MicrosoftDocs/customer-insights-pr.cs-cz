---
title: Přijímání a omezení dat v reálném čase
description: Obecné informace o funkcích v reálném čase v přehledech cílové skupiny.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270272"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="a7127-103">Příjem dat v reálném čase (náhled)</span><span class="sxs-lookup"><span data-stu-id="a7127-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="a7127-104">Díky funkcím téměř v reálném čase můžete během několika sekund vidět nejnovější interakce, které vaši zákazníci provedli s vašimi produkty nebo službami.</span><span class="sxs-lookup"><span data-stu-id="a7127-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="a7127-105">[Plánované aktualizace](system.md#schedule-tab) zahrnují velké množství záznamů a několik složitých operací.</span><span class="sxs-lookup"><span data-stu-id="a7127-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="a7127-106">Nejprve jsou data stažena ze zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="a7127-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="a7127-107">Dále jsou data sjednocena a poté obohacena o další informace.</span><span class="sxs-lookup"><span data-stu-id="a7127-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="a7127-108">Každé spuštění tohoto procesu může trvat minuty až hodiny.</span><span class="sxs-lookup"><span data-stu-id="a7127-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="a7127-109">Tato funkce v reálném čase poskytuje data okamžitě ke spotřebě, dokud následující naplánovaná aktualizace nevytáhne tato data ze zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="a7127-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="a7127-110">Aktualizace v reálném čase mají čas vypršení platnosti, po kterém již nepřepisují hodnotu ze zdroje dat:</span><span class="sxs-lookup"><span data-stu-id="a7127-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="a7127-111">Aktualizace profilu bude zachována po dobu 4 hodin</span><span class="sxs-lookup"><span data-stu-id="a7127-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="a7127-112">Činnosti budou udržovány po dobu 30 dnů</span><span class="sxs-lookup"><span data-stu-id="a7127-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="a7127-113">Tyto hodnoty jsou parametry volání API, které můžete změnit.</span><span class="sxs-lookup"><span data-stu-id="a7127-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="a7127-114">Jejich cílem je zajistit, aby vaše zdrojová data zůstala vaším důvěryhodným zdrojem.</span><span class="sxs-lookup"><span data-stu-id="a7127-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="a7127-115">Pokud chcete, aby byly aktualizace v reálném čase uchovány déle, musíte je přidat do zdroje dat, aby se stáhly během příští plánované aktualizace.</span><span class="sxs-lookup"><span data-stu-id="a7127-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="a7127-116">Aktualizace sjednocených polí profilu zákazníka v reálném čase</span><span class="sxs-lookup"><span data-stu-id="a7127-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="a7127-117">Aktualizované profily se projeví v zobrazení zákaznické karty nebo v jakékoli jiné vizualizaci během několika sekund.</span><span class="sxs-lookup"><span data-stu-id="a7127-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="a7127-118">Protože operace v reálném čase probíhají po sjednocení dat, vztahují se pouze na sjednocené profily zákazníků.</span><span class="sxs-lookup"><span data-stu-id="a7127-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="a7127-119">V důsledku toho nebudou změny profilu v reálném čase aktualizovat opatření, členství v segmentech ani obohacení.</span><span class="sxs-lookup"><span data-stu-id="a7127-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="a7127-120">Omezení</span><span class="sxs-lookup"><span data-stu-id="a7127-120">Limitations</span></span>

- <span data-ttu-id="a7127-121">Profily zákazníků lze aktualizovat, ale nelze je vytvářet ani odstraňovat.</span><span class="sxs-lookup"><span data-stu-id="a7127-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="a7127-122">Export aktualizací v reálném čase do externích systémů, například Power BI, v tuto chvíli není možný.</span><span class="sxs-lookup"><span data-stu-id="a7127-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="a7127-123">Tvorba aktivit v reálném čase</span><span class="sxs-lookup"><span data-stu-id="a7127-123">Real-time creation of activities</span></span>

<span data-ttu-id="a7127-124">Rozhraní API v reálném čase umožňuje publikovat novou aktivitu ze zdrojového systému (samostatný zdrojový záznam) ve sjednoceném profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a7127-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="a7127-125">Nová aktivita bude k dispozici jako sjednocená aktivita na časové ose tohoto sjednoceného zákaznického profilu během několika sekund.</span><span class="sxs-lookup"><span data-stu-id="a7127-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="a7127-126">Časovou osu můžete vidět v zobrazení zákaznické karty nebo v jakékoli jiné integraci časové osy, kterou jste nakonfigurovali.</span><span class="sxs-lookup"><span data-stu-id="a7127-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="a7127-127">Aktivity jsou neměnné.</span><span class="sxs-lookup"><span data-stu-id="a7127-127">Activities are immutable.</span></span> <span data-ttu-id="a7127-128">Jakmile se jednou vytvoří, nezmění se.</span><span class="sxs-lookup"><span data-stu-id="a7127-128">They don't change once created.</span></span>
> - <span data-ttu-id="a7127-129">V současné době se segmenty a měření na základě nové aktivity neaktualizují.</span><span class="sxs-lookup"><span data-stu-id="a7127-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="a7127-130">Aktivity přidané pouze prostřednictvím rozhraní API v reálném čase nejsou součástí exportu a nebudou se zobrazovat v PowerBI.</span><span class="sxs-lookup"><span data-stu-id="a7127-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="a7127-131">K rozhraní API v reálném čase se můžete připojit dvěma způsoby:</span><span class="sxs-lookup"><span data-stu-id="a7127-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="a7127-132">[nepřímo](#connect-via-the-dynamics-365-customer-insights-connector), pomocí konektoru [Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="a7127-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="a7127-133">[přímo](#connect-directly-to-the-real-time-api), s kódem</span><span class="sxs-lookup"><span data-stu-id="a7127-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="a7127-134">Oba způsoby mají společné následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="a7127-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="a7127-135">Prostředí Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a7127-135">A Customer Insights environment</span></span>
- <span data-ttu-id="a7127-136">Sjednocené profily zákazníka</span><span class="sxs-lookup"><span data-stu-id="a7127-136">Unified customer profiles</span></span>
- <span data-ttu-id="a7127-137">Nakonfigurované a spuštěné činnosti</span><span class="sxs-lookup"><span data-stu-id="a7127-137">Activities configured and run</span></span>
- <span data-ttu-id="a7127-138">Oprávnění přispěvatele nebo správce k ověření vašeho účtu</span><span class="sxs-lookup"><span data-stu-id="a7127-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="a7127-139">Připojení přes konektor Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a7127-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="a7127-140">Rozhraní API v reálném čase může ingestovat data z vyhrazeného konektoru Power Platform, konektoru [Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), bez nutnosti zapisovat a nasazovat kód.</span><span class="sxs-lookup"><span data-stu-id="a7127-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="a7127-141">Konektor může provádět stejné akce v reálném čase jako API.</span><span class="sxs-lookup"><span data-stu-id="a7127-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="a7127-142">Pro prémiové konektory potřebujete platnou licenci.</span><span class="sxs-lookup"><span data-stu-id="a7127-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="a7127-143">Další informace získáte v části [Nejčastější dotazy k licencování Power Apps a Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="a7127-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="a7127-144">Power Platform [Power Apps a/nebo Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="a7127-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="a7127-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="a7127-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="a7127-146">Podrobnosti o vytváření toků viz [dokumentace Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="a7127-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="a7127-147">Připojení se přímo k rozhraní API v reálném čase</span><span class="sxs-lookup"><span data-stu-id="a7127-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="a7127-148">Funkce v reálném čase můžete využít vytvořením vlastního kanálu a přímým připojením k rozhraní API v reálném čase.</span><span class="sxs-lookup"><span data-stu-id="a7127-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="a7127-149">Aktivitu můžete zveřejnit ve formátu zdrojového systému nebo ve formátu UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="a7127-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="a7127-150">Formát získejte voláním rozhraní API /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="a7127-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="a7127-151">Podrobnosti o tomto rozhraní API, včetně parametrů a odpovědí, najdete v sekci **EntityData** v části [Referenční informace o rozhraních API v Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="a7127-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="a7127-152">Další informace naleznete v části [Práce s rozhraními API v Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="a7127-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="a7127-153">Využití v reálném čase pomocí telemetrie</span><span class="sxs-lookup"><span data-stu-id="a7127-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="a7127-154">Získejte přehled o objemu požadavků na rozhraní API v reálném čase a informace o problémech, se kterými se systém může setkat.</span><span class="sxs-lookup"><span data-stu-id="a7127-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="a7127-155">Můžete [přistupovat k telemetrii v reálném čase](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="a7127-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]