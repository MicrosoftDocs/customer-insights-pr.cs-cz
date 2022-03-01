---
title: Začínáme s možnostmi přehledu zapojení
description: Přehled zdrojů nápovědy, abyste mohli rychle začít.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405350"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Začínáme s možnostmi přehledu zapojení Dynamics 365 Customer Insights (Public Preview)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkce přehledy zapojení umožňuje shromažďovat a měřit chování zákazníků na vašem webu. Integruje se s možností přehledu cílové skupiny, takže vedle přehledů profilů zákazníků můžete vidět bohatou analýzu chování v reálném čase. Odkazy v tomto článku vám pomohou rychle nakonfigurovat a nastavit vaše prostředí.

## <a name="step-1-review-prerequisites"></a>Krok 1: Kontrola předpokladů

Nejprve musíte mít aktivní uživatelský účet Microsoft Azure Active Directory. Pak než si nastavíte pracovní prostor přehledů zapojení, přečtěte si následující články.

- Přečtěte si a odsouhlaste [podmínky služby](terms-of-service.md) společnosti Microsoft.  
- Přečtěte si článek [Správa souborů cookie a souhlas uživatele](user-consent-storage.md). Po přečtení tohoto článku posuďte, zda potřebujete aktualizovat oznámení o souhlasu uživatele. Pokud jste dříve neměli žádné „nepodstatné“ soubory cookie, budete pravděpodobně muset aktualizovat zásady svého webu.
- Přečtěte si [glosář](glossary.md) pro rychlý úvod do klíčových pojmů a konceptů.

## <a name="step-2-explore-engagement-insights"></a>Krok 2: Prozkoumejte přehledy zapojení

Při první návštěvě přehledů zapojení můžete nakonfigurovat nastavení, zkontrolovat zásady a prozkoumat produkt.

1. Přihlaste se do [portál funkce přehledu zapojení](https://pi.dynamics.com) pomocí uživatelského účtu Microsoft Azure Active Directory. (Může to být váš školní nebo pracovní účet.)

1. Vyberte svou oblast a pomocí zaškrtávacího políčka označte, zda se chcete přihlásit k přijímání aktualizací a nabídek prostřednictvím e-mailu.

1. Přečtěte si **Podmínky použití přehledů zapojení (Preview)** a **Prohlášení o zásadách ochrany osobních údajů** a potom vyberte **Prozkoumat ukázku**, abyste je přijali.

1. Prozkoumejte produkt pomocí sady ukázkových dat.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Krok 3: Nastavte pracovní prostor a přidejte kód na svůj web

Pracovní prostor je místo, kde můžete zobrazit aktivitu uživatelů v reálném čase a ukládat a spravovat zprávy. Přidejte kód na svůj web a začněte sbírat *události*, údaje o aktivitě, které přicházejí od uživatelů.

1. [Vytvořte pracovní prostor](create-workspace.md) a přidejte členy.

1. [Přidejte kód na web](instrument-website.md) nebo do [mobilní aplikace](developer-resources.md#capture-events-from-mobile-apps), abyste mohli zobrazit aktivitu uživatelů přicházejících do vašeho pracovního prostoru.

1. Zobrazte [sestavu v reálném čase](view-reports.md) zobrazující aktivní uživatele podle prohlížeče, zařízení, operačního systému, umístění a jazyka. Můžete také vytvářet [vlastní sestavy](custom-reports.md) k vytvoření vlastních vizualizací.
    
## <a name="step-4-export-data-to-other-channels"></a>Krok 4: Exportujte data do jiných kanálů

Můžete vytvářet *upřesněné události* (virtuální pohled) vašich webových analytických dat. Poté filtrujte a exportujte data do Azure Data Lake Storage. Exportovaná data můžete přijmout jako zdroj dat. Více informací najdete v části [Vytvoření propojení mezi přehledy cílových skupin a přehledy zapojení](integrate-audience-insights-engagement-insights.md)

1. [Vytvářejte upřesněné události](refined-events.md) pro export.

1. [Exportujte data](export-events.md) do Data Lake Storage.

1. Zjistěte, jak [odstranit a exportovat data událostí obsahující osobní údaje](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Krok 5: Zůstaňte ve spojení

Vážíme si vaší aktivní účasti a plánujeme zohlednit veškerou relevantní zpětnou vazbu při vývoji budoucích verzí. Sdělte nám svůj názor a nahlaste problémy jedním z těchto kanálů:
- [Komunita](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Poskytnutí názorů](https://go.microsoft.com/fwlink/?linkid=2143222)
- [žádost o podporu](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
