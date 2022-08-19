---
title: Zobrazení konfigurace systému
description: Informace o nastavení systému v Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246239"
---
# <a name="view-system-configuration"></a>Zobrazení konfigurace systému

Zobrazení systémových informací, stavu systému a využití API.

## <a name="view-api-usage"></a>Zobrazení využití API

Zobrazte podrobnosti o použití rozhraní API v reálném čase a podívejte se, které události se udály v daném časovém rámci.

1. Jděte na **Správa** > **Systém** a vyberte kartu **Použití rozhraní API**.

1. **Vyberte časový rámec** k zobrazení.

   Stránka **Využití rozhraní API** obsahuje tři sekce:

   - **Volání rozhraní API** – graf, který vizualizuje agregovaný počet volání do rozhraní API ve vybraném časovém rámci.
   - **Přenos dat** – graf, který zobrazuje množství dat, která byla přenesena prostřednictvím rozhraní API ve vybraném časovém rámci.
   - **Operace** – tabulka s řádky pro každou dostupnou operaci rozhraní API a podrobnostmi o využití operací. Můžete vybrat název operace a přejít na [reference k rozhraním API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operace, které používají [příjem dat v reálném čase](real-time-data-ingestion.md), obsahují symbol dalekohledu pro zobrazení využití rozhraní API v reálném čase.

   1. Výběrem dalekohledu otevřete podokno **použití rozhraní v reálném čase** obsahující podrobnosti o operaci.
   1. **Vyberte časový rámec** k zobrazení.
   1. Pomocí pole **Seskupit podle** vyberte, jak nejlépe prezentovat své interakce v reálném čase. Seskupte data podle **metody**, **kvalifikovaného názvu entity** (spotřebované entity), **Vytvořil(a)** (zdroj události), **Výsledek** (Úspěch nebo selhání) nebo **Kódy chyb**. Data jsou k dispozici jako graf historie a jako tabulka.

## <a name="view-system-information"></a>Zobrazení informací o systému

Zobrazte prostředí zobrazované jméno, ID, oblast, typ a ID relace.

1. Jděte na **Správa** > **Systém** a vyberte kartu **O programu**.

1. Chcete-li zobrazit jazyk a zemi/oblast, vyberte kartu **Obecné**.

### <a name="update-preferred-language-or-countryregion"></a>Aktualizujte preferovaný jazyk nebo zemi/oblast

Řešení Customer Insights [podporuje mnoho jazyků](/dynamics365/get-started/availability). Aplikace používá vaše jazykové preference k zobrazení prvků, jako je nabídka, text štítku a systémové zprávy ve vašem upřednostňovaném jazyce.

Importovaná data a informace, které jste zadali ručně, se nepřekládají.

1. Jděte na **Správa** > **Systém** a vyberte kartu **Obecné**.

1. Chcete-li změnit preferovaný jazyk, vyberte a **Jazyk** z rozevíracího seznamu.

1. Chcete-li změnit preferované formátování pro data, čas a čísla, použijte rozbalovací nabídku **Formát země / regionu**. Zobrazí se náhled formátování. Když zvolíte nový jazyk, systém automaticky navrhne výběr.

1. Vyberte **Uložit**.

## <a name="view-system-status"></a>Zobrazit stav systému

Sledujte průběh úloh, příjmu dat, exportu dat a několik dalších důležitých procesů produktu. Projděte si informace, abyste se ujistili, že vaše aktivní úlohy a procesy jsou dokončeny.

1. Jděte na **Správa** > **Systém** a vyberte kartu **Stav**.

   Zobrazí se informace o stavu a zpracování pro různé procesy. Zobrazte **Název** úlohy a její odpovídající entity, **Stav** jejího posledního běhu a kdy proběhla **Poslední aktualizace**.

1. Chcete-li zobrazit podrobnosti o posledních několika spuštěních, vyberte název úlohy nebo procesu.

1. Chcete-li zobrazit podrobnosti o pokroku úkolu, vyberte stav. Zobrazí se podokno **Podrobnosti průběhu**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Systémové podokno podrobností o průběhu":::

1. Chcete-li zobrazit podrobnosti o průběhu všech úkolů, vyberte **Celý pracovní postup**.

### <a name="status-definitions"></a>Definice stavu

Systém používá pro úlohy a procesy následující stavy:

|Status  |definice  |
|---------|---------|
|Zrušeno |Úkol nebo proces byly uživatelem zrušeny před dokončením.   |
|Nezdařilo se   |Úkol nebo proces narazil na chyby.         |
|Chyba  |Úkol nebo proces selhal.  |
|Nezahájeno   |Zdroj dat zatím nemá žádná ingestovaná data nebo je úkol stále v režimu konceptu.         |
|Zpracování  |Úloha nebo proces probíhá.  |
|Probíhá aktualizace    |Úloha nebo proces probíhá. Chcete-li tuto operaci zrušit, vyberte **Aktualizace** a **Zrušit úlohu**. Zastavením aktualizace úkolu nebo procesu se vrátíte do posledního stavu obnovy.       |
|Přeskočena  |Úloha nebo proces byl přeskočen. Jeden nebo více následných procesů, na kterých tato úloha závisí, selhávají nebo jsou přeskočeny.|
|Úspěch  |Úloha nebo proces byl úspěšně dokončen. U zdrojů dat označuje, že data byla úspěšně přijata, pokud je ve sloupci **Aktualizováno** uveden čas.|
|Zařazeno do fronty | Zpracování je zařazeno do fronty a bude zahájeno, jakmile budou dokončeny všechny upstreamové úlohy a procesy. Další informace najdete v tématu [Aktualizace procesů](#refresh-processes).|

### <a name="refresh-processes"></a>Procesy aktualizací

Aktualizace úloh a procesů se spouští podle [konfigurovaného plánu](schedule-refresh.md).

|Zpracovat  |Popis  |
|---------|---------|
|Aktivita  |Spouští se ručně (jednorázová aktualizace). Závisí na procesu sloučení. Přehledy závisí na jeho zpracování.|
|Propojení analýzy |Spouští se ručně (jednorázová aktualizace). Závisí na segmentech.  |
|Příprava analýzy |Spouští se ručně (jednorázová aktualizace). Závisí na segmentech.  |
|Příprava dat   |Ke spuštění potřebuje entitu. Zdroj dat entity závisí na příjmu. Rozšířené entity závisí na rozšíření. Entita Zákazník závisí na sloučení.  |
|Zdroje dat   |Nezávisí na žádném jiném procesu. Shoda závisí na úspěšném dokončení tohoto procesu.  |
|Rozšíření   |Spouští se ručně (jednorázová aktualizace). Závisí na procesu sloučení. |
|Cíle exportů |Spouští se ručně (jednorázová aktualizace). Závisí na segmentech.  |
|Přehledy |Spouští se ručně (jednorázová aktualizace). Závisí na segmentech.  |
|Analytické nástroje   |Závisí na sloučení.   |
|Párování |Závisí na zpracování zdrojů dat použitých v definici shody.      |
|Míry  |Spouští se ručně (jednorázová aktualizace). Závisí na procesu sloučení.  |
|Sloučení   |Závisí na úspěšném dokončení procesu párování. Segmenty, opatření, obohacení, vyhledávání, aktivity, předpovědi a příprava dat závisí na úspěšném dokončení tohoto procesu.   |
|Profily   |Spouští se ručně (jednorázová aktualizace). Závisí na procesu sloučení. |
|Vyhledávat   |Spouští se ručně (jednorázová aktualizace). Závisí na procesu sloučení. |
|Segmenty  |Spouští se ručně (jednorázová aktualizace). Závisí na procesu sloučení. Přehledy závisí na jeho zpracování.|
|Systémová   |Závisí na úspěšném dokončení procesu párování. Segmenty, opatření, obohacení, vyhledávání, aktivity, předpovědi a příprava dat závisí na úspěšném dokončení tohoto procesu.   |
|Uživatelská  |Spouští se ručně (jednorázová aktualizace). Závisí na entitách.  |

Výběrem stavu procesu zobrazíte podrobnosti o průběhu celé úlohy, ve které byl. Výše popsané procesy aktualizací vám pomohou lépe pochopit, co můžete dělat s úlohami nebo procesy ve stavu **Přeskočeno** nebo **Ve frontě**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
