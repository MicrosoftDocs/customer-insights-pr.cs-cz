---
title: Trychtýřové sestavy
description: Jak používat trychtýřové sestavy k pochopení toho, jak se cílová skupina rozhoduje.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/17/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 901e7ec50037d66c7c5ceb635d1c6cda6cfff83b
ms.sourcegitcommit: 3bafa27adae113948636b30c7462e0af060c7131
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/17/2021
ms.locfileid: "7498634"
---
# <a name="create-and-manage-funnel-reports"></a>Vytvoření a správa trychtýřových sestav

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Trychtýřová sestava shromažďuje informace o krocích, ke kterým dojde během cesty zákazníka prostřednictvím vašeho webu nebo mobilní aplikace. Pomáhá vám pochopit, jak cílová skupina postupuje procesem a identifikuje místa opuštění. Například můžete použít trychtýřovou sestavu k identifikaci cest, které vaši zákazníci provádějí před nákupem. Trychtýřová sestava poskytuje údaje, které slouží k informování rozhodnutí a identifikaci oblastí pro optimalizaci a vylepšení procesů.

## <a name="create-a-funnel-report"></a>Vytvoření trychtýřové sestavy

Chcete-li vytvořit trychtýřovou sestavu, zadejte kroky, které chcete zahrnout, a aktivitu pro každý krok. Aktivita je [událost](glossary.md), která představuje chování uživatele. Trychtýřová sestava zobrazuje počet uživatelů, kteří dokončili každý definovaný krok. 

1. Trychtýřovou sestavu spustíte přechodem na **Trychtýře** a výběrem **+ Nový trychtýř**.

1. V **Editoru trychtýře** pod **Kroky** vyberte **+Přidat krok**. 

1. Zadejte název do **Název kroku**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Nová trychtýřová sestava.":::

1. Vyberte **aktivitu**. Aktivita se zaznamenává, kdy uživatel zobrazí stránku (aktivita **Zobrazení**) nebo interaguje s obsahem (aktivita **Akce**).

1. Pomocí **Kritéria kroku** můžete určit dimenze aktivity. [Dimenze](dimensions.md) jsou atributy, které mohou popisovat, filtrovat nebo seskupovat data.

1. Volitelně můžete konfigurovat kroky trychtýře s více podmínkami. Vyberte položku **Přidat podmínku** a určete více dimenzí v kroku. Další kritéria musejí používat stejný typ aktivity. U více podmínek můžete zvolit, zda jsou spojeny operátorem AND nebo OR.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Editor trychtýře zobrazující konfiguraci kroku u kroků s více podmínkami.":::

1. Vybírejte **Přidat krok**, dokud nedokončíte všechny kroky, které v přehledu chcete.

1. Vyberte **Uložit**, zprávu pojmenujte a znovu vyberte **Uložit**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Příklad: Trychtýřová sestava společnosti Fourth Coffee

Následující scénář ukazuje jeden způsob použití trychtýřové sestavy. Analytik společnosti Fourth Coffee chce pochopit vliv nedávné propagace na sazby předplatného. Analytik vytvoří trychtýřovou sestavu k identifikaci aktivity zákazníka. Začíná to, když zákazníci dorazí na domovskou stránku společnosti, dokud nepoužijí propagační kód předplatného. Analytik vytvoří přehled cesty s následujícími kroky:

Krok 1: Zákazníci, kteří začnou na domovské stránce   
Krok 2: Zákazníci, kteří provedou nákup   
Krok 3: Zákazníci, kteří používají propagační kód k získání slevy na předplatné   
Krok 4: Registrace předplatného   

:::image type="content" source="media/funnel-report-example.png" alt-text="příklad trychtýřové sestavy.":::
  
Tento trychtýř umožňuje zobrazit počet uživatelů, kteří použili propagační kód po jednorázovém nákupu k přihlášení k odběru.

### <a name="configure-advanced-settings"></a>Konfigurace upřesňujících nastavení 

Trychtýřové sestavy vám umožňují definovat omezení času potřebného k dokončení trychtýře. Můžete například nastavit čas dokončení trychtýře na čtyři dny. Toto nastavení bude počítat pouze úspěšné registrace předplatného, ke kterým došlo do čtyř dnů od doby, kdy uživatel navštívil domovskou stránku.

1. Přejděte na **Trychtýře** a otevřete **Knihovna trychtýřů**.

1. Otevřete sestavu výběrem jejího názvu. 

1. V podokně **Editor trychtýře** vyberte **Rozšířená nastavení**. 

1. Nastavte možnost Omezit dobu dokončení trychtýře na **Zapnuto**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Editor trychtýře zobrazující rozšířené nastavení a možnosti omezující čas na dokončení trychtýře.":::

1. Vyberte čas, ve kterém musí být trychtýř dokončen, v rozevíracím seznamu **Nastavit limit na**.

1. Výběrem možnosti **Uložit** se vaše změny uplatní.


## <a name="cross-channel-funnel-reports"></a>Trychtýřové sestavy cest napříč kanály 

Statistiky zapojení mohou také shromažďovat údaje o chování zákazníků ve vaší mobilní aplikaci. Jakmile vybavíte svou mobilní aplikaci přehledy zapojení [Android SDK](get-started-android.md) nebo [iOS SDK](get-started-ios.md), můžete vytvářet trychtýřové sestavy napříč kanály. 

### <a name="create-a-cross-channel-funnel-report"></a>Vytvoření trychtýřové sestavy napříč kanály 

1. Postupujte podle pokynů k [vytvoření trychtýřové sestavy](#create-a-funnel-report).    

1. Chcete-li sledovat, jak zákazníci interagují s vaší značkou na vašem webu i v mobilní aplikaci nebo na více webech, použijte přepínač pracovního prostoru k vytvoření kroků cesty s daty z jiných pracovních prostorů. V **trychtýřovém editoru** v části **Kroky** vyberte, že kterého pracovního prostoru by měla pocházet data pro krok trychtýře.

## <a name="manage-funnel-reports"></a>Správa trychtýřových sestav

Trychtýřové sestavy můžete používat k analýze dat, sledování výkonu a shromažďování přehledů.

> [!NOTE]
> - Trychtýřové sestavy přehledu zapojení aktuálně podporují scénáře, ve kterých jsou všichni uživatelé v trychtýři anonymní nebo jsou všichni uživatelé ověřeni. 
> - Historická data v trychtýřových sestavách jsou k dispozici za posledních 30 dní.

### <a name="view-funnel-reports"></a>Zobrazení trychtýřových sestav

1. Přejděte na **Trychtýře** a otevřete **Knihovna trychtýřů**.
1. Otevřete sestavu výběrem jejího názvu.    

### <a name="see-the-data-collected-for-a-report"></a>Podívejte se na údaje shromážděné pro sestavu   

Chcete-li zobrazit informace o fázi

- Namiřte na krok v sestavě.

:::image type="content" source="media/funnel-step-data.png" alt-text="data trychtýře.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Změna časového období pro trychtýřovou sestavu

1. Přejděte na **Trychtýře** a otevřete **Knihovna trychtýřů**.

1. Otevřete sestavu výběrem jejího názvu.

1. Otevřete **časový rozsah** a vyberte nové časové období ze seznamu nebo **Pevné časové období** k určení časového období.

## <a name="edit-or-delete-funnel-reports"></a>Úprava nebo mazání trychtýřových sestav

Můžete změnit název trychtýřové sestavy, odstranit ji nebo upravit kroky v sestavě.

### <a name="rename-or-delete-a-funnel-report"></a>Přejmenování nebo odstranění trychtýřové sestavy

1. Přejděte na **Trychtýře** a otevřete **Knihovna trychtýřů**. 

1. Vyberte **Více** vedle sestavy, kterou chcete změnit, a vyberte **Upravit název** nebo **Odstranit**.

### <a name="edit-a-funnel-step"></a>Úprava kroku trychtýře  

1. Přejděte na **Trychtýře** a otevřete **Knihovna trychtýřů**. 

1. Otevřete sestavu výběrem jejího názvu.

1. Vyberte krok, který chcete upravit.

1. Vyberte položku **Upravit**.

1. V **Editoru trychtýře** aktualizujte informace, které chcete změnit.  

1. Zvolte **Uložit**.

### <a name="reorder-a-funnel-step"></a>Úprava pořadí kroků trychtýře

1. Přejděte na **Trychtýře** a otevřete **Knihovna trychtýřů**. 

1. Otevřete sestavu výběrem jejího názvu.

1. Vyberte krok, jehož pořadí chcete změnit.

1. Vyberte **Přesunout** a pak **Nahoru**, **Dolů**, **Na začátek** nebo **Na konec** k posunutí kroku.

### <a name="delete-a-funnel-step"></a>Odstranění kroku trychtýře

1. Přejděte na **Trychtýře** a otevřete **Knihovna trychtýřů**. 

1. Otevřete sestavu výběrem jejího názvu.

1. Vyberte krok, který chcete odebrat, a poté zvolte **Odstranit**.

## <a name="funnel-insights"></a>Přehledy trychtýře 

Přehledy zapojení nyní nabízí přehledy trychtýře pro zákazníky. Pomocí přehledů trychtýře získáte hlubší vhled do chování zákazníků ohledně kroků v sestavě trychtýře. Když vytvoříte a uložíte novou sestavu trychtýře, automaticky se pro vaši sestavu vygenerují přehledy trychtýře. 

Přehledy trychtýře můžete zobrazit v následujících kategoriích, na hlavní i krokové úrovni: 

 - Převodní poměr 
 - Doba přechodu 
 - Čas dokončení 

Využijte tyto poznatky k hlubšímu prozkoumání chování zákazníků a lepšímu porozumění bodům opuštění a konverzím v sestavě trychtýře. 

Přehledy trychtýře se přepočítávají každých 24 hodin, nebo když **uložíte** svou sestavu trychtýře. 

> [!NOTE]
> Abyste mohli zobrazit přehledy svého trychtýře, musíte sestavu uložit při každé změně. 

