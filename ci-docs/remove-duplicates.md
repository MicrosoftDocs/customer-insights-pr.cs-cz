---
title: Odstranění duplicit před sjednocením dat
description: Druhým krokem v procesu sjednocení je výběr záznamu, který se má zachovat, když jsou nalezeny duplikáty.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304465"
---
# <a name="remove-duplicates-before-unifying-data"></a>Odstranění duplicit před sjednocením dat

Tento volitelný krok sjednocení umožňuje nastavit pravidla pro eliminaci duplicitních záznamů **v rámci** entity. Deduplikace identifikuje více záznamů pro zákazníka a vybere nejlepší záznam k uchování (na základě základních předvoleb sloučení) nebo sloučí záznamy do jednoho (na základě pokročilých předvoleb sloučení). Zdrojové záznamy se propojí se sloučeným záznamem s alternativními ID. Pokud pravidla nejsou nakonfigurována, použijí se systémem definovaná pravidla.

## <a name="default-deduplication"></a>Výchozí deduplikace

Pokud nejsou přidána žádná pravidla deduplikace, použijí se pravidla definovaná systémem.

- Primární klíč je deduplikován.
  U všech záznamů se stejným primárním klíčem vyhrává **nejvíce vyplněný** záznam (s nejmenším počtem hodnot null).
- Na entitu se použijí všechna pravidla pro párování mezi entitami.
  Například: V kroku shody, pokud je entita A porovnána s entitou B zapnutá u *FullName* a *DateofBirth*, pak je entita A také deduplikována pomocí *FullName* a *DateofBirth*. Protože *FullName* a *DateofBirth* jsou platné klíče pro identifikaci zákazníka v entitě A, tyto klíče jsou platné i pro identifikaci duplicitních odběratelů v entitě A.

## <a name="include-enriched-entities-preview"></a>Zahrnutí rozšířených entit (Preview)

Pokud jste obohatili entity na úrovni zdroje dat, abyste pomohli zlepšit výsledky sjednocení, vyberte je. Další informace najdete v tématu [Rozšíření zdrojů dat](data-sources-enrichment.md).

1. V horní části stránky **Duplicitní záznamy** vyberte **Použít obohacené entity**.

1. V podokně **Používat rozšířené entity** vyberte jednu nebo více rozšířených entit.

1. Vyberte **Hotovo**.

## <a name="define-deduplication-rules"></a>Definování odstranění duplicit

1. Na stránce **Duplikovat záznamy** vyberte entitu a vyberte **Přidat pravidlo** k definování pravidel deduplikace.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Screenshot stránky duplicitních záznamů se zvýrazněnou entitou a zobrazeným pravidlem Přidat"  lightbox="media/m3_duplicates_showmore.png":::

   1. V podokně **Přidat pravidlo** zadejte následující informace:
      - **Vyberte pole**: Vyberte ze seznamu dostupných polí entity, u které chcete zkontrolovat duplikáty. Vyberte pole, která jsou potenciálně jedinečná pro každého jednotlivého zákazníka. Například e-mailová adresa nebo kombinace jména, města a telefonního čísla.
      - **Normalizovat**: Vyberte z následujících možností normalizace pro vybrané atributy.
        - **Číslice**: Převede jiné číselné systémy, například římské číslice, na arabské číslice. Z *VIII* se stane *8*.
        - **Symboly**: Odstraní všechny symboly a speciální znaky. Z *Head&Shoulder* se stane *HeadShoulder*.
        - **Text na malá písmena: Převede všechny znaky na malá písmena**. Z *VŠECHNA PÍSMENA VELKÁ a Název Případu* se stane *všechna písmena velká a název případu*.
        - **Typ (telefon, jméno, adresa, organizace)**: Standardizuje jména, tituly, telefonní čísla, adresy atd.
        - **Unicode na ASCII**: Převede zápis Unicode na znaky ASCII. Z */u00B2* se stane *2*.
        - **Mezera**: Odebere všechny mezery. Z *Ahoj světe* se stane *Ahojsvěte*.
      - **Přesnost**: Nastaví úroveň přesnosti pro tuto podmínku.
        - **Základní**: Vyberte jednu z možností *Nízká* (30 %), *Střední (60 %)*, *Vysoká (80 %)* a *Přesná (100 %)*. Vyberte **Přesný**, aby se shodovaly pouze záznamy, které se stoprocentně shodují.
        - **Vlastní**: Nastaví procento, kterému musí záznamy odpovídat. Systém bude párovat pouze záznamy splňující tuto prahovou hodnotu.
      - **Název**: Název pravidla.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Screenshot Přidat pravidlo pro odstranění duplikátů.":::

   1. Volitelně vyberte **Přidat** > **Přidat podmínku** pro přidání dalších podmínek do pravidla. Podmínky jsou spojeny s logickým operátorem AND a jsou tedy prováděny pouze tehdy, jsou-li všechny splněny.

   1. Volitelně **Přidat** > **Přidat výjimku** na [přidat výjimky do pravidla](match-entities.md#add-exceptions-to-a-rule). Výjimky se používají k řešení vzácných případů falešně pozitivních a falešně negativních výsledků.

   1. Vyberte **Hotovo** pro vytvoření pravidla.

1. Volitelně [přidejte další pravidla](#define-deduplication-rules).

1. Vyberte entitu a poté **Upravit předvolby sloučení**.

1. V podokně **Sloučit předvolby**:
   1. Vyberte jednu ze tří možností, jak určit, který záznam se má ponechat, pokud je nalezen duplikát:
      - **Nejvíce vyplněný**: Identifikuje záznam s nejvíce vyplněnými poli atributů jako vítězný záznam. Toto je výchozí možnost sloučení.
      - **Nejnovější**: Identifikuje vítězný záznam na základě největší aktuálnosti. Vyžaduje datum nebo číselné pole pro definování aktuálnosti.
      - **Nejdřívější**: Identifikuje vítězný záznam na základě nejmenší aktuálnosti. Vyžaduje datum nebo číselné pole pro definování aktuálnosti.

      V případě nerozhodného výsledku je vítězem záznam s hodnotou MAX(PK) nebo vyšší hodnotou primárního klíče.

   1. Volitelně, chcete-li definovat předvolby sloučení pro jednotlivé atributy entity, vyberte **Pokročilý** ve spodní části podokna. Můžete se například rozhodnout zachovat nejnovější e-mail A nejúplnější adresu z různých záznamů. Rozbalte entitu, abyste viděli všechny její atributy a definujte, kterou možnost mají použít jednotlivé atributy. Pokud zvolíte možnost založenou na aktuálnosti, musíte také zadat pole data/času, které definuje aktuálnost.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Panel rozšířených předvoleb sloučení zobrazující poslední e-mail a úplnou adresu":::

   1. Výběrem možnosti **Hotovo** použijte předvolby sloučení.

1. Po definování pravidel deduplikace a předvoleb sloučení vyberte **Další**.
  
> [!div class="nextstepaction"]
> [Další krok pro jednu entitu: Sjednocení polí](merge-entities.md)

> [!div class="nextstepaction"]
> [Další krok pro více entit: Přizpůsobení podmínek](match-entities.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
