---
title: Sémantická mapování (Preview)
description: Přehled sémantických mapování a jejich použití.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881822"
---
# <a name="semantic-mappings-preview"></a>Sémantická mapování (Preview)

Sémantická mapování vám umožňují mapovat data o vaší neaktivitě na předem definovaná schémata. Tato schémata pomáhají přehledům cílové skupiny lépe porozumět vašim datovým atributům. Sémantické mapování a poskytovaná data umožňují nové přehledy a funkce v přehledech cílové skupiny. Chcete -li namapovat data o vaší aktivitě na schémata, zkontrolujte dokumentaci k [aktivitám](activities.md).

**Sémantická mapování jsou aktuálně povolena pro prostředí založená na firemních účtech**. *ContactProfile* je jediným typem sémantického mapování, který je v současnosti k dispozici v přehledech cílové skupiny.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definování mapování sémantické entity ContactProfile

1. V přehledech cílové skupiny jděte na **Data** > **Sémantická mapování (náhled)**.

1. Vyberte **Přidat sémantické mapování** k zahájení řízeného prostředí.

1. V kroku **Data entity** nastavte hodnoty pro následující pole:

   - **Název mapování sémantické entity**: Zadejte název pro mapování sémantické entity.
   - **Zdrojová entita**: Vyberte entitu, která obsahuje kontaktní údaje.
   - **Primární klíč**: Umožňuje vybrat pole, které jedinečně identifikuje záznam kontaktu. Nemělo by obsahovat žádné duplicitní hodnoty, prázdné hodnoty nebo chybějící hodnoty.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Nastavte mapování sémantických entit pomocí názvu, zdrojové entity a primárního klíče.":::

1. Pokračujte kliknutím na tlačítko **Další**.

1. V kroku **Vztahy** nakonfigurujte podrobnosti tak, aby se data o vašem kontaktu připojila k odpovídajícímu záznamu zákaznického účtu. Tento krok vizualizuje spojení mezi entitami.  

   Lze implementovat dva typy cest vztahů: **Přímé vztahy** a **Nepřímé vztahy**. Další informace najdete v [přímých a nepřímých cestách vztahů](relationships.md#relationship-paths).

   1. Výběrem možnosti **Přidat vztah** nakonfigurujte vztah.
   1. Vyberte atribut ze své zdrojové entity, která spojuje vaši kontaktní entitu s jinou entitou.
   1. Vyberte entitu, ke které chcete připojit svou kontaktní entitu. Entitu si můžete vybrat v sekci **Účetní entity** nebo **Zprostředkující entita**. Pokud vyberete zprostředkující entitu, musíte definovat druhý vztah pro připojení k vaší cílové entitě účtu.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Vyberte buď entitu účtu, nebo zprostředkující entitu.":::

   1. Zadejte **název vztahu**. Pokud vztah mezi vašimi entitami již existuje, je název vztahu pouze pro čtení. Pokud žádný vztah neexistuje, bude vytvořen nový vztah se zadaným jménem.
   1. Vyberte **Použít** pro dokončení konfigurace vztahu.

   > [!NOTE]
   > Můžete nakonfigurovat více vztahů mezi entitou kontaktu a jinými entitami účtu se zprostředkujícími entitami.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Vizualizace různých vztahů propojuje entity kontaktu s entitami účtu.":::

1. Vyberte **Další**, až budete s konfigurací vztahu hotovi.

1. V kroku **Nastavit sémantický typ** vyberte **Sémantický typ**. V současné době existuje jeden **Sémantický typ** nazvaný *ContactProfile*.

1. Namapujte data na *sémantický typ* **ContactProfile** pro zobrazená pole.
   - Povinné pole: Contact ID
   - Volitelná pole: Křestní jméno, Příjmení, Datum narození, Pohlaví, Primární e-mail a Primární telefon

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Namapujte atributy svých kontaktních údajů na zadaná povinná a volitelná pole.":::

1. Pokračujte kliknutím na tlačítko **Další**.

1. V kroku **Recenze** se podívejte na konfiguraci sémantického mapování. Vyyberte **Upravit** pro odpovídající sekci k provedení změn.

1. Vyberte **Uložit** pro uložení nového **Sémantického mapování**.

1. Po uložení můžete vybrat proces **Spustit** ke zpracování sémantického mapování nebo můžete vybrat **Zavřít** pro uložení sémantického mapování bez zpracování.

1. Chcete -li sémantické mapování spustit později, vyberte sémantické mapování a vyberte **Obnovit**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Správa stávajících sémantických mapování

Na kartě **Data** > **Sémantická mapování (náhled)** můžete zobrazit všechna uložená sémantická mapování a spravovat je. Každé sémantické mapování je reprezentováno samostatným řádkem. Najdete podrobnosti o zdrojové entitě, sémantickém typu, typu mapování a jeho stavu.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Možnosti správy sémantických mapování.":::

- **Upravit**: Otevře konfiguraci nastavení sémantického mapování v kroku přezkoumání. Aktuální konfiguraci můžete změnit. Vyberte **Uložit** a **Spustit** ke zpracování změn.

- **Obnovit**: Obnoví vybrané sémantické mapování nejaktuálnějšími daty z entit, které jsou součástí jeho konfigurace. Obnovením jakéhokoli daného sémantického mapování se obnoví všechna sémantická mapování stejného typu.

- **Přejmenovat**: Otevře dialog, kde můžete zadat jiný název pro vybrané sémantické mapování. Výběrem možnosti **Uložit** se vaše změny uplatní.

- **Odstranit**: Otevře dialog pro potvrzení odstranění vybraného sémantického mapování. Můžete také odstranit více než jedno sémantické mapování najednou výběrem sémantického mapování a ikonou odstranění. Vyberte **Odstranit** pro potvrzení odstranění.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Pomocí mapování sémantické entity ContactProfile vytvořte aktivity na úrovni kontaktu

Po vytvoření mapování sémantické entity *ContactProfile*, můžete zachytit aktivity kontaktů. Na časové ose aktivity pro obchodní vztah vám umožňuje vidět , který kontakt byl zodpovědný za jednotlivé aktivity. Většina kroků se řídí typickou konfigurací mapování aktivit.

   > [!NOTE]
   > Aby aktivity na úrovni kontaktu fungovaly, musíte mít oba atributy **AccountID** a **ContactID** pro každý záznam v datech aktivity.

1. [Definujte mapování sémantické entity *ContactProfile*.](#define-a-contactprofile-semantic-entity-mapping) a spusťte sémantické mapování.

1. V přehledech cílové skupiny přejděte na **Data** > **Aktivity**.

1. Volbou **Přidat aktivitu** vytvořte novou aktivitu.

1. Pojmenujte aktivitu, vyberte zdrojovou entitu aktivity a vyberte primární klíč entity aktivity.

1. V kroku **Vztahy** vytvořte nepřímý vztah mezi zdroji dat aktivity a obchodními vztahy prostřednictvím vašich kontaktních údajů jako zprostředkující entity. Další informace viz [přímé a nepřímé cesty vztahů](relationships.md#relationship-paths).
   - Příklad vztahu pro aktivitu nazvanou *Nákupy*:
      - **Zdrojová data aktivity pro nákupy** > **Kontaktní údaje** na atributu **ContactID**
      - **Kontaktní údaje** > **Údaje o obchodním vztahu** na atributu **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Ukázkové nastavení vztahu.":::

1. Po nastavení vztahů vyberte **Další** a dokončete konfiguraci mapování aktivit. Podrobné kroky k vytvoření aktivity viz [definování aktivity](activities.md).

1. Spusťte mapování aktivit.

1. Vaše aktivity na úrovni kontaktu budou nyní viditelné na časové ose zákazníka.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Konečný výsledek po konfiguraci kontaktních aktivit":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtrování časové osy aktivity na úrovni kontaktu

Po konfiguraci mapování aktivity na úrovni kontaktu a jejím spuštění se aktualizuje časová osa aktivit vašich zákazníků. Obsahuje jejich ID nebo jména v závislosti na konfiguraci entity *ContactProfile* pro aktivity, které prováděli. Aktivity můžete filtrovat podle kontaktů na časové ose, abyste viděli konkrétní kontakty, které vás zajímají. Kromě toho můžete zobrazit všechny aktivity, které nejsou přiřazeny ke konkrétnímu kontaktu, výběrem možnosti **Aktivity, které nejsou mapovány na kontakt**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Možnosti filtrování dostupné pro aktivity na úrovni kontaktu.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
