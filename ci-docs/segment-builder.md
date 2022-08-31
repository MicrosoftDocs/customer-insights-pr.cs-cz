---
title: Vytvoření komplexních segmentů pomocí tvůrce segmentů
description: Pomocí tvůrce segmentů můžete vytvářet komplexní segmenty zákazníků jejich seskupením na základě různých atributů.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304741"
---
# <a name="create-complex-segments-with-segment-builder"></a>Vytvoření komplexních segmentů pomocí tvůrce segmentů

Definujte složité filtry kolem sjednoceného zákazníka nebo sjednoceného kontaktu a souvisejících entit. Každý segment po zpracování vytvoří sadu záznamů zákazníka nebo kontaktu, které můžete exportovat a provést akci.

> [!TIP]
> Segmenty založené na **jednotlivých zákaznících** automaticky obsahují dostupné kontaktní informace pro členy segmentu. V **obchodních účtech**, pokud jste [sjednotili](data-unification.md) účty i kontakty, vyberte, zda je segment založen na účtech nebo obchodních kontaktech. Chcete-li exportovat do cíle, který očekává informace o kontaktu, použijte segment kontaktů. Chcete-li exportovat do cíle, který očekává informace o účtu, použijte segment účtů.

## <a name="segment-builder"></a>Tvůrce segmentů

Následující obrázek ukazuje různé aspekty tvůrce segmentů. Ukazuje segment, jehož výsledkem je skupina zákazníků. Zákazníci si objednali zboží v konkrétním časovém rámci a nasbírali body za odměnu nebo utratili určitou částku peněz.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Prvky nástroje pro tvorbu segmentů." lightbox="media/segment-builder-overview.png":::

1. Uspořádejte svůj segment pomocí pravidel a dílčích pravidel. Každé pravidlo nebo dílčí pravidlo se skládá z podmínek. Podmínky kombinujte s logickými operátory.

1. Vyberte [cestu vztahu](relationships.md) mezi entitami, které platí pro pravidlo. Cesta vztahu určuje, které atributy lze použít v podmínce.

1. Spravujte pravidla a dílčí pravidla. Změňte pozici pravidla nebo jej odstraňte.

1. Přidejte podmínky a vytvořte správnou úroveň vnoření pomocí dílčích pravidel.

1. Aplikujte nastavené operace na připojená pravidla.

1. Pomocí podokna atributů přidejte dostupné atributy entit nebo vytvořte podmínky na základě atributů. Podokno zobrazuje seznam entit a atributů na základě zvolené cesty vztahu, které jsou k dispozici pro vybrané pravidlo.

1. Přidejte podmínky na základě atributů ke stávajícím pravidlům a dílčím pravidlům nebo je přidejte do nového pravidla.

1. Zrušte a znovu proveďte změny při vytváření segmentu.

Výše uvedený příklad ilustruje schopnost segmentace. Definovali jsme segment pro zákazníky, kteří nakoupili zboží online alespoň za 500 USD *a* mají zájem o vývoj softwaru.

## <a name="create-a-new-segment-with-segment-builder"></a>Vytvoření nového segmentu pomocí tvůrce segmentů

1. Jděte na **Segmenty**.

1. Vyberte **Nový** > **Vytvořit svůj vlastní**. Na stránce tvůrce segmentů definujete nebo sestavujete pravidla. Pravidlo se skládá z jedné nebo více podmínek, které definují skupinu zákazníků.

   > [!NOTE]
   > Pro prostředí založená na obchodních účtech vyberte **Nový** > **Segment účtů** nebo **Segment kontaktů (Preview)** podle typu segmentu, který chcete vytvořit. Pokud [hierarchie účtu](relationships.md#set-up-account-hierarchies) byla definována a chcete vytvořit pravidla pro filtrování dat na základě vztahu podřízeného a nadřízeného objektu, vyberte **Použít hierarchii? (Preview)**, vyberte hierarchii a poté **Použít**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Podokno pro výběr hierarchie účtů v segmentu.":::

1. Vedle segmentu bez názvu vyberte možnost **Upravit podrobnosti**. Zadejte název pro svůj segment a aktualizujte navrhovaný **Název výstupní entity** pro segment. Volitelně do segmentu přidejte popis a [značky](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialogové okno Úprava podrobností.":::

1. V sekci **Pravidlo1** vyberte atribut entity, podle které chcete filtrovat zákazníky. Vybrat atributy lze dvěma způsoby:
   - Zkontrolujte seznam dostupných entit a atributů v podokně **Přidat do pravidla** a vyberte ikonu **+** vedle atributu, který chcete přidat. Vyberte, zda chcete přidat atribut do existujícího pravidla, nebo jej použít k vytvoření nového pravidla.
   - Chcete -li zobrazit návrhy shod, zadejte název atributu do sekce pravidel.

1. Vyberte operátory k určení odpovídajících hodnot podmínky. Atribut může mít jako hodnotu jeden ze čtyř datových typů: číselný, řetězec, datum nebo logickou hodnotu. V závislosti na datovém typu atributu jsou k určení podmínky k dispozici různé operátory.

1. Vyberte **Přidat podmínku** pro přidání dalších podmínek do pravidla. Chcete -li vytvořit pravidlo pod aktuálním pravidlem, vyberte **Přidat dílčí pravidlo**.

1. Pokud pravidlo používá jiné entity než *Zákazník* (resp. entitu *ContactProfile* v případě B2B), vyberte **Nastavení cesty vztahu** k mapování vybrané entity na sjednocenoou entitu zákazníka. Pokud existuje pouze jedna možná cesta vztahu, systém ji automaticky vybere. Různé [cesty vztahů](relationships.md#relationship-paths) mohou přinést různé výsledky. Každé pravidlo může mít svou vlastní cestu vztahu.

   :::image type="content" source="media/relationship-path.png" alt-text="Cesta potenciálního vztahu při vytváření pravidla na základě entity mapované na jednotnou entitu zákazníka.":::

1. Pokud máte v pravidle více podmínek, vyberte, který logický operátor je spojuje.  
   - Operátor **AND**: Pro zařazení záznamu do segmentu musí být splněny všechny podmínky. Tuto možnost použijte při definování podmínek mezi různými entitami.
   - Operátor **OR**: Pro zařazení záznamu do segmentu musí být jedna z podmínek. Tuto možnost použijte při definování více podmínek pro stejnou entitu.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravidlo s dvěma podmínkami AND":::

   Při použití operátoru OR musí být všechny podmínky založeny na entitách zahrnutých v cestě vztahu.

1. Chcete-li vytvořit různé sady záznamů o zákaznících, vytvořte více pravidel. Chcete-li zahrnout zákazníky požadované pro váš obchodní případ, slučte skupiny. Konkrétně, pokud nemůžete do pravidla zahrnout entitu kvůli zadané cestě vztahu, vytvořte nové pravidlo a z něj vyberte atributy.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Přidejte nové pravidlo do segmentu a vyberte nastavený operátor.":::

   1. Vyberte položku **Přidat pravidlo**.
   1. Vyberte jednoho z nastavených operátorů: **Union**, **Intersect** nebo **Except**.

      - **Sjednocení** sjednotí dvě skupiny.
      - **Průnik** překrývá dvě skupiny. Pouze data, která *jsou společné* pro obě skupiny zůstávají v jednotné skupině.
      - **Výjimka** kombinuje dvě skupiny. Pouze data ve skupině A, která *nejsou společná* s daty ve skupině B, jsou zachována.

1. Ve výchozím nastavení výstupní entita obsahuje všechny atributy zákaznických profilů, které odpovídají definovaným filtrům. V případě B2B při použití entity *ContactProfile* je automaticky zahrnuto ID účtu. Pokud je segment založen na jiných entitách než *Zákazník* nebo má obsahovat více atributů z entity *ContactProfile*, volbou **Atributy projektu** přidáte další atributy z těchto entit do výstupní entity.
 
   Například: Segment je založen na entitě, která obsahuje data o nákupu, která souvisí s entitou *Zákazník*. Segment hledá všechny zákazníky ze Španělska, kteří zakoupili zboží v aktuálním roce. Ke všem odpovídajícím záznamům zákazníků ve výstupní entitě se můžete rozhodnout připojit atributy, jako cena zboží nebo datum nákupu. Tyto informace mohou být užitečné pro analýzu sezónních korelací s celkovou útratou.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Příklad projektovaných atributů vybraných v postranním podokně, které mají být přidány do výstupní entity.":::
 
   Ukázkový výstup segmentu založený na obchodních účtech s předpokládanými atributy kontaktů by mohl vypadat takto:

   |ID  |Název obchodního vztahu  |Výnosy  |Jméno kontaktu  | Role kontaktu|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100 tis. | [Abbie Moss, Ruth Soto]  | [Výkonný ředitel, vedoucí zásobování]

   > [!NOTE]
   > - **Atributy projektu** fungují pouze pro entity, které mají vztah jeden ku mnoha s entitou *Zákazník* nebo *ContactProfile*. Například jeden zákazník může mít více předplatných.
   > - Pokud je atribut, který chcete promítat, více než jeden krok od entity *Zákazník* nebo *ContactProfile*, jak je definována vztahem, tento atribut by měl být použit v každém pravidle segmentového dotazu, který vytváříte.
   > - Pokud je atribut, který chcete promítat, pouhý jeden krok od entity *Zákazník* nebo *ContactProfile*, nemusí být tento atribut přítomen v každém pravidle dotazu na segment, který vytváříte.
   > - Při použití operátorů sady jsou zohledněny **projektované atributy**.

1. Výběrem možnosti **Spustit** vytvořte segment. Vyberte **Uložit**, chcete-li zachovat aktuální konfiguraci a spustit segment později. Zobrazí se stránka **Segmenty**.

### <a name="segment-builder-tips"></a>Typy ohledně tvůrce segmentů

Při vytváření segmentů pomocí tvůrce segmentů mějte na paměti následující tipy:

- Při nastavování operátorů pro podmínky nebude tvůrce segmentů navrhovat platné hodnoty z entit. Můžete přejít na **Data** > **Entity** a stáhněte si data entit, abyste zjistili, které hodnoty jsou k dispozici.
- Podmínky založené na datech umožňují přepínat mezi pevnými daty a pohyblivým rozsahem dat.
- Pokud pro svůj segment máte více pravidel, pravidlo, které upravujete, má vedle něj svislou modrou čáru.
- Pravidla a podmínky můžete přesunout na jiná místa v definici segmentu. Vyberte vertikální tři tečky (&vellip;) vedle pravidla nebo podmínky a vyberte, jak a kam ji přesunete.
- Ovládací prvky **Zpět** a **Znovu** na panelu příkazů vám umožňují vrátit změny zpět.
- Po vytvoření segmentu umožňují některé segmenty [sledovat využití segmentu](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Další kroky

[Exportujte segment](export-destinations.md) a prozkoumejte [integraci karty zákazníka](customer-card-add-in.md) pro použití segmentů v jiných aplikacích.

[!INCLUDE [footer-include](includes/footer-banner.md)]
