---
title: Sjednocení zákaznických polí pro sjednocení dat
description: Sloučením entit můžete vytvořit sjednocené profily zákazníků.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: ceb2724ad490c1ba44fd9b7ff2be04721892fca4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081167"
---
# <a name="unify-customer-fields-for-data-unification"></a>Sjednocení zákaznických polí pro sjednocení dat

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

V tomto kroku procesu sjednocení vyberte a vylučte atributy, které chcete sloučit v rámci entity sjednoceného profilu. Pokud například tři entity měly e-mailová data, můžete si ponechat všechna tři samostatná pole e-mailu nebo je sloučit do jednoho pole e-mailu pro sjednocený profil. Některé atributy jsou systémem automaticky kombinovány. Můžete vytvořit stabilní a jedinečná ID zákazníků a seskupovat související profily do clusteru.

:::image type="content" source="media/m3_unify.png" alt-text="Stránka sloučení v procesu sjednocení dat zobrazující tabulku se sloučenými poli, která definují sjednocený profil zákazníka.":::

## <a name="review-and-update-the-customer-fields"></a>Kontrola a aktualizace polí zákazníka

1. Zkontrolujte seznam polí, která budou sjednocena na kartě **Zákaznická pole** tabulky. Proveďte případné změny.

   1. Pro jakákoli kombinovaná pole můžete provést tyto akce:
      - [Úpravy](#edit-a-merged-field)
      - [Přejmenovat](#rename-fields)
      - [Oddělit](#separate-merged-fields)
      - [Vyloučit](#exclude-fields)
      - [Posunutí nahoru nebo dolů](#change-the-order-of-fields)

   1. Pro jakákoli jednotlivá pole můžete provést tyto akce:
      - [Zkombinovat pole](#combine-fields-manually)
      - [Kombinace skupiny polí](#combine-a-group-of-fields)
      - [Přejmenovat](#rename-fields)
      - [Vyloučit](#exclude-fields)
      - [Posunutí nahoru nebo dolů](#change-the-order-of-fields)

1. Volitelně [vygenerovat konfiguraci ID zákazníka](#configure-customer-id-generation).

1. Volitelně [seskupte profily do domácností nebo clusterů](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Další krok: Zkontrolujte sjednocení](review-unification.md)

### <a name="edit-a-merged-field"></a>Úprava sloučeného pole

1. Vyberte sloučené pole a zvolte **Upravit**. Zobrazí se podokno Kombinovat pole.

1. Určete, jak kombinovat nebo sloučit pole jednou ze tří možností:
    - **Důležitost**: Identifikuje hodnotu vítěze na základě pořadí důležitosti specifikovaného pro zúčastněná pole. Toto je výchozí možnost sloučení. Vyberte **Přesunout nahoru/dolů** a nastavte pořadí důležitosti.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Možnost důležitosti v dialogovém okně sloučení polí.":::

    - **Nejnovější**: Identifikuje vítěznou hodnotu na základě aktuálnosti. K definování aktuálnosti vyžaduje datum nebo číselné pole pro každou zúčastněnou entitu v rozsahu sloučených polí.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Možnost aktuálnosti v dialogovém okně sloučení polí.":::

    - **Nejstarší**: Identifikuje vítěznou hodnotu na základě nejstarší aktuálnosti. K definování aktuálnosti vyžaduje datum nebo číselné pole pro každou zúčastněnou entitu v rozsahu sloučených polí.

1. Chcete -li se účastnit procesu sloučení, můžete přidat další pole.

1. Sloučené pole můžete přejmenovat.

1. Výběrem možnosti **Hotovo** se vaše změny použijí.

### <a name="rename-fields"></a>Přejmenovat pole

Změňte zobrazované jméno sloučených nebo samostatných polí. Název výstupní entity nelze změnit.

1. Vyberte pole a zvolte **Přejmenovat**.

1. Zadejte nový zobrazovaný název.

1. Vyberte **Hotovo**.

### <a name="separate-merged-fields"></a>Oddělení sloučených polí

Chcete-li oddělit sloučená pole, vyhledejte atribut v tabulce. Oddělená pole se zobrazují jako jednotlivé datové body ve sjednoceném profilu zákazníka.

1. Vyberte sloučené pole a vyberte **Samostatná pole**.

1. Oddělení potvrďte.

### <a name="exclude-fields"></a>Vyloučení polí

Vylučte sloučené nebo samostatné pole ze sjednoceného profilu zákazníka. Pokud se pole používá v jiných procesech, například v segmentu, před vyloučením z profilu zákazníka jej z těchto procesů odstraňte.

1. Vyberte sloučené pole a zvolte **Vyloučit**.

1. Potvrďte vyloučení.

Chcete-li zobrazit seznam všech vyloučených polí, vyberte **Vyloučená pole**. V případě potřeby můžete vyloučené pole přečíst.

### <a name="change-the-order-of-fields"></a>Změna pořadí polí

Některé entity obsahují více podrobností než jiné. Pokud entita obsahuje nejnovější data o poli, můžete ji při slučování hodnot upřednostnit před jinými entitami.

1. Vyberte pole.
  
1. Vyberte **Posunout nahoru/dolů** pro nastavení pořadí nebo je přetáhněte na požadované místo.

### <a name="combine-fields-manually"></a>Ruční kombinace polí

Spojením oddělených polí vytvořte sloučený atribut.

1. Vyberte **Kombinovat** > **Pole**. Zobrazí se podokno Kombinovat pole.

1. Upřesněte vítěznou zásadu sloučení v rozevíracím seznamu **Kombinovat pole podle**.

1. Vyberte **Přidat pole** ke zkombinování více polí.

1. Zadejte **Název** a **Název výstupního pole**.

1. Výběrem možnosti **Hotovo** se změny použijí.

### <a name="combine-a-group-of-fields"></a>Kombinace skupiny polí

Zacházejte se skupinou polí jako s jednou jednotkou. Pokud například naše záznamy obsahují pole Adresa1, Adresa2, Město, Stát a PSČ, nechceme je sloučit do adresy2 jiného záznamu, protože si myslíme, že by tím byla naše data úplnější.

1. Vyberte **Kombinovat** > **Skupina polí**.

1. Upřesněte vítěznou zásadu sloučení v rozevíracím seznamu **Seřadit skupiny podle**.

1. Vyberte možnost **Přidat** a zvolte, zda chcete k polím přidat pole nebo skupiny do polí.

1. Zadejte **Název** a **Název výstupu** pro každé kombinované pole.

1. Zadejte **Název** pro skupinu polí.

1. Výběrem možnosti **Hotovo** se změny použijí.

## <a name="configure-customer-id-generation"></a>Konfigurace generování ID zákazníka

Definujte, jak generovat hodnoty ID zákazníka, jedinečné identifikátory profilu zákazníka. Krok sjednocení polí v procesu sjednocení dat vygeneruje jedinečný identifikátor profilu zákazníka. Identifikátor je *CustomerId* v entitě *Zákazník*, která je výsledkem procesu sjednocení dat.

*CustomerId*  se zakládá na algoritmu hash první hodnoty nenulových primárních klíčů vítěze. Tyto klíče pocházejí z entit používaných při sjednocování dat a jsou ovlivněny pořadím shody.Vygenerované ID zákazníka se tedy může změnit, když se změní hodnota primárního klíče v primární entitě odpovídající objednávky. Hodnota primárního klíče nemusí vždy představovat stejného zákazníka.

Konfigurace stabilního ID zákazníka vám umožní vyhnout se tomuto chování.

1. Vyberte kartu **Klíče**.

1. Najeďte myší na řádek **CustomerId** a vyberte **Konfigurovat**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Ovládací prvek pro přizpůsobení generování ID.":::

1. Vyberte až pět polí, která budou obsahovat jedinečné ID zákazníka a jsou stabilnější. Záznamy, které neodpovídají vaší konfiguraci, používají místo toho ID nakonfigurované systémem.  

1. Vyberte **Hotovo**.

## <a name="group-profiles-into-households-or-clusters"></a>Seskupení profilů do domácností nebo clusterů

Můžete definovat pravidla pro seskupení souvisejících profilů do clusteru. V současné době jsou k dispozici dva typy clusterů - clustery domácnosti a vlastní clustery. Systém automaticky vybere domácnost s předdefinovanými pravidly, pokud entita *Zákazník* obsahuje sémantická pole *Osoba. Příjmení* a *Umístění. Adresa*. Můžete také vytvořit cluster s vlastními pravidly a podmínkami, podobně jako [pravidla porovnání](match-entities.md#define-rules-for-match-pairs).

1. Vyberte **Pokročilé** > **Vytvořit cluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Ovládací prvek pro vytvoření nového clusteru.":::

1. Vyberte si mezi clusterem **Domácnost** nebo **Vlastní**. Pokud sémantická pole *Osoba. Příjmení* a *Místo. Adresa* existují v entitě *Zákazník*, je automaticky vybrána domácnost.

1. Zadejte název klastru a vyberte **Hotovo**.

1. Vyberte kartu **Clustery** a vyhledejte cluster, který jste vytvořili.

1. Zadejte pravidla a podmínky pro definování clusteru.

1. Vyberte **Hotovo**. Cluster se vytvoří po dokončení procesu sjednocení. Identifikátory clusteru jsou přidány jako nová pole do entity *Zákazník*.

> [!div class="nextstepaction"]
> [Další krok: Zkontrolujte sjednocení](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
