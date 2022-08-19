---
title: Přehled zdrojů dat
description: Naučte se importovat nebo ingestovat data z různých zdrojů.
ms.date: 07/26/2022
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
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245641"
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

Zdroje dat lze aktualizovat podle automatického plánu nebo ručně na vyžádání. [On-premise zdroje dat](connect-power-query.md#add-data-from-on-premises-data-sources) se aktualizují podle vlastních plánů, které jsou nastaveny během příjmu dat. U připojených zdrojů dat přijímá zpracování dat nejnovější data dostupná z tohoto zdroje dat.

Jděte na **Admin** > **Systém** > [**Plán**](schedule-refresh.md) ke konfiguraci systémově naplánovaných aktualizací vašich zpracovaných datových zdrojů.

Chcete-li aktualizovat zdroj dat na vyžádání:

1. Přejděte na **Data** > **Zdroje dat**.

1. Vyberte zdroj dat, který chcete aktualizovat, a vyberte **Aktualizovat**. Zdroj dat je nyní spuštěn pro ruční aktualizaci. Aktualizací zdroj dat aktualizujete schéma entity i data pro všechny entity uvedené ve zdroji dat.

1. Výběrem stavu otevřete podokno **Podrobnosti o průběhu** a zobrazíte průběh. Chcete-li úlohu zrušit, vyberte **Zrušit úlohu** ve spodní části panelu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
