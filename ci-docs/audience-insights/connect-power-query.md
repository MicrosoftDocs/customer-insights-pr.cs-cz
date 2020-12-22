---
title: Ingestování data prostřednictvím konektoru Power Query
description: Konektory pro zdroje dat založené na Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405375"
---
# <a name="connect-to-a-power-query-data-source"></a>Připojte se k Power Query zdroji dat

Power Query nabízí širokou sadu konektorů pro příjem dat. Většina z těchto konektorů je podporována Dynamics 365 Customer Insights. Přidání zdrojů dat na základě Power Query konektorů obecně postupuje podle kroků uvedených v následující části. V závislosti na použitém konektoru jsou však vyžadovány různé informace. Další informace najdete v dokumentaci o jednotlivých konektorech v [Odkazu na konektory Power Query](https://docs.microsoft.com/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Vytvořit nový zdroj dat

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

1. Vyberte **Přidat zdroj dat**.

1. Vyberte metodu **Import dat** a vyberte **Další**.

1. Uveďte **Název** pro zdroj dat a vyberte **Další** k vytvoření zdroje dat.

1. Vyberte jeden z [dostupných konektorů](#available-power-query-data-sources). V tomto příkladu vybereme konektor **Text / CSV**.

1. Zadejte požadované podrobnosti do **Nastavení připojení** pro vybraný konektor a vyberte **Další** pro zobrazení náhledu dat.

1. Vyberte **Transformovat data**. V tomto kroku přidáte entity do zdroj dat. Entity jsou datové sady. Pokud máte databázi, která obsahuje více datových sad, je každá datová sada vlastní entitou.

1. Dialogové okno **Power Query - Upravit dotazy** umožňuje zkontrolovat a upřesnit data. V levém podokně se zobrazí entity, které systémy identifikované ve vybraném zdroj dat.

   > [!div class="mx-imgBorder"]
   > ![Dialog Upravit dotazy](media/data-manager-configure-edit-queries.png "Dialog Upravit dotazy")

1. Data lze rovněž transformovat. Vyberte entitu, kterou chcete upravit nebo transformovat. K použití transformací použijte možnosti v okně Power Query. Každá transformace bude uvedena v **Použité kroky**. Power Query poskytuje řadu předem připravených možností transformace. Další informace najdete v tématu [Transormace Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).

1. Výběrem **Získejte data** v dialogu **Upravit dotazy** můžete do svého zdroje dat přidat další entity.

   Tyto transformace jsou vysoce doporučeny:

   - Pokud přijímáte data ze souboru CSV, první řádek často obsahuje záhlaví. Přejděte na **Transformační tabulka** a vyberte **Jako první řádek použijte záhlaví**.
   - Zajistěte, aby byl datový typ nastaven správně.

1. Výběrem tlačítka **Uložit** ve spodní části Power Query uložte transformace. Po uložení najdete svůj zdroj dat v **Data** > **Zdroje dat**.

1. Na stránce **Zdroje dat** si všimnete, že nový zdroj dat je ve stavu **Aktualizace**.

## <a name="available-power-query-data-sources"></a>Dostupné Power Query zdroje dat

Viz [Odkaz na konektory Power Query](https://docs.microsoft.com/power-query/connectors/) pro aktuální seznam konektorů, které můžete vybrat k importu dat do Customer Insights. 

Konektory se zaškrtnutím ve sloupci **Customer Insights (toky dat)** slouží k vytvoření nových zdrojů dat založených na Power Query. Projděte si dokumentaci konkrétního konektoru a dozvíte se více o jeho požadavcích, omezeních a dalších podrobnostech.

## <a name="edit-power-query-data-sources"></a>Upravit zdroje dat Power Query

> [!NOTE]
> Pravděpodobně nebude možné provést změny ve zdrojích dat, které se aktuálně používají v jednom z procesů aplikace (např. *segmentace*, *shoda* nebo *sloučit*). 
>
> Za použití stránky **Nastavení** můžete sledovat průběh každého z aktivních procesů. Po dokončení procesu se můžete vrátit na stránku **Zdroje dat** stránku a provést změny.

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2. Vyberte vertikální tři tečky vedle zdroje dat, který chcete změnit, a vyberte **Upravit** z rozbalovací nabídky.

   > [!div class="mx-imgBorder"]
   > ![Upravit možnost](media/edit-option-data-sources.png "Upravit možnost")

3. Aplikujte své změny a transformace v dialogovém okně **Power Query - Upravit dotazy**, jak je popsáno v sekci [Vytvořte nový zdroj dat](#create-a-new-data-source).

4. Vyberte **Uložit** po dokončení úprav a uložte změny v Power Query.
