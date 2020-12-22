---
title: Konfigurace systému v přehledech cílové skupiny
description: Další informace o nastavení systému ve funkci přehledů cílové skupiny v Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405395"
---
# <a name="system-configuration"></a>konfigurace systému,

Stránka **Systém** obsahuje čtyři karty: **Stav**, **Plán**, **O produktu** a **Obecné**.

> [!div class="mx-imgBorder"]
> ![Systémová stránka](media/system-tabs.png "Systémová stránka")

## <a name="status-tab"></a>Karta stavu

Karta **Stav** umožňuje sledovat průběh přijímání dat, exportování dat a několik důležitých procesů produktu. Zkontrolujte informace na této kartě pro zajištění úplnosti aktivních procesů.

Tato karta obsahuje stavové tabulky pro **Zdroje dat**, **Systémové procesy** a **Přípravu dat**. Každá tabulka sleduje **Název** úlohy a její odpovídající entity, **Stav** jejího posledního běhu a kdy proběhla **Poslední aktualizace**.

Podrobnosti o posledních několika bězích úlohy zobrazíte výběrem jejího názvu.

### <a name="status-types"></a>Typy stavu

Existuje šest typů stavů pro úkoly. Následující typy stavu se také zobrazují na stránkách *Párování*, *Sloučení*, *Zdroje dat*, *Segmenty*, *Opatření*, *Obohacení*, *Aktivity* a *Předpovědi*:

- **Zpracovává se:** Probíhá úkol. Stav se může změnit na Úspěšný nebo Neúspěšný.
- **Úspěšný:** Úloha byla úspěšně dokončena.
- **Přeskočeno:** Úloha byla přeskočena. Jeden nebo více následných procesů, na kterých tato úloha závisí, selhávají nebo jsou přeskočeny.
- **Selhání:** Zpracování úlohy se nezdařilo.
- **Zrušeno:** Zpracování bylo uživatelem zrušeno před dokončením.
- **Ve frontě:** Zpracování je ve frontě a začne, jakmile budou dokončeny všechny následné úkoly. Další informace naleznete v [Zásadách aktualizace](#refresh-policies).

### <a name="refresh-policies"></a>Zásady aktualizace

Tento seznam zobrazuje zásady aktualizace pro každý z hlavních procesů:

- **Zdroje dat:** Běží podle [nakonfigurovaného plánu](#schedule-tab). Nezávisí na žádném jiném procesu. Shoda závisí na úspěšném dokončení tohoto procesu.
- **Párování** Běží podle [nakonfigurovaného plánu](#schedule-tab). Závisí na zpracování zdrojů dat použitých v definici shody. Párování závisí na úspěšném dokončení tohoto procesu.
- **Sloučení**: Běží podle [nakonfigurovaného plánu](#schedule-tab). Závisí na úspěšném dokončení procesu párování. Segmenty, opatření, obohacení, vyhledávání, aktivity, předpovědi a příprava dat závisí na úspěšném dokončení tohoto procesu.
- **Segmenty**: Spouštěny ručně (jednorázová aktualizace) a podle [nakonfigurovaného plánu](#schedule-tab). Závisí na sloučení. Přehledy závisí na jeho zpracování.
- **Opatření**: Spouštěny ručně (jednorázová aktualizace) a podle [nakonfigurovaného plánu](#schedule-tab). Závisí na sloučení.
- **Aktivity**: Spouštěny ručně (jednorázová aktualizace) a podle [nakonfigurovaného plánu](#schedule-tab). Závisí na sloučení.
- **Obohacení**: Spouštěno ručně (jednorázová aktualizace) a podle [nakonfigurovaného plánu](#schedule-tab). Závisí na sloučení.
- **Vyhledávání**: Spouštěno ručně (jednorázová aktualizace) a podle [nakonfigurovaného plánu](#schedule-tab). Závisí na sloučení.
- **Připrava dat**: Běží podle [nakonfigurovaného plánu](#schedule-tab). Závisí na sloučení.
- **Přehledy**: Spouštěny ručně (jednorázová aktualizace) a podle [nakonfigurovaného plánu](#schedule-tab). Závisí na segmentech.

Vyberte stav úkolu a zobrazte podrobnosti o průběhu celé úlohy, ve které se nachází. Výše uvedené zásady aktualizace mohou pomoci pochopit, co můžete udělat pro splnění úkolu **Přeskočeno** nebo **Ve frontě**.

## <a name="schedule-tab"></a>Karta Plán

Pomocí karty **Plán** můžete naplánovat automatické aktualizace všech vašich [ingestovaných zdrojů dat](data-sources.md). Automatické aktualizace pomáhají zajistit, aby se aktualizace ze zdrojů dat projevily ve vašich sjednocených profilech zákazníků.

1. V přehledech cílové skupiny přejděte na **Správa** > **Systém** a vyberte kartu **Plán**.

2. Výchozí stav pro plánovanou aktualizaci je **Vypnuto**. Chcete-li povolit naplánované aktualizace, změňte přepínač v horní části obrazovky na **Zapnuto**.

3. Vyberte mezi aktualizacemi **Týdně** (výchozí) a **Denně**. Pokud chcete naplánovat týdenní aktualizace, vyberte jeden nebo více dní, ve kterých chcete aktualizaci spustit.

4. Nastavte své **Časové pásmo**, pak použijte rozbalovací nabídku **Čas** pro nastavení času aktualizace. Jakmile budete hotovi, zvolte tlačítko **Nastavit**. Pokud chcete naplánovat více aktualizací v jeden den, vyberte **Přidejte další čas**.

5. Výběrem možnosti **Uložit** se vaše změny uplatní.

## <a name="about-tab"></a>Karta O systému

Karta **Informace** obsahuje **Zobrazovaný název** vaší organizace, aktivní **ID prostředí**, **Oblast** a vaše **ID relace**. Pokud máte více než jedno pracovní prostředí, měli byste každému dát srozumitelný zobrazovaný název.

## <a name="general-tab"></a>Karta Obecné

Jsou dvě možnosti na kartě **Obecné**, **Jazyk** a **Formát země / regionu**.

Aplikace [podporuje řadu jazyků](supported-languages.md). Chcete-li změnit preferovaný jazyk, vyberte a **Jazyk** z rozevíracího seznamu.

Chcete-li změnit preferované formátování pro data, čas a čísla, použijte rozbalovací nabídku **Formát země / regionu**. Pod tímto polem se zobrazí náhled formátování. Když zvolíte nový jazyk, systém automaticky navrhne výběr.

Vyberte **Uložit** a potvrďte tak svůj výběr.

## <a name="api-usage-tab"></a>Karta využití rozhraní API

Najděte podrobnosti o využití rozhraní API v reálném čase a podívejte se, které události se v daném časovém období odehrály. Další informace viz [Příjem dat v reálném čase](real-time-data-ingestion.md).
