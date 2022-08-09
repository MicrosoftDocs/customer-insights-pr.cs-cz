---
title: Vytvoření měr ze šablon
description: Definujte míry pomocí šablon pro běžné případy použití.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170765"
---
# <a name="create-measures-from-templates"></a>Vytvoření měr ze šablon

K jejich vytváření můžete použít předdefinované šablony běžně používaných [měr](measures.md). Šablony vycházejí z mapovaných dat entity *Sjednocená aktivita*. Ujistěte se tedy, že jste nakonfigurovali [aktivity zákazníků](activities.md) před vytvořením míry ze šablony.

Šablony měr jsou podporovány pouze v prostředích pro **jednotlivé zákazníky**. Chcete-li vytvořit vlastní míry nebo vytvořit míry pro B2B, podívejte se do části [Použití tvůrce měr](measure-builder.md).

Dostupné šablony měr:
- Průměrná hodnota transakce
- Celková hodnota transakce
- Průměrné denní výnosy
- Průměrné měsíční výnosy
- Průměrné roční výnosy
- Počet transakcí
- Získané věrnostní body
- Uplatněné věrnostní body
- Zůstatek věrnostních bodů
- Životnost aktivního zákazníka
- Doba trvání věrnostního členství
- Čas od posledního nákupu

## <a name="build-a-new-measure-using-a-template"></a>Vytvoření nové míry pomocí šablony

1. Přejděte na **Míry**.

1. Vyberte **Nová** a vyberte **Zvolit šablonu**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Screenshot rozevírací nabídky při vytváření nové míry se zvýrazněním šablony.":::

1. Najděte šablonu, která vyhovuje vašim potřebám, a vyberte **Zvolit šablonu**.

1. Zkontrolujte požadovaná data a vyberte **Začít**, pokud máte všechna data na místě.

1. Vedle názvu míry vyberte možnost **Upravit podrobnosti**. Zadejte název míry. Volitelně přidejte [značky](work-with-tags-columns.md#manage-tags) do nové míry.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogové okno Úprava podrobností":::

1. Vyberte **Hotovo**.

1. V části **Nastavit časové období** definujte časový rámec dat. Vyberte, zda má nová míra pokrývat celou datovou sadu, výběrem **Kdykoli**, nebo zda se má zaměřovat na **Specifické časové období**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Screenshot zobrazující část časového období při konfiguraci míry ze šablony.":::

1. V další části vyberte **Přidat data** pro výběr aktivit a namapování příslušných dat z entity *Sjednocená aktivita*.

    1. Krok 1 ze 2: V části **Typ aktivity** vyberte typ entity, kterou chcete použít. Pro **Aktivity** vyberte entity, které chcete mapovat, a poté vyberte **Další**.
    1. Krok 2 ze 2: Vyberte atribut z entity *Sjednocená aktivita* pro komponentu požadovanou vzorcem. Například pro průměrnou hodnotu transakce je to atribut představující hodnotu transakce. Pro **Časové razítko aktivity** vyberte atribut z entity *Sjednocená aktivita*, která představuje datum a čas aktivity.
    1. Vyberte **Uložit**.

    Když je mapování dat úspěšné, stav se zobrazí jako **Kompletní** a zobrazí se název mapovaných aktivit a atributů.

1. Vyberte **Spustit** k výpočtu výsledků míry. Vyberte **Uložit koncept**, chcete-li zachovat aktuální konfiguraci a spustit míru později. Zobrazí se stránka **Míry**.

## <a name="next-step"></a>Další krok

Pomocí existujících měr vytvoříte [segment zákazníka](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
