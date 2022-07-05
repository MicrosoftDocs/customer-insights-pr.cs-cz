---
title: Přehled zdrojů dat
description: Naučte se importovat nebo ingestovat data z různých zdrojů.
ms.date: 05/18/2022
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
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051445"
---
# <a name="data-sources-overview"></a>Přehled zdrojů dat

Dynamics 365 Customer Insights poskytuje připojení k přinesení dat ze široké škály zdrojů. Připojení k zdroji dat se často označuje jako proces *příjmu dat*. Po přijetí dat můžete [sjednotit](data-unification.md), generovat statistiky a aktivovat data pro vytváření personalizovaných zážitků.

## <a name="add-data-sources"></a>Přidat zdroje dat

Do Customer Insights můžete připojit nebo importovat zdroje dat. Níže uvedené odkazy poskytují pokyny k přidávání zdrojů dat.

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

Jděte na **Data** > **Zdroje dat** pro zobrazení názvu každého zpracovaného zdroj dat, jeho stavu a poslední aktualizace dat pro daný zdroj. Seznam zdrojů dat můžete seřadit podle každého sloupce.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Přidaný zdroj dat.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Načítání dat může nějakou dobu trvat. Po úspěšné aktualizaci lze přijatá data zkontrolovat na stránce **Entity**. Další informace najdete v tématu [Entity](entities.md).

## <a name="refresh-data-sources"></a>Aktualizovat zdroje dat

Zdroje dat lze aktualizovat podle automatického plánu nebo ručně na vyžádání. [On-premise zdroje dat](connect-power-query.md#add-data-from-on-premises-data-sources) se aktualizují podle vlastních plánů, které jsou nastaveny během příjmu dat. U připojených zdrojů dat přijímá zpracování dat nejnovější data dostupná z tohoto zdroje dat.

Jděte na **Admin** > **Systém** > [**Plán**](system.md#schedule-tab) ke konfiguraci systémově naplánovaných aktualizací vašich zpracovaných datových zdrojů.

Chcete-li aktualizovat zdroj dat na vyžádání, postupujte takto:

1. Přejděte na **Data** > **Zdroje dat**.

1. Vyberte vertikální tři tečky (&vellip;) vedle zdroje dat, který chcete aktualizovat, a v rozevíracím seznamu vyberte **Obnovit**. Zdroj dat je nyní spuštěn pro ruční aktualizaci. Aktualizací zdroj dat aktualizujete schéma entity i data pro všechny entity uvedené ve zdroji dat.

1. Vyberte **Zastavit aktualizaci**, pokud chcete zrušit existující aktualizaci a zdroj dat se vrátí do svého posledního stavu aktualizace.

## <a name="delete-a-data-source"></a>Odstranit datový zdroj

Zdroj dat lze smazat pouze v případě, že data nejsou použita při žádném zpracování, jako je sjednocení, statistiky, aktivace nebo exporty.

1. Přejděte na **Data** > **Zdroje dat**.

2. Vyberte svislé tlačítko se třemi tečkami (&vellip;) vedle zdroje dat, který chcete odebrat, a v rozevírací nabídce vyberte **Odstranit**.

3. Odstranění potvrďte.


[!INCLUDE [footer-include](includes/footer-banner.md)]
