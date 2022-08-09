---
title: Zobrazení profilů zákazníků
description: Prohlédněte si svá sjednocená zákaznická data, včetně použití vyhledávání a filtrování
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188085"
---
# <a name="view-customer-profiles"></a>Zobrazení profilů zákazníků

Profily zákazníků jsou k dispozici, jakmile [vytvoříte sjednocenou entitu *Zákazník*](data-unification.md). Stránka **Zákazníci** obsahuje kombinované zobrazení vašich sjednocených zákaznických profilů. Zákazníky mohou být jednotlivci nebo organizace.

Přechodem na stránku **Zákazníci** zobrazíte své zákazníky a jejich profily. Každý zákaznický profil je reprezentován dlaždicí. Pomocí ovládacích prvků stránkování získáte další záznamy. Karta zobrazuje pole z entity *Zákazník* , jak je definována v souboru **indexu vyhledávání a filtrování**. Pořadí polí na jednotlivých kartách vybírá systém.

> [!NOTE]
> Pokud při výběru možnosti **Zákazníci** nevidíte příslušné dlaždice, musí váš správce [definovat alespoň jeden vyhledatelný atribut](search-filter-index.md) v **indexu vyhledávání a filtrování**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Stránka Zákazníci obsahující dlaždice výsledků.":::

Vyberte některou z následujících akcí:
- [Zobrazit podrobnosti zákazníka](#view-customer-details)
- [Spravovat index vyhledávání a filtrování](search-filter-index.md) (pouze správci)
- [Filtrování zákazníků](#filter-customers)
- **Rozbalit karty** nebo **Sbalit karty** pro rozbalení nebo sbalení informací zobrazených na dlaždici zákazníka
- **Řadit podle** určitého atributu
- [Hledat zákazníky](#search-for-customers)

  > [!NOTE]
  > Chcete-li použít vyhledávání a filtrování, musí správce nakonfigurovat vyhledatelné atributy a definovat filtrovatelná pole pomocí indexu vyhledávání a filtrování.

## <a name="search-for-customers"></a>Hledat zákazníky

Vyhledejte zákazníky zadáním jména nebo jiného atributu v poli **Hledat zákazníky**. Vyhledatelné atributy jsou definovány správcem a pocházejí ze sjednocené entity *Zákazník*.

> [!NOTE]
> **Řetězec** je jediný datový typ, který je součástí vyhledávání. Použijte jej v poli **Hledat zákazníky** na stránce Zákazníci k vyhledání zákazníků.

## <a name="filter-customers"></a>Filtrování zákazníků

Zákazníky můžete filtrovat podle polí entity *Zákazník*. Filtrovatelná pole definuje správce.

1. Na stránce **Zákazníci** vyberte **Zobrazit filtry**. Zobrazí se podokno Filtr.

1. Zaškrtněte políčka vedle atributů, podle kterých chcete zákazníky filtrovat.

1. Odeberte všechny filtry výběrem možnosti **Vymazat filtry** nebo zrušte zaškrtnutí políčka vedle vybraného atributu.

1. Volbou **Skrýt filtry** zavřete podokno filtru.

1. Chcete-li uložit výsledky filtru jako [segment](segments.md), vyberte **Uložit filtry jako segment**.
   1. Zadání název segmentu.
   1. Možností **Uložit** uložte segment.
   1. Zvolte, zda chcete spustit segment, volbou **Aktivovat**, nebo zda jej chcete spustit **Později**.

## <a name="view-customer-details"></a>Zobrazení podrobností zákazníka

Na stránce **Zákazníci** vyberte dlaždici zákazníka, čímž zobrazíte podrobnosti o vybraném zákazníkovi.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Stránka podrobností zákazníka.":::

Podrobnosti o zákazníkovi zahrnují následující:

**Dlaždice profilu zákazníka** zobrazuje různé hodnoty ze sjednocené entity *Zákazník*. Pokud pole pro vybraný zákaznický profil nemá žádnou hodnotu, nezobrazí se kromě pole adresy. Dlaždice je strukturována do sekcí:

- První část ukazuje předdefinovanou sadu polí a za ní všechna pole, která jsou součástí indexu vyhledávání a filtrování. Všechna pole související s adresou jsou sloučena do jednoho řádku, který ukazuje, pokud profil neobsahuje žádné informace o adrese.
- **Kontakty na tohoto zákazníka** se zobrazují v prostředích pro obchodní účty. Každý kontakt je zobrazen se svými poli. Prázdná pole jsou skrytá.
- **Další pole** zobrazují zbývající pole vybraného zákazníka kromě ID.
- **ID** uvádí všechna ID pod odpovídajícím názvem entity. Pole jsou identifikována jako ID podle jejich sémantiky.

**Časová osa aktivity** zobrazuje data, pokud jste nakonfigurovali [aktivity](activities.md). Zobrazení časové osy obsahuje chronologicky seřazené aktivity vybraného zákazníka, počínaje nejnovější aktivitou.

**Přehledy**:

- **Míry** ukazují, zda jste nakonfigurovali [míry atributu zákazníka](measures.md). Zahrnují vypočítané klíčové ukazatele výkonu ohledně vašich zákazníků na úrovni jednotlivých zákazníků.

- **Potenciální zájmy, potenciální značky** zobrazuje, zda jste nakonfigurovali [rozšíření spřežení značky nebo zájmů](enrichment-microsoft.md). Představuje potenciální zájmy a spříznění pro značky založené na jiných zákaznících, jejichž profil je podobný zvolenému zákaznickému profilu.

Chcete-li se vrátit na stránku **Zákazníci**, vyberte **Zpět na zákazníky**.

## <a name="next-steps"></a>Další kroky

[Přidejte další zdroje dat](data-sources.md), [obohaťte sjednocené profily](enrichment-hub.md) nebo [vytvářejte segmenty](segments.md) pro práci se sjednocenými zákaznickými profily v jiných aplikacích.

[!INCLUDE [footer-include](includes/footer-banner.md)]
