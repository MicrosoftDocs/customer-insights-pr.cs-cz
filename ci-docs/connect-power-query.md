---
title: Připojení ke zdroji dat Power Query (obsahuje video)
description: Příjem dat přes konektor Power Query (obsahuje video).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6a25e332bafab414c9def4e1e6b461139dd24ea6
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463257"
---
# <a name="connect-to-a-power-query-data-source"></a>Připojení ke zdroji dat Power Query

Power Query nabízí širokou sadu konektorů pro ingestaci dat. Většina z těchto konektorů je podporována Dynamics 365 Customer Insights.

Přidávání zdrojů dat na základě konektorů Power Query se obecně řídí kroky popsanými v této části. V závislosti na použitém konektoru jsou však vyžadovány různé informace. Další informace naleznete v dokumentaci k jednotlivým konektorům v [podkladech ke konektoru Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Vytvořit nový zdroj dat

1. Přejděte na **Data** > **Zdroje dat**.

1. Vyberte **Přidat zdroj dat**.

1. Vyberte **Microsoft Power Query**.

1. Uveďte **název** a volitelný **popis** zdroje dat a vyberte **Další**.

1. Vyberte jeden z [dostupných konektorů](#available-power-query-data-sources). V tomto příkladu vybereme konektor **Text/CSV**.

1. Zadejte požadované podrobnosti do **Nastavení připojení** pro vybraný konektor a vyberte **Další** pro zobrazení náhledu dat.

1. Vyberte **Transformovat data**.

1. Dialogové okno **Power Query - Upravit dotazy** umožňuje zkontrolovat a upřesnit data. V levém podokně se zobrazí entity, které systémy identifikované ve vybraném zdroj dat.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dialog Upravit dotazy":::

1. Data lze rovněž transformovat. Vyberte entitu, kterou chcete upravit nebo transformovat. Použijte možnosti v okně Power Query pro použití transformací. Každá transformace je uvedena v části **Použité kroky**. Power Query poskytuje řadu [předpřipravených možností transformace](/power-query/power-query-what-is-power-query#transformations).

   Doporučujeme použít následující transformace:

   - Pokud přijímáte data ze souboru CSV, první řádek často obsahuje záhlaví. Přejděte na **Transformovat** a vyberte **Použijte první řádek jako záhlaví**.
   - Zajistěte, aby byl datový typ nastaven správně. Například pro datová pole vyberte typ dat.

1. Chcete-li přidat další entity do zdroje dat v dialogu **Upravit dotazy**, přejděte na **Domů** a vyberte **Získat data**. Opakujte kroky 5-10, dokud nepřidáte všechny entity pro toto zdroj dat. Pokud máte databázi, která obsahuje více datových sad, je každá datová sada vlastní entitou.

1. Vyberte **Uložit**. Otevře se stránka **Zdroje dat** s novým zdrojem dat se stavem **Aktualizace**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Načítání dat může nějakou dobu trvat. Po úspěšné aktualizaci lze přijatá data zkontrolovat na stránce [**Entity**](entities.md).

> [!CAUTION]
>
> - Zdroj dat na základě Power Query vytvoří [tok dat v Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Neměňte název datového toku v centru pro správu Power Platform, který se používá v Customer Insights. Přejmenování toku dat způsobuje problémy s odkazy mezi zdrojem dat Customer Insights a datovým tokem Dataverse.
> - Souběžná hodnocení pro zdroje dat Power Query v Customer Insights mají stejné [obnovovací limity jako datové toky v PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Pokud se aktualizace dat nezdaří, protože dosáhla limitu hodnocení, doporučujeme upravit plán aktualizace pro každý tok dat, abyste zajistili, že zdroje dat nebudou zpracovávány současně.

### <a name="available-power-query-data-sources"></a>Dostupné zdroje dat Power Query

Viz [podklady ke konektoru Power Query](/power-query/connectors/), kde najdete seznam konektorů, které můžete použít k importu dat do Customer Insights.

Konektory se zaškrtnutím ve sloupci **Customer Insights (Datové toky)** jsou k dispozici pro vytváření nových zdrojů dat na základě Power Query. Prohlédněte si dokumentaci konkrétního konektoru, abyste se dozvěděli více o jeho předpokladech, [omezení dotazů](/power-query/power-query-online-limits) a další podrobnosti.

## <a name="add-data-from-on-premises-data-sources"></a>Přidání dat z místních zdrojů dat

Zpracování dat ze zdrojů dat místní je podporováno na základě datových toků Microsoft Power Platform (PPDFs). Datové toky v Customer Insights můžete povolit [zadáním adresy URL prostředí Microsoft Dataverse](create-environment.md) při nastavování prostředí.

Zdroje dat, které jsou vytvořeny po přidružení prostředí Dataverse ke Customer Insights, standardně používají [datové toky Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Datové toky podporují místní připojení pomocí datové brány. Zdroje dat, které existovaly před přidružením prostředí Dataverse, můžete odebrat a znovu vytvořit [pomocí místní bran dat](/data-integration/gateway/service-gateway-app).

Datové brány z existujícího prostředí Power BI nebo Power Apps budou viditelné a můžete je znovu použít v Customer Insights, pokud jsou datová brána a prostředí Customer Insights ve stejné oblasti Azure. Na stránce zdroje dat jsou zobrazeny odkazy, na které chcete přejít v prostředí Microsoft Power Platform, kde můžete prohlížet a konfigurovat místní datové brány.

> [!IMPORTANT]
> Ujistěte se, že jsou vaše brány aktualizovány na nejnovější verzi. Můžete nainstalovat aktualizaci a překonfigurovat bránu přímo z výzvy zobrazené na obrazovce brány nebo [stáhnout nejnovější verzi](https://powerapps.microsoft.com/downloads/). Pokud nepoužíváte nejnovější verzi brány, aktualizace toku dat selže s chybovými zprávami, například **Klíčové slovo není podporováno: vlastnosti konfigurace. Název parametru: klíčové slovo**.
>
> Chyby místních datových bran v Customer Insights jsou často způsobeny problémy s konfigurací. Další informace o řešení problémů s bránami dat naleznete na stránce [Řešení problémů s místní bránou dat](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Upravte zdroje dat Power Query

> [!NOTE]
> Pravděpodobně nebude možné provést změny ve zdrojích dat, které se aktuálně používají v jednom z procesů aplikace (např. segmentace nebo sjednocení dat).
>
> Na stránce **Nastavení** můžete sledovat průběh každého z aktivních procesů. Po dokončení procesu se můžete vrátit na stránku **Zdroje dat** stránku a provést změny.

1. Přejděte na **Data** > **Zdroje dat**.

1. Vedle zdroje dat, který chcete aktualizovat, vyberte **Upravit**.

1. Použijte změny a transformace v dialogu **Power Query - Upravit dotazy**, jak je popsáno v sekci [Vytvořte nový zdroj dat](#create-a-new-data-source).

1. Volbou **Uložit** použijete změny a návrat na stránku **Zdroje dat**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
