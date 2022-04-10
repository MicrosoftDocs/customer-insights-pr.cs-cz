---
title: Zobrazení profilů zákazníků
description: Získejte kombinované zobrazení sjednocených údajů o zákaznících.
ms.date: 09/30/2021
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
ms.openlocfilehash: 074d84eff65d52b083fff6c161282d4fafa1af85
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523714"
---
# <a name="customer-profiles"></a>Profily zákazníků

Stránka **Zákazníci** zobrazuje kombinovaný pohled na vaše sjednocené zákaznické profily. Profily zákazníků jsou k dispozici, jakmile [vytvoříte sjednocenou entitu zákazníka](data-unification.md). Stránka vám umožňuje vyhledávat zákazníky a definovat index pro toto vyhledávání.

Zákazníky mohou být jednotlivci nebo organizace. Každý zákaznický profil je reprezentován dlaždicí. Pomocí ovládacích prvků stránkování získáte další záznamy. Karta zobrazuje pole z entity *Zákazník* , jak je definována v souboru **indexu vyhledávání a filtrování**. Pořadí polí na jednotlivých kartách vybírá systém.

Výběrem dlaždice zobrazíte data pro vybraného zákazníka na vyhrazené stránce s názvem [Stránka s podrobnostmi o zákazníkovi](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Stránka zákazníků zobrazující dlaždice výsledků](media/customers-page-result-tiles-B2C.png "Stránka zákazníků zobrazující dlaždice výsledků")

> [!NOTE]
> Pokud při výběru nevidíte dlaždice **Zákazníci** v navigaci, musí váš správce [definovat alespoň jeden atribut, který lze prohledávat](search-filter-index.md) v **indexu vyhledávání a filtrování**.

## <a name="search-for-customers"></a>Hledat zákazníky

Vyhledejte zákazníky zadáním jména nebo jiného atributu do vyhledávacího pole. Vyhledávání funguje pouze v rámci entity _Zákazník_ vytvořené během procesu sjednocení dat.

Jako správce můžete konfigurovat prohledávatelné atributy pomocí stránky **Hledat a filtrovat rejstřík**. Další informace najdete v části [Správa indexu vyhledávání a filtrování](search-filter-index.md).

## <a name="filter-customers"></a>Filtrování zákazníků

Zákazníky můžete filtrovat podle polí entity _Zákazník_. Podobně jako při vyhledávání bude muset správce nejprve definovat pole jako filtrovatelná pomocí stránky **Hledat a filtrovat rejstřík**.

1. Vyberte **Zobrazit filtry** na stránce **Zákazníci**.

1. Zaškrtněte políčka vedle atributů, podle kterých chcete zákazníky filtrovat.

1. Odeberte filtry volbou **Vymazat filtry** na stránce **Zákazníci**.

## <a name="customer-details-page"></a>Stránka podrobností zákazníka

Vyberte některou z dlaždic zákazníků a otevřete **stránku podrobností zákazníka**. Toto zobrazení obsahuje jednotné informace o vybraném zákazníkovi. Podrobnosti o zákazníkovi zahrnují následující obsah:

**Dlaždice profilu zákazníka**: Tato dlaždice zobrazuje různé hodnoty ze sjednocené entity _Zákazník_. Pokud pole pro vybraný zákaznický profil nemá žádnou hodnotu, nezobrazí se. Dlaždice je strukturována do sekcí:  
  - První část ukazuje předdefinovanou sadu polí a za ní všechna pole, která jsou součástí indexu vyhledávání a filtrování. Všechna pole související s adresou jsou sloučena do jednoho řádku, pokud profil taková pole obsahuje. 
  - **Kontakty na tohoto zákazníka**: V prostředích pro firemní zákaznické účty uvidíte všechny související kontakty tohoto zákazníka jako druhou sekci. Každý kontakt je zobrazen se svými poli. Prázdná pole jsou skrytá.
  - **Další pole**: Zobrazí zbývající pole vybraného zákazníka kromě ID. 
  - **ID**: Uvádí všechna ID pod odpovídajícím názvem entity. Pole jsou identifikována jako ID svou sémantikou, která je podle toho kategorizuje.

**Časová osa aktivity**: Zobrazuje data, pokud jste nakonfigurovali aktivity. Zobrazení časové osy obsahuje chronologicky seřazené aktivity vybraného zákazníka, počínaje nejnovější aktivitou. Další informace najdete v části [Aktivity zákazníka](activities.md).

**Přehledy**:  
  - **Míry**: Ukazuje, zda jste nakonfigurovali jednu nebo více měr atributu zákazníka. Zahrnují vypočítané klíčové ukazatele výkonu ohledně vašich zákazníků na úrovni jednotlivých zákazníků. Další informace najdete v tématu [Definování a správa měr](measures.md).

  - **Potenciální zájmy, potenciální značky**: Zobrazuje, zda jste nakonfigurovali obohacení značky nebo zájmové afinity. Představuje potenciální zájmy a spříznění pro značky založené na jiných zákaznících, jejichž profil je podobný zvolenému zákaznickému profilu. Další informace najdete v části [Obohacení profilů zákazníka pomocí afinit ke značkám a zájmům](enrichment-microsoft.md).

Chcete -li se vrátit na stránku vyhledávání zákazníků, vyberte **Zpět k zákazníkům**.

## <a name="next-steps"></a>Další kroky

[Přidejte další zdroje dat](data-sources.md), [obohaťte sjednocené profily](enrichment-hub.md) nebo [vytvářejte segmenty](segments.md) pro práci se sjednocenými zákaznickými profily v jiných aplikacích.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
