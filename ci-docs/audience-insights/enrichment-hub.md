---
title: Rozšíření sjednocených profilů zákazníka
description: Využijte možnosti rozšíření svých zákaznických dat.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305240"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Rozšíření profilů zákazníků (náhled)

K rozšíření svých zákaznických dat použijte data ze zdrojů, jako je Microsoft a další partneři.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohacení":::

V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**, kde můžete pracovat s možnostmi rozšíření.  

K vytváření nebo úpravě rozšíření musíte mít oprávnění přispěvatele nebo správce. Další informace naleznete v části [Oprávnění](permissions.md).

Na kartě **Zjistit** najdete následující rozšíření:

- [Značky](enrichment-microsoft.md) poskytované společností Microsoft
- [Zájmy](enrichment-microsoft.md) poskytované společností Microsoft
- [Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované společností Microsoft
- [Údaje o společnosti](enrichment-leadspace.md) poskytované společností Leadspace
- [Demografické údaje](enrichment-experian.md) poskytované společností Experian
- [Údaje o poloze](enrichment-here.md) poskytované společností HERE Technologies
- [Vlastní data](enrichment-SFTP-custom-import.md) prostřednictvím vlastního importu protokolu (SFTP)

Na kartě **Moje rozšíření** se můžete podívat na rozšíření, která jste nakonfigurovali, a upravit jejich vlastnosti.

## <a name="manage-existing-enrichments"></a>Správa existujících rozšíření

Jděte na kartu **Moje obohacení**, kde zobrazíte všechna nakonfigurovaná obohacení. Každé rozšíření je uvedeno jako jeden jako řádek, který obsahuje další informace o rozšíření.

Výběrem rozšíření zobrazíte dostupné možnosti. Můžete také vybrat tři tečky (...) na položce seznamu a zobrazit možnosti.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti správy rozšíření v seznamu rozšíření":::

- Možností **Zobrazit** zobrazíte podrobnosti o rozšíření s počtem rozšířených profilů zákazníků.
- Možností **Upravit** upravíte konfiguraci rozšíření.
- **Spustit** rozšíření k aktualizaci profilů zákazníků o nejnovější data.
- Možností **Deaktivovat** zastavíte automatické aktualizace rozšíření při každé plánované aktualizaci. Data z poslední úspěšné aktualizace budou nadále k dispozici. Možností **Aktivovat** restartujete automatické aktualizace rozšíření s každou plánovanou aktualizací.
- **Odstranění** rozšíření.

Výběrem ze seznamu můžete spustit nebo deaktivovat více rozšíření najednou. Možnosti zobrazení a úpravy nejsou k dispozici jako hromadná akce a fungují vždy jen pro jedno rozšíření.

## <a name="enrichments-and-connections"></a>Rozšíření a propojení 

Rozšíření třetích stran se konfigurují pomocí [připojení](connections.md), které správce nastaví pomocí pověření a poskytne souhlas s datovými přenosy. propojení mohou správci a přispěvatelé použít ke konfiguraci rozšíření.  

## <a name="multiple-enrichments-of-the-same-type"></a>Více rozšíření stejného typu

Entita, kterou chcete rozšířit, je zadána během konfigurace rozšíření, což vám umožní rozšířit pouze podmnožinu vašich profilů. Například obohaťte data pouze pro konkrétní segment. Můžete nakonfigurovat několik rozšíření stejného typu a znovu použít stejné propojení . Některá rozšíření budou mít rozšíření počtu obohacení stejného typu, které lze vytvořit. Limity a současné použití lze zobrazit na stránce **Rozšíření**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
