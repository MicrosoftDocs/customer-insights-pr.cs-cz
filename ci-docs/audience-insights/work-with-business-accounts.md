---
title: Začněte s obchodními účty jako primární cílová skupina
description: Přečtěte si o obchodních účtech jako o primární cílové skupině Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ac5ae950a44f7f32e3cb9fdc0ffad05b78fddef0
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673679"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Práce s firemními účty v přehledech cílové skupiny

Funkce přehledů cílové skupiny v Dynamics 365 Customer Insights umožňují konfigurovat prostředí pro různé primární cílové skupiny: jednotlivé spotřebitele (B2C) a obchodní účty (B2B). Ve scénářích B2C jsou data soustředěna kolem jednotlivců. U B2B jsou primární cílovou skupinou obchodní účty – organizace nebo společnosti – a kontakty. Tento článek vám pomůže začít s prostředím pro obchodní zákaznické účty. Uvádí rozdíly pro oblasti funkcí v přehledech cílové skupiny v závislosti na zaměření na prostředí. Další informace o rozdílech najdete v dokumentech oblastí funkcí. 

## <a name="create-an-environment-for-business-accounts"></a>Vytvoření prostředí pro obchodní účty

Správci mohou [vytvořit prostředí ve stávající organizaci](create-environment.md). Krok v procesu vytváření nového prostředí žádá správce pro primární cílovou skupinu prostředí. V případě, že se jedná o úvodní nastavení přehledů cílové skupiny po zakoupení licence, průvodce vám pomůže s vytvořením prvního prostředí.

Pak můžete [přijímat data](data-sources.md) pro obchodní účty a související kontakty jako zdroje dat ze všech podporovaných zdrojů.

Po sjednocení dat [určete hierarchie účtů](relationships.md#set-up-account-hierarchies) jako součást konfigurace vztahu. Můžete také [konfigurovat sémantická mapování](semantic-mappings.md) pro propojení entit kontaktu a účtu. 

## <a name="switch-between-primary-target-audience"></a>Přepínání mezi primární cílovou skupinou

Pokud vaše organizace spravuje prostředí pro jednotlivé zákazníky a obchodní účty, můžete pomocí přepínače v levém podokně vybrat primární cíl cílovou skupinu.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Přepínač pro změnu primární cílové skupiny mezi jednotlivými zákaznickými a firemními účty.":::

## <a name="supported-feature-areas"></a>Podporované oblasti funkce

- [Aktivity](activities.md): Podpora účtů a souvisejících kontaktů k vytváření aktivit a jejich zobrazení na časové ose.
- [Vztahy](relationships.md): Průvodce aktivitami pomáhá vytvářet vztahy mezi entitami, aby zobrazení účtu mohlo zobrazovat všechny aktivity z kontaktů. Kontakty lze zobrazit podrobněji, aby bylo možné zobrazit zobrazení kontaktů, a pro agregaci aktivit účtu lze použít hierarchie.
- [Míry](measures.md): Podporuje opatření vytvořená z nástroje pro tvorbu měření jedním výpočtem. Volitelné nastavení umožňuje souhrn pro podúčty při vytváření měr.
- [Segmenty](segments.md): Podporuje segmenty, které jsou vytvořeny od začátku pomocí nástroje pro tvorbu segmentů. Noví operátoři umožňují začlenění hierarchie účtů při vytváření segmentů.
- [Příjem dat](data-sources.md): Všechny funkce v této oblasti jsou stejné pro firemní účty a individuální zákazníky.
- [Sjednocení dat](data-unification.md): Všechny funkce v této oblasti jsou stejné pro firemní účty a individuální zákazníky.
- [Obohacení](enrichment-hub.md): Některé typy obohacení jsou k dispozici pouze pro jednotlivé scénáře zákazníků, zatímco jiné jsou k dispozici výhradně pro firemní účty.
- [Předpovědi a modely po vybalení](predictions-overview.md): Predikce úbytku transakcí obsahuje další kroky pro obchodní účty. Další předpovědi jsou k dispozici pouze pro jednotlivé zákazníky.
- [Aktivace a export](export-destinations.md): Exporty jsou k dispozici pro firemní účty a individuální zákazníky. Některé exporty vyžadují zvláštní konfiguraci a kontaktní informace promítnuté v podkladových segmentech, aby byly platné pro firemní účty.
- [Nastavení systému](system.md) a [správa uživatelů](permissions.md): Všechny funkce v této oblasti jsou stejné pro firemní účty a individuální zákazníky.

