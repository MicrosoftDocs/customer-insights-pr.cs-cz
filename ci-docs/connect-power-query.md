---
title: Příjem dat přes konektor Power Query (obsahuje video)
description: Konektory pro datové zdroje založené na Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4db97ec02eb96662d30a8536ea42372f81f318d2
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800136"
---
# <a name="connect-to-a-power-query-data-source"></a>Připojení ke zdroji dat Power Query

Power Query nabízí širokou sadu konektorů pro ingestaci dat. Většina z těchto konektorů je podporována Dynamics 365 Customer Insights. 

Přidávání zdrojů dat na základě konektorů Power Query se obecně řídí kroky popsanými v této části. V závislosti na použitém konektoru jsou však vyžadovány různé informace. Další informace naleznete v dokumentaci k jednotlivým konektorům v [podkladech ke konektoru Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Vytvořit nový zdroj dat

1. Přejděte na **Data** > **Zdroje dat**.

1. Vyberte **Přidat zdroj dat**.

1. Vyberte **Microsoft Power Query**.

1. Uveďte **Název** pro zdroj dat a vyberte **Další** k vytvoření zdroje dat.

1. Vyberte jeden z [dostupných konektorů](#available-power-query-data-sources). V tomto příkladu vybereme konektor **Text/CSV**.

1. Zadejte požadované podrobnosti do **Nastavení připojení** pro vybraný konektor a vyberte **Další** pro zobrazení náhledu dat.

1. Vyberte **Transformovat data**. V tomto kroku přidáte entity do zdroj dat. Entity jsou datové sady. Pokud máte databázi, která obsahuje více datových sad, je každá datová sada vlastní entitou.

1. Dialogové okno **Power Query - Upravit dotazy** umožňuje zkontrolovat a upřesnit data. V levém podokně se zobrazí entity, které systémy identifikované ve vybraném zdroj dat.

   > [!div class="mx-imgBorder"]
   > ![Dialog Upravit dotazy.](media/data-manager-configure-edit-queries.png "Dialog Upravit dotazy")

1. Data lze rovněž transformovat. Vyberte entitu, kterou chcete upravit nebo transformovat. Použijte možnosti v okně Power Query pro použití transformací. Každá transformace bude uvedena v **Použité kroky**. Power Query poskytuje řadu předpřipravených možností transformace. Další informace najdete v [Transformacích Power Query](/power-query/power-query-what-is-power-query#transformations).

   Doporučujeme použít následující transformace:

   - Pokud přijímáte data ze souboru CSV, první řádek často obsahuje záhlaví. Přejděte na **Transformovat** a vyberte **Použijte první řádek jako záhlaví**.
   - Zajistěte, aby byl datový typ nastaven správně. Například pro datová pole vyberte typ dat.

1. Chcete-li přidat další entity do zdroje dat v dialogu **Upravit dotazy**, přejděte na **Domů** a vyberte **Získat data**.

1. Výběrem tlačítka **Uložit** ve spodní části okna Power Query uložte transformace. Po uložení najdete svůj zdroj dat v **Data** > **Zdroje dat**.

1. Na stránce **Zdroje dat** si všimnete, že nový zdroj dat je ve stavu **Aktualizace**.

## <a name="available-power-query-data-sources"></a>Dostupné zdroje dat Power Query

Viz [podklady ke konektoru Power Query](/power-query/connectors/), kde najdete seznam konektorů, které můžete použít k importu dat do Customer Insights. 

Konektory se zaškrtnutím ve sloupci **Customer Insights (Datové toky)** jsou k dispozici pro vytváření nových zdrojů dat na základě Power Query. Projděte si dokumentaci konkrétního konektoru a dozvíte se více o jeho požadavcích, omezeních a dalších podrobnostech.

## <a name="edit-power-query-data-sources"></a>Upravte zdroje dat Power Query

> [!NOTE]
> Pravděpodobně nebude možné provést změny ve zdrojích dat, které se aktuálně používají v jednom z procesů aplikace (např. *segmentace*, *shoda* nebo *sloučit*). 
>
> Na stránce **Nastavení** můžete sledovat průběh každého z aktivních procesů. Po dokončení procesu se můžete vrátit na stránku **Zdroje dat** stránku a provést změny.

1. Přejděte na **Data** > **Zdroje dat**.

2. Vyberte svislé tlačítko se třemi tečkami (&vellip;) vedle zdroje dat, který chcete změnit, a v rozevírací nabídce vyberte **Upravit**.

   > [!div class="mx-imgBorder"]
   > ![Upravit možnost.](media/edit-option-data-sources.png "Upravit možnost")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. Použijte změny a transformace v dialogu **Power Query - Upravit dotazy**, jak je popsáno v sekci [Vytvořte nový zdroj dat](#create-a-new-data-source).

4. Vyberte **Uložit** v Power Query po dokončení úprav pro uložení změn.


[!INCLUDE [footer-include](includes/footer-banner.md)]
