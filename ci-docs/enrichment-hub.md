---
title: Rozšíření sjednocených profilů zákazníka
description: Využijte možnosti rozšíření svých zákaznických dat.
ms.date: 03/29/2022
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
ms.openlocfilehash: 5c14e6c96d2f907ba161331b6f92277191cbdbef
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653515"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Rozšíření profilů zákazníků (náhled)

K rozšíření svých zákaznických dat použijte data ze zdrojů, jako je Microsoft a další partneři.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra rozšíření.":::

Přejděte na **Data** > **Rozšíření**, chcete-li pracovat s možnostmi rozšíření.  

K vytváření nebo úpravě rozšíření musíte mít oprávnění přispěvatele nebo správce. Další informace naleznete v části [Oprávnění](permissions.md).

Na kartě **Objevit** najdete všechny podporované možnosti rozšíření.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

- [Značky](enrichment-microsoft.md) poskytované společností Microsoft
- [Zájmy](enrichment-microsoft.md) poskytované společností Microsoft
- [Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované společností Microsoft 
- [Demografické údaje](enrichment-experian.md) poskytované společností Experian
- [Vlastní data](enrichment-SFTP-custom-import.md) prostřednictvím vlastního importu protokolu (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) poskytuje společnost Microsoft
- [Údaje o poloze](enrichment-here.md) poskytované společností HERE Technologies 
- [Identitu](enrichment-liveramp.md) poskytuje společnost LiveRamp AbiliTec

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

- [Údaje o společnosti](enrichment-leadspace.md) poskytované společností Leadspace
- [Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované společností Microsoft 
- [Vylepšená data společnosti](enrichment-enhanced-company-data.md) poskytnutá společností Microsoft
- [Údaje o poloze](enrichment-here.md) poskytované společností HERE Technologies 
- [Vlastní data](enrichment-SFTP-custom-import.md) prostřednictvím vlastního importu protokolu (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) poskytuje společnost Microsoft
- [Firemní data](enrichment-dnb.md) z Dun & Bradstreet
- [Data o zapojení obchodního vztahu](enrichment-office.md) poskytované společností Microsoft

---

Na kartě **Moje rozšíření** se můžete podívat na rozšíření, která jste nakonfigurovali, a upravit jejich vlastnosti.

## <a name="manage-existing-enrichments"></a>Správa existujících rozšíření

Jděte na kartu **Moje rozšíření**, kde zobrazíte všechna nakonfigurovaná rozšíření. Každé rozšíření je uvedeno jako jeden jako řádek, který obsahuje další informace o rozšíření.

Výběrem rozšíření zobrazíte dostupné možnosti. Můžete také vybrat tři tečky (...) na položce seznamu a zobrazit možnosti. Pokud jste nakonfigurovali několik rozšíření, můžete je rychle najít pomocí vyhledávacího pole.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti správy rozšíření v seznamu rozšíření.":::

- Možností **Zobrazit** zobrazíte podrobnosti o rozšíření s počtem rozšířených profilů zákazníků.
- Možností **Upravit** upravíte konfiguraci rozšíření.
- **Spustit** rozšíření k aktualizaci profilů zákazníků o nejnovější data.
- Možností **Deaktivovat** zastavíte automatické aktualizace rozšíření při každé plánované aktualizaci. Data z poslední úspěšné aktualizace budou nadále k dispozici. Možností **Aktivovat** restartujete automatické aktualizace rozšíření s každou plánovanou aktualizací.
- **Odstraňte** rozšíření.

Spusťte nebo deaktivujte více rozšíření najednou jejich výběrem v seznamu. Možnosti zobrazení a úprav nejsou k dispozici jako hromadné akce. Pracují vždy jen na jedno rozšíření.

## <a name="enrichments-and-connections"></a>Rozšíření a propojení 

Rozšíření třetích stran se konfigurují pomocí [připojení](connections.md), které správce nastaví pomocí pověření a poskytne souhlas s datovými přenosy. Připojení mohou používat správci a přispěvatelé ke konfiguraci rozšíření.  

## <a name="multiple-enrichments-of-the-same-type"></a>Více rozšíření stejného typu

Entita, kterou chcete rozšířit, je zadána během konfigurace rozšíření, což vám umožní rozšířit pouze podmnožinu vašich profilů. Například rozšiřte data pouze pro konkrétní segment. Můžete nakonfigurovat několik rozšíření stejného typu a znovu použít stejné propojení . Některá rozšíření budou mít rozšíření počtu rozšíření stejného typu, které lze vytvořit. Limity a současné použití lze zobrazit na stránce **Rozšíření**.

## <a name="enrich-data-sources-before-unification"></a>Rozšíření zdrojů dat před sjednocením

Před sjednocením dat můžete rozšířit zákaznická data, abyste zvýšili kvalitu shody dat. Další informace najdete v tématu [Rozšíření zdroje dat](data-sources-enrichment.md).

## <a name="see-the-progress-of-the-enrichment-process"></a>Podívejte se na průběh procesu rozšíření

Můžete najít podrobnosti o zpracování rozšíření, včetně jeho stavu a potenciálních problémů, v průběhu obnovování nebo po dokončení aktualizace. Pochopte, které procesy jsou zahrnuty pro aktualizaci rozšíření, a jak dlouho trvalo spuštění procesů. Stav rozšíření je podporován pro Experian, Leadspace, HERE Technologies, SFTP Import a Azure Maps.

Chcete -li zobrazit stav rozšíření

1. Přejděte na **Data** > **Rozšíření**. 
1. Na karě **Moje rozšíření** vyberte stav rozšíření a otevřete boční panel. 
1. V podokně **Podrobnosti o průběhu** rozbalte část **Rozšíření**. 
1. Pod rozšířením, pro které chcete vidět průběh, vyberte **Zobrazit podrobnosti**. 
1. V podokně **Podrobnosti o úkolu** vyberte **Zobrazit podrobnosti** a zobrazte procesy, které se podílejí na aktualizaci rozšíření, a jejich stav. 

## <a name="enrichment-results"></a>Výsledky rozšíření

Po dokončení rozšíření můžete zkontrolovat jeho výsledky.

1. Přejděte na **Data** > **Rozšíření**. 
1. Vyberte rozšíření, o kterém chcete informace.

Všechna rozšíření ukazují základní informace, jako je počet rozšířených profilů, náhled generované entity rozšíření a počet rozšířených profilů v průběhu času. Pokud je k dispozici možnost **Počet zákazníků obohacených o pole**, můžete procházet k podrobnostem pokrytí každého rozšířeného pole.

:::image type="content" source="media/enrichments-results.png" alt-text="Stránka s výsledky rozšíření.":::

Některá rozšíření také zobrazují informace specifické pro typ rozšíření. Další informace naleznete v dokumentaci k příslušnému rozšíření.


[!INCLUDE [footer-include](includes/footer-banner.md)]
