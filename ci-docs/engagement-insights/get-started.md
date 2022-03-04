---
title: Začínáme s možnostmi přehledu zapojení
description: Přehled zdrojů nápovědy, abyste mohli rychle začít.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225536"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Začínáme s možnostmi přehledu zapojení Dynamics 365 Customer Insights (Public Preview)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkce přehledy zapojení umožňuje shromažďovat a měřit chování zákazníků na vašem webu. Integruje se s možností přehledu cílové skupiny, takže vedle přehledů profilů zákazníků můžete vidět bohatou analýzu chování v reálném čase. Odkazy v tomto článku vám pomohou rychle nakonfigurovat a nastavit vaše prostředí.

## <a name="step-1-review-prerequisites"></a>Krok 1: Kontrola předpokladů

Nejprve musíte mít aktivní uživatelský účet Microsoft Azure Active Directory (AAD). Pak než si nastavíte pracovní prostor přehledů zapojení, přečtěte si následující články.

- Přečtěte si a odsouhlaste [podmínky služby](terms-of-service.md) společnosti Microsoft.  
- Přečtěte si článek [Správa souborů cookie a souhlas uživatele](user-consent-storage.md). Poté zhodnoťte, zda je třeba aktualizovat oznámení o souhlasu uživatele. Pokud jste dříve neměli žádné „nepodstatné“ soubory cookie, budete pravděpodobně muset aktualizovat zásady svého webu.
- Přečtěte si [glosář](glossary.md) pro rychlý úvod do klíčových pojmů a konceptů.

## <a name="step-2-explore-engagement-insights"></a>Krok 2: Prozkoumejte přehledy zapojení

Při první návštěvě přehledů zapojení můžete konfigurovat nastavení, kontrolovat zásady a prozkoumávat funkci.

1. Přihlaste se na [portál funkcí přehledů zapojení](https://home.ci.ai.dynamics.com/app/engagement-insights) pomocí vašeho uživatelského účtu Microsoft AAD (školního nebo pracovního).

1. Vyberte svou oblast a zaškrtněte políčko, pokud se chcete přihlásit k odběru novinek a nabídek e-mailem.

1. Zkontrolujte **podmínky použití funkce přehledů zapojení (náhled)** a **prohlášení o ochraně osobních údajů** a poté vyberte **Prozkoumat ukázku** pro přijetí tohoto nastavení.

1. Prozkoumejte produkt pomocí sady ukázkových dat.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Krok 3: Vytvořte pracovní prostor a vytvořte sestavy

Pracovní prostor je místo, kde můžete v reálném čase sledovat aktivitu uživatelů a ukládat a spravovat sestavy. Přidejte kód na svůj web a začněte sbírat *události*, údaje o aktivitě, které přicházejí od uživatelů.

1. [Vytvořte pracovní prostor](create-workspace.md) a přidejte členy.

1. Přidejte kód na [web](instrument-website.md) nebo do [mobilní aplikace](developer-resources.md#capture-events-from-mobile-apps), abyste mohli zobrazit aktivitu uživatelů přicházejících do vašeho pracovního prostoru.

1. Podívejte se na [sestavu v reálném čase](view-reports.md), která zobrazuje aktivní uživatele podle prohlížeče, zařízení, operačního systému, místa a jazyka. Můžete také vytvářet [vlastní sestavy](custom-reports.md) k vytvoření vlastních vizualizací.

1. Vytvořte [dimenze](dimensions.md) pro třídění návštěvníků podle nových a vracejících se uživatelů, [metriky](metrics.md) na pomoc pro lepší pochopení chování uživatelů a [segmenty](segments.md) k identifikaci podmnožin návštěvníků na základě charakteristik nebo interakcí na webových stránkách.
    
## <a name="step-4-export-data-to-other-channels"></a>Krok 4: Exportujte data do jiných kanálů

Můžete vytvářet *upřesněné události* (virtuální pohled) vašich webových analytických dat. Poté filtrujte a exportujte data do Azure Data Lake Storage. Exportovaná data můžete přijmout jako zdroj dat.

1. [Vytvářejte upřesněné události](refined-events.md) pro export.

1. [Exportujte data](export-events.md) do Azure Data Lake Storage.

1. [Vytvořte propojení mezi přehledy cílových skupin a přehledy zapojení](integrate-audience-insights-engagement-insights.md) a sdílejte data mezi těmito dvěma funkcemi.

1. [Rozpoznání webových událostí od dříve ověřených uživatelů](unknown-to-known.md) pomocí funkce **Od neznámých ke známým**.

1. Zjistěte, jak [odstranit a exportovat data událostí obsahující osobní údaje](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Krok 5: Vytvoření a správa trychtýřových sestav

Trychtýřová sestava shromažďuje informace o krocích, ke kterým dojde během cesty zákazníka prostřednictvím vašeho webu nebo mobilní aplikace. Kromě vytváření předdefinovaných profilových sestav a vlastních přehledů můžete vytvořit také trychtýřovou sestavu, která identifikuje cesty, kterými se vaši zákazníci vydají před nákupem. 

1. [Vytvořte trychtýřovou sestavu](funnel-reports.md) pro informování o rozhodnutích a identifikaci oblasti pro optimalizaci a vylepšení procesů.

1. Vytvářejte přehledy vícekanálových trychtýřových sestav, jakmile svou mobilní aplikaci vybavíte přehledy zapojení [Android SDK](get-started-android.md) nebo [iOS SDK](get-started-ios.md).

1. Pomocí [trychtýřových přehledů](funnel-reports.md#funnel-insights) získáte hlubší vhled do chování zákazníků ohledně kroků v trychtýřové sestavě.
 
## <a name="step-6-stay-connected"></a>Krok 6: Zůstaňte ve spojení

Vážíme si vaší aktivní účasti a při vývoji budoucích verzí zohledňujeme veškerou relevantní zpětnou vazbu. Sdělte nám svůj názor a nahlaste problémy jedním z těchto kanálů:
- [Komunita](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Poskytnutí názorů](https://go.microsoft.com/fwlink/?linkid=2143222)
- [žádost o podporu](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
