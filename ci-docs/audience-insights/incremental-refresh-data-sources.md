---
title: Přírůstková aktualizace pro zdroje dat založené na Power Query
description: Aktualizujte nová a aktualizovaná data pro velké zdroje dat založené na Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 03f76bcfc7336d8430146e8a26ffa649c6a17db0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596813"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="f58f4-103">Přírůstková aktualizace pro zdroje dat založené na Power Query</span><span class="sxs-lookup"><span data-stu-id="f58f4-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="f58f4-104">Přírůstková aktualizace pro zdroje dat poskytuje následující výhody:</span><span class="sxs-lookup"><span data-stu-id="f58f4-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="f58f4-105">**Rychlejší aktualizace** – Obnoví se pouze data, která se změnila.</span><span class="sxs-lookup"><span data-stu-id="f58f4-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="f58f4-106">Můžete například obnovit pouze posledních pět dní historické množiny dat.</span><span class="sxs-lookup"><span data-stu-id="f58f4-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="f58f4-107">**Zvýšená spolehlivost** – U menších aktualizací nemusíte udržovat připojení k nestabilním zdrojovým systémům tak dlouho, což snižuje riziko problémů s připojením.</span><span class="sxs-lookup"><span data-stu-id="f58f4-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="f58f4-108">**Snížená spotřeba zdrojů** – Aktualizace pouze podmnožiny vašich celkových dat vede k efektivnějšímu využití výpočetních zdrojů a snižuje dopad na životní prostředí.</span><span class="sxs-lookup"><span data-stu-id="f58f4-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="f58f4-109">Konfigurovat přírůstkovou aktualizaci</span><span class="sxs-lookup"><span data-stu-id="f58f4-109">Configure incremental refresh</span></span>

<span data-ttu-id="f58f4-110">Přehledy cílové skupiny umožňují přírůstkovou aktualizaci zdrojů dat importovaných prostřednictvím Power Query, které podporují přírůstkovou ingestaci.</span><span class="sxs-lookup"><span data-stu-id="f58f4-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="f58f4-111">Například databáze Azure SQL s datovými a časovými poli, která označují, kdy byly naposledy aktualizovány datové záznamy.</span><span class="sxs-lookup"><span data-stu-id="f58f4-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="f58f4-112">[Vytvoření nového zdroje dat na základě Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f58f4-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="f58f4-113">Zadejte název zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="f58f4-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="f58f4-114">Vyberte zdroj dat, který podporuje přírůstkové aktualizace, například databázi Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="f58f4-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="f58f4-115">Vyberte entity nebo tabulky, které chcete ingestovat.</span><span class="sxs-lookup"><span data-stu-id="f58f4-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="f58f4-116">Dokončete kroky transformace a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="f58f4-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="f58f4-117">V dialogovém okně **Nastavení přírůstkové aktualizace** volbou **Nastavit** otevřete **Nastavení přírůstkové aktualizace**.</span><span class="sxs-lookup"><span data-stu-id="f58f4-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="f58f4-118">Pokud vyberete volbu **Přeskočit**, zdroj dat aktualizuje celou datovou sadu.</span><span class="sxs-lookup"><span data-stu-id="f58f4-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="f58f4-119">Můžete také použít přírůstkovou aktualizaci později úpravou existujícího zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="f58f4-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="f58f4-120">Na stránce **Nastavení přírůstkové aktualizace** nakonfigurujete přírůstkovou aktualizaci pro všechny entity, které jste vybrali při vytváření zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="f58f4-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f58f4-121">![Konfigurace entit ve zdroj dat pro přírůstkovou aktualizaci](media/incremental-refresh-settings.png "Konfigurace entit ve zdroj dat pro přírůstkovou aktualizaci")</span><span class="sxs-lookup"><span data-stu-id="f58f4-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="f58f4-122">Vyberte entitu a uveďte následující podrobnosti:</span><span class="sxs-lookup"><span data-stu-id="f58f4-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="f58f4-123">**Definujte primární klíč**: Vyberte primární klíč pro entitu nebo tabulku.</span><span class="sxs-lookup"><span data-stu-id="f58f4-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="f58f4-124">**Definujte pole „poslední aktualizace“**: Toto pole zobrazí pouze atributy typu datum nebo čas.</span><span class="sxs-lookup"><span data-stu-id="f58f4-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="f58f4-125">Vyberte atribut, který označuje, kdy byly záznamy naposledy aktualizovány.</span><span class="sxs-lookup"><span data-stu-id="f58f4-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="f58f4-126">Bude se používat k identifikaci záznamů, které spadají do časového rámce přírůstkové aktualizace.</span><span class="sxs-lookup"><span data-stu-id="f58f4-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="f58f4-127">**Zkontrolovat aktualizace každých**: Určete, jak velký časový rámec přírůstkové aktualizace chcete.</span><span class="sxs-lookup"><span data-stu-id="f58f4-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="f58f4-128">Volbou **Uložit** dokončete vytvoření zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="f58f4-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="f58f4-129">Počáteční aktualizace dat bude úplná aktualizace.</span><span class="sxs-lookup"><span data-stu-id="f58f4-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="f58f4-130">Poté dochází k přírůstkové aktualizaci dat, jak bylo nakonfigurováno v předchozím kroku.</span><span class="sxs-lookup"><span data-stu-id="f58f4-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]