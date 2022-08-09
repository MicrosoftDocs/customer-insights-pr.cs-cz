---
title: Aktivity zákazníka
description: Definujte aktivity zákazníků a zobrazte je na časové ose v zákaznických profilech.
ms.date: 07/22/2022
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
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188131"
---
# <a name="customer-activities"></a>Aktivity zákazníka

Zákaznické aktivity jsou akce nebo události prováděné zákazníky. Například transakce, doba trvání podpory hovoru, recenze webů, nákupy nebo vrácení zboží. Tyto aktivity jsou obsaženy v jednom nebo více zdrojích dat. Pomocí Customers Insights konsolidujte své zákaznické aktivity z těchto [zdrojů dat](data-sources.md) a přidružte je k profilům zákazníků. Tyto aktivity se zobrazují chronologicky na časové ose v profilu zákazníka. Zahrňte časovou osu do aplikací Dynamics 365 s řešením [Doplněk zákaznické karty](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definování aktivity

Entita musí mít alespoň jeden atribut typu **Datum**, aby byla součástí na časové osy zákazníka. Ovládací prvek **Přidat aktivitu** není povolen, pokud není taková entita nalezena.

1. Přejděte na **Data** > **Aktivity**.

1. Vyberte **Přidat aktivitu** k zahájení řízeného prostředí.

1. V kroku **Data aktivity** zadejte informace do následujících polí:

   - **Název aktivity**: Název vaší aktivity.
   - **Entita aktivity**: Entita, která obsahuje údaje o transakcích nebo aktivitách.
   - **Primární klíč**: Pole, které jedinečně identifikuje záznam. Nemělo by obsahovat žádné duplicitní hodnoty, prázdné hodnoty nebo chybějící hodnoty.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nastavte data aktivity s názvem, entitou a primárním klíčem.":::

1. Vyberte **Další**.

1. V kroku **Vztah** vyberte možnost **Přidat vztah** pro připojení dat aktivity k odpovídajícímu záznamu zákazníka. Tento krok vizualizuje spojení mezi entitami.  

   - **Cizí klíč z entity**: Pole ve vaší entitě aktivity, které se použije k navázání vztahu s jinou entitou.
   - **Název entity**: Odpovídající entita zdrojového zákazníka, se kterou bude vaše entita aktivity ve vztahu. Můžete ji přidružit pouze ke zdrojovým entitám zákazníků, které se používají v procesu sjednocení dat.
   - **Název vztahu**: Název identifikující vztah mezi entitami. Pokud vztah mezi touto entitou aktivity a vybranou entitou zdrojového zákazníka již existuje, název vztahu je jen pro čtení.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definujte vztah entity.":::

   > [!TIP]
   > V prostředích B2B můžete vybírat mezi entitami účtu a jinými entitami. Pokud vyberete entitu účtu, cesta vztahu se nastaví automaticky. U ostatních entit musíte definovat cestu vztahu přes jednu nebo více mezilehlých entit, dokud nedosáhnete entity účtu.

1. Výběrem položky **Použít** vytvoříte vztah.

1. Vyberte **Další**.

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

1. Vyberte **Další** pro výběr typu aktivity nebo vyberte **Dokončit a zkontrolovat** pro uložení aktivity s typem **Ostatní**.

1. V kroku **Typ aktivity** vyberte typ aktivity a volitelně vyberte, zda chcete sémanticky mapovat některé typy aktivit pro použití v jiných oblastech Customer Insights. V současné době typy aktivit *Zpětná vazba*, *Věrnost*, *Prodejní objednávka*, *SalesOrderLine*, a *Předplatné* podporují sémantiku po odsouhlasení mapování polí. Pokud typ aktivity není pro novou aktivitu relevantní, můžete si vybrat *Jiný* nebo *Vytvořit nový* pro vlastní typ aktivity.

1. Vyberte **Další**.

1. V kroku **Kontrola** ověřte výběr. Vraťte se k některému z předchozích kroků a v případě potřeby informace aktualizujte.

1. Vyberte **Uložit aktivitu** pro použití změn a vyberte **Hotovo** pro návrat na **Data** > **Aktivity**. Zobrazí se vytvořená aktivita.

1. Po vytvoření všech aktivit je zpracujete volbou **Spustit**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Správa existujících aktivit

Jděte na **Data** > **Aktivity** k zobrazení vašich uložených aktivit, jejich zdrojové entity, typu aktivity a zda jsou zahrnuty na časové ose zákazníka. Seznam aktivit můžete seřadit podle libovolného sloupce nebo pomocí vyhledávacího pole najít aktivitu, kterou chcete spravovat.

Vyberte aktivitu pro zobrazení dostupných akcí.

- **Úpravou** aktivity změníte její konfiguraci. Konfigurace se otevře v kroku kontroly. Po změně konfigurace vyberte **Uložit aktivitu** a poté vyberte **Spustit** ke zpracování změn.
- **Přejmenujte** aktivitu. Výběrem možnosti **Uložit** se vaše změny uplatní.
- **Odstraňte** aktivitu. Chcete-li odstranit více než jednu aktivitu najednou, vyberte příslušné aktivity a poté vyberete **Odstranit**. Potvrďte odstranění.

## <a name="view-activity-timelines-on-customer-profiles"></a>Zobrazení časových os aktivit v zákaznických profilech

1. Pokud jste vybrali **Zobrazit na časové ose aktivity** v konfiguraci aktivity, přejděte do části **Zákazníci** a výběrem profilu zákazníka zobrazíte aktivity zákazníka v sekci **Časová osa aktivity**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Zobrazte nakonfigurované aktivity v zákaznických profilech.":::

1. Chcete-li filtrovat aktivity na časové ose aktivity:

   - Vyberte jednu nebo více ikon aktivit a upřesněte výsledky tak, aby zahrnovaly pouze vybrané typy.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrujte aktivity podle typu pomocí ikon.":::

   - Vyberte **Filtr** pro otevření panelu filtrů a konfiguraci filtrů časové osy. Můžete filtrovat podle *ActivityType* a *Date*. Vyberte **Použít**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Pomocí panelu filtru nakonfigurujte podmínky filtru.":::

1. Chcete-li odstranit filtry, vyberte **Vymazat filtry** nebo vyberte **Filtr** a zrušte zaškrtnutí políčka filtru.

> [!NOTE]
> Filtry aktivit se odstraní, když opustíte profil zákazníka. Musíte je použít při každém otevření v zákaznickém profilu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
