---
title: Vytváření a úpravy událostí
description: Jak vytvořit a upravit události
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606190"
---
# <a name="create-and-modify-events"></a>Vytváření a úpravy událostí

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Událost jsou data, která představují chování uživatelů, například aktivitu na webu.

- *Základní* událost zaznamenává, kdy uživatel zobrazí stránku (aktivita zobrazení) nebo interaguje s obsahem (aktivita akce).
- *Upřesněná* událost je virtuální pohled na základní událost. Upřesněné události definujete odebráním a přidáním vlastností nebo filtrováním událostí na základě hodnot vlastností.

## <a name="prerequisites"></a>Předpoklady

Chcete-li získat události, je nutné nejprve připojit data webu k přehledům zapojení pomocí jednoduchého fragmentu kódu. Další informace viz [Instalace webové sady SDK na web](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Nejprve připojte data.":::

## <a name="create-refined-events"></a>Vytvořit upřesněné události

Pomocí rafinovaných událostí můžete snížit rozsah základní události pro [export](export-events.md) nebo odstranění vlastností, které není nutné vystavovat.

> [!NOTE]
> Jakmile na svůj web přidáte webovou sadu SDK, můžete si prohlížet základní události a vytvářet upřesněné události. 

Chcete -li zobrazit základní události:

1. V levém navigačním podokně přejděte na **Data**.

1. Vyberte **Události** k zobrazení seznamu všech událostí v pracovním prostoru.

    :::image type="content" source="media/data-events.png" alt-text="Zobrazte události.":::

Vytvoření upřesněné události ze základní události: 

1. Jděte na **Data** > **Události** a vyberte **+ Nové události** v horní části obrazovky.

1. V dialogu **Nové akce** vyberte **Vytvořit propracované události** a poté vyberte **Další**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Průvodce novými událostmi":::
     
1. V dialogu **Nové akce** zadejte následující informace:

   - Vyberte událost z rozevíracího seznamu **Základní události**.
   - Do pole **Zobrazovaný název upřesněných událostí** zadejte název.
   - Volitelně aktualizujte navrhovaný **Skutečný název** bez použití mezer.

1. Vyberte **Vytvořit** a použijte své nastavení.

Upřesněná událost se nyní zobrazí v seznamu **Události**.

### <a name="edit-event-name"></a>Úprava názvu události

Můžete změnit název a vlastnosti základní nebo upřesněné události.

1. Přejděte na **Data** > **Události**. 

1. Vyberte **Více [...]** pro událost a vyberte **Upravit název**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Možnosti pro vytvoření upřesněných událostí.":::

3. Aktualizujte název události a vyberte **Přejmenovat**.

### <a name="view-the-details-of-a-refined-event"></a>Zobrazení podrobností o upřesněné události:

1. V seznamu **Událost** vyberte svou základní nebo upřesněnou událost. 

1. Vyberte **Přidat a odebrat vlastnosti** v horní části obrazovky k otevření podokna **Upravit vlastnosti**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Přidejte a odeberte vlastnosti.":::

1. Pomocí zaškrtávacích políček vyberte vlastnosti, které chcete zobrazit, a ty, které chcete skrýt. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Úprava vlastností pro upřesněné události.":::

1. Vyberte **Potvrdit** pro použití výběru a pak vyberte **Uložit**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Úprava vybraných vlastností pro upřesněnou událost

1. Přejděte na **Data** > **Události** a výběrem upřesněných událostí otevřete podrobné zobrazení.
1. Vyberte **Přidat a odebrat vlastnosti**. 
1. Upravte výběr zaškrtávacích políček.
1. Vyberte **Potvrdit** a pak **Uložit** k použití změn.

Informace o exportu událostí viz [Export událostí](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
