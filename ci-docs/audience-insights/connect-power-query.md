---
title: Příjem dat přes konektor Power Query (video)
description: Konektory pro zdroje dat založené na Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 38c447d80a25feca087ca9f110278b8401423018
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903832"
---
# <a name="connect-to-a-power-query-data-source"></a>Připojte se k Power Query zdroji dat

Power Query nabízí širokou sadu konektorů pro příjem dat. Většina z těchto konektorů je podporována Dynamics 365 Customer Insights. 

Přidávání zdrojů dat na základě konektorů Power Query se obecně řídí kroky popsanými v této části. V závislosti na použitém konektoru jsou však vyžadovány různé informace. Další informace naleznete v dokumentaci k jednotlivým konektorům v [podkladech ke konektoru Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Vytvořit nový zdroj dat

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

1. Vyberte **Přidat zdroj dat**.

1. Vyberte **Microsoft Power Query** a poté vyberte **Další**.

1. Uveďte **Název** pro zdroj dat a vyberte **Další** k vytvoření zdroje dat.

1. Vyberte jeden z [dostupných konektorů](#available-power-query-data-sources). V tomto příkladu vybereme konektor **Text/CSV**.

1. Zadejte požadované podrobnosti do **Nastavení připojení** pro vybraný konektor a vyberte **Další** pro zobrazení náhledu dat.

1. Vyberte **Transformovat data**. V tomto kroku přidáte entity do zdroj dat. Entity jsou datové sady. Pokud máte databázi, která obsahuje více datových sad, je každá datová sada vlastní entitou.

1. Dialogové okno **Power Query - Upravit dotazy** umožňuje zkontrolovat a upřesnit data. V levém podokně se zobrazí entity, které systémy identifikované ve vybraném zdroj dat.

   > [!div class="mx-imgBorder"]
   > ![Dialog Upravit dotazy.](media/data-manager-configure-edit-queries.png "Dialog Upravit dotazy")

1. Data lze rovněž transformovat. Vyberte entitu, kterou chcete upravit nebo transformovat. K použití transformací použijte možnosti v okně Power Query. Každá transformace bude uvedena v **Použité kroky**. Power Query poskytuje řadu předem připravených možností transformace. Další informace najdete v tématu [Transormace Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Výběrem **Získejte data** v dialogu **Upravit dotazy** můžete do svého zdroje dat přidat další entity.

   Doporučujeme použít následující transformace:

   - Pokud přijímáte data ze souboru CSV, první řádek často obsahuje záhlaví. Přejděte na **Transformační tabulka** a vyberte **Jako první řádek použijte záhlaví**.
   - Zajistěte, aby byl datový typ nastaven správně.

1. Výběrem tlačítka **Uložit** ve spodní části Power Query uložte transformace. Po uložení najdete svůj zdroj dat v **Data** > **Zdroje dat**.

1. Na stránce **Zdroje dat** si všimnete, že nový zdroj dat je ve stavu **Aktualizace**.

## <a name="available-power-query-data-sources"></a>Dostupné Power Query zdroje dat

Viz [podklady ke konektoru Power Query](/power-query/connectors/), kde najdete seznam konektorů, které můžete použít k importu dat do Customer Insights. 

Konektory se zaškrtnutím ve sloupci **Customer Insights (toky dat)** slouží k vytvoření nových zdrojů dat založených na Power Query. Projděte si dokumentaci konkrétního konektoru a dozvíte se více o jeho požadavcích, omezeních a dalších podrobnostech.

## <a name="edit-power-query-data-sources"></a>Upravit zdroje dat Power Query

> [!NOTE]
> Pravděpodobně nebude možné provést změny ve zdrojích dat, které se aktuálně používají v jednom z procesů aplikace (např. *segmentace*, *shoda* nebo *sloučit*). 
>
> Na stránce **Nastavení** můžete sledovat průběh každého z aktivních procesů. Po dokončení procesu se můžete vrátit na stránku **Zdroje dat** stránku a provést změny.

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2. Vyberte svislé tlačítko se třemi tečkami vedle zdroje dat, který chcete změnit, a v rozevírací nabídce vyberte **Upravit**.

   > [!div class="mx-imgBorder"]
   > ![Upravit možnost.](media/edit-option-data-sources.png "Upravit možnost")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Aplikujte své změny a transformace v dialogovém okně **Power Query - Upravit dotazy**, jak je popsáno v sekci [Vytvořte nový zdroj dat](#create-a-new-data-source).

4. Vyberte **Uložit** po dokončení úprav a uložte změny v Power Query.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
