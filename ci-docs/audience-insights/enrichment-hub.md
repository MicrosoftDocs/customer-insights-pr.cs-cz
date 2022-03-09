---
title: Rozšíření sjednocených profilů zákazníka
description: Využijte možnosti rozšíření svých zákaznických dat.
ms.date: 02/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e8cac35ccf7012524dc22cb4a499dc605dd66346
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355375"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Rozšíření profilů zákazníků (náhled)

K rozšíření svých zákaznických dat použijte data ze zdrojů, jako je Microsoft a další partneři.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra rozšíření.":::

V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**, kde můžete pracovat s možnostmi rozšíření.  

K vytváření nebo úpravě rozšíření musíte mít oprávnění přispěvatele nebo správce. Další informace naleznete v části [Oprávnění](permissions.md).

Na kartě **Objevit** najdete všechny podporované možnosti obohacení.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

- [Značky](enrichment-microsoft.md) poskytované společností Microsoft
- [Zájmy](enrichment-microsoft.md) poskytované společností Microsoft
- [Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované společností Microsoft 
- [Demografické údaje](enrichment-experian.md) poskytované společností Experian
- [Vlastní data](enrichment-SFTP-custom-import.md) prostřednictvím vlastního importu protokolu (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) poskytuje společnost Microsoft
- [Údaje o poloze](enrichment-here.md) poskytované společností HERE Technologies 

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

- [Údaje o společnosti](enrichment-leadspace.md) poskytované společností Leadspace
- [Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované společností Microsoft 
- [Vylepšená data společnosti](enrichment-enhanced-company-data.md) poskytnutá společností Microsoft
- [Údaje o poloze](enrichment-here.md) poskytované společností HERE Technologies 
- [Vlastní data](enrichment-SFTP-custom-import.md) prostřednictvím vlastního importu protokolu (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) poskytuje společnost Microsoft
- [Data o zapojení obchodního vztahu](enrichment-office.md) poskytované společností Microsoft

---

Na kartě **Moje rozšíření** se můžete podívat na rozšíření, která jste nakonfigurovali, a upravit jejich vlastnosti.

## <a name="manage-existing-enrichments"></a>Správa existujících rozšíření

Jděte na kartu **Moje obohacení**, kde zobrazíte všechna nakonfigurovaná obohacení. Každé rozšíření je uvedeno jako jeden jako řádek, který obsahuje další informace o rozšíření.

Výběrem rozšíření zobrazíte dostupné možnosti. Můžete také vybrat tři tečky (...) na položce seznamu a zobrazit možnosti. Pokud jste nakonfigurovali několik rozšíření, můžete je rychle najít pomocí vyhledávacího pole.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti správy rozšíření v seznamu rozšíření.":::

- Možností **Zobrazit** zobrazíte podrobnosti o rozšíření s počtem rozšířených profilů zákazníků.
- Možností **Upravit** upravíte konfiguraci rozšíření.
- **Spustit** rozšíření k aktualizaci profilů zákazníků o nejnovější data.
- Možností **Deaktivovat** zastavíte automatické aktualizace rozšíření při každé plánované aktualizaci. Data z poslední úspěšné aktualizace budou nadále k dispozici. Možností **Aktivovat** restartujete automatické aktualizace rozšíření s každou plánovanou aktualizací.
- **Odstraňte** rozšíření.

Spusťte nebo deaktivujte více rozšíření najednou jejich výběrem v seznamu. Možnosti zobrazení a úprav nejsou k dispozici jako hromadné akce. Pracují vždy jen na jedno rozšíření.

## <a name="enrichments-and-connections"></a>Rozšíření a propojení 

Rozšíření třetích stran se konfigurují pomocí [připojení](connections.md), které správce nastaví pomocí pověření a poskytne souhlas s datovými přenosy. Připojení mohou používat správci a přispěvatelé ke konfiguraci obohacení.  

## <a name="multiple-enrichments-of-the-same-type"></a>Více rozšíření stejného typu

Entita, kterou chcete rozšířit, je zadána během konfigurace rozšíření, což vám umožní rozšířit pouze podmnožinu vašich profilů. Například obohaťte data pouze pro konkrétní segment. Můžete nakonfigurovat několik rozšíření stejného typu a znovu použít stejné propojení . Některá rozšíření budou mít rozšíření počtu obohacení stejného typu, které lze vytvořit. Limity a současné použití lze zobrazit na stránce **Rozšíření**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Podívejte se na průběh procesu obohacování

Můžete najít podrobnosti o zpracování obohacení, včetně jeho stavu a potenciálních problémů, v průběhu obnovování nebo po dokončení aktualizace. Pochopte, které procesy jsou zahrnuty pro aktualizaci obohacení, a jak dlouho trvalo spuštění procesů. Stav obohacení je podporován pro Experian, Leadspace, HERE Technologies, SFTP Import a Azure Maps.

Chcete -li zobrazit stav obohacení

1. Přejděte na **Data** > **Rozšíření**. 
1. Na karě **Moje obohacení** vyberte stav obohacení a otevřete boční panel. 
1. V podokně **Podrobnosti o průběhu** rozbalte část **Obohacení**. 
1. Pod obohacením, pro které chcete vidět průběh, vyberte **Zobrazit podrobnosti**. 
1. V podokně **Podrobnosti o úkolu** vyberte **Zobrazit podrobnosti** a zobrazte procesy, které se podílejí na aktualizaci obohacení, a jejich stav. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
