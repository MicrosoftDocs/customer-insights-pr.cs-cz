---
title: Práce s obchodními účty
description: Přečtěte si o obchodních účtech jako o primární cílové skupině v Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303908"
---
# <a name="work-with-business-accounts"></a>Práce s obchodními účty

Dynamics 365 Customer Insights umožňuje konfigurovat prostředí pro různé primární cílové skupiny: jednotlivé spotřebitele (B2C) a obchodní účty (B2B). Ve scénářích B2C jsou data soustředěna kolem jednotlivců. U B2B jsou primární cílovou skupinou obchodní účty – organizace nebo společnosti – a kontakty. Tento článek vám pomůže začít s prostředím pro obchodní zákaznické účty. Uvádí rozdíly pro oblasti funkcí v Customer Insights v závislosti na zaměření na prostředí. Další informace o rozdílech najdete v dokumentech oblastí funkcí. 

## <a name="create-an-environment-for-business-accounts"></a>Vytvoření prostředí pro obchodní účty

Správci mohou [vytvořit prostředí ve stávající organizaci](create-environment.md). Krok v procesu vytváření nového prostředí žádá správce pro primární cílovou skupinu prostředí. V případě, že se jedná o úvodní nastavení po zakoupení licence, průvodce vám pomůže s vytvořením prvního prostředí.

Pak můžete [přijímat data](data-sources.md) pro obchodní účty a související kontakty jako zdroje dat ze všech podporovaných zdrojů.

 [Sjednoťte](data-unification.md) data účtu následované kontaktními údaji za účelem propojení entit kontaktů a účtu.

## <a name="switch-between-primary-target-audience"></a>Přepínání mezi primární cílovou skupinou

Pokud vaše organizace spravuje prostředí pro jednotlivé zákazníky a obchodní účty, můžete pomocí přepínače v levém podokně vybrat primární cíl cílovou skupinu.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Přepínač pro změnu primární cílové skupiny mezi jednotlivými zákaznickými a firemními účty.":::

## <a name="supported-feature-areas"></a>Podporované oblasti funkce

- [Aktivity](activities.md): Podpora účtů a souvisejících kontaktů k vytváření aktivit a jejich zobrazení na časové ose.
- [Vztahy](relationships.md): Průvodce aktivitami pomáhá vytvářet vztahy mezi entitami, aby zobrazení účtu mohlo zobrazovat všechny aktivity z kontaktů. Kontakty lze zobrazit podrobněji, aby bylo možné zobrazit zobrazení kontaktů, a pro agregaci aktivit účtu lze použít hierarchie.
- [Míry](measures.md): Podporuje opatření vytvořená z nástroje pro tvorbu měření jedním výpočtem. Volitelné nastavení umožňuje souhrn pro podúčty při vytváření měr.
- [Segmenty](segments.md): Podporuje segmenty, které jsou vytvořeny od začátku pomocí nástroje pro tvorbu segmentů. Segmenty mohou být založeny na účtech nebo kontaktech.
- [Příjem dat](data-sources.md): Všechny funkce v této oblasti jsou stejné pro firemní účty a individuální zákazníky.
- Sjednocení dat B2-B je velmi podobné sjednocení dat B2C, ale zahrnuje další krok sjednocení kontaktů po sjednocení účtu. Viz [Obchodní účty (B2B)](data-unification.md).
- [Obohacení](enrichment-hub.md): Některé typy obohacení jsou k dispozici pouze pro jednotlivé scénáře zákazníků, zatímco jiné jsou k dispozici výhradně pro firemní účty.
- [Předpovědi a modely po vybalení](predictions-overview.md): Predikce úbytku transakcí obsahuje další kroky pro obchodní účty. Další předpovědi jsou k dispozici pouze pro jednotlivé zákazníky.
- [Aktivace a export](export-destinations.md): Exporty jsou k dispozici pro firemní účty a individuální zákazníky. Některé exporty vyžadují zvláštní konfiguraci a kontaktní informace promítnuté v podkladových segmentech, aby byly platné pro firemní účty.
- [Nastavení systému](system.md) a [správa uživatelů](permissions.md): Všechny funkce v této oblasti jsou stejné pro firemní účty a individuální zákazníky.

[!INCLUDE [footer-include](includes/footer-banner.md)]
