---
title: Konfigurace systému v přehledech cílové skupiny
description: Další informace o nastavení systému ve funkci přehledů cílové skupiny v Dynamics 365 Customer Insights.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2af8728009b4f1d53ebc2557bab8c79537a0dc5dda54477493ab1ad16f3f9a8a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035889"
---
# <a name="system-configuration"></a>konfigurace systému,

Stránka **Systém** obsahuje následující karty:
- [Průběh](#status-tab)
- [Naplánovat](#schedule-tab)
- [Využití rozhraní API](#api-usage-tab)
- [O uživateli](#about-tab)
- [Obecná](#general-tab)

> [!div class="mx-imgBorder"]
> ![Systémová stránka.](media/system-tabs.png "Systémová stránka")

## <a name="status-tab"></a>Karta stavu

Karta **Stav** umožňuje sledovat průběh příjmu dat, exportu dat a několik dalších důležitých procesů produktu. Zkontrolujte informace na této kartě pro zajištění úplnosti aktivních procesů.

Tato karta obsahuje tabulky se stavem a informacemi o zpracování pro různé procesy. Každá tabulka sleduje **Název** úlohy a její odpovídající entity, **Stav** jejího posledního běhu a kdy proběhla **Poslední aktualizace**.

Podrobnosti o posledních několika bězích úlohy zobrazíte výběrem jejího názvu.

### <a name="status-types"></a>Typy stavu

Existuje šest typů stavů pro úkoly. Následující typy stavu se také zobrazují na stránkách *Párování*, *Sloučení*, *Zdroje dat*, *Segmenty*, *Opatření*, *Obohacení*, *Aktivity* a *Předpovědi*:

- **Zpracovává se:** Probíhá úkol. Stav se může změnit na Úspěšný nebo Neúspěšný.
- **Úspěšný:** Úloha byla úspěšně dokončena.
- **Přeskočeno:** Úloha byla přeskočena. Jeden nebo více následných procesů, na kterých tato úloha závisí, selhávají nebo jsou přeskočeny.
- **Selhání:** Zpracování úlohy se nezdařilo.
- **Zrušeno:** Zpracování bylo uživatelem zrušeno před dokončením.
- **Ve frontě:** Zpracování je ve frontě a začne po dokončení všech předcházejících úkolů. Další informace naleznete v [Zásadách aktualizace](#refresh-policies).

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

Vyhledejte podrobnosti o použití rozhraní API v reálném čase a podívejte se, které události se udály v daném časovém rámci. V rozevírací nabídce **Vyberte časový rámec** vyberte časový rámec. 

Část **Využití rozhraní API** obsahuje tři sekce: 
- **Volání rozhraní API** – graf, který vizualizuje agregovaný počet volání do rozhraní API ve vybraném časovém rámci.

- **Přenos dat** – graf, který zobrazuje množství dat, která byla přenesena prostřednictvím rozhraní API ve vybraném časovém rámci.

-  **Operace** – tabulka s řádky pro každou dostupnou operaci rozhraní API a podrobnostmi o využití operací. Výběrem názvu operace můžete přejít na [reference k rozhraním API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operace, které používají [příjem dat v reálném čase](real-time-data-ingestion.md), obsahují tlačítko se symbolem dalekohledu pro zobrazení využití rozhraní API v reálném čase. Výběrem tohoto tlačítka otevřete postranní panel obsahující podrobnosti o využití rozhraní API v reálném čase v aktuálním prostředí.   
   Pomocí pole **Seskupit podle** v podokně **Využití rozhraní API v reálném čase** vyberte, jak nejlépe prezentovat své interakce v reálném čase. Data lze seskupit podle metody rozhraní API, kvalifikovaného názvu entity (přijaté entity), autora (zdroj události), výsledku (úspěch nebo selhání) nebo kódů chyb. Data jsou k dispozici jako graf historie a jako tabulka.


[!INCLUDE[footer-include](../includes/footer-banner.md)]