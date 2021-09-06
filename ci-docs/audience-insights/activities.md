---
title: Aktivity zákazníka
description: Definování aktivit zákazníků a jejich zobrazení na časové ose zákazníků.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 6ebe899d3e3da43c4108678cd2e4f9a986e18ab35e839044becab4619adb0f14
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033623"
---
# <a name="customer-activities"></a>Aktivity zákazníka

Zkombinujte aktivity zákazníků z [různých zdrojů dat](data-sources.md) v Dynamics 365 Customer Insights k vytvoření časové osy, která chronologicky uvádí aktivity. Zahrňte časovou osu do aplikací Dynamics 365 pomocí řešení [Doplněk Zákaznická karta](customer-card-add-in.md) nebo v řídicím panelu Power BI.

## <a name="define-an-activity"></a>Definování aktivity

Vaše zdroje dat mohou zahrnovat entity s transakčními a aktivními daty z více zdrojů dat. Identifikujte tyto entity a vyberte aktivity, které chcete zobrazit na časové ose zákazníka. Vyberte entitu, která zahrnuje vaši cílovou aktivitu nebo aktivity.

> [!NOTE]
> Entita musí mít alespoň jeden atribut typu **Datum**, aby byla součástí na časové osy zákazníka a nelze přidávat entity bez pole **Datum**. Ovládací prvek **Přidat aktivitu** není povolen, pokud není taková entita nalezena.

1. V přehledech cílové skupiny přejděte na **Data** > **Aktivity**.

1. Výběrem možnosti **Přidat aktivitu** spusťte řízené prostředí pro proces nastavení aktivity.

1. V kroku **Data aktivity** nastavte hodnoty pro následující pole:

   - **Název aktivity**: Vyberte název své aktivity.
   - **Entita**: Vyberte entitu, která obsahuje údaje o transakcích nebo aktivitách.
   - **Primární klíč**: Vyberte pole, které jedinečně identifikuje záznam. Nemělo by obsahovat žádné duplicitní hodnoty, prázdné hodnoty nebo chybějící hodnoty.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nastavte data aktivity s názvem, entitou a primárním klíčem.":::

1. Vyberte **Další** pro přechod k dalšímu kroku.

1. V kroku **Vztah** nakonfigurujte podrobnosti pro propojení dat o aktivitě s odpovídajícím zákazníkem. Tento krok vizualizuje spojení mezi entitami.  

   - **První**: Cizí pole ve vaší entitě aktivity, které se použije k navázání vztahu s jinou entitou.
   - **Druhý**: Odpovídající entita zdrojového zákazníka, se kterou bude vaše entita aktivity ve vztahu. Můžete ji přidružit pouze ke zdrojovým entitám zákazníků, které se používají v procesu sjednocení dat.
   - **Třetí**: Pokud vztah mezi touto entitou aktivity a vybranou entitou zdrojového zákazníka již existuje, název vztahu bude v režimu jen pro čtení. Pokud takový vztah neexistuje, vytvoří se nový vztah se jménem, které uvedete v tomto poli.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definujte vztah entity.":::

1. Vyberte **Další** pro přechod k dalšímu kroku. 

1. V kroku **Sjednocení aktivity** vyberte událost aktivity a čas zahájení aktivity. 
   - **Povinná pole**
      - **Aktivita události**: Pole, které je událostí pro tuto aktivitu.
      - **Časové razítko**: Pole, které představuje čas zahájení vaší aktivity.

   - **Nepovinná pole**
      - **Další podrobnosti**: Pole s příslušnými informacemi pro tuto aktivitu.
      - **Ikona**: Ikona, která nejlépe představuje tento typ aktivity.
      - **Webová adresa**: Pole obsahující adresu URL s informacemi o této aktivitě. Například transakční systém, který tuto aktivitu využívá. Tato adresa URL může být libovolné pole zdroje dat, nebo může být vytvořeno jako nové pole pomocí transformace Power Query. Data URL budou uložena v entitě *Sjednocená aktivita*, kterou lze následně spotřebovat pomocí [API](apis.md).
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Zadejte údaje o aktivitě zákazníka v entitě Unified Activity.":::

1. Volbou **Další** přejdete na další krok. Můžete vybrat **Dokončit a zkontrolovat** pro uložení aktivity nyní s typem aktivity nastaveným na **Jiný**. 

1. V kroku **Typ aktivity** vyberte typ aktivity a volitelně vyberte, zda chcete sémanticky mapovat některé typy aktivit pro použití v jiných oblastech Customer Insights. V současné době lze typy aktivit *Předplatné* a *SalesOrderLine* sémanticky mapovat po souhlasu s mapováním polí. Pokud typ aktivity není pro novou aktivitu relevantní, můžete si vybrat *Jiný* nebo *Vytvořit nový* pro vlastní typ aktivity.

1. Volbou **Další** přejdete na další krok. 

1. V kroku **Kontrola** ověřte výběr. Vraťte se k některému z předchozích kroků a v případě potřeby informace aktualizujte.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Zkontrolujte aktivitu v zadaných polích.":::
   
1. Vyberte **Uložit aktivitu** pro použití změn a vyberte **Hotovo** pro návrat na **Data** > **Aktivity**. Zde vidíte, které aktivity jsou nastaveny tak, aby se zobrazovaly na časové ose. 

1. Na stránce **Aktivity** vyberte **Spustit** ke zpracování aktivity. 

> [!TIP]
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies). Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy. Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.


## <a name="manage-existing-activities"></a>Správa existujících aktivit

Na stránce **Data** > **Aktivity** můžete zobrazit všechny uložené aktivity a spravovat je. Každá aktivita je reprezentována řádkem, který také obsahuje podrobnosti o zdroji, entitě a typu aktivity.

Následující akce jsou k dispozici, když vyberete aktivitu. 

- **Upravit**: Otevře nastavení aktivity v kroku kontroly. Z tohoto kroku můžete změnit některou nebo celou aktuální konfiguraci. Po změně konfigurace vyberte **Uložit aktivitu** a poté vyberte **Spustit** ke zpracování změn.

- **Přejmenovat**: Otevře dialogové okno, kde můžete zadat jiný název vybrané aktivity. Výběrem možnosti **Uložit** se vaše změny uplatní.

- **Vymazat**: Otevře dialogové okno s potvrzením odstranění vybrané aktivity. Můžete také odstranit více než jednu aktivitu najednou tak, že vyberete aktivity a poté vyberete ikonu odstranění. Vyberte **Odstranit** pro potvrzení odstranění.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
