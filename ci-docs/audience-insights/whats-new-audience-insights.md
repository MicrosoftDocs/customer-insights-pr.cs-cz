---
title: Nové a připravované funkce
description: Informace o nových funkcích, vylepšeních a opravách chyb.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 9183c8af4fb9f9f08ac63d8d0cd37c6868bba310
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270424"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a><span data-ttu-id="444d9-103">Co je nového ve funkci přehledů cílové skupiny Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="444d9-103">What's new in the audience insights capability of Dynamics 365 Customer Insights</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="444d9-104">S radostí představujeme naše nejnovější aktualizace!</span><span class="sxs-lookup"><span data-stu-id="444d9-104">We're excited to announce our newest updates!</span></span> <span data-ttu-id="444d9-105">Tento článek shrnuje funkce Public Preview, rozšíření obecné dostupnosti a aktualizace funkcí.</span><span class="sxs-lookup"><span data-stu-id="444d9-105">This article summarizes public preview features, general availability enhancements, and feature updates.</span></span> <span data-ttu-id="444d9-106">Chcete-li zobrazit dlouhodobé plány funkcí, projděte si [plány vydávání Dynamics 365 a Power Platform](https://docs.microsoft.com/dynamics365/release-plans/).</span><span class="sxs-lookup"><span data-stu-id="444d9-106">To see the long-term feature plans, take a look at the [Dynamics 365 and Power Platform release plans](https://docs.microsoft.com/dynamics365/release-plans/).</span></span>

<span data-ttu-id="444d9-107">Můžete se také podívat na následující video a dozvědět se více o plánovaných funkcích za posledních šest měsíců.</span><span class="sxs-lookup"><span data-stu-id="444d9-107">You can also watch the following video to learn more about the capabilities planned for the last six months.</span></span>

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

<span data-ttu-id="444d9-108">Zavádíme aktualizace podle oblastí.</span><span class="sxs-lookup"><span data-stu-id="444d9-108">We roll out updates on a region-by-region basis.</span></span> <span data-ttu-id="444d9-109">Některé oblasti tedy budou disponovat funkcemi dříve než ostatní.</span><span class="sxs-lookup"><span data-stu-id="444d9-109">So certain regions might see features before others.</span></span> <span data-ttu-id="444d9-110">Pokud není uvedeno jinak, nemusíte podnikat žádné kroky a my automaticky aktualizujeme aplikaci bez prostojů.</span><span class="sxs-lookup"><span data-stu-id="444d9-110">Unless specified differently, you don't need to take any action and we'll update the app automatically with no downtime.</span></span>

> [!TIP]
> <span data-ttu-id="444d9-111">Pokud chcete zasílat žádosti o funkce a návrhy na produkty a hlasovat o nich, přejděte na [portál pro nápady k aplikaci Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span><span class="sxs-lookup"><span data-stu-id="444d9-111">To submit and vote on feature requests and product suggestions, go to the [Dynamics 365 Application Ideas portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span></span>

## <a name="january-2021-updates"></a><span data-ttu-id="444d9-112">Aktualizace z ledna 2021</span><span class="sxs-lookup"><span data-stu-id="444d9-112">January 2021 updates</span></span>

<span data-ttu-id="444d9-113">Aktualizace v lednu 2021 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.</span><span class="sxs-lookup"><span data-stu-id="444d9-113">The updates in January 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="444d9-114">Rozšiřitelnost</span><span class="sxs-lookup"><span data-stu-id="444d9-114">Extensibility</span></span>

- <span data-ttu-id="444d9-115">**Rozšířená funkčnost a vylepšený výkon pro export SFTP** Nyní můžete exportovat všechny výstupní entity z Customer Insights do hostitele SFTP.</span><span class="sxs-lookup"><span data-stu-id="444d9-115">**Extended functionality and enhanced performance for SFTP export** You can now export all output entities from Customer Insights to an SFTP host.</span></span> <span data-ttu-id="444d9-116">Dříve byl export omezen na segmentové entity.</span><span class="sxs-lookup"><span data-stu-id="444d9-116">Previously, export was limited to segment entities.</span></span> <span data-ttu-id="444d9-117">Výkon exportu SFTP navíc umožňuje větší objem dat za kratší dobu, v závislosti na výkonu vašeho hostitele SFTP.</span><span class="sxs-lookup"><span data-stu-id="444d9-117">Additionally, the performance of the SFTP export allows more data volume in less time, depending on the performance of your SFTP host.</span></span>    
  <span data-ttu-id="444d9-118">Další informace viz [Konektor pro SFTP (Preview)](export-sftp.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-118">For more information, see [Connector for SFTP (preview)](export-sftp.md).</span></span>  

#### <a name="segments"></a><span data-ttu-id="444d9-119">Segmenty</span><span class="sxs-lookup"><span data-stu-id="444d9-119">Segments</span></span>

- <span data-ttu-id="444d9-120">**Navrhované segmenty využívají strojové učení ke zlepšení metrik** Nový způsob objevování a vytváření segmentů.</span><span class="sxs-lookup"><span data-stu-id="444d9-120">**Machine learning powered suggested segments to improve metrics** There's a new way do discover and create segments.</span></span> <span data-ttu-id="444d9-121">Systém používá model AI k navrhování segmentů, což může zlepšit ukazatel KPI (míru), který již sledujete.</span><span class="sxs-lookup"><span data-stu-id="444d9-121">The system uses an AI model to suggest segments that can help improve a KPI (measure) you are already tracking.</span></span> <span data-ttu-id="444d9-122">Ukazujeme rozsah vlivu atributů, které vyberete na míře nebo jiném primárním atributu.</span><span class="sxs-lookup"><span data-stu-id="444d9-122">We show the extent of influence of attributes that you select on a measure or another primary attribute.</span></span> <span data-ttu-id="444d9-123">Tyto informace pomáhají najít potenciální segmenty, které představují příležitosti.</span><span class="sxs-lookup"><span data-stu-id="444d9-123">This information helps finding potential segments that present opportunities.</span></span>    
  <span data-ttu-id="444d9-124">Další informace viz [Navrhované segmenty (Preview)](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-124">For more information, see [Suggested segments (preview)](suggested-segments.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="444d9-125">Sjednocení dat</span><span class="sxs-lookup"><span data-stu-id="444d9-125">Data unification</span></span>

- <span data-ttu-id="444d9-126">**Vylepšený prostředí párování** V oblasti sjednocení dat bylo aktualizováno prostředí párování.</span><span class="sxs-lookup"><span data-stu-id="444d9-126">**Enhanced match experience** In the data unification area, the match experience was updated.</span></span> <span data-ttu-id="444d9-127">To vám umožňuje konfigurovat a zobrazovat pravidla párování, včetně podrobných statistik, které vám dále vysvětlí, jak párování funguje.</span><span class="sxs-lookup"><span data-stu-id="444d9-127">It lets you configure and view the match rules, including detailed stats to further explain how matching works.</span></span> <span data-ttu-id="444d9-128">Existují možnosti, jak zakázat pravidlo párování, takže již nebude aktivní při zachování konfigurace, pravidel párování při přetažení apod.</span><span class="sxs-lookup"><span data-stu-id="444d9-128">There are options to disable a match rule so it's no longer active while retaining the configuration, drag and drop match rules, and more.</span></span>
  <span data-ttu-id="444d9-129">Další informace najdete v tématu [Párování entit](match-entities.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-129">For more information, see [Match entities](match-entities.md).</span></span>

- <span data-ttu-id="444d9-130">**Výstup odstraněných duplicit z procesu párování je k dispozici jako entita** Výstup procesu odstranění duplicit z procesu párování je nyní zapsán do samostatné entity pro další analýzu.</span><span class="sxs-lookup"><span data-stu-id="444d9-130">**Deduplication output from the match process is available as an entity** Deduplication process output from the match process is now written into a separate entity for further analysis.</span></span> <span data-ttu-id="444d9-131">Tato entita se skládá z polí použitých v procesu odstranění duplicit, vítězného záznamu a odpovídajících alternativních záznamů, které jsou sloučeny s vítězným záznamem.</span><span class="sxs-lookup"><span data-stu-id="444d9-131">This entity consists of the fields used in the deduplication process and the winner record and the corresponding alternate records that get merged with the winner record.</span></span>
  <span data-ttu-id="444d9-132">Další informace viz [Výstup odebraných duplicit jako entita](match-entities.md#deduplication-output-as-an-entity).</span><span class="sxs-lookup"><span data-stu-id="444d9-132">For more information, see [Deduplication output as an entity](match-entities.md#deduplication-output-as-an-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="444d9-133">správa systému,</span><span class="sxs-lookup"><span data-stu-id="444d9-133">System administration</span></span>

- <span data-ttu-id="444d9-134">**Bezproblémové sdílení dat s Microsoft Dataverse** Nyní můžete sdílet výstup Customer Insights s aplikacemi Microsoft Dataverse využívajícími službu Data Lake spravovanou Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="444d9-134">**Seamlessly share data to Microsoft Dataverse** You can now share Customer Insights output with Microsoft Dataverse applications using the Microsoft Dataverse Managed Data Lake.</span></span> <span data-ttu-id="444d9-135">Jakmile přidružíte prostředí Dataverse k Customer Insights, budete moci povolit sdílení dat.</span><span class="sxs-lookup"><span data-stu-id="444d9-135">Once you associate a Dataverse environment with Customer Insights, you get the option to enable data sharing.</span></span>
  <span data-ttu-id="444d9-136">Další informace naleznete v tématu [Správa prostředí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-136">For more information, see [Manage environments](manage-environments.md).</span></span>


## <a name="december-2020-updates"></a><span data-ttu-id="444d9-137">Aktualizace z prosince 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-137">December 2020 updates</span></span>

<span data-ttu-id="444d9-138">Aktualizace v prosinci 2020 zahrnují několik funkcí, upgrady výkonu a opravy chyb.</span><span class="sxs-lookup"><span data-stu-id="444d9-138">The updates in December 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-december-2020"></a><span data-ttu-id="444d9-139">Nové a aktualizované funkce v prosinci 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-139">New and updated features in December 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="444d9-140">Rozšiřování dat</span><span class="sxs-lookup"><span data-stu-id="444d9-140">Data enrichment</span></span>

- <span data-ttu-id="444d9-141">**Vylepšené rozšíření afinity značek a zájmů**</span><span class="sxs-lookup"><span data-stu-id="444d9-141">**Improved Brand and Interest affinity enrichments**</span></span>
  
  <span data-ttu-id="444d9-142">Zjednodušili jsme skóre afinity, abychom usnadnili jeho pochopení a použití.</span><span class="sxs-lookup"><span data-stu-id="444d9-142">We simplified our affinity scores to make them easier to understand and use.</span></span> <span data-ttu-id="444d9-143">Nyní můžete rychle identifikovat zákazníky podle toho, jak velkou afinitu vykazují k dané značce nebo zájmu.</span><span class="sxs-lookup"><span data-stu-id="444d9-143">You can now quickly identify customers based on how much affinity they have for a given brand or interest.</span></span>

  <span data-ttu-id="444d9-144">Navíc jsme přidali nové možnosti konfigurace, abyste měli více možností při rozšiřování zákaznických profilů.</span><span class="sxs-lookup"><span data-stu-id="444d9-144">Additionally, we have added new configuration options to better control how you want your customer profiles to be enriched.</span></span> 

  <span data-ttu-id="444d9-145">Další informace viz [Rozšíření profilů zákazníků afinitami značky a zájmů](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="444d9-145">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

- <span data-ttu-id="444d9-146">**Určete, které profily chcete rozšířit**</span><span class="sxs-lookup"><span data-stu-id="444d9-146">**Control which profiles to enrich**</span></span>

  <span data-ttu-id="444d9-147">Nyní můžete rozšířit pouze podmnožinu profilů zákazníků s možností vybrat entitu segmentu namísto výchozí entity zákazníka.</span><span class="sxs-lookup"><span data-stu-id="444d9-147">You can now enrich only a subset of your customer profiles with the option to select a segment entity instead of the default customer entity.</span></span> <span data-ttu-id="444d9-148">Vytvořte segment s profily zákazníků, které chcete rozšířit, a vyberte jej v konfiguraci rozšíření pro datovou sadu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="444d9-148">Create a segment with the customer profiles you would like to enrich and select it in the enrichment configuration for your customer data set.</span></span>
  <span data-ttu-id="444d9-149">Tato funkce je v současné době k dispozici pouze pro rozšíření poskytované společnostmi Experian a HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="444d9-149">This feature is currently available only for enrichments provided by Experian and HERE Technologies.</span></span> <span data-ttu-id="444d9-150">Brzy tuto funkci aktivujeme pro další rozšíření.</span><span class="sxs-lookup"><span data-stu-id="444d9-150">We will be enabling this capability to more enrichments soon.</span></span>

  <span data-ttu-id="444d9-151">Další informace viz [Rozšíření profilů zákazníků o demografické údaje společnosti Experian](enrichment-experian.md) nebo [Rozšíření profilů zákazníků o demografické údaje společnosti HERE Technologies](enrichment-here.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-151">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md) or [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="444d9-152">Rozšiřitelnost</span><span class="sxs-lookup"><span data-stu-id="444d9-152">Extensibility</span></span>

- <span data-ttu-id="444d9-153">**Aktivace segmentů prostřednictvím služby Autopilot**</span><span class="sxs-lookup"><span data-stu-id="444d9-153">**Activate your segments through Autopilot**</span></span>

  <span data-ttu-id="444d9-154">Exportujte segmenty do služby Autopilot a použijte je pro marketingové účely.</span><span class="sxs-lookup"><span data-stu-id="444d9-154">Export segments to Autopilot and use them for marketing purposes.</span></span> <span data-ttu-id="444d9-155">Další informace viz [Konektor pro Autopilot (Preview)](export-autopilot.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-155">For more information, see [Connector for Autopilot (preview)](export-autopilot.md).</span></span>

- <span data-ttu-id="444d9-156">**Aktivace segmentů prostřednictvím služby Sendgrid**</span><span class="sxs-lookup"><span data-stu-id="444d9-156">**Activate your segments through SendGrid**</span></span>

  <span data-ttu-id="444d9-157">Exportujte segmenty do služby SendGrid a použijte je pro marketingové účely.</span><span class="sxs-lookup"><span data-stu-id="444d9-157">Export segments to SendGrid and use them for marketing purposes.</span></span> <span data-ttu-id="444d9-158">Další informace viz [Konektor pro SendGrid](export-sendgrid.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-158">For more information, see [Connector for SendGrid](export-sendgrid.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="444d9-159">správa systému,</span><span class="sxs-lookup"><span data-stu-id="444d9-159">System administration</span></span>

- <span data-ttu-id="444d9-160">**Aktualizované prostředí pro správu prostředí**</span><span class="sxs-lookup"><span data-stu-id="444d9-160">**Updated environment management experience**</span></span>
  
  <span data-ttu-id="444d9-161">Nyní můžete vytvářet, upravovat, odstraňovat a obnovovat prostředí přímo z nástroje pro výběr prostředí v záhlaví aplikace.</span><span class="sxs-lookup"><span data-stu-id="444d9-161">You can now create, edit, delete, and reset environments directly from the environment picker in the app header.</span></span> 
  
  <span data-ttu-id="444d9-162">Prostředí, které právě používáte, bude navíc připnuto v horní části panelu prostředí, takže jej již nemusíte hledat.</span><span class="sxs-lookup"><span data-stu-id="444d9-162">Additionally, the environment you are using will be pinned at the top of the environment panel so you don't need to search for it anymore.</span></span>

  <span data-ttu-id="444d9-163">Další informace naleznete v tématu [Správa prostředí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-163">For more information, see [Manage environments](manage-environments.md).</span></span>

## <a name="november-2020-updates"></a><span data-ttu-id="444d9-164">Aktualizace z listopadu 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-164">November 2020 updates</span></span>

<span data-ttu-id="444d9-165">Aktualizace v listopadu 2020 zahrnují několik funkcí, upgrady výkonu a opravy chyb.</span><span class="sxs-lookup"><span data-stu-id="444d9-165">The updates in November 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-november-2020"></a><span data-ttu-id="444d9-166">Nové a aktualizované funkce v listopadu 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-166">New and updated features in November 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="444d9-167">Rozšiřování dat</span><span class="sxs-lookup"><span data-stu-id="444d9-167">Data enrichment</span></span>

- <span data-ttu-id="444d9-168">**Zavedení vlastních dat rozšíření vlastním importem prostřednictvím protokolu SFTP (Secure File Transfer Protocol)**</span><span class="sxs-lookup"><span data-stu-id="444d9-168">**Bring your own enrichment data via Secure File Transfer Protocol (SFTP) custom import**</span></span>
  
  <span data-ttu-id="444d9-169">Vlastní import pomocí protokolu SFTP umožňuje importovat data rozšíření, která nemusí projít procesem sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="444d9-169">SFTP custom import lets you import enrichment data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="444d9-170">Zjistěte více o vlastním importu prostřednictvím protokolu SFTP.</span><span class="sxs-lookup"><span data-stu-id="444d9-170">Learn more about SFTP custom import.</span></span>

  <span data-ttu-id="444d9-171">Další informace viz [Rozšíření profilů zákazníků o vlastní data (Preview)](enrichment-SFTP-custom-import.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-171">For more information, see [Enrich customer profiles with custom data (preview)](enrichment-SFTP-custom-import.md).</span></span>
 
- <span data-ttu-id="444d9-172">**Rozšíření zákaznických dat o údaje o poloze od společnosti HERE Technologies**</span><span class="sxs-lookup"><span data-stu-id="444d9-172">**Enrich your customer data with location data from HERE Technologies**</span></span>

  <span data-ttu-id="444d9-173">Se službami rozšíření dat HERE Technologies můžete dosáhnout přesnějšího porozumění polohy svých zákazníků normalizací adres, získáním zeměpisné šířky a délky atd.</span><span class="sxs-lookup"><span data-stu-id="444d9-173">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span> <span data-ttu-id="444d9-174">Zjistěte více o rozšíření od společnosti HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="444d9-174">Learn more about enriching with HERE Technologies.</span></span>

  <span data-ttu-id="444d9-175">Další informace viz [Rozšíření profilů zákazníků od HERE Technologies](enrichment-here.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-175">For more information, see [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="444d9-176">Sjednocení dat</span><span class="sxs-lookup"><span data-stu-id="444d9-176">Data unification</span></span>

- <span data-ttu-id="444d9-177">**Flexibilita umožňující profilování dat u vybraných entit a polí z vašeho účtu úložiště**</span><span class="sxs-lookup"><span data-stu-id="444d9-177">**Flexibility to enable data profiling on selected entities and fields from your storage account**</span></span>

  <span data-ttu-id="444d9-178">Můžete určit, pro které datové entity a pole ze složky Common Data Model ve vašem účtu úložiště Azure Data Lake chcete povolit profilování dat jako součást procesu příjmu dat.</span><span class="sxs-lookup"><span data-stu-id="444d9-178">You can indicate which data entities and fields from a Common Data Model folder in your Azure Data Lake storage account you want to enable data profiling as part of the data ingestion process.</span></span>

  <span data-ttu-id="444d9-179">Další informace viz [Připojení ke složce Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="444d9-179">For more information, see [Connect to a Common Data Model folder](connect-common-data-model.md#connect-to-a-common-data-model-folder).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="444d9-180">Rozšiřitelnost</span><span class="sxs-lookup"><span data-stu-id="444d9-180">Extensibility</span></span>

- <span data-ttu-id="444d9-181">**Aktivace svých segmentů prostřednictvím služby Google Ads**</span><span class="sxs-lookup"><span data-stu-id="444d9-181">**Activate your segments through Google Ads**</span></span>

  <span data-ttu-id="444d9-182">Exportujte segmenty ze seznamu cílových skupin Google Ads a použijte tyto seznamy k inzerci ve službách Google Search, Google Display Network, YouTube a Gmail.</span><span class="sxs-lookup"><span data-stu-id="444d9-182">Export segments from to Google Ads audience lists and use these lists to advertise on Google Search, Google Display Network, YouTube, and Gmail.</span></span> <span data-ttu-id="444d9-183">Zjistěte více o aktivaci vašich segmentů prostřednictvím služby Google Ads.</span><span class="sxs-lookup"><span data-stu-id="444d9-183">Learn more about activating your segments through Google Ads.</span></span>

  <span data-ttu-id="444d9-184">Další informace viz [Konektor pro Google Ads](export-google-ads.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-184">For more information, see [Connector for Google Ads](export-google-ads.md).</span></span>

- <span data-ttu-id="444d9-185">**Aktivace svých segmentů prostřednictvím služby Marketo**</span><span class="sxs-lookup"><span data-stu-id="444d9-185">**Activate your segments through Marketo**</span></span>

  <span data-ttu-id="444d9-186">Exportujte segmenty do cílových skupin služby Marketo a použijte je pro automatizaci marketingu.</span><span class="sxs-lookup"><span data-stu-id="444d9-186">Export segments to Marketo audiences and use these audiences for marketing automation.</span></span> <span data-ttu-id="444d9-187">Zjistěte více o aktivaci vašich segmentů prostřednictvím služby Marketo.</span><span class="sxs-lookup"><span data-stu-id="444d9-187">Learn more about activating your segments through Marketo.</span></span> 

  <span data-ttu-id="444d9-188">Další informace viz [Konektor pro Marketo](export-marketo.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-188">For more information, see [Connector for Marketo](export-marketo.md).</span></span>

- <span data-ttu-id="444d9-189">**Aktivace svých segmentů prostřednictvím služby DotDigital**</span><span class="sxs-lookup"><span data-stu-id="444d9-189">**Activate your segments through DotDigital**</span></span>

  <span data-ttu-id="444d9-190">Exportujte segmenty do služby DotDigital a použijte je pro marketingové účely.</span><span class="sxs-lookup"><span data-stu-id="444d9-190">Export segments to DotDigital and use them for marketing purposes.</span></span> <span data-ttu-id="444d9-191">Zjistěte více o aktivaci vašich segmentů prostřednictvím služby DotDigital.</span><span class="sxs-lookup"><span data-stu-id="444d9-191">Learn more about activating your segments through DotDigital.</span></span> 

  <span data-ttu-id="444d9-192">Další informace viz [Konektor pro DotDigital](export-dotdigital.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-192">For more information, see [Connector for DotDigital](export-dotdigital.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="444d9-193">Predikce</span><span class="sxs-lookup"><span data-stu-id="444d9-193">Predictions</span></span>

- <span data-ttu-id="444d9-194">**Predikce úbytku transakcí**</span><span class="sxs-lookup"><span data-stu-id="444d9-194">**Predict transactional churn**</span></span>

  <span data-ttu-id="444d9-195">Funkce predikce úbytku transakcí vám umožňuje bez pomoci datového vědce předpovědět pravděpodobnost, že zákazník přestane kupovat produkty nebo služby.</span><span class="sxs-lookup"><span data-stu-id="444d9-195">The transaction churn prediction feature enables you, without the help of a data scientist, to predict the likelihood of a customer to stop purchasing products or services.</span></span>  <span data-ttu-id="444d9-196">Pomocí skóre predikce můžete zkombinovat další informace o vašich zákaznících, jako je hodnota zákazníka, a vytvořit segmenty s vysokým rizikem odlivu zákazníků nebo se zákazníky s vysokou hodnotou.</span><span class="sxs-lookup"><span data-stu-id="444d9-196">Using the prediction score, you can combine other information about your customers, like customer value, to create segments of high churn risk or high value customers.</span></span> <span data-ttu-id="444d9-197">Tento segment slouží k přímému cílení na zákazníky prostřednictvím marketingových aktivit, zákaznické podpory a dalších scénářů ke snížení rizika odlivu zákazníků.</span><span class="sxs-lookup"><span data-stu-id="444d9-197">Use this segment to directly target customers through marketing activities, customer support, and other scenarios to reduce churn risk.</span></span>
 
  <span data-ttu-id="444d9-198">Nakonfigurujte definici odlivu zákazníků jako časové okno specifické pro vaši firmu a definujte, kdy u zákazníků hrozí riziko odchodu.</span><span class="sxs-lookup"><span data-stu-id="444d9-198">Configure the definition of churn as a time-based window specific to your business and define when customers are considered churned.</span></span> <span data-ttu-id="444d9-199">Například obchod s potravinami může považovat za rizikového zákazníka takového, který si nic nekoupil za posledních 30 dní.</span><span class="sxs-lookup"><span data-stu-id="444d9-199">For example, a grocery store may want to consider a customer churned if they have not purchased anything in the past 30 days.</span></span>
 
  <span data-ttu-id="444d9-200">Jak budete pokračovat ve vytváření predikce, provedeme vás, jaká data jsou potřebná, a umožníme vám mapovat data o vaší firmě na pole potřebná k předpovědi odlivu vašich zákazníků.</span><span class="sxs-lookup"><span data-stu-id="444d9-200">As you continue creating the prediction, we'll guide you what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="444d9-201">Můžete také nastavit plán opětovného trénování modelu na základě nových informací ve vašem systému, aby se přizpůsobil měnícím se obchodním okolnostem.</span><span class="sxs-lookup"><span data-stu-id="444d9-201">You can also set a schedule to retrain the model based on new information in your system to adapt to changing business circumstances.</span></span>
 
  <span data-ttu-id="444d9-202">Další informace viz [Predikce úbytku transakcí (Preview)](predict-transactional-churn.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-202">For more information, see [Transactional churn prediction (preview)](predict-transactional-churn.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="444d9-203">správa systému,</span><span class="sxs-lookup"><span data-stu-id="444d9-203">System administration</span></span>

- <span data-ttu-id="444d9-204">**Obnovit prostředí**</span><span class="sxs-lookup"><span data-stu-id="444d9-204">**Reset environment**</span></span>

  <span data-ttu-id="444d9-205">Obnovení veškerého obsahu prostředí vybrané instance a nový začátek.</span><span class="sxs-lookup"><span data-stu-id="444d9-205">Reset everything in an environment of a selected instance to start fresh.</span></span>

  <span data-ttu-id="444d9-206">Další informace najdete v článku [Obnovení existujícího prostředí](manage-environments.md#reset-an-existing-environment).</span><span class="sxs-lookup"><span data-stu-id="444d9-206">For more information, see [Reset an existing environment](manage-environments.md#reset-an-existing-environment).</span></span>


- <span data-ttu-id="444d9-207">**Připojení k účtu úložiště Azure Data Lake pomocí instančního objektu**</span><span class="sxs-lookup"><span data-stu-id="444d9-207">**Connect to your Azure Data Lake storage account using a service principal**</span></span>

  <span data-ttu-id="444d9-208">Zápis datového výstupu a čtení dat z vašeho účtu úložiště pomocí instančního objektu Azure.</span><span class="sxs-lookup"><span data-stu-id="444d9-208">Write data output to and read data from your storage account using an Azure service principal.</span></span> <span data-ttu-id="444d9-209">Existující připojení k účtu úložiště mohou nadále používat klíč účtu.</span><span class="sxs-lookup"><span data-stu-id="444d9-209">Existing storage account connections can continue to use the account key.</span></span> <span data-ttu-id="444d9-210">Nabízejí také možnost upgradu pro použití instančního objektu při postupu vpřed.</span><span class="sxs-lookup"><span data-stu-id="444d9-210">They also offer an upgrade option to use the service principal moving forward.</span></span> <span data-ttu-id="444d9-211">Nová připojení budou založena na metodě ověřování instančního objektu pro váš účet úložiště.</span><span class="sxs-lookup"><span data-stu-id="444d9-211">New connections will be based on the service principal authentication method for your storage account.</span></span>

  <span data-ttu-id="444d9-212">Další informace viz [Připojení k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure pro přehledy cílové skupiny](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-212">For more information, see [Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights](connect-service-principal.md).</span></span>

## <a name="october-2020-updates"></a><span data-ttu-id="444d9-213">Aktualizace říjen 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-213">October 2020 updates</span></span>

<span data-ttu-id="444d9-214">Aktualizace ze října 2020 zahrnují několik funkcí, upgrady výkonu a opravy chyb.</span><span class="sxs-lookup"><span data-stu-id="444d9-214">The updates in October 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-october-2020"></a><span data-ttu-id="444d9-215">Nové a aktualizované funkce v říjnu 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-215">New and updated features in October 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="444d9-216">Rozšiřitelnost</span><span class="sxs-lookup"><span data-stu-id="444d9-216">Extensibility</span></span>

- <span data-ttu-id="444d9-217">**Export do služby Mailchimp**</span><span class="sxs-lookup"><span data-stu-id="444d9-217">**Export to Mailchimp**</span></span>

<span data-ttu-id="444d9-218">Exportujte segmenty do existujících seznamů cílových skupin ve službě Mailchimp a poskytněte svým zákazníkům přizpůsobené e-mailové prostředí.</span><span class="sxs-lookup"><span data-stu-id="444d9-218">Export segments to existing audience lists in Mailchimp to provide a personalized email experience for your customers.</span></span>

<span data-ttu-id="444d9-219">Další informace viz [Konektor pro Mailchimp](export-mailchimp.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-219">For more information, see [Connector for Mailchimp](export-mailchimp.md).</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="444d9-220">Rozšiřování dat</span><span class="sxs-lookup"><span data-stu-id="444d9-220">Data enrichment</span></span>

- <span data-ttu-id="444d9-221">**Zrušení duplicit zdrojových záznamů v entitě Párování**</span><span class="sxs-lookup"><span data-stu-id="444d9-221">**Deduplicate the source records in a Match entity**</span></span>

<span data-ttu-id="444d9-222">Určete pravidla zrušení duplicit u entit použitých v procesu párování k identifikaci duplicitních záznamů.</span><span class="sxs-lookup"><span data-stu-id="444d9-222">Specify deduplication rules on entities used in the match process to identify duplicate records.</span></span> <span data-ttu-id="444d9-223">Slučte je do jednoho záznamu a propojte všechny zdrojové záznamy s tímto sloučeným záznamem.</span><span class="sxs-lookup"><span data-stu-id="444d9-223">Merge them into one record and link all the source records to this merged record.</span></span> <span data-ttu-id="444d9-224">Tento záznamu se zrušenou duplicitou bude poté použit v procesu párování mezi entitami.</span><span class="sxs-lookup"><span data-stu-id="444d9-224">This deduplicated record will then be used in the cross-entity matching process.</span></span>

<span data-ttu-id="444d9-225">Další informace viz [Definování zrušení duplicit v entitě párování](match-entities.md#define-deduplication-on-a-match-entity).</span><span class="sxs-lookup"><span data-stu-id="444d9-225">For more information, see [Define deduplication on a match entity](match-entities.md#define-deduplication-on-a-match-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="444d9-226">správa systému,</span><span class="sxs-lookup"><span data-stu-id="444d9-226">System administration</span></span>

- <span data-ttu-id="444d9-227">**Orchestrace: Nová možnost aktualizace při sloučení**</span><span class="sxs-lookup"><span data-stu-id="444d9-227">**Orchestration: New refresh option in Merge**</span></span>

<span data-ttu-id="444d9-228">Do dneška, když jste spustili proces sloučení, systém spustil všechny následné procesy, které závisí na sloučení a následných procesech.</span><span class="sxs-lookup"><span data-stu-id="444d9-228">Until today, when you run the merge process, the system ran all the downstream processes that depend on merge and subsequent processes.</span></span> <span data-ttu-id="444d9-229">Nyní můžete ověřit výstup procesu sloučení (sjednocená entita zákazníka) před použitím v následném zpracování jako segmenty nebo míry.</span><span class="sxs-lookup"><span data-stu-id="444d9-229">You can now verify the output of the merge process (the unified customer entity) before using it in downstream processing like segments or measures.</span></span>
<span data-ttu-id="444d9-230">Na stránce sloučení nyní můžete zvolit spuštění pouze kroku sloučení a spuštění pouze tohoto procesu.</span><span class="sxs-lookup"><span data-stu-id="444d9-230">On the merge page, you can now choose to run only the merge step and run only this process.</span></span> <span data-ttu-id="444d9-231">Chcete-li také aktualizovat všechny následné procesy, můžete zvolit sloučení a následné procesy.</span><span class="sxs-lookup"><span data-stu-id="444d9-231">To refresh all the downstream processes too, you can choose run merge and downstream processes.</span></span> 

## <a name="september-2020-updates"></a><span data-ttu-id="444d9-232">Aktualizace ze září 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-232">September 2020 updates</span></span>

<span data-ttu-id="444d9-233">Aktualizace ze září 2020 zahrnují několik funkcí, upgrady výkonu a opravy chyb.</span><span class="sxs-lookup"><span data-stu-id="444d9-233">The updates in September 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-september-2020"></a><span data-ttu-id="444d9-234">Nové a aktualizované funkce ze září 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-234">New and updated features in September 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="444d9-235">Aktivity</span><span class="sxs-lookup"><span data-stu-id="444d9-235">Activities</span></span>

- <span data-ttu-id="444d9-236">**Inteligentní predikce sémantiky atributů**</span><span class="sxs-lookup"><span data-stu-id="444d9-236">**Intelligent prediction of attribute semantics**</span></span>

<span data-ttu-id="444d9-237">Tato nová funkce predikuje sémantické typy vstupních atributů, které jsou předávány procesu sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="444d9-237">This new feature predicts the semantic types of input attributes that are passed on to the data unification process.</span></span> <span data-ttu-id="444d9-238">Funkce využívá modely strojového učení, které zlepšují přesnost a šetří čas.</span><span class="sxs-lookup"><span data-stu-id="444d9-238">It uses machine learning models that improve accuracy and save time.</span></span>

#### <a name="enrichments"></a><span data-ttu-id="444d9-239">Rozšíření</span><span class="sxs-lookup"><span data-stu-id="444d9-239">Enrichments</span></span>

- <span data-ttu-id="444d9-240">**Rozšíření demografických údajů od společnosti Experian**</span><span class="sxs-lookup"><span data-stu-id="444d9-240">**Demographics enrichment from Experian**</span></span>

<span data-ttu-id="444d9-241">Rozšíření demografických údajů od společnosti Experian je nyní k dispozici ve verzi Preview.</span><span class="sxs-lookup"><span data-stu-id="444d9-241">The demographics enrichment from Experian is now available in preview.</span></span> <span data-ttu-id="444d9-242">Experian je světový lídr v oblasti spotřebitelských a obchodních úvěrových reportů a marketingových služeb.</span><span class="sxs-lookup"><span data-stu-id="444d9-242">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="444d9-243">Se [službami rozšíření dat společnosti Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) můžete lépe porozumět svým zákazníkům díky rozšíření profilů zákazníků o demografické údaje, jako je velikost domácnosti, příjem a další.</span><span class="sxs-lookup"><span data-stu-id="444d9-243">With [Experian’s data enrichment services](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

<span data-ttu-id="444d9-244">Abyste mohli používat tuto funkci, musíte mít aktivní předplatné Experian.</span><span class="sxs-lookup"><span data-stu-id="444d9-244">To use this feature, you must have an active Experian subscription.</span></span>

<span data-ttu-id="444d9-245">Další informace viz [Rozšíření profilů zákazníků o demografické údaje společnosti Experian](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="444d9-245">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md)</span></span>


#### <a name="system-administration"></a><span data-ttu-id="444d9-246">správa systému,</span><span class="sxs-lookup"><span data-stu-id="444d9-246">System administration</span></span>

- <span data-ttu-id="444d9-247">**Podokno podrobností o úlohách**</span><span class="sxs-lookup"><span data-stu-id="444d9-247">**Task details pane**</span></span>

<span data-ttu-id="444d9-248">Podokno podrobností o úlohách umožňuje zobrazit podrobnosti o úlohách spouštěných systémem.</span><span class="sxs-lookup"><span data-stu-id="444d9-248">The task details pane enables you to see details about tasks that the system runs.</span></span> <span data-ttu-id="444d9-249">Je to užitečný způsob, jak identifikovat problémy s konfigurací a najít řešení.</span><span class="sxs-lookup"><span data-stu-id="444d9-249">It's a handy way to identify issues with the configuration and find solutions.</span></span>
<span data-ttu-id="444d9-250">Přečtením chybové zprávy zjistíte, jak řešit potenciální problémy.</span><span class="sxs-lookup"><span data-stu-id="444d9-250">Review the error messages see how you address potential issues.</span></span>
 
- <span data-ttu-id="444d9-251">**Zpracování informací přidáno na další stránky**</span><span class="sxs-lookup"><span data-stu-id="444d9-251">**Processing information added to more pages**</span></span>

<span data-ttu-id="444d9-252">Toto vylepšení přidává informace o stavu vašich entit na stránkách **Entity** a **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="444d9-252">This improvement adds information about the status of your entities on the **Entities** and **Customers** page.</span></span>
 
<span data-ttu-id="444d9-253">Na obou těchto stránkách navíc najdete podrobnosti o průběhu procesů a podrobnosti o úkolech.</span><span class="sxs-lookup"><span data-stu-id="444d9-253">Additionally, you can find details about the progress of processes, along with the task details, on both of these pages.</span></span>

- <span data-ttu-id="444d9-254">**Vylepšení stránky stavu systému**</span><span class="sxs-lookup"><span data-stu-id="444d9-254">**Improvements to system status page**</span></span>

<span data-ttu-id="444d9-255">Vylepšili jsme strukturu tabulky podrobností na stránce **Systém** > **Stav** při kontrole exportu dat.</span><span class="sxs-lookup"><span data-stu-id="444d9-255">We improved the structure of the status details table on **System** > **Status** when reviewing data exports.</span></span>
 
<span data-ttu-id="444d9-256">Navíc chyby ve sloupci **Podrobnosti** jsou nyní podrobnější a použitelnější.</span><span class="sxs-lookup"><span data-stu-id="444d9-256">Additionally, errors in the **Details** column are now more detailed and actionable.</span></span> 
 
- <span data-ttu-id="444d9-257">**Zrušení vrácení úlohy zpět do předchozího stavu**</span><span class="sxs-lookup"><span data-stu-id="444d9-257">**Cancel reverts job back to previous state**</span></span>

<span data-ttu-id="444d9-258">Když zrušíte úlohu, například během procesu párování, vrátí se zpět do předchozího stavu.</span><span class="sxs-lookup"><span data-stu-id="444d9-258">When you cancel a task, for example, in the match process, it will revert back to its latest state.</span></span> <span data-ttu-id="444d9-259">Například pokud byl proces párování dokončen včera a dnes jej zrušíte, vrátí se do včerejšího úspěšně dokončeného stavu.</span><span class="sxs-lookup"><span data-stu-id="444d9-259">For example, if the Match process completed yesterday and you cancel it today, it will revert to yesterday's successful state.</span></span>


## <a name="august-2020-updates"></a><span data-ttu-id="444d9-260">Aktualizace ze srpna 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-260">August 2020 updates</span></span>

<span data-ttu-id="444d9-261">Aktualizace ze srpna 2020 zahrnují několik funkcí, upgrady výkonu a opravy chyb.</span><span class="sxs-lookup"><span data-stu-id="444d9-261">The updates in August 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-august-2020"></a><span data-ttu-id="444d9-262">Nové a aktualizované funkce ze srpna 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-262">New and updated features in August 2020</span></span>

#### <a name="data-unification"></a><span data-ttu-id="444d9-263">Sjednocení dat</span><span class="sxs-lookup"><span data-stu-id="444d9-263">Data unification</span></span>

- <span data-ttu-id="444d9-264">**Vylepšené prostředí pro fázi mapy během sjednocení dat**</span><span class="sxs-lookup"><span data-stu-id="444d9-264">**Improved experience for the map stage during data unification**</span></span>

  <span data-ttu-id="444d9-265">Prostředí pro fázi mapy během procesu sjednocení dat vám umožní vybrat plynuleji vybrat entity, atributy a definovat sémantiku.</span><span class="sxs-lookup"><span data-stu-id="444d9-265">The experience to the map stage in the data unification process lets you select entities, attributes, and define semantics in a more seamless way.</span></span>

  <span data-ttu-id="444d9-266">Změny zahrnují:</span><span class="sxs-lookup"><span data-stu-id="444d9-266">The changes include:</span></span>
  
  - <span data-ttu-id="444d9-267">méně potřebných interakcí pro přidání entit a polí,</span><span class="sxs-lookup"><span data-stu-id="444d9-267">fewer interactions required to add entities and fields</span></span>
  - <span data-ttu-id="444d9-268">vylepšené možnosti vyhledávání na stránce mapy,</span><span class="sxs-lookup"><span data-stu-id="444d9-268">improved search capabilities on the map page</span></span>
  - <span data-ttu-id="444d9-269">vizuální a snadná identifikace navrhovaného typu pole.</span><span class="sxs-lookup"><span data-stu-id="444d9-269">visual and easy identification of the suggested field type</span></span>

#### <a name="enrichment"></a><span data-ttu-id="444d9-270">Obohacení</span><span class="sxs-lookup"><span data-stu-id="444d9-270">Enrichment</span></span>

- <span data-ttu-id="444d9-271">**Rozšíření afinit k zájmům jsou k dispozici na více trzích**</span><span class="sxs-lookup"><span data-stu-id="444d9-271">**Interest affinities enrichment available in more markets**</span></span>

  <span data-ttu-id="444d9-272">Rozšiřujeme dostupnost rozšíření afinit k zájmům mimo USA na pět dalších trhů: Kanada, Austrálie, Velká Británie, Francie a Německo.</span><span class="sxs-lookup"><span data-stu-id="444d9-272">We're extending the availability of the interest affinities enrichment beyond the United States to five other markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="444d9-273">S tímto rozšířením můžete rozšířit svá zákaznická data o další zájmy vztahující se na tyto trhy.</span><span class="sxs-lookup"><span data-stu-id="444d9-273">With this extension, you can enrich your customer data with more interests applicable to these markets.</span></span> <span data-ttu-id="444d9-274">Rovněž obohatíme profily vašich zákazníků na těchto trzích, použitím místních patentovaných dat z aplikace Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="444d9-274">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="444d9-275">Další informace viz [Obohacení profilů zákazníků afinitami značky a zájmů](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="444d9-275">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>


## <a name="july-2020-updates"></a><span data-ttu-id="444d9-276">Aktualizace z července 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-276">July 2020 updates</span></span>

<span data-ttu-id="444d9-277">Aktualizace v červenci 2020 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.</span><span class="sxs-lookup"><span data-stu-id="444d9-277">The updates in July 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-july-2020"></a><span data-ttu-id="444d9-278">Nové a aktualizované funkce v červenci 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-278">New and updated features in July 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="444d9-279">Rozšiřitelnost</span><span class="sxs-lookup"><span data-stu-id="444d9-279">Extensibility</span></span>

- <span data-ttu-id="444d9-280">Trigger **Power Automate pro dokončení procesu sjednocení**</span><span class="sxs-lookup"><span data-stu-id="444d9-280">**Power Automate trigger for completed unification process**</span></span>

  <span data-ttu-id="444d9-281">Rozšířili jsme triggery pro Power Automate a umožňujeme vám vytvořit oznámení nebo akci po dokončení aktualizace procesu sjednocení (mapa, shoda, sloučení).</span><span class="sxs-lookup"><span data-stu-id="444d9-281">We have extended our triggers for Power Automate and let you create a notification or action when a refresh of the unification process (map, match, merge) is completed.</span></span>    
  <span data-ttu-id="444d9-282">Další informace viz [Konektor Power Automate](export-power-automate.md)</span><span class="sxs-lookup"><span data-stu-id="444d9-282">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

#### <a name="enrichment"></a><span data-ttu-id="444d9-283">Obohacení</span><span class="sxs-lookup"><span data-stu-id="444d9-283">Enrichment</span></span>

- <span data-ttu-id="444d9-284">**Rozšíření afinit ke značkám jsou k dispozici na více trzích**</span><span class="sxs-lookup"><span data-stu-id="444d9-284">**Brand affinities enrichment available in more markets**</span></span>

  <span data-ttu-id="444d9-285">Rozšiřujeme dostupnost rozšíření afinit ke značkám mimo USA na pět dalších trhů: Kanada, Austrálie, Velká Británie, Francie a Německo.</span><span class="sxs-lookup"><span data-stu-id="444d9-285">We're extending the availability of the brand affinities enrichment beyond the United States to five other markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="444d9-286">Tímto rozšířením můžete na těchto trzích obohatit své zákaznické údaje o místní značky.</span><span class="sxs-lookup"><span data-stu-id="444d9-286">With this extension, you can enrich your customer data with local brands in these markets.</span></span> <span data-ttu-id="444d9-287">Rovněž obohatíme profily vašich zákazníků na těchto trzích, použitím místních patentovaných dat z aplikace Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="444d9-287">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="444d9-288">Další informace viz [Obohacení profilů zákazníků afinitami značky a zájmů](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="444d9-288">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>

## <a name="june-2020-updates"></a><span data-ttu-id="444d9-289">Aktualizace z června 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-289">June 2020 updates</span></span>

<span data-ttu-id="444d9-290">Aktualizace v červnu 2020 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.</span><span class="sxs-lookup"><span data-stu-id="444d9-290">The updates in June 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-june-2020"></a><span data-ttu-id="444d9-291">Nové a aktualizované funkce v červnu 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-291">New and updated features in June 2020</span></span>

#### <a name="enrichment"></a><span data-ttu-id="444d9-292">Rozšíření</span><span class="sxs-lookup"><span data-stu-id="444d9-292">Enrichment</span></span>

- <span data-ttu-id="444d9-293">**Rozšíření firemními údaji z Leadspace**</span><span class="sxs-lookup"><span data-stu-id="444d9-293">**Enrichment with company data from Leadspace**</span></span>
  
  <span data-ttu-id="444d9-294">Definujte pole ve sjednocených profilech zákazníků, které se používají k vyhledávání souvisejících dat společnosti z Leadspace.</span><span class="sxs-lookup"><span data-stu-id="444d9-294">Define fields in unified customer profiles that are used to look up related company data from Leadspace.</span></span> <span data-ttu-id="444d9-295">Po spuštění procesu rozšíření jsou profily B2B obohaceny o další atributy, včetně velikosti společnosti, jejího umístění a odvětví apod.</span><span class="sxs-lookup"><span data-stu-id="444d9-295">After running the enrichment process, B2B profiles are enriched with more attributes including company size, location, industry, and more.</span></span>    
  <span data-ttu-id="444d9-296">Tato spolupráce umožňuje zlepšit kvalitu vašich dat pomocí vstupů ze služeb třetích stran.</span><span class="sxs-lookup"><span data-stu-id="444d9-296">This collaboration allows you to improve the quality of your data with input from third-party services.</span></span> <span data-ttu-id="444d9-297">K použití tohoto rozšíření potřebujete licenci od Leadspace pro přístup k jejím firemním datům B2B.</span><span class="sxs-lookup"><span data-stu-id="444d9-297">To use this enrichment, you'll need a license from Leadspace to access its B2B company data.</span></span> <span data-ttu-id="444d9-298">Systém použije tuto licenci k průběžnému rozšiřování vašich dat.</span><span class="sxs-lookup"><span data-stu-id="444d9-298">The system will use that license to keep your data enriched continuously.</span></span>    
  <span data-ttu-id="444d9-299">Další informace viz [Obohacení profilů společnosti s Leadspace](enrichment-leadspace.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-299">For more information, see [Enrichment of company profiles with Leadspace](enrichment-leadspace.md).</span></span>

- <span data-ttu-id="444d9-300">**Stránka centra obohacení**</span><span class="sxs-lookup"><span data-stu-id="444d9-300">**Enrichment hub page**</span></span>

  <span data-ttu-id="444d9-301">Veškeré dostupné obohacení dat od poskytovatelů obohacování první a třetí strany se konfiguruje na stejném místě.</span><span class="sxs-lookup"><span data-stu-id="444d9-301">All available data enrichment from first- and third-party enrichment providers gets configured in the same place.</span></span> <span data-ttu-id="444d9-302">Konfigurace rozšiřování dat je plynulý zážitek, který je spravován z běžného místa.</span><span class="sxs-lookup"><span data-stu-id="444d9-302">Configuring data enrichment is a seamless experience that is managed from a common place.</span></span>    
  <span data-ttu-id="444d9-303">Další informace viz [rozšiřování pro profily zákazníků](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-303">For more information, see [Enrichment for customer profiles](enrichment-hub.md).</span></span>

- <span data-ttu-id="444d9-304">**Samostatné rozšíření o značku a zájmovou afinitu**</span><span class="sxs-lookup"><span data-stu-id="444d9-304">**Separate brand and interest affinity enrichment**</span></span>

  <span data-ttu-id="444d9-305">Afinity značky a zájmů jsou nyní k dispozici ve dvou nezávislých rozšířeních.</span><span class="sxs-lookup"><span data-stu-id="444d9-305">The brands and interests affinities are now available as two independent enrichments.</span></span> <span data-ttu-id="444d9-306">Oddělená rozšíření poskytují flexibilitu při konfiguraci a správě individuálně v závislosti na vašich obchodních požadavcích nebo potřebách.</span><span class="sxs-lookup"><span data-stu-id="444d9-306">Separated enrichments give you the flexibility to configure and manage them individually, depending on your business requirements or needs.</span></span>    
  <span data-ttu-id="444d9-307">Další informace viz [Rozšíření profilů zákazníků afinitami značky a zájmů](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="444d9-307">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="444d9-308">Rozšiřitelnost</span><span class="sxs-lookup"><span data-stu-id="444d9-308">Extensibility</span></span>

- <span data-ttu-id="444d9-309">**Adresy URL pro sjednocené aktivity v doplňku karty zákazníka Dynamics 365, na které lze klikat**</span><span class="sxs-lookup"><span data-stu-id="444d9-309">**Clickable URLs for unified activities on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="444d9-310">Sjednocené aktivity v doplňku zákaznické karty nyní zobrazují klikatelné adresy URL, pokud byly takové adresy URL definovány během konfigurace aktivit.</span><span class="sxs-lookup"><span data-stu-id="444d9-310">The unified activities in the Customer Card Add-in are now showing clickable URLs if such URLs have been defined during the configuration of activities.</span></span>    
  <span data-ttu-id="444d9-311">Další informace najdete v tématu [Doplněk karty zákazníka](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-311">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="444d9-312">**Afinity značky a zájmů dostupné v doplňku karty zákazníka Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="444d9-312">**Brand and interest affinities available on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="444d9-313">Nový ovládací prvek doplňku karty zákazníka Dynamics 365 vám umožní ukázat rozšíření o značku a zájem o vaše kontakty v aplikacích Customer Engagement Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="444d9-313">A new control on the Dynamics 365 Customer Card Add-in lets you show brand and interest enrichments on your contacts in customer engagement apps in Dynamics 365.</span></span>    
  <span data-ttu-id="444d9-314">Další informace najdete v tématu [Doplněk karty zákazníka](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-314">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="444d9-315">**Další triggery Power Automate**</span><span class="sxs-lookup"><span data-stu-id="444d9-315">**More Power Automate triggers**</span></span>

  <span data-ttu-id="444d9-316">Rozšířili jsme triggery Power Automate a přidali následující triggery:</span><span class="sxs-lookup"><span data-stu-id="444d9-316">We have extended our triggers for Power Automate and added the following triggers:</span></span>
  - <span data-ttu-id="444d9-317">Po dokončení automatického úplného obnovení (zdroje dat, sjednocení, segmenty, míry, export) si nechte zaslat oznámení nebo proveďte akci</span><span class="sxs-lookup"><span data-stu-id="444d9-317">Get a notification or perform an action when an automated full refresh (data sources, unification, segments, measures, exports) completes</span></span>
  - <span data-ttu-id="444d9-318">Definujte práh pro obchodní opatření.</span><span class="sxs-lookup"><span data-stu-id="444d9-318">Define a threshold for a business measure.</span></span> <span data-ttu-id="444d9-319">Můžete například vytvořit oznámení, které bude odesláno po překročení definované prahové hodnoty.</span><span class="sxs-lookup"><span data-stu-id="444d9-319">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span> <span data-ttu-id="444d9-320">Trigger navíc přináší informace, které vám umožní vytvářet složitější pracovní postupy v Power Automate.</span><span class="sxs-lookup"><span data-stu-id="444d9-320">Additionally, the trigger brings information that allows you to build more complex workflows in Power Automate.</span></span>    
  <span data-ttu-id="444d9-321">Další informace viz [Konektor Power Automate](export-power-automate.md)</span><span class="sxs-lookup"><span data-stu-id="444d9-321">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

- <span data-ttu-id="444d9-322">**Exportovat do programu Facebook Ads Manager**</span><span class="sxs-lookup"><span data-stu-id="444d9-322">**Export to Facebook Ads Manager**</span></span>
  
  <span data-ttu-id="444d9-323">Tato funkce umožňuje exportovat segmenty do služby Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="444d9-323">This capability lets you export segments to Facebook Ads Manager.</span></span> <span data-ttu-id="444d9-324">Segmenty se exportují jako vlastní cílové skupiny, aby bylo možné používat sjednocené profily v marketingových kampaních a reklamách na Facebooku.</span><span class="sxs-lookup"><span data-stu-id="444d9-324">Segments are exported as custom audiences to use unified customer profiles in Facebook marketing campaigns and ads.</span></span> <span data-ttu-id="444d9-325">Vlastní segmenty cílové skupiny lze také použít k vytváření kampaní na Instagramu prostřednictvím nástroje Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="444d9-325">The custom audiences are also usable to create campaigns on Instagram through Facebook Ads Manager.</span></span>    
  <span data-ttu-id="444d9-326">Další informace viz [Konektor pro Facebook Ads Manager](export-facebook.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-326">For more information, see [Connector for Facebook Ads Manager](export-facebook.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="444d9-327">Predikce</span><span class="sxs-lookup"><span data-stu-id="444d9-327">Predictions</span></span>

- <span data-ttu-id="444d9-328">**Predikce ukončení předplatného**</span><span class="sxs-lookup"><span data-stu-id="444d9-328">**Subscription churn prediction**</span></span>

  <span data-ttu-id="444d9-329">Postupujte podle řízené zkušenosti a vytvořte kanál predikce ztrát v oblastech předplatného, jako jsou cloudové služby, členství zákazníků a další sektory.</span><span class="sxs-lookup"><span data-stu-id="444d9-329">Follow a guided experience to create churn prediction in subscription areas like cloud services, customer membership, and other sectors.</span></span> 

  <span data-ttu-id="444d9-330">Funkce predikce ztrát předplatného vám umožňuje předvídat pravděpodobnost, že zákazník přestane používat produkty nebo služby založené na předplatném, aniž byste zapojili odborníka na data.</span><span class="sxs-lookup"><span data-stu-id="444d9-330">The subscription churn prediction feature enables you to predict the likelihood of a customer stopping the use of subscription-based products or services without engaging a data scientist.</span></span> <span data-ttu-id="444d9-331">Pomocí skóre predikce můžete kombinovat další informace o svých zákaznících a vytvářet segmenty s vysokým rizikem ztráty.</span><span class="sxs-lookup"><span data-stu-id="444d9-331">Using the prediction score, you can combine other information about your customers to create segments of high churn risk.</span></span> <span data-ttu-id="444d9-332">S pomocí tohoto segmentu můžete přímo cílit na zákazníky v oblasti marketingu, podpory zákazníků a dalších scénářů, abyste snížili riziko odlivu konkrétních zákazníků, abyste zvýšili výnosy a snížili náklady.</span><span class="sxs-lookup"><span data-stu-id="444d9-332">With the help of this segment, you can directly target customers in marketing, customer support, and other scenarios to reduce the risk of churn for specific customers to improve revenue and reduce cost.</span></span>

  <span data-ttu-id="444d9-333">V rámci prostředí můžete definovat definici ztrát jako časové okno specifické pro vaši firmu.</span><span class="sxs-lookup"><span data-stu-id="444d9-333">Within the experience, you can configure the definition of churn as a time-based window specific to your business.</span></span> <span data-ttu-id="444d9-334">Například firma zabývající se streamováním videa, která má měsíční předplatné, může předpokládat, že zákazníka ztratí 15 dní poté, co vyprší jeho předplatné.</span><span class="sxs-lookup"><span data-stu-id="444d9-334">For example, a video streaming business that has a monthly subscription process might want to consider a customer to have churned after 15 days after the expiration of their subscription.</span></span>

  <span data-ttu-id="444d9-335">Při pokračování v predikci vás provedeme potřebnými údaji a umožníme vám mapovat údaje o vaší firmě do polí potřebných k předvídání ztrát zákazníků.</span><span class="sxs-lookup"><span data-stu-id="444d9-335">As you continue through the prediction, we'll guide you through what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="444d9-336">S tím, jak se mění obchodní informace, můžete také nastavit plán, aby se v systému aktualizovaly nové informace a přizpůsobily se měnícím se obchodním okolnostem.</span><span class="sxs-lookup"><span data-stu-id="444d9-336">As business information changes, you can also set a schedule to retrain on new information in your system to adapt to changing business circumstances.</span></span>    
  <span data-ttu-id="444d9-337">Další informace viz [Predikce ukončení předplatného (náhled)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-337">For more information, see [Subscription churn prediction (preview)](predict-subscription-churn.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="444d9-338">Segmenty</span><span class="sxs-lookup"><span data-stu-id="444d9-338">Segments</span></span>

- <span data-ttu-id="444d9-339">**Najít podobné zákazníky**</span><span class="sxs-lookup"><span data-stu-id="444d9-339">**Find similar customers**</span></span>
  
  <span data-ttu-id="444d9-340">Najděte podobné zákazníky ve své zákaznické základně pomocí umělé inteligence.</span><span class="sxs-lookup"><span data-stu-id="444d9-340">Find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="444d9-341">Model binární klasifikace strojové učení přiřazuje skóre podobnosti zákazníkům v rozšířeném segmentu.</span><span class="sxs-lookup"><span data-stu-id="444d9-341">A binary classification machine learning model assigns a similarity score to customers in the expanded segment.</span></span> <span data-ttu-id="444d9-342">Skóre je založeno na podobnosti se zákazníky ve zdrojovém segmentu.</span><span class="sxs-lookup"><span data-stu-id="444d9-342">The score is based on the similarity to customers in the source segment.</span></span> <span data-ttu-id="444d9-343">V závislosti na skóre podobnosti se profily zákazníků přidávají do nově vytvořeného segmentu.</span><span class="sxs-lookup"><span data-stu-id="444d9-343">Depending on the similarity score, customer profiles are added to a newly created segment.</span></span>

  <span data-ttu-id="444d9-344">Někdy se v digitálním marketingu označuje jako lookalike modeling, používá model AI, aby pomohl najít zákazníky, kteří jsou podobní jinému segmentu vašich zákazníků, tím, že zohlední více atributů.</span><span class="sxs-lookup"><span data-stu-id="444d9-344">Sometimes referred to as lookalike modeling in digital marketing, it uses an AI model to help find customers who are similar to another segment of your customers by factoring in more attributes.</span></span> <span data-ttu-id="444d9-345">Umožňuje vám nejen vybrat atributy, ale také určit maximální počet zákazníků, kteří by měli být v tomto novém segmentu.</span><span class="sxs-lookup"><span data-stu-id="444d9-345">It not only allows you to pick the attributes but also allows you to specify the maximum number of customers who should be in this new segment.</span></span> <span data-ttu-id="444d9-346">Model AI poté vypočítá skóre podobnosti pro každého zákazníka na základě vybraných atributů a vyhledá zákazníky s vyšším průměrným skóre podobnosti.</span><span class="sxs-lookup"><span data-stu-id="444d9-346">The AI model will then compute similarity scores for each customer based on your selected attributes and find customers with the higher average similarity score.</span></span> <span data-ttu-id="444d9-347">Výsledný segment bude zahrnovat zákazníky, kteří vypadají podobně jako zákazníci ve vašem původním segmentu.</span><span class="sxs-lookup"><span data-stu-id="444d9-347">The resulting segment will include customers who look similar to the customer in your original segment.</span></span>    
  <span data-ttu-id="444d9-348">Další informace naleznete v článku [Podobní zákazníci](find-similar-customer-segments.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-348">For more information, see [Similar Customers](find-similar-customer-segments.md).</span></span>

- <span data-ttu-id="444d9-349">**Překrytí a diferenciátory segmentu**</span><span class="sxs-lookup"><span data-stu-id="444d9-349">**Segment overlap and differentiators**</span></span>

  <span data-ttu-id="444d9-350">Překrývání segmentů vám umožní zjistit, kolik a kteří zákazníci jsou společní pro dva nebo více segmentů.</span><span class="sxs-lookup"><span data-stu-id="444d9-350">Segment overlap lets you see how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="444d9-351">Například to, jak se segment s vysokými výdaji překrývá se segmentem zákazníků s vysokou spokojeností, nebo jak se segment v oblasti zákazníků překrývá se segmentem zákazníků s nízkou spokojeností.</span><span class="sxs-lookup"><span data-stu-id="444d9-351">For example, how a high-spenders segment overlaps with a high-satisfaction customers segment or how a churning customer segment overlaps with a low-satisfaction customers segment.</span></span> <span data-ttu-id="444d9-352">Kromě toho můžete analyzovat, jak se překrývání mění na základě zvláštního atributu podle vašeho výběru.</span><span class="sxs-lookup"><span data-stu-id="444d9-352">Additionally, you can analyze how the overlap changes based on an extra attribute of your choice.</span></span>

  <span data-ttu-id="444d9-353">Diferenciátory segmentů odhalují, co odlišuje jeden segment od zbytku vašich zákazníků nebo od jiného segmentu.</span><span class="sxs-lookup"><span data-stu-id="444d9-353">Segment differentiators reveal what differentiates one segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="444d9-354">Vše, co musíte udělat, je identifikovat segment a systém identifikuje atributy profilu a opatření, která odlišují segment ve formě seřazeného seznamu diferenciátorů - od nejsilnějšího diferenciátoru k nejslabšímu.</span><span class="sxs-lookup"><span data-stu-id="444d9-354">All you need to do is identify a segment and the system will identify profile attributes and measures that distinguish the segment in the form of a ranked list of differentiators—from the strongest differentiator to the weakest.</span></span>    
  <span data-ttu-id="444d9-355">Další informace viz [Přehled segmentů (náhled)](segment-insights.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-355">For more information, see [Segment insights (preview)](segment-insights.md).</span></span>

- <span data-ttu-id="444d9-356">**Životnost segmentu**</span><span class="sxs-lookup"><span data-stu-id="444d9-356">**Segment lifetime**</span></span>
  
  <span data-ttu-id="444d9-357">Definujte plán pro aktivaci nebo deaktivaci segmentu.</span><span class="sxs-lookup"><span data-stu-id="444d9-357">Define a schedule to activate or deactivate a segment.</span></span>    
  <span data-ttu-id="444d9-358">Další informace získáte v tématu [Správa existujících segmentů](segments.md#manage-existing-segments).</span><span class="sxs-lookup"><span data-stu-id="444d9-358">For more information, see [Manage existing segments](segments.md#manage-existing-segments).</span></span>

## <a name="may-2020-updates"></a><span data-ttu-id="444d9-359">Aktualizace z května 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-359">May 2020 updates</span></span>

<span data-ttu-id="444d9-360">Aktualizace v květnu 2020 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.</span><span class="sxs-lookup"><span data-stu-id="444d9-360">The updates in May 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-may-2020"></a><span data-ttu-id="444d9-361">Nové a aktualizované funkce v květnu 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-361">New and updated features in May 2020</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="444d9-362">Příjem dat</span><span class="sxs-lookup"><span data-stu-id="444d9-362">Data ingestion</span></span>

- <span data-ttu-id="444d9-363">**Příjem dat v reálném čase: zobrazení historie**</span><span class="sxs-lookup"><span data-stu-id="444d9-363">**Real-time data ingestion: history views**</span></span>

  <span data-ttu-id="444d9-364">Při použití našeho rozhraní API k přijímání aktualizací v reálném čase můžete zobrazit až 30 dnů agregované historie těchto aktualizací.</span><span class="sxs-lookup"><span data-stu-id="444d9-364">When using our API to ingest real-time updates, you can see up to 30 days of aggregated history for these updates.</span></span> <span data-ttu-id="444d9-365">Máte přístup k agregacím všech úspěšných nebo neúspěšných volání rozhraní API, včetně jejich výsledku, zdrojového systému a dalších užitečných metadat.</span><span class="sxs-lookup"><span data-stu-id="444d9-365">You have access to aggregates of all successful or failed API calls including their outcome, source system, and other useful metadata.</span></span>    
  <span data-ttu-id="444d9-366">Další informace viz [Příjem dat v reálném čase](real-time-data-ingestion.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-366">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="444d9-367">**Příjem dat v reálném čase: aktualizace profilů**</span><span class="sxs-lookup"><span data-stu-id="444d9-367">**Real-time data ingestion: profile updates**</span></span>

  <span data-ttu-id="444d9-368">Toto rozšíření přijímání dat v reálném čase umožňuje během několika sekund zobrazit změny v konkrétních polích uživatelského profilu.</span><span class="sxs-lookup"><span data-stu-id="444d9-368">This extension of the real-time data ingestion lets you see, within seconds, changes to specific user profile fields.</span></span>    
  <span data-ttu-id="444d9-369">Kromě funkcí pro aktivity v reálném čase podporuje systém aktualizace polí profilů s nízkou latencí.</span><span class="sxs-lookup"><span data-stu-id="444d9-369">In addition to the real-time functionality for activities, the system supports low latency updates to profile fields.</span></span> <span data-ttu-id="444d9-370">Aktualizace polí profilů v reálném čase mají čas vypršení platnosti, a proto nenahrazují plánované aktualizace.</span><span class="sxs-lookup"><span data-stu-id="444d9-370">Real-time updates for profile fields have an expiration time and are therefore not a replacement for scheduled refreshes.</span></span>    
  <span data-ttu-id="444d9-371">Další informace viz [Příjem dat v reálném čase](real-time-data-ingestion.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-371">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="444d9-372">Rozšiřitelnost</span><span class="sxs-lookup"><span data-stu-id="444d9-372">Extensibility</span></span>

- <span data-ttu-id="444d9-373">**Aktualizovaná časová osa a stránkování v řešení Doplněk karty zákazníka**</span><span class="sxs-lookup"><span data-stu-id="444d9-373">**Updated timeline and pagination on the Customer Card Add-in**</span></span>

  <span data-ttu-id="444d9-374">Časová osa řešení doplňku zákaznické karty odpovídá časové ose aktivit.</span><span class="sxs-lookup"><span data-stu-id="444d9-374">The timeline of the Customer Card Add-in solution matches the activity timeline.</span></span> <span data-ttu-id="444d9-375">Stránkování časové osy se zlepšilo a nyní zobrazuje až 50 aktivit najednou.</span><span class="sxs-lookup"><span data-stu-id="444d9-375">The pagination of the timeline improved, showing up to 50 activities at once.</span></span> <span data-ttu-id="444d9-376">Umožňuje také načíst více aktivit na časovou osu.</span><span class="sxs-lookup"><span data-stu-id="444d9-376">It also allows loading more activities in the timeline.</span></span>    
  <span data-ttu-id="444d9-377">Další informace najdete v tématu [Doplněk karty zákazníka](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-377">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="444d9-378">**Mění se trigger Power Automate pro segmenty**</span><span class="sxs-lookup"><span data-stu-id="444d9-378">**Power Automate trigger for segment changes**</span></span>

  <span data-ttu-id="444d9-379">Triggery pro Power Automate definují, z čeho můžete vytvořit tok.</span><span class="sxs-lookup"><span data-stu-id="444d9-379">Triggers for Power Automate define what you can build a flow from.</span></span> <span data-ttu-id="444d9-380">Nově přidaný trigger vám umožní definovat prahovou hodnotu pro segment.</span><span class="sxs-lookup"><span data-stu-id="444d9-380">The newly added trigger lets you define a threshold for a segment.</span></span> <span data-ttu-id="444d9-381">Můžete například vytvořit oznámení, které bude odesláno po překročení definované prahové hodnoty.</span><span class="sxs-lookup"><span data-stu-id="444d9-381">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span>    
  <span data-ttu-id="444d9-382">Další informace viz [Konektor Power Automate](export-power-automate.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-382">For more information, see [Power Automate connector](export-power-automate.md).</span></span>

- <span data-ttu-id="444d9-383">**Podpora více klientů pro vlastní modely**</span><span class="sxs-lookup"><span data-stu-id="444d9-383">**Multitenant support for custom models**</span></span>

  <span data-ttu-id="444d9-384">Nakonfigurujte pracovní postupy pro vlastní modely pomocí webové služby jiného klienta Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="444d9-384">Configure workflows for custom models with a web service of a different Azure Machine Learning tenant.</span></span> <span data-ttu-id="444d9-385">Při vytváření nového pracovního postupu pro vlastní modely se můžete přihlásit do klienta Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="444d9-385">You can sign in to the Azure Machine Learning tenant when creating a new workflow for custom models.</span></span> <span data-ttu-id="444d9-386">Tato funkce je doplňkem stávající funkce integrace s vaší vlastní webovou službou Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="444d9-386">This capability is an addition to the existing capability of integrating with your own custom Azure Machine Learning web service.</span></span>    
  <span data-ttu-id="444d9-387">Další informace viz [Vlastní modely strojového učení](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-387">For more information, see [Custom machine learning models](custom-models.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="444d9-388">Segmenty</span><span class="sxs-lookup"><span data-stu-id="444d9-388">Segments</span></span>

- <span data-ttu-id="444d9-389">**Automatizace cesty entity**</span><span class="sxs-lookup"><span data-stu-id="444d9-389">**Entity path automation**</span></span>

  <span data-ttu-id="444d9-390">Při vytváření segmentu musí uživatelé definovat cestu k entitě.</span><span class="sxs-lookup"><span data-stu-id="444d9-390">When creating a segment, users need to define the entity path.</span></span> <span data-ttu-id="444d9-391">Tato funkce provede první krok k automatizaci definice cesty entity, takže se můžete soustředit na kritéria segmentace, která máte na mysli.</span><span class="sxs-lookup"><span data-stu-id="444d9-391">This capability takes a first step at automating the entity path definition so you can focus on the segmentation criteria that you have in mind.</span></span>    
  <span data-ttu-id="444d9-392">Pokud entita, podle které chcete segmentovat své zákazníky, přímo souvisí s entitou sjednoceného zákazníka, již nemusíte definovat cestu entity.</span><span class="sxs-lookup"><span data-stu-id="444d9-392">If the entity by which you want to segment your customers is directly related to the unified customer entity, you won't need to define the entity path anymore.</span></span> <span data-ttu-id="444d9-393">Pokud však existuje více než jedna cesta k entitě, je třeba ji definovat ručně.</span><span class="sxs-lookup"><span data-stu-id="444d9-393">However, if there is more than one possible entity path, you still need to define it manually.</span></span>

- <span data-ttu-id="444d9-394">**Akce na více segmentech**</span><span class="sxs-lookup"><span data-stu-id="444d9-394">**Actions on multiple segments**</span></span>
  
  <span data-ttu-id="444d9-395">Uživatelé si mohou vybrat více segmentů a jedním kliknutím s nimi provádět akce, například je aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="444d9-395">Users can select multiple segments and take actions on them, like refreshing the segments, with a single click.</span></span>    

- <span data-ttu-id="444d9-396">**Aktualizovat segmenty**</span><span class="sxs-lookup"><span data-stu-id="444d9-396">**Refresh segments**</span></span>

  <span data-ttu-id="444d9-397">Uživatelé mohou aktualizovat jediný segment nebo vybrat pouze segmenty, které chtějí aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="444d9-397">Users can refresh a single segment or select only the segments they want to refresh.</span></span>    

  
- <span data-ttu-id="444d9-398">**Vylepšení složených segmentů**</span><span class="sxs-lookup"><span data-stu-id="444d9-398">**Improvements to compounded segments**</span></span>

  <span data-ttu-id="444d9-399">Uživatelé mohou vytvářet, upravovat a odstraňovat segmenty založené na jiných segmentech.</span><span class="sxs-lookup"><span data-stu-id="444d9-399">Users can create, edit, and delete segments that are based on other segments.</span></span> <span data-ttu-id="444d9-400">Například segment vytvořený na jiném segmentu, který byl vytvořen na třetím segmentu.</span><span class="sxs-lookup"><span data-stu-id="444d9-400">For example, a segment constructed on another segment that was constructed on a third segment.</span></span>    

- <span data-ttu-id="444d9-401">**Stránka se seznamem segmentů**</span><span class="sxs-lookup"><span data-stu-id="444d9-401">**Segment list page**</span></span>

  <span data-ttu-id="444d9-402">Nový design stránky segmentů používá formát seznamu, který umožňuje zobrazit více segmentů najednou.</span><span class="sxs-lookup"><span data-stu-id="444d9-402">The new design of the segments page uses a list format that lets you see more segments at once.</span></span> <span data-ttu-id="444d9-403">Pro rychlé nalezení segmentů je přidáno vyhledávací pole.</span><span class="sxs-lookup"><span data-stu-id="444d9-403">A search field is added to find segments quickly.</span></span> <span data-ttu-id="444d9-404">Uživatelé mohou nyní provádět akce, jako je stahování nebo odstraňování, na více segmentech najednou.</span><span class="sxs-lookup"><span data-stu-id="444d9-404">Users can now apply actions like downloading or deleting on multiple segments at once.</span></span> <span data-ttu-id="444d9-405">Je zavedena nová funkce trendů pro rychlou identifikaci významných změn v segmentech.</span><span class="sxs-lookup"><span data-stu-id="444d9-405">A new trend experience is introduced to quickly identify significant changes on segments.</span></span>    
  <span data-ttu-id="444d9-406">Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-406">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="444d9-407">správa systému,</span><span class="sxs-lookup"><span data-stu-id="444d9-407">System administration</span></span>

- <span data-ttu-id="444d9-408">**Řešení Customer Insights dostupné v Microsoft Dynamics 365 Online Government**</span><span class="sxs-lookup"><span data-stu-id="444d9-408">**Customer Insights available in Microsoft Dynamics 365 Online Government**</span></span>

  <span data-ttu-id="444d9-409">S více a více kanály pro interakce jsou údaje o občanech rozptýleny v nesčetných systémech, což vede ke skladování velkých objemů dat a roztříštěnému zobrazení informací o interakcích občanů.</span><span class="sxs-lookup"><span data-stu-id="444d9-409">With more and more channels for interactions, citizen data is scattered across myriad systems, leading to siloed data, and a fragmented view of information about citizen interactions.</span></span> <span data-ttu-id="444d9-410">Bez úplného zobrazení interakcí každého občana napříč kanály je nemožné, aby se vlády modernizovaly v potřebném měřítku.</span><span class="sxs-lookup"><span data-stu-id="444d9-410">Without a complete view of each citizen's interactions across channels, it's impossible for governments to modernize at scale.</span></span> <span data-ttu-id="444d9-411">Společnost Microsoft je odhodlána podporovat technologické potřeby vlády, aby udržovala krok s očekáváním občanů ohledně konzistence a pohotovosti.</span><span class="sxs-lookup"><span data-stu-id="444d9-411">Microsoft is committed to supporting the technology needs of government to keep up with citizen expectations for consistent and responsive experiences.</span></span>    
  <span data-ttu-id="444d9-412">S 1. vlnou vydání v r. 2020 bude Dynamics 365 Customer Insights k dispozici pro cloud komunity státní správy (GCC), což je prostředí vytvořené pro naplnění vyšších požadavků státních úřadů Spojených států na dodržování předpisů.</span><span class="sxs-lookup"><span data-stu-id="444d9-412">With 2020 release wave 1, Dynamics 365 Customer Insights will be available for the Government Community Cloud (GCC), an environment built to meet the higher compliance needs of United States government agencies.</span></span> <span data-ttu-id="444d9-413">Úřady získají sjednocené zobrazení občanů a využijí předdefinovanou umělou inteligenci k získávání poznatků, které zlepšují interakce, posilují zaměstnance a transformují komunity, a zároveň snižují složitost IT a splňují normy a bezpečnostní standardy Spojených států.</span><span class="sxs-lookup"><span data-stu-id="444d9-413">Agencies gain a unified view of citizens and use prebuilt AI to derive insights that improve interactions, empower employees, and transform communities, while reducing IT complexity and meeting United States compliance and security standards.</span></span> <span data-ttu-id="444d9-414">Dynamics 365 Government splňuje náročné požadavky programu Federal Risk and Authorization Management Program (FedRAMP), což federálním úřadům Spojených států umožňuje využívat úspory nákladů a přísné zabezpečení cloudu Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="444d9-414">Dynamics 365 Government meets the demanding requirements of the US Federal Risk and Authorization Management Program (FedRAMP), enabling United States federal agencies to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

## <a name="april-2020-updates"></a><span data-ttu-id="444d9-415">Aktualizace z dubna 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-415">April 2020 updates</span></span>

<span data-ttu-id="444d9-416">Aktualizace v dubnu 2020 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.</span><span class="sxs-lookup"><span data-stu-id="444d9-416">The updates in April 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-april-2020"></a><span data-ttu-id="444d9-417">Nové a aktualizované funkce v dubnu 2020</span><span class="sxs-lookup"><span data-stu-id="444d9-417">New and updated features in April 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="444d9-418">Aktivity</span><span class="sxs-lookup"><span data-stu-id="444d9-418">Activities</span></span>

- <span data-ttu-id="444d9-419">**Mapování entity aktivity na standardní typ aktivity**</span><span class="sxs-lookup"><span data-stu-id="444d9-419">**Map activity entity to standard activity type**</span></span>
  
  <span data-ttu-id="444d9-420">Konfigurace aktivity a úložiště jsou v současné době založeny na statickém návrhu, který umožňuje jejich zobrazení na časové ose.</span><span class="sxs-lookup"><span data-stu-id="444d9-420">Activity configuration and storage are currently based on a static design to view them in a timeline.</span></span> <span data-ttu-id="444d9-421">Sémantický význam aktivit, které mají potenciál pro vícenásobné použití v případech v AI modelech, není v současné době plně využíván.</span><span class="sxs-lookup"><span data-stu-id="444d9-421">The semantic meaning of activities, which has potential for multiple use-cases in AI models, isn't fully used at the moment.</span></span> <span data-ttu-id="444d9-422">Plánujeme zlepšit dynamiku časové osy aktivit na základě typu aktivity a lepšího sémantického porozumění aktivitám.</span><span class="sxs-lookup"><span data-stu-id="444d9-422">We plan to make the activity timeline more dynamic, based on the activity type and better semantic understanding of the activities.</span></span> <span data-ttu-id="444d9-423">Cílem této funkce je identifikovat typ aktivity, jak je definován ve schématu Common Data Model, pro každou přijatou aktivitu.</span><span class="sxs-lookup"><span data-stu-id="444d9-423">This feature aims to identify the activity type as defined in Common Data Model for any ingested activity.</span></span>
  <span data-ttu-id="444d9-424">Další informace najdete v tématu [Aktivity zákazníka](activities.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-424">For more information, see [Customer activities](activities.md).</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="444d9-425">Příjem dat</span><span class="sxs-lookup"><span data-stu-id="444d9-425">Data ingestion</span></span>

- <span data-ttu-id="444d9-426">**Příjem dat v reálném čase: aktivity**</span><span class="sxs-lookup"><span data-stu-id="444d9-426">**Real-time data ingestion: activities**</span></span>
  
  <span data-ttu-id="444d9-427">Příjem dat v reálném čase poskytuje data okamžitě ke spotřebě, dokud následující naplánovaná aktualizace nevytáhne tato data ze zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="444d9-427">Real-time data ingestion provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>    
  <span data-ttu-id="444d9-428">Další informace viz [Příjem dat v reálném čase](real-time-data-ingestion.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-428">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="444d9-429">**Vylepšení přípravy dat**</span><span class="sxs-lookup"><span data-stu-id="444d9-429">**Improvements to data preparation**</span></span>
  
  <span data-ttu-id="444d9-430">Další informace o datech přijatých v entitě.</span><span class="sxs-lookup"><span data-stu-id="444d9-430">Learn more about the data ingested in an entity.</span></span> <span data-ttu-id="444d9-431">Pomocí souhrnu údajů můžete porozumět charakteristikám kvality dat, což může pomoci podniknout příslušné kroky.</span><span class="sxs-lookup"><span data-stu-id="444d9-431">With the data summary, you can understand the data quality characteristics that can help to take appropriate action.</span></span>    
  <span data-ttu-id="444d9-432">Další informace naleznete v článku [Zkoumání dat entity](entities.md#exploring-a-specific-entitys-data).</span><span class="sxs-lookup"><span data-stu-id="444d9-432">For more information, see [Explore entity data](entities.md#exploring-a-specific-entitys-data).</span></span>

- <span data-ttu-id="444d9-433">**Příjem analytických dat z Dynamics 365 pomocí Common Data Service**</span><span class="sxs-lookup"><span data-stu-id="444d9-433">**Ingest analytical data from Dynamics 365 with Common Data Service**</span></span>
  
  <span data-ttu-id="444d9-434">Common Data Service je k dispozici jako způsob vytváření zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="444d9-434">Common Data Service is available as a way to create data sources.</span></span> <span data-ttu-id="444d9-435">Stávající zákazníci Dynamics 365 mohou přijímat analytické entity z Common Data Service do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="444d9-435">Existing Dynamics 365 customers can ingest analytical entities from Common Data Service to Customer Insights.</span></span> <span data-ttu-id="444d9-436">Jeden zdroj dat může současně používat totéž spravované jezero Common Data Service v prostředí Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="444d9-436">A single data source can simultaneously use the same Common Data Service-managed lake in a Customer Insights environment.</span></span>    
  <span data-ttu-id="444d9-437">Další informace viz [Připojení k datům v datovém jezeru spravovaném systémem Common Data Service](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-437">For more information, see [Connect to data in a Common Data Service managed data lake](connect-common-data-service-lake.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="444d9-438">Rozšiřitelnost</span><span class="sxs-lookup"><span data-stu-id="444d9-438">Extensibility</span></span>

- <span data-ttu-id="444d9-439">**Export do LiveRamp**</span><span class="sxs-lookup"><span data-stu-id="444d9-439">**Export to LiveRamp**</span></span>

  <span data-ttu-id="444d9-440">Aktivujte data v LiveRamp® a propojte se s více než 500 platformami napříč digitálními, sociálními a televizními ekosystémy.</span><span class="sxs-lookup"><span data-stu-id="444d9-440">Activate your data in LiveRamp® to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="444d9-441">Využijte své údaje ve službě LiveRamp k cílení, potlačování a personalizaci reklamních kampaní.</span><span class="sxs-lookup"><span data-stu-id="444d9-441">Use your data in LiveRamp for targeting, suppressing, and personalizing ad campaigns.</span></span>    
  <span data-ttu-id="444d9-442">Další informace viz [Konektor LiveRamp&reg;](export-liveramp.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-442">For more information, see [LiveRamp&reg; connector](export-liveramp.md).</span></span>

- <span data-ttu-id="444d9-443">**Doplněk Teams pro Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="444d9-443">**Customer Insights Teams Add-in**</span></span>
  
  <span data-ttu-id="444d9-444">Bot poskytuje možnosti vyhledávání pro jednotné profily zákazníků.</span><span class="sxs-lookup"><span data-stu-id="444d9-444">The bot provides lookup capabilities for unified customer profiles.</span></span> <span data-ttu-id="444d9-445">Zobrazí kartu s až 15 poli z výsledného zákaznického profilu.</span><span class="sxs-lookup"><span data-stu-id="444d9-445">It will show a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="444d9-446">Více shod vrátí seznam výsledků, kde si můžete vybrat profil.</span><span class="sxs-lookup"><span data-stu-id="444d9-446">Multiple matches return a list of results where you can select a profile.</span></span>    
  <span data-ttu-id="444d9-447">Další informace viz [Robot Teams pro Customer Insights](export-teams-bot.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-447">For more information, see [Teams bot for Customer Insights](export-teams-bot.md).</span></span>

#### <a name="measures"></a><span data-ttu-id="444d9-448">Míry</span><span class="sxs-lookup"><span data-stu-id="444d9-448">Measures</span></span>

- <span data-ttu-id="444d9-449">**Stránka se seznamem měr**</span><span class="sxs-lookup"><span data-stu-id="444d9-449">**Measure list page**</span></span>
  
  <span data-ttu-id="444d9-450">Vylepšení na stránce měr zahrnují podporu akcí pro jednu míru a pro více měr najednou.</span><span class="sxs-lookup"><span data-stu-id="444d9-450">Improvements to the measures page include support for actions on a single measure and on multiple measures at once.</span></span> <span data-ttu-id="444d9-451">Kromě toho najdete vyhledávací pole pro rychlé vyhledání a sledování měr.</span><span class="sxs-lookup"><span data-stu-id="444d9-451">Additionally, you'll find a search field to find and track measures quickly.</span></span>    
  <span data-ttu-id="444d9-452">Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-452">For more information, see [Create and manage segments](segments.md).</span></span>

- <span data-ttu-id="444d9-453">**Vylepšení složených měr**</span><span class="sxs-lookup"><span data-stu-id="444d9-453">**Improvements to compounded measures**</span></span>
  
  <span data-ttu-id="444d9-454">Uživatelé mohou vytvářet, upravovat a odstraňovat míry založené na jiných mírách.</span><span class="sxs-lookup"><span data-stu-id="444d9-454">Users can create, edit, and delete measures that are based on other measures.</span></span> <span data-ttu-id="444d9-455">Například míra vytvořená na jiné míře, která byla vytvořena na třetí míře.</span><span class="sxs-lookup"><span data-stu-id="444d9-455">For example, a measure constructed on another measure that was constructed on a third measure.</span></span>

#### <a name="segments"></a><span data-ttu-id="444d9-456">Segmenty</span><span class="sxs-lookup"><span data-stu-id="444d9-456">Segments</span></span>

- <span data-ttu-id="444d9-457">**Další operátor**</span><span class="sxs-lookup"><span data-stu-id="444d9-457">**Another operator**</span></span>
  
  <span data-ttu-id="444d9-458">Operátor množiny In umožňuje segmentaci zákazníků podle několika možných hodnot řetězce.</span><span class="sxs-lookup"><span data-stu-id="444d9-458">The In-set operator allows segmentation for customers by several possible string values.</span></span> <span data-ttu-id="444d9-459">Než byl tento operátor přidán, museli jste zkonstruovat takové segmenty s více podmínkami OR.</span><span class="sxs-lookup"><span data-stu-id="444d9-459">Before this operator was added, you had to construct such segments with multiple OR conditions.</span></span> <span data-ttu-id="444d9-460">Operátor množiny In vám to umožňuje s jedinou podmínkou.</span><span class="sxs-lookup"><span data-stu-id="444d9-460">The In-set operator lets you do that with a single condition.</span></span>    
  <span data-ttu-id="444d9-461">Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-461">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="444d9-462">správa systému,</span><span class="sxs-lookup"><span data-stu-id="444d9-462">System administration</span></span>

- <span data-ttu-id="444d9-463">**Kopírování nastavení konfigurace do nového prostředí**</span><span class="sxs-lookup"><span data-stu-id="444d9-463">**Copy configuration settings to a new environment**</span></span>
  
  <span data-ttu-id="444d9-464">Zkopírujte svou konfiguraci z jednoho prostředí do jiného.</span><span class="sxs-lookup"><span data-stu-id="444d9-464">Copy your configuration from one environment to another.</span></span> <span data-ttu-id="444d9-465">Při vytváření nového prostředí můžete vybrat existující prostředí, ze kterého chcete kopírovat konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="444d9-465">While creating a new environment, you can select an existing environment you want to copy the configuration from.</span></span> <span data-ttu-id="444d9-466">V současné době podporujeme zdroje dat, sjednocení dat, vztahy, míry a segmenty, které mají být zkopírovány.</span><span class="sxs-lookup"><span data-stu-id="444d9-466">We currently support data sources, data unification, relationships, measures, and segments to be copied.</span></span> <span data-ttu-id="444d9-467">Nekopírují se přihlašovací údaje zdroje dat a samotná data.</span><span class="sxs-lookup"><span data-stu-id="444d9-467">Data source credentials and actual data aren't copied.</span></span>    
  <span data-ttu-id="444d9-468">Další informace naleznete v tématu [Správa prostředí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="444d9-468">For more information, see [Manage environments](manage-environments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]