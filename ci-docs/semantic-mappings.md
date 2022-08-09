---
title: Sémantická mapování (Preview)
description: Přehled sémantických mapování a jejich použití.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183623"
---
# <a name="semantic-mappings-preview"></a>Sémantická mapování (Preview)

Sémantická mapování vám umožňují mapovat data o vaší neaktivitě na předem definovaná schémata. Tato schémata pomáhají Customer Insights lépe porozumět vašim datovým atributům. Sémantické mapování a poskytovaná data umožňují nové přehledy a funkce v Customer Insights. Chcete -li namapovat data o vaší aktivitě na schémata, zkontrolujte dokumentaci k [aktivitám](activities.md).

**Sémantická mapování jsou aktuálně povolena pro prostředí založená na firemních účtech**. *ContactProfile* je jediným typem sémantického mapování, který je v současnosti k dispozici v Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definování mapování sémantické entity ContactProfile

1. Přejděte na **Data** > **Sémantická mapování (Preview)**.

1. Vyberte **Přidat sémantické mapování** k zahájení řízeného prostředí.

1. V kroku **Data entity** nastavte hodnoty pro následující pole:

   - **Název mapování sémantické entity**: Název mapování sémantické entity.
   - **Zdrojová entita**: Entita, která obsahuje kontaktní údaje.
   - **Primární klíč**: Pole, které jedinečně identifikuje záznam kontaktu. Nemělo by obsahovat žádné duplicitní hodnoty, prázdné hodnoty nebo chybějící hodnoty.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Nastavte mapování sémantických entit pomocí názvu, zdrojové entity a primárního klíče.":::

1. Vyberte **Další**.

1. V kroku **Vztahy** nakonfigurujte podrobnosti tak, aby se data o vašem kontaktu připojila k odpovídajícímu záznamu zákaznického účtu. Tento krok vizualizuje spojení mezi entitami.  

   Lze implementovat dva typy cest vztahů: **Přímé vztahy** a **Nepřímé vztahy**. Další informace najdete v [přímých a nepřímých cestách vztahů](relationships.md#relationship-paths).

   1. Výběrem možnosti **Přidat vztah** nakonfigurujte vztah.
   1. Vyberte atribut ze své zdrojové entity, která spojuje vaši kontaktní entitu s jinou entitou.
   1. Vyberte entitu, ke které chcete připojit svou kontaktní entitu. Vyberte entitu v sekci **Entity obchodního vztahu** nebo **Zprostředkující entita**. Pokud vyberete zprostředkující entitu, definujte druhý vztah pro připojení k vaší cílové entitě účtu.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Vyberte buď entitu účtu, nebo zprostředkující entitu.":::

   1. Zadejte **název vztahu**. Pokud vztah mezi vašimi entitami již existuje, je název vztahu pouze pro čtení. Pokud žádný vztah neexistuje, bude vytvořen nový vztah se zadaným jménem.
   1. Vyberte **Použít** pro dokončení konfigurace vztahu.

   > [!NOTE]
   > Můžete nakonfigurovat více vztahů mezi entitou kontaktu a jinými entitami účtu se zprostředkujícími entitami.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Vizualizace různých vztahů propojuje entity kontaktu s entitami účtu.":::

1. Vyberte **Další**.

1. V kroku **Nastavit sémantický typ** vyberte **Sémantický typ**. V současné době existuje jeden **Sémantický typ** nazvaný *ContactProfile*.

1. Namapujte své ID kontaktu na sémantický typ *ContactProfile* **ID kontaktu**. Volitelně namapujte další pole, například křestní jméno, příjmení, pohlaví nebo e-mail.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Namapujte atributy svých kontaktních údajů na zadaná povinná a volitelná pole.":::

1. Vyberte **Další**.

1. V kroku **Kontrola** zkontrolujte konfiguraci sémantického mapování. Chcete-li provést změny, vyberte **Upravit** pro odpovídající sekci.

1. Vyberte **Uložit**.

1. Pro zpracování sémantického mapování vyberte **Spustit**. Nebo volbou **Zavřít** uložte vaše sémantické mapování bez jeho zpracování. Chcete-li jej spustit později, vyberte sémantické mapování a vyberte **Aktualizovat**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Správa stávajících sémantických mapování

Jděte na **Data** > **Sémantická mapování (Preview)** pro zobrazení uložených sémantických mapování, jejich zdrojových entit, sémantického typu, typu mapování a stavu.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Možnosti správy sémantických mapování.":::

Vyberte sémantické mapování pro zobrazení dostupných akcí.
- **Upravte** aktuální konfiguraci. Vyberte **Uložit** a **Spustit** ke zpracování změn.
- **Aktualizujte** sémantické mapování, aby obsahovalo nejnovější data. Obnovením jakéhokoli daného sémantického mapování se obnoví všechna sémantická mapování stejného typu.
- **Odeberte** sémantické mapování. Vyberte **Uložit**.
- **Odstraňte** sémantické mapování. Chcete-li odstranit více než jedno sémantické mapování najednou, vyberte sémantické mapování a ikonu odstranění. Vyberte **Odstranit** pro potvrzení odstranění.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Pomocí mapování sémantické entity ContactProfile vytvořte aktivity na úrovni kontaktu

Po vytvoření mapování sémantické entity *ContactProfile*, můžete zachytit aktivity kontaktů. Na časové ose aktivity pro obchodní vztah vám umožňuje vidět , který kontakt byl zodpovědný za jednotlivé aktivity. Většina kroků se řídí typickou konfigurací mapování aktivit.

   > [!NOTE]
   > Aby aktivity na úrovni kontaktu fungovaly, musíte mít oba atributy **AccountID** a **ContactID** pro každý záznam v datech aktivity.

1. [Definujte sémantické mapování entity *ContactProfile*](#define-a-contactprofile-semantic-entity-mapping) a spusťte sémantické mapování.

1. Přejděte na **Data** > **Aktivity**.

1. Volbou **Přidat aktivitu** vytvořte novou aktivitu.

1. Pojmenujte aktivitu, vyberte zdrojovou entitu aktivity a vyberte primární klíč entity aktivity.

1. V kroku **Vztahy** vytvořte nepřímý vztah mezi zdroji dat aktivity a obchodními vztahy prostřednictvím vašich kontaktních údajů jako zprostředkující entity. Další informace viz [přímé a nepřímé cesty vztahů](relationships.md#relationship-paths).
   - Příklad vztahu pro aktivitu nazvanou *Nákupy*:
      - **Zdrojová data aktivity pro nákupy** > **Kontaktní údaje** na atributu **ContactID**
      - **Kontaktní údaje** > **Údaje o obchodním vztahu** na atributu **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Ukázkové nastavení vztahu.":::

1. Po nastavení vztahů vyberte **Další** a dokončete konfiguraci mapování aktivit. Podrobné kroky k vytvoření aktivity viz [definování aktivity](activities.md).

1. Spusťte mapování aktivit.

1. Po spuštění mapování aktivity na úrovni kontaktu vyberte **Zákazníci**. Aktivity na úrovni kontaktu se zobrazí na časové ose zákazníka.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Konečný výsledek po konfiguraci kontaktních aktivit":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtrování časové osy aktivity na úrovni kontaktu

Časová osa aktivity vašich zákazníků obsahuje jejich ID nebo jména v závislosti na konfiguraci entity *ContactProfile* pro aktivity, které prováděli. Aktivity můžete filtrovat podle kontaktů na časové ose, abyste viděli konkrétní kontakty, které vás zajímají. Chcete-li zobrazit všechny aktivity, které nejsou přiřazeny ke konkrétnímu kontaktu, vyberte možnost **Aktivity, které nejsou mapovány na kontakt**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Možnosti filtrování dostupné pro aktivity na úrovni kontaktu.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
