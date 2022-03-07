---
title: Vytvořit a upravit upřesněné události
description: Jak vytvořit a upravit upřesněné události.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034766"
---
# <a name="create-and-modify-refined-events"></a>Vytvořit a upravit upřesněné události

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Událost jsou data, která představují chování uživatelů, například aktivitu na webu.

- *Základní* událost zaznamenává, kdy uživatel zobrazí stránku (aktivita zobrazení) nebo interaguje s obsahem (aktivita akce).
- *Upřesněná* událost je virtuální pohled na základní událost. Upřesněné události definujete odebráním a přidáním vlastností nebo filtrováním událostí na základě hodnot vlastností.

Pomocí rafinovaných událostí můžete snížit rozsah základní události pro [export](export-events.md) nebo odstranění vlastností, které není nutné vystavovat.

## <a name="create-refined-events"></a>Vytváření upřesněných událostí

Existují tři způsoby, jak vytvořit upřesněnou událost ze základní události. 

1. Přejděte na **Data**> **Události** a vyberte jednu z následujících možností:
    - Vyberte **Nové události** a poté vyberte **Vytvořit upřesněné události**.
    - Vyberte základní událost, otevřete podrobné zobrazení a vyberte **Vytvořit upřesněné události** z horní nabídky.
    - Vyberte **Více [...]** k otevření místní nabídky pro základní událost. Poté vyberte **Vytvořit upřesněné události**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Možnosti pro vytvoření upřesněných událostí.":::

1. V dialogovém okně **Vytvořit upřesněné události** zadejte následující informace:

- Vyberte událost z rozevírací nabídky **Základní události**, pokud vytváříte novou událost.
- Do pole **Zobrazovaný název upřesněných událostí** zadejte název.
- Volitelně aktualizujte navrhovaný **Skutečný název** bez použití mezer.

3. Vyberte **Vytvořit** a použijte své nastavení.

1. V podrobném zobrazení vaší upřesněné události vyberte **Přidat a odeberte vlastnosti** a otevřete podokno **Upravit vlastnosti**. 

1. Pomocí zaškrtávacích políček vyberte vlastnosti, které chcete zobrazit, a ty, které chcete skrýt. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Úprava vlastností pro upřesněné události.":::

1. Vyberte **Potvrdit** k použití vašeho výběru.

1. Chcete-li uložit konfiguraci, vyberte tlačítko **Uložit**.

## <a name="edit-refined-events"></a>Úprava upřesněných událostí

Můžete změnit název a vlastnosti upřesněné události.

### <a name="edit-event-name"></a>Úprava názvu události

1. Přejděte na **Data** > **Události**. 
1. Vyberte **Více [...]** pro událost a vyberte **Upravit název**.
1. Aktualizujte název události a vyberte **Přejmenovat**.

### <a name="edit-selected-properties"></a>Úprava vybraných vlastností

1. Přejděte na **Data** > **Události** a výběrem upřesněných událostí otevřete podrobné zobrazení.
1. Vyberte **Přidat a odebrat vlastnosti**. 
1. Upravte výběr zaškrtávacích políček.
1. Vyberte **Potvrdit** a pak **Uložit** k použití změn.

Informace o exportu událostí viz [Export událostí](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
