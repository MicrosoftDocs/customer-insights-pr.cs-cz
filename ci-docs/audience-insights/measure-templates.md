---
title: Vytvoření měr ze šablon
description: Definujte míry pomocí šablon pro běžné případy použití.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359900"
---
# <a name="use-a-template-to-build-a-measure"></a>Vytvoření míry pomocí šablony

K jejich vytváření můžete použít předdefinované šablony běžně používaných [měr](measures.md). Podrobné popisy šablon a průvodce vám pomohou s efektivním vytvořením míry. Šablony vycházejí z mapovaných dat entity *Sjednocená aktivita*. Ujistěte se tedy, že jste nakonfigurovali [aktivity zákazníků](activities.md) před vytvořením míry ze šablony.

Chcete-li vytvořit vlastní míry, podívejte se do části [Pomocí nástroje pro tvorbu míry vytvořte míry od začátku](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

Dostupné šablony měr: 
- Průměrná hodnota transakce
- Celková hodnota transakce
- Průměrné denní výnosy
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

1. V podokně **Upravit jméno** nastavte název míry a výstupní entitu. 

1. Vyberte **Hotovo**.

1. V části **Nastavit časové období** definujte časový rámec dat, která se mají použít. Vyberte, zda má nová míra pokrývat celou datovou sadu, výběrem **Kdykoli**, nebo zda se má zaměřovat na **Specifické časové období**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Screenshot zobrazující část časového období při konfiguraci míry ze šablony.":::

1. V další části vyberte **Přidat data** pro výběr aktivit a namapování příslušných dat z entity *Sjednocená aktivita*.

    1. Krok 1 ze 2: V části **Typ aktivity** vyberte typ entity, kterou chcete použít. Pro **Aktivity** vyberte entity, které chcete mapovat.
    1. Krok 2 ze 2: Vyberte atribut z entity *Sjednocená aktivita* pro komponentu požadovanou vzorcem. Například pro průměrnou hodnotu transakce je to atribut představující hodnotu transakce. Pro **Časové razítko aktivity** vyberte atribut z entity Unified Activity, která představuje datum a čas aktivity.
   
1. Jakmile je mapování dat úspěšné, můžete vidět stav jako **Kompletní** a název mapovaných aktivit a atributů.

1. Nyní můžete vybrat **Spustit** k výpočtu výsledků míry. Chcete-li to upřesnit později, vyberte **Uložit koncept**.

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

Tato funkce je k dispozici pouze pro míry vytvořené v prostředích s individuálním zákazníkem jako primární cílovou skupinou.

---
