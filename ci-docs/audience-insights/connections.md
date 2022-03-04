---
title: Propojení k dalším službám z Customer Insights.
description: Sdílejte data s dalšími službami.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: ccad090d3bf6eab96eff37f7a96289ca2882d369
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354375"
---
# <a name="connections-preview-overview"></a>Přehled propojení (preview)

Propojení jsou klíčem k povolení sdílení dat do a z Customer Insights. Každé propojení navazuje sdílení dat s konkrétní službou. Propojení jsou základem [konfigurace rozšíření třetích stran](enrichment-hub.md) a [konfigurace exportů](export-destinations.md). Stejné propojení lze použít vícekrát. Například jedno propojení k Dynamics 365 Marketing funguje pro více exportů a jedno propojení Leadspace lze použít pro několik rozšíření.

Jděte na **Správce** > **Propojení** k vytvoření a zobrazení propojení.

Na kartě **Propojení** se zobrazují všechna aktivní propojení. Seznam zobrazuje řádek pro každé propojení. 

Získejte rychlý přehled, popis a zjistěte, co můžete dělat s každou možností rozšiřitelnosti na kartě **Objev**.

### <a name="exports"></a>Exporty

Pouze správci mohou konfigurovat nová propojení, ale mohou udělit přístup přispěvatelům k použití stávajících propojení. Správci kontrolují, kam mohou data směřovat, přispěvatelé definují datovou část a frekvenci podle svých potřeb. Další informace viz [Umožnění přispěvatelům použít připojení pro export](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Rozšíření

Jenom správci mohou konfigurovat nová propojení, ale vytvořená propojení jsou vždy k dispozici správcům i přispěvatelům. Správci spravují přihlašovací údaje a udělují souhlas s datovými přenosy. Následně mohou správci i přispěvatelé propojení použít.

## <a name="add-a-new-connection"></a>Přidat nové propojení

Chcete-li přidat propojení, musíte mít [oprávnění správce](permissions.md). Pokud se připojíte k jiným službám společnosti Microsoft, předpokládáme, že jsou obě služby ve stejné organizaci.

1. Přejděte na **Správce** > **Propojení (náhled)**.

1. Přejde na kartu **Propojení**.

1. Výběrem možnosti **Přidat propojení** vytvořte nové propojení. Z rozbalovací nabídky vyberte, jaký typ připojení chcete vytvořit.

1. V podokně **Nastavení propojení** uveďte požadované podrobnosti. 
   1. Propojení popisuje **zobrazované jméno** a typ propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl tohoto propojení.
   1. Přesná pole závisí na tom, ke které službě se připojujete. V článku o cílové službě se můžete dozvědět o podrobnostech konkrétního typu propojení.
   1. Pokud [použijete vlastní trezor klíčů](use-azure-key-vault.md) k uložení tajných kódů, aktivujte **Použít trezor klíčů** a vyberte tajný kód ze seznamu.

1. Pokud chcete vytvořit propojení, vyberte **Uložit**.

Můžete také vybrat **Založit** na dlaždici na kartě **Objevit**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Umožnit přispěvatelům použít propojení pro export

Při nastavování nebo úpravách propojení pro export si vyberete, kterým uživatelům je povoleno definovat toto konkrétní propojení [exporty](export-destinations.md). Ve výchozím nastavení je propojení k dispozici uživatelům s rolí správce. Toto nastavení můžete změnit v části **Vyberte, kdo může toto propojení použít** a umožnit uživatelům s rolí přispěvatel používat toto propojení.

- Přispěvatelé nebudou moci propojení zobrazit ani upravit. Při vytváření exportu uvidí pouze zobrazované jméno a jeho typ.
- Sdílením propojení umožňujete přispěvatelům propojení používat. Přispěvatelé uvidí sdílená propojení, když nastaví export. Mohou spravovat každý export, který používá toto konkrétní propojení.
- Toto nastavení můžete změnit při zachování exportů, které již byly definovány přispěvateli.

## <a name="edit-a-connection"></a>Úprava propojení

1. Přejděte na **Správce** > **Propojení (náhled)**.

1. Přejde na kartu **Propojení**.

1. Vyberte vertikální tři tečky pro cíl propojení, který chcete upravit.

1. Vyberte položku **Upravit**.

1. Změňte hodnoty, které chcete aktualizovat, a vyberte **Uložit**.

## <a name="remove-a-connection"></a>Odebrání propojení

Pokud propojení, které odebíráte, používá rozšíření nebo export, musíte je nejprve odpojit nebo odebrat. Dialogové okno odebrání vás provede příslušným rozšířením nebo exportem. 

Oddělená rozšíření a exporty se stanou neaktivními. Znovu je aktivujete přidáním dalšího propojení na stránce [Rozšíření](enrichment-hub.md) nebo [Exporty](export-destinations.md).

1. Přejděte na **Správce** > **Propojení (náhled)**.

1. Přejde na kartu **Propojení**.

1. Vyberte vertikální tři tečky pro cíl propojení, který chcete odebrat.

1. V rozevírací nabídce vyberte možnost **Odebrat**. Zobrazí se dialogové okno s potvrzením.

   1. Pokud existují rozšíření nebo exporty, která toto propojení používají, vyberte tlačítko a podívejte se, co propojení používá.
      - **Exporty:** Můžete se rozhodnout buď odebrat nebo odpojit exporty, abyste mohli odebrat propojení. Pro odpojení exportu mohou správci použít akci **Odpojit**. Tato akce je k dispozici pro jednotlivé a více vybraných exportů. Odpojením zachováte exportní konfiguraci, ale nebude spuštěna, dokud k ní nebude přidáno další propojení.
      - **Rozšíření:** Můžete se rozhodnout buď odebrat nebo deaktivovat rozšíření, abyste mohli odebrat propojení. 
   1. Jakmile propojení již nemá žádné závislosti, vraťte se zpět na **Správce** > **Propojení** a zkuste propojení znovu odebrat.

1. Odstranění potvrďte výběrem **Odstranit**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Nastavte připojení pomocí tajných kódů spravovaných vaším vlastním trezorem klíčů

Některá připojení vyžadují tajné kódy, jako jsou klíče API nebo hesla. Některá připojení podporují tajné kódy uložené ve vašem vlastním trezoru klíčů. Další informace o podporovaných připojeních a o tom, jak je nastavit ve [vašem vlastním trezoru klíčů pro přehledy cílové skupiny](use-azure-key-vault.md).
