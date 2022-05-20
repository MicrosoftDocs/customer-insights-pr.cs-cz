---
title: Odstranění duplicit před sjednocením dat
description: Druhým krokem v procesu sjednocení je výběr záznamu, který se má zachovat, když jsou nalezeny duplikáty.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741614"
---
# <a name="remove-duplicates-before-unifying-data"></a>Odstranění duplicit před sjednocením dat

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Tento krok sjednocení volitelně umožňuje nastavit pravidla pro zacházení s duplicitními záznamy v rámci entity. *Deduplikace* identifikuje duplicitní záznamy a sloučí je do jednoho záznamu. Zdrojové záznamy se propojí se sloučeným záznamem s alternativními ID. Pokud pravidla nejsou nakonfigurována, použijí se systémem definovaná pravidla.

## <a name="include-enriched-entities-preview"></a>Zahrnutí rozšířených entit (Preview)

Pokud jste obohatili entity na úrovni zdroje dat, abyste pomohli zlepšit výsledky sjednocení, vyberte je. Další informace najdete v tématu [Rozšíření zdrojů dat](data-sources-enrichment.md).

1. V horní části stránky **Duplicitní záznamy** vyberte **Použít obohacené entity**.

1. V podokně **Používat rozšířené entity** vyberte jednu nebo více rozšířených entit.

1. Vyberte **Hotovo**.

## <a name="define-deduplication-rules"></a>Definování odstranění duplicit

1. Na stránce **Duplikovat záznamy** vyberte entitu a vyberte **Přidat pravidlo** k definování pravidel deduplikace.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Snímek obrazovky duplicitních záznamů se zvýrazněnou možností Zobrazit více":::

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

## <a name="deduplication-output-as-an-entity"></a>Výstup odebraných duplicit jako entita

Proces deduplikace vytvoří novou deduplikovanou entitu pro každou ze zdrojových entit. Tyto entity lze nalézt spolu s **ConflationMatchPairs:CustomerInsights** v sekci **Systém** na stránce **Entity** s názvem **Deduplication_DataSource_Entity**.

Entita výstupu odstraněných duplicit obsahuje následující informace:

- ID/klíče
  - Pole Primární klíč a Alternativní ID. Pole Alternativní ID obsahuje všechna alternativní ID identifikovaná pro záznam.
  - Pole Deduplication_GroupId zobrazuje skupinu nebo cluster identifikované v rámci entity, které seskupují všechny podobné záznamy na základě zadaných polí odstraněných duplicit. Používá se pro účely systémového zpracování. Pokud nejsou zadána žádná pravidla pro ruční odstranění duplicit a platí systémově definovaná pravidla pro odstranění duplicit, možná toto pole v entitě výstupu odstraněných duplicit nenajdete.
  - Deduplication_WinnerId: Toto pole obsahuje vítězné ID z identifikovaných skupin nebo clusterů. Pokud je hodnota Deduplication_WinnerId stejná jako hodnota primárního klíče záznamu, znamená to, že záznam je vítězným záznamem.
- Pole použitá k definování pravidel odstranění duplicit.
- Pole Pravidlo a Skóre označují, která z pravidel pro odstranění duplicit byla použita a které skóre bylo vráceno algoritmem pro párování.

[!INCLUDE[footer-include](includes/footer-banner.md)]
