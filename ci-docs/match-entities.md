---
title: Podmínky shody pro sjednocení dat
description: Spárováním entit můžete vytvořit sjednocené profily zákazníků.
recommendations: false
ms.date: 10/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721513"
---
# <a name="match-conditions-for-data-unification"></a>Podmínky shody pro sjednocení dat

Tento krok sjednocení definuje pořadí párování a pravidla pro párování mezi entitami. Tento krok vyžaduje alespoň dvě entity.

> [!NOTE]
> Jakmile vytvoříte podmínky shody a vyberete **Další**, nemůžete odstranit vybranou entitu nebo atribut. V případě potřeby vyberte **Zpět** ke kontrole vybraných entit a atributů předtím, než budete pokračovat.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Zahrnutí rozšířených entit (Preview)

Pokud jste obohatili entity na úrovni zdroje dat, abyste pomohli zlepšit výsledky sjednocení, vyberte je. Další informace najdete v tématu [Rozšíření zdrojů dat](data-sources-enrichment.md). Pokud jste vybrali obohacené entity na stránce **Duplicitní záznamy**, nemusíte je znovu vybírat.

1. V horní části stránky **Podmínky shody** vyberte **Použít obohacené entity**.

1. V podokně **Používat rozšířené entity** vyberte jednu nebo více rozšířených entit.

1. Vyberte **Hotovo**.

## <a name="specify-the-match-order"></a>Určení pořadí párování

Každé párování sjednocuje dvě nebo více entit do jedné konsolidované entity. Zároveň uchovává jedinečné záznamy o zákaznících. Pořadí shody udává pořadí, ve kterém se systém pokusí záznamy spárovat.

> [!IMPORTANT]
> První entita je označována jako primární a slouží jako základ sjednocených profilů. K této entitě budou přidány další vybrané entity.
>
> Důležité poznámky:
>
> - Jako primární subjekt vyberte subjekt s nejúplnějšími a nejspolehlivějšími profilovými údaji o vašich zákaznících.
> - Vyberte entitu, která ma několik atrubutů společných s jinými entitami (například jméno, telefonní číslo nebo e-mailová adresa), jakožto primární entitu.

1. Na stránce **Odpovídající podmínky** pomocí šipek pro pohyb nahoru a dolů přesuňte entity v požadovaném pořadí nebo je přetáhněte. Například vyberte **eCommerceCustomers** jako primární entitu a **loyCustomers** jako druhou entitu.

1. Pokud chcete mít každý záznam v entitě jako jedinečného zákazníka bez ohledu na to, zda je nalezena shoda, vyberte **Zahrnou všechny záznamy**. Všechny záznamy v této entitě, které se neshodují se záznamy v jiných entitách, jsou zahrnuty do sjednoceného profilu. Záznamy, které nemají shodu, se nazývají singletony.
  
Primární entita *Contacts:eCommerce* je spárována s další entitou *CustomerLoyalty:Loyalty*. Pokud máte více než dvě entity, datová sada, která je výsledkem prvního kroku shody, se shoduje s následující entitou.

:::image type="content" source="media/m3_match.png" alt-text="Snímek obrazovky vybraného pořadí shody pro entity." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definování pravidel pro párování

Pravidla párováníí určují logiku, podle které bude přiřazen určitý pár entit. Pravidlo se skládá z jedné nebo více podmínek.

Upozornění vedle názvu entity znamená, že pro dvojici shody není definováno žádné pravidlo shody.

1. Vyberte **Přidat pravidlo** pro dvojici entit k definování pravidel shody.

1. V podokně **Přidat pravidlo** nakonfigurujte podmínky pro pravidlo.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Snímek podokna Přidat pravidlo":::

   - **Vyberte entitu/pole (první řádek)**: Vyberte entitu a atribut, která je pravděpodobně jedinečný pro zákazníka. Například telefonní číslo nebo e-mailová adresa. Vyvarujte se párování podle atributů typu aktivity. Například ID nákupu pravděpodobně nenajde shodu v jiných typech záznamů.

   - **Vyberte entitu/pole (druhý řádek)**: Vyberte atribut, který souvisí s atributem entity zadané v prvním řádku.

   - **Normalizovat**: Vyberte z následujících možností normalizace pro vybrané atributy.
     - **Číslice**: Převede jiné číselné systémy, například římské číslice, na arabské číslice. Z *VIII* se stane *8*.
     - **Symboly**: Odstraní všechny symboly a speciální znaky. Z *Head&Shoulder* se stane *HeadShoulder*.
     - **Text na malá písmena:** Převede všechny znaky na malá písmena. Z *VŠECHNA PÍSMENA VELKÁ a Název Případu* se stane *všechna písmena velká a název případu*.
     - **Typ (telefon, jméno, adresa, organizace)**: Standardizuje jména, tituly, telefonní čísla, adresy a organizace.
     - **Unicode na ASCII**: Převede zápis Unicode na znaky ASCII. Z */u00B2* se stane *2*.
     - **Mezera**: Odebere všechny mezery. Z *Ahoj světe* se stane *Ahojsvěte*.

   - **Přesnost**: Nastaví úroveň přesnosti pro tuto podmínku.
     - **Základní**: Vyberte jednu z možností *Nízká* (30 %), *Střední (60 %)*, *Vysoká (80 %)* a *Přesná (100 %)*. Vyberte **Přesný**, aby se shodovaly pouze záznamy, které se stoprocentně shodují.
     - **Vlastní**: Nastaví procento, kterému musí záznamy odpovídat. Systém bude párovat pouze záznamy splňující tuto prahovou hodnotu.

   - **Název**: Název pravidla.

1. Chcete-li přiřadit entity pouze v případě, že atributy splňují více podmínek, vyberte **Přidat** > **Přidat podmínku** pro přidání dalších podmínek k pravidlu shody. Podmínky jsou spojeny s logickým operátorem AND a jsou tedy prováděny pouze tehdy, jsou-li všechny splněny.

1. Případně zvažte pokročilé možnosti jako např. [výjimky](#add-exceptions-to-a-rule) nebo [vlastní podmínky shody](#specify-custom-match-conditions).

1. Vyberte **Hotovo** pro dokončení pravidla.

1. Volitelně [přidejte další pravidla](#add-rules-to-a-match-pair).

1. Klikněte na tlačítko **Další**.

> [!div class="nextstepaction"]
> [Další krok: Sjednocení polí](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Přidání pravidel pro spárování dvojice

Pravidla párování jsou sady podmínek. Pro párování entit podle podmínek založených na několika atributech přidejte další pravidla.

1. Vyberte **Přidat pravidlo** v entitě, do které chcete přidat pravidla.

1. Postupujte podle pokynů v části [Definování pravidel pro párování](#define-rules-for-match-pairs).

> [!NOTE]
> Na pořadí pravidel záleží. Porovnávací algoritmus se pokusí porovnat daný záznam zákazníka na základě vašeho prvního pravidla a pokračuje k druhému pravidlu, pouze pokud nebyly identifikovány žádné shody s prvním pravidlem.

## <a name="advanced-options"></a>Rozšířené možnosti

### <a name="add-exceptions-to-a-rule"></a>Přidání výjimek do pravidla

Ve většině případů párování entit vede k jedinečným zákaznickým profilům s konsolidovanými daty. Chcete-li řešit vzácné případy falešně pozitivních a falešně negativních výsledků, definujte výjimky pro pravidlo shody. Výjimky se uplatňují po zpracování pravidel shody a zabraňují spárování všech záznamů, které splňují kritéria výjimky.

Pokud například vaše pravidlo shody kombinuje příjmení, město a datum narození, systém by identifikoval dvojčata se stejným příjmením, která žijí ve stejném městě, jako stejný profil. Můžete zadat výjimku, která nespáruje profily, pokud křestní jména v entitách, které kombinujete, nejsou stejná.

1. V podokně **Upravit pravidlo** vyberte **Přidat** > **Přidat výjimku**.

1. Zadejte kritéria výjimky.

1. Pravidlo uložte kliknutím na tlačítko **Hotovo**.

### <a name="specify-custom-match-conditions"></a>Zadání vlastních podmínek párování

Zadejte podmínky, které přepíší výchozí logiku shody. K dispozici jsou čtyři možnosti:

|Možnost  |Description |Příklad  |
|---------|---------|---------|
|Vždy se shodovat     | Definuje hodnoty primárních klíčů, které se vždy shodují.         |  Vždy porovná řádek s primárním klíčem *12345* s řádkem s primárním klíčem *54321*.       |
|Nikdy se neshodovat     | Definuje hodnoty primárních klíčů, které se nikdy neshodují.        | Nikdy neporovná řádek s primárním klíčem *12345* s řádkem s primárním klíčem *54321*.        |
|Obejít            | Definuje hodnoty, které by měl systém ve fázi shody vždy ignorovat. |  Ignorujte hodnoty *11111* a *Neznámá* během shody.        |
|Mapování aliasů    | Definování hodnot, které by měl systém považovat za stejnou hodnotu.         | Považuje *Joe* za shodné s *Joseph*.        |

1. Vyberte **Vlastní**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Vlastní tlačítko":::

1. Vyberte **Vlastní typ** a vyberte **Stáhnout šablonu**. Přejmenujte šablonu bez použití mezer. Pro každou možnost shody použijte samostatnou šablonu.

1. Otevřete stažený soubor šablony a vyplňte podrobnosti. Šablona obsahuje pole pro určení entity a hodnoty primárního klíče entity, které mají být použity ve vlastní shodě. U názvů entit se rozlišují velká a malá písmena. Například pokud chcete, aby se primární klíč *12345* z entity *Prodej* vždy shodoval s primárním klíčem *34567* z entity *Kontakt*, vyplňte šablonu:
   - Entita 1: Prodej
   - Klíč entity 1: 12345
   - Entita 2: Kontakt
   - Klíč entity 2: 34567

   Stejný soubor šablony může určit vlastní záznamy shody z více entit.

   > [!NOTE]
   > Pokud chcete zadat vlastní párování pro odstranění duplicit v entitě, zadejte stejnou entitu jako Entita 1 a Entita 2 a nastavte různé hodnoty primárního klíče. Chcete-li použít vlastní párování, musíte pro entitu definovat alespoň jedno pravidlo odstranění duplicit.

1. Po přidání všech přepsání uložte soubor šablony.

1. Přejděte na **Data** > **Zdroje dat** a ingestujte soubory šablon jako nové entity.

1. Po nahrání souborů vyberte znovu možnost **Vlastní**. Vyberte požadované entity z rozbalovacího seznamu a vyberte **Hotovo**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Screenshot dialogového okna pro výběr přepsání v případě scénáře vlastní shody.":::

1. Použití vlastní shody závisí na možnosti shody, kterou chcete použít.

   - Pro **Vždy se shodovat** nebo **Nikdy se neshodovat** pokračujte dalším krokem.
   - Pro **Obejití** nebo **Mapování aliasů** vyberte **Upravit** v existujícím pravidlu shody nebo vytvořte nové pravidlo. V rozevíracím seznamu Normalizace vyberte možnost **Vlastní obejití** nebo **Mapování aliasů** a vyberte **Hotovo**.

1. Vyberte **Hotovo** na stránce **Vlastní** pro použití vlastní konfigurace shody.

   Každý zpracovaný soubor šablony je vlastní zdroj dat. Pokud jsou objeveny záznamy, které vyžadují speciální ošetření ohledně shody, aktualizujte příslušný zdroj dat. Aktualizace bude použita během dalšího procesu sjednocení. Například identifikujete dvojčata s téměř stejným jménem žijící na stejné adrese, která byla sloučena jako jedna osoba. Aktualizací zdroje dat identifikujete dvojčata jako samostatné, jedinečné záznamy.

> [!div class="nextstepaction"]
> [Další krok: Sjednocení polí](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
