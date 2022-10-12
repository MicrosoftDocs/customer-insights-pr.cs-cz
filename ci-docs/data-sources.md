---
title: Přehled zdrojů dat
description: Naučte se importovat nebo ingestovat data z různých zdrojů.
ms.date: 09/29/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610044"
---
# <a name="data-sources-overview"></a>Přehled zdrojů dat

Dynamics 365 Customer Insights poskytuje připojení k přinesení dat ze široké škály zdrojů. Připojení k zdroji dat se často označuje jako proces *příjmu dat*. Po přijetí dat můžete [sjednotit](data-unification.md), generovat statistiky a aktivovat data pro vytváření personalizovaných zážitků.

## <a name="add-or-edit-data-sources"></a>Přidání nebo úprava zdrojů dat

Do Customer Insights můžete připojit nebo importovat zdroje dat. Níže uvedené odkazy poskytují pokyny k přidávání a úpravám zdrojů dat.

**Připojit zdroj dat**

Pokud máte data připravená v jedné z datových služeb Azure od společnosti Microsoft, Customer Insights se mohou snadno připojit k zdroj dat, aniž byste museli data znovu přijímat. Vyberte jednu z následujících možností:
- [Azure Data Lake Storage (soubory csv nebo Parquet ve složce Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics (databáze Lake)](connect-synapse.md)
- [Datové jezero Microsoft Dataverse](connect-dataverse-managed-lake.md)

**Importovat a transformovat**

Pokud používáte místní zdroje dat, Microsoft nebo data třetích stran, importujte a transformujte data pomocí konektorů Power Query.
- [Konektory Power Query](connect-power-query.md)

## <a name="review-data-sources"></a>Zkontrolovat zdroje dat

Pokud bylo vaše prostředí nakonfigurováno pro použití úložiště Customer Insights a používáte místní zdroje dat, použijete datové toky Power Platform. S datovými toky Power Platform můžete zobrazit sdílené zdroje dat a zdroje dat spravované ostatními. Stránka **Zdroje dat** uvádí zdroje dat ve třech částech:
- **Sdílené**: Zdroje dat, které mohou spravovat všichni správci Customer Insights. Příklady sdílených zdrojů dat jsou toky dat Power Platform, váš vlastní účet úložiště nebo připojení k datovému jezeru spravovanému pomocí Dataverse.
- **Spravováno mnou**: Datové toky Power Platform, které můžete spravovat pouze vy. Ostatní správci Customer Insights mohou tyto toky dat pouze zobrazit, ale nemohou je upravovat, aktualizovat ani odstraňovat.
- **Spravováno ostatními**: Toky dat Power Platform vytvořené jinými správci. Můžete je pouze zobrazovat. Uvádí vlastníka toku dat, kterého lze kontaktovat s žádostí o pomoc.
> [!NOTE]
> Všechny entity mohou zobrazovat a používat ostatní uživatelé. Zatímco zdroje dat vlastní uživatel, který je vytvořil, výsledné entity z příjmu dat může použít každý uživatel Customer Insights.

Pokud vaše prostředí nepoužívá datové toky Power Platform, strýnja **Zdroje dat** obsahuje pouze seznam všech zdrojů dat. Nezobrazují se žádné sekce.

## <a name="manage-existing-data-sources"></a>Správa existujících zdrojů dat

Jděte na **Data** > **Zdroje dat** pro zobrazení názvu každého zpracovaného zdroj dat, jeho stavu a poslední aktualizace dat pro daný zdroj. Seznam zdrojů dat můžete seřadit podle libovolného sloupce nebo pomocí vyhledávacího pole najít zdroj dat, který chcete spravovat.

Výběrem zdroje dat zobrazíte dostupné akce.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Přidaný zdroj dat.":::

- [**Úpravou**](#add-or-edit-data-sources) zdroje dat změníte jeho vlastnosti.
- [**Aktualizací**](#refresh-data-sources) zdroje dat zahrnete nejnovější data.
- [**Rozšiřte**](data-sources-enrichment.md) zdroj dat před sjednocením.
- **Odstraňte** zdroj dat. Zdroj dat lze smazat pouze v případě, že data nejsou použita při žádném zpracování, jako je sjednocení, statistiky, aktivace nebo exporty.

## <a name="refresh-data-sources"></a>Aktualizovat zdroje dat

Zdroje dat lze aktualizovat podle automatického plánu nebo ručně na vyžádání. [On-premise zdroje dat](connect-power-query.md#add-data-from-on-premises-data-sources) se aktualizují podle vlastních plánů, které jsou nastaveny během příjmu dat. Tipy pro odstraňování problémů viz [Odstraňování problémů s aktualizací zdroje dat na základě PPDF Power Query](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

U připojených zdrojů dat přijímá zpracování dat nejnovější data dostupná z tohoto zdroje dat.

Jděte na **Admin** > **Systém** > [**Plán**](schedule-refresh.md) ke konfiguraci systémově naplánovaných aktualizací vašich zpracovaných datových zdrojů.

Chcete-li aktualizovat zdroj dat na vyžádání:

1. Přejděte na **Data** > **Zdroje dat**.

1. Vyberte zdroj dat, který chcete aktualizovat, a vyberte **Aktualizovat**. Zdroj dat je nyní spuštěn pro ruční aktualizaci. Aktualizací zdroj dat aktualizujete schéma entity i data pro všechny entity uvedené ve zdroji dat.

1. Výběrem stavu otevřete podokno **Podrobnosti o průběhu** a zobrazíte průběh. Chcete-li úlohu zrušit, vyberte **Zrušit úlohu** ve spodní části panelu.

## <a name="corrupt-data-sources"></a>Poškozené zdroje dat

Přijímaná data mohou mít poškozené záznamy, což může způsobit, že proces příjmu dat bude proveden s chybami nebo varováními.

> [!NOTE]
> Pokud příjem dat skončí s chybami, následné zpracování (jako je sjednocení nebo vytvoření aktivity), které využívá toto zdroj dat, bude přeskočeno. Pokud je příjem dokončen s varováními, následné zpracování pokračuje, ale některé záznamy nemusí být zahrnuty.

Tyto chyby lze vidět v detailech úlohy.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Detail úkolu zobrazující chybu poškozených dat.":::

Poškozené záznamy se zobrazují v systémově vytvořených entitách.

### <a name="fix-corrupt-data"></a>Oprava poškozených dat

1. Chcete-li zobrazit poškozená data přejděte na **Data** > **Subjekty** a vyhledejte poškozené entity v sekci **Systém**. Schéma pojmenování poškozených entit: „DataSourceName_EntityName_corrupt“.

1. Vyberte poškozenou entitu a poté kartu **Data**.

1. Identifikujte poškozená pole v záznamu a důvod.

   :::image type="content" source="media/corruption-reason.png" alt-text="Důvod poškození." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Data** > **Entity** zobrazují pouze část poškozených záznamů. Chcete-li zobrazit všechny poškozené záznamy, exportujte soubory do kontejneru v účtu úložiště pomocí [procesu exportu Customer Insights](export-destinations.md). Pokud jste použili svůj vlastní účet úložiště, můžete se také podívat do složky Customer Insights ve svém účtu úložiště.

1. Opravte poškozená data. Například pro zdroje dat Azure Data Lake, [opravte data v Data Lake Storage nebo aktualizujte datové typy v souboru manifest/model.json](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Pro zdroje dat Power Query opravte data ve zdrojovém souboru a [opravte datový typ v kroku transformace](connect-power-query.md#data-type-does-not-match-data) na stránce **Power Query – Upravit dotazy**.

Po dalším obnovení zdroje dat budou opravené záznamy přijaty do Customer Insights a předány do navazujících procesů.

Sloupec „narozeniny“ má například datový typ nastavený jako „datum“. Záznam zákazníka má jeho narozeniny zadané jako '01/01/19777'. Systém označí tento záznam jako poškozený. Změňte narozeniny ve zdrojovém systému na „1977“. Po automatickém obnovení zdrojů dat má pole nyní platný formát a záznam bude odebrán z poškozené entity.

[!INCLUDE [footer-include](includes/footer-banner.md)]
