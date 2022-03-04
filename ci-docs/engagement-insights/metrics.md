---
title: Zobrazení a vytvoření metrik
description: Vytváření, úprava a odstraňování metrik.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7e8c96f38af74f25080a40fd92e73f05c71320a8
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229808"
---
# <a name="view-and-create-metrics"></a>Zobrazení a vytvoření metrik

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metriky pomáhají porozumět chování vašich návštěvníků. Agregují vlastnosti událostí a měří statistiky a výkon vašich webových vlastností.  

Předpokládejme, že na svém webu provozujete marketingovou propagační akci. Pomocí metrik můžete sledovat počet jedinečných návštěvníků nebo uživatelů, kteří přišli na váš web během propagační akce. Analýza metrik vám pomůže lépe porozumět cílové skupině vašeho webu. Kombinace metrik s [dimenzemi](dimensions.md) ve [vlastní sestavě](custom-reports.md) vám umožní měřit chování, abyste porozuměli svým uživatelům. Můžete například rozdělit návštěvníky do kategorií nových a vracejících se osob, abyste zjistili rozdíly v zájmu a záměru mezi skupinami.

## <a name="view-metrics"></a>Zobrazení metrik

Přehledy zapojení zahrnují běžně používané agregace vlastností událostí jako systémové metriky: 

- Návštěvníci
- Návštěvy
- Zobrazení stránky
- Kliknutí

Tyto systémové metriky jsou založeny na existujících vlastnostech událostí v základních událostech.

1. V levém navigačním podokně přejděte na **Data**. 
1. Výběrem karty **Metriky** zobrazíte seznam všech metrik v pracovním prostoru. 
   > [!NOTE]
   > Metriky generované systémem jsou jen ke čtení. Nemůžete je upravit ani odstranit. Vytvářet a upravovat můžete pouze vlastní metriky.

## <a name="create-a-metric"></a>Vytvoření metriky

Správci prostředí a pracovního prostoru mohou vytvářet metriky. Před vytvořením metriky je nutné do pracovního prostoru odeslat vlastnosti události. Metriky můžete vytvořit na základě vlastností událostí, které jsou odesílány základními událostmi, nebo použít webové SDK [k odeslání uživatelských vlastností události](advanced-SDK-implementation.md).

1. Přejděte na **Data** > **Metriky**.
1. Výběrem možnosti **Nová metrika** otevřete dialog **Knihovna zdrojů** a **Nová metrika bez názvu**.

   :::image type="content" source="media/new-metric.png" alt-text="Přidání metriky k události.":::

1. V dialogovém okně **Nová metrika bez názvu** vyberte rozevíracího seznam **Formát** a vyberte datový typ **Celé číslo** nebo **Dvojnásobek**. Celé číslo je číslo bez desetinné části. U možnosti Dvojnásobek můžete zvolit jedno a tři desetinná místa.

   :::image type="content" source="media/create-new-metric.png" alt-text="Vytvoření nové metriky":::
   
5. V podokně **Knihovna zdrojů** vyhledejte vlastnost události, na které bude metrika založena.
6. Vyberte **znaménko plus (+)** vedle vlastnosti, kterou chcete použít ve vzorci. Vzorec můžete vytvořit pouze na základě jedné vlastnosti. 
7. Zvolte jednu z následujících agregačních funkcí. 

   - Součet: aritmetický součet všech hodnot 
   - Průměr: průměr všech hodnot
   - Počet: celkový počet hodnot
   - Počet jedinečných položek: celkový počet jedinečných hodnot

   Po definování metriky se zobrazí náhled aktivity metriky za poslední hodinu.

1. Zvolte **Uložit**. 
1. Zadejte název metriky a vyberte příkaz **Uložit**.

Než metriku budete moci použít k [vytváření vlastních sestav](custom-reports.md), může to trvat až minutu.

## <a name="edit-a-metric"></a>Úprava metriky

Upravovat lze pouze vlastní metriky.

1. Přejděte na **Data** > **Metriky**.
1. V seznamu vyberte metriku.
1. Změna definice metriky
1. Zvolte **Uložit**.

## <a name="change-the-name-of-a-metric"></a>Změna názvu metriky

Můžete změnit pouze název vlastních metrik.

1. Přejděte na **Data** > **Metriky**.
1. U metriky vyberte položku **Více [...]** a zvolte **Upravit název**.
1. Upravte název. 
1. Vyberte položku **Přejmenovat**.

## <a name="delete-a-metric"></a>Odstranění metriky

Odstranit lze pouze vlastní metriky.

1. Přejděte na **Data** > **Metriky**.
1. U metriky vyberte položku **Více [...]** a zvolte **Odstranit**.

   :::image type="content" source="media/delete-metric.png" alt-text="Odstranění metriky události.":::

1. Vyberte **Odstranit** pro potvrzení odstranění.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
