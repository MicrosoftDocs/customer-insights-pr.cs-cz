---
title: Konfigurace systému v přehledech cílové skupiny
description: Další informace o nastavení systému ve funkci přehledů cílové skupiny v Dynamics 365 Customer Insights.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1b790106f8b9617d0c1f244e1d15a74c7ef9a82b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732353"
---
# <a name="system-configuration"></a>Konfigurace systému

Chcete-li získat přístup ke konfiguraci systému v přehledech cílových skupin, na levém navigačním panelu vyberte **Správa** > **Systém**, čímž zobrazíte seznam systémových úloh a procesů.

Stránka **Systém** obsahuje následující karty:
- [Průběh](#status-tab)
- [Naplánovat](#schedule-tab)
- [Využití rozhraní API](#api-usage-tab)
- [O uživateli](#about-tab)
- [Obecná](#general-tab)
- [Zabezpečení](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Karty Nastavení na systémové stránce.":::

## <a name="status-tab"></a>Karta stavu

Karta **Stav** umožňuje sledovat průběh úloh, příjmu dat, exportu dat a několik dalších důležitých procesů produktu. Projděte si informace na této kartě, abyste se ujistili, že vaše aktivní úlohy a procesy jsou dokončeny.

Tato karta obsahuje tabulky se stavem a informacemi o zpracování pro různé procesy. Každá tabulka sleduje **Název** úlohy a její odpovídající entity, **Stav** jejího posledního běhu a kdy proběhla **Poslední aktualizace**. Podrobnosti o posledních několika spuštěních můžete zobrazit výběrem názvu úlohy nebo procesu. 

Výběrem stavu vedle úlohy nebo procesu ve sloupci **Stav** otevřete podokno **Podrobnosti o průběhu**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Systémové podokno podrobností o průběhu":::

### <a name="status-definitions"></a>Definice stavu

Systém používá pro úlohy a procesy následující stavy:

|Průběh  |Definice  |
|---------|---------|
|Zrušeno |Zpracování bylo před dokončením zrušeno uživatelem.   |
|Nezdařilo se   |Při přijímání dat došlo k chybám.         |
|Chyba  |Zpracování selhalo.  |
|Nezahájeno   |Zdroj dat zatím nemá žádná ingestovaná data nebo je stále v režimu konceptu.         |
|Zpracování  |Úloha nebo proces probíhá.  |
|Probíhá aktualizace    |Probíhá příjem dat. Tuto operaci můžete zrušit výběrem **Přestat obnovovat** v sloupci **Akce**. Zastavením aktualizace zdroje dat se vrátíte do posledního stavu obnovy.       |
|Přeskočena  |Úloha nebo proces byl přeskočen. Jeden nebo více následných procesů, na kterých tato úloha závisí, selhávají nebo jsou přeskočeny.|
|Úspěch  |Úloha nebo proces byl úspěšně dokončen. U zdrojů dat označuje, že data byla úspěšně přijata, pokud je ve sloupci **Aktualizováno** uveden čas.|
|Zařazeno do fronty | Zpracování je zařazeno do fronty a bude zahájeno, jakmile budou dokončeny všechny upstreamové úlohy a procesy. Další informace najdete v tématu [Aktualizace procesů](#refresh-processes).|

### <a name="refresh-processes"></a>Procesy aktualizací

Aktualizace úloh a procesů se spouští podle [konfigurovaného plánu](#schedule-tab). 

|Zpracovat  |Popis  |
|---------|---------|
|Aktivita  |Spouští se ručně (jednorázová aktualizace). Závisí na procesu sloučení. Přehledy závisí na jeho zpracování.|
|Propojení analýzy |Spouští se ručně (jednorázová aktualizace). Závisí na segmentech.  |
|Příprava analýzy |Spouští se ručně (jednorázová aktualizace). Závisí na segmentech.  |
|Příprava dat   |Závisí na sloučení.   |
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

Na kartě **Obecné** můžete změnit jazyk a formát země/oblasti.

Řešení Customer Insights [podporuje mnoho jazyků](/dynamics365/get-started/availability). Aplikace používá vaše jazykové preference k zobrazení prvků, jako je nabídka, text štítku a systémové zprávy ve vašem upřednostňovaném jazyce.

Importovaná data a informace, které jste zadali ručně, se nepřekládají.

### <a name="update-the-settings"></a>Aktualizace nastavení

Chcete-li změnit preferovaný jazyk, vyberte a **Jazyk** z rozevíracího seznamu.

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

## <a name="security-tab"></a>Karta Zabezpečení

Karta **Zabezpečení** umožňuje propojit a spravovat svůj vlastní [trezor klíčů Azure](/azure/key-vault/general/basic-concepts) k prostředí.
Vyhrazený trezor klíčů lze použít k vytvoření a použití tajných kódů na hranici dodržování předpisů organizace. Přehledy cílové skupiny mohou použít tajné kódy v Azure Key Vault pro [nastavení připojení](connections.md) se systémy třetích stran.

Další informace viz téma [Použití vlastního trezoru klíčů Azure](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
