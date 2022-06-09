---
title: Aktivity zákazníka
description: Definujte aktivity zákazníků a zobrazte je na časové ose v zákaznických profilech.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: 6c0a1bc5d9a42806b458142804199c733ff530ec
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755490"
---
# <a name="customer-activities"></a>Aktivity zákazníka

Kombinujte zákaznické aktivity z [různých zdrojů dat](data-sources.md) v Dynamics 365 Customer Insights. Vytvořte časovou osu, která uvádí aktivity chronologicky. Zahrňte časovou osu do aplikací Dynamics 365 s řešením [Doplněk zákaznické karty](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definování aktivity

Vaše zdroje dat mohou zahrnovat entity s transakčními a aktivními daty z více zdrojů dat. Identifikujte tyto entity a vyberte aktivity, které chcete zobrazit na časové ose zákazníka. Vyberte entitu, která zahrnuje vaši cílovou aktivitu nebo aktivity.

Entita musí mít alespoň jeden atribut typu **Datum**, aby byla součástí na časové osy zákazníka a nelze přidávat entity bez pole **Datum**. Ovládací prvek **Přidat aktivitu** není povolen, pokud není taková entita nalezena.

1. Přejděte na **Data** > **Aktivity**.

1. Výběrem možnosti **Přidat aktivitu** spusťte řízené prostředí pro proces nastavení aktivity.

1. V kroku **Data aktivity** nastavte hodnoty pro následující pole:

   - **Název aktivity**: Vyberte název své aktivity.
   - **Entita**: Vyberte entitu, která obsahuje údaje o transakcích nebo aktivitách.
   - **Primární klíč**: Vyberte pole, které jedinečně identifikuje záznam. Nemělo by obsahovat žádné duplicitní hodnoty, prázdné hodnoty nebo chybějící hodnoty.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nastavte data aktivity s názvem, entitou a primárním klíčem.":::

1. Vyberte **Další** pro přechod k dalšímu kroku.

1. V kroku **Vztah** nakonfigurujte podrobnosti tak, aby se data o vaší činnosti připojila k odpovídajícímu záznamu zákazníka. Tento krok vizualizuje spojení mezi entitami.  

   - **První**: Cizí pole ve vaší entitě aktivity, které se použije k navázání vztahu s jinou entitou.
   - **Druhý**: Odpovídající entita zdrojového zákazníka, se kterou bude vaše entita aktivity ve vztahu. Můžete ji přidružit pouze ke zdrojovým entitám zákazníků, které se používají v procesu sjednocení dat.
   - **Třetí**: Pokud vztah mezi touto entitou aktivity a vybranou entitou zdrojového zákazníka již existuje, název vztahu bude v režimu jen pro čtení. Pokud takový vztah neexistuje, vytvoří se nový vztah se jménem, které uvedete v tomto poli.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definujte vztah entity.":::

   > [!TIP]
   > V prostředích B2B můžete vybírat mezi entitami účtu a jinými entitami. Pokud vyberete entitu účtu, cesta vztahu se nastaví automaticky. U ostatních entit musíte definovat cestu vztahu přes jednu nebo více mezilehlých entit, dokud nedosáhnete entity účtu.

1. Vyberte **Další** pro přechod k dalšímu kroku. 

1. V kroku **Sjednocení aktivity** vyberte událost aktivity a čas zahájení aktivity. 
   - **Povinná pole**
      - **Aktivita události**: Pole, které je událostí pro tuto aktivitu.
      - **Časové razítko**: Pole, které představuje čas zahájení vaší aktivity.

   - **Nepovinná pole**
      - **Další podrobnosti**: Pole s příslušnými informacemi pro tuto aktivitu.
      - **Ikona**: Ikona, která nejlépe představuje tento typ aktivity.
      - **Webová adresa**: Pole obsahující adresu URL s informacemi o této aktivitě. Například transakční systém, který tuto aktivitu využívá. Tato adresa URL může být libovolné pole ze zdroj dat, nebo může být vytvořeno jako nové pole pomocí transformace Power Query. Data URL budou uložena v entitě *Sjednocená aktivita*, kterou lze následně spotřebovat pomocí [API](apis.md).

   - **Zobrazit na časové ose**
      - Vyberte, zda se má tato aktivita zobrazovat v zobrazení časové osy ve vašich zákaznických profilech. Vyberte **Ano** pro zobrazení aktivity na časové ose nebo **Ne**, čímž ji skryjete.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Zadejte údaje o aktivitě zákazníka v entitě Unified Activity.":::

1. Volbou **Další** přejdete na další krok. Můžete vybrat **Dokončit a zkontrolovat** pro uložení aktivity nyní s typem aktivity nastaveným na **Jiný**. 

1. V kroku **Typ aktivity** vyberte typ aktivity a volitelně vyberte, zda chcete sémanticky mapovat některé typy aktivit pro použití v jiných oblastech Customer Insights. V současné době typy aktivit *Zpětná vazba*, *Věrnost*, *Prodejní objednávka*, *SalesOrderLine*, a *Předplatné* podporují sémantiku po odsouhlasení mapování polí. Pokud typ aktivity není pro novou aktivitu relevantní, můžete si vybrat *Jiný* nebo *Vytvořit nový* pro vlastní typ aktivity.

1. Volbou **Další** přejdete na další krok. 

1. V kroku **Kontrola** ověřte výběr. Vraťte se k některému z předchozích kroků a v případě potřeby informace aktualizujte.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Zkontrolujte aktivitu v zadaných polích.":::
   
1. Vyberte **Uložit aktivitu** pro použití změn a vyberte **Hotovo** pro návrat na **Data** > **Aktivity**. Zde vidíte, které aktivity jsou nastaveny tak, aby se zobrazovaly na časové ose. 

1. Na stránce **Aktivity** vyberte **Spustit** ke zpracování aktivity. 

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Správa existujících aktivit

Na stránce **Data** > **Aktivity** můžete zobrazit všechny uložené aktivity a spravovat je. Každá aktivita je reprezentována řádkem, který také obsahuje podrobnosti o zdroji, entitě a typu aktivity.

Následující akce jsou k dispozici, když vyberete aktivitu. 

- **Upravit**: Otevře nastavení aktivity v kroku kontroly. Z tohoto kroku můžete změnit některou nebo celou aktuální konfiguraci. Po změně konfigurace vyberte **Uložit aktivitu** a poté vyberte **Spustit** ke zpracování změn.

- **Přejmenovat**: Otevře dialogové okno, kde můžete zadat jiný název vybrané aktivity. Výběrem možnosti **Uložit** se vaše změny uplatní.

- **Vymazat**: Otevře dialogové okno s potvrzením odstranění vybrané aktivity. Můžete také odstranit více než jednu aktivitu najednou tak, že vyberete aktivity a poté vyberete ikonu odstranění. Vyberte **Odstranit** pro potvrzení odstranění.

## <a name="view-activity-timelines-on-customer-profiles"></a>Zobrazení časových os aktivit v zákaznických profilech

Po konfiguraci zákaznických aktivit vyberte **Zobrazit na časové ose aktivity** v konfiguraci aktivity k vyhledání všech aktivit vašeho zákazníka na jeho zákaznickém profilu.

Chcete -li zákazníkovi otevřít časovou osu, přejděte na **Zákazníci** a vyberte profil zákazníka, který chcete zobrazit.

Pokud se zákazník zúčastnil konfigurované aktivity, najdete ji v části **Časová osa aktivity**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Zobrazte nakonfigurované aktivity v zákaznických profilech.":::

Existuje několik způsobů, jak filtrovat aktivity na časové ose aktivity:

- Můžete vybrat jednu nebo více ikon aktivit a upřesnit výsledky tak, aby zahrnovaly pouze vybrané typy.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrujte aktivity podle typu pomocí ikon.":::

- Můžete vybrat **Filtr** pro otevření panelu filtrů a konfiguraci filtrů časové osy.

   1. Můžete filtrovat podle *Typ aktivity* a *datum*
   1. Vyberte **Použít** k použití filtrů na časové ose aktivity.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Pomocí panelu filtru nakonfigurujte podmínky filtru.":::

Chcete -li filtry odebrat, vyberte **X** vedle každého filtru použitého na časové ose nebo vyberte **Vymazat filtry**.


> [!NOTE]
> Filtry aktivit se odstraní, když opustíte profil zákazníka. Musíte je použít při každém otevření v zákaznickém profilu.

[!INCLUDE [footer-include](includes/footer-banner.md)]