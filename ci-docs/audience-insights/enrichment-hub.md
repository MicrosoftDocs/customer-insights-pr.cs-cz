---
title: Rozšíření sjednocených profilů zákazníka
description: Využijte možnosti rozšíření svých zákaznických dat.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667086"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Rozšíření profilů zákazníků (náhled)

K rozšíření svých zákaznických dat použijte data ze zdrojů, jako je Microsoft a další partneři.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohacení":::

V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**, kde můžete pracovat s možnostmi rozšíření.    
K vytváření nebo úpravě rozšíření musíte mít oprávnění přispěvatele nebo správce. Další informace naleznete v části [Oprávnění](permissions.md).

Na kartě **Zjistit** najdete následující rozšíření:

- [Značky](enrichment-microsoft-graph.md) poskytované produktem Microsoft Graph
- [Zájmy](enrichment-microsoft-graph.md) poskytované produktem Microsoft Graph
- [Údaje o společnosti](enrichment-leadspace.md) poskytované společností Leadspace
- [Demografická data](enrichment-experian.md) poskytované společností Experian
- [Údaje o poloze](enrichment-here.md) poskytované společností HERE Technologies
- [Vlastní data](enrichment-SFTP-custom-import.md) prostřednictvím vlastního importu protokolu (SFTP)

Na kartě **Moje rozšíření** se můžete podívat na rozšíření, která jste nakonfigurovali, a upravit jejich vlastnosti.

## <a name="manage-existing-enrichments"></a>Správa existujících rozšíření

Přejděte do oblasti **Moje rozšíření**, kde se nacházejí všechna konfigurovaná rozšíření. Každé rozšíření je uvedeno jako jeden jako řádek, který obsahuje další informace o rozšíření.

Výběrem rozšíření zobrazíte dostupné možnosti. Alternativně můžete vybrat tři tečky (...) u položky seznamu a zobrazit možnosti.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti správy rozšíření v seznamu rozšíření":::

- Možností **Zobrazit** zobrazíte podrobnosti o rozšíření s počtem rozšířených profilů zákazníků.
- Možností **Upravit** upravíte konfiguraci rozšíření.
- **Spustit** rozšíření k aktualizaci profilů zákazníků o nejnovější data.
- Možností **Deaktivovat** zastavíte automatické aktualizace rozšíření při každé plánované aktualizaci. Data z poslední úspěšné aktualizace budou nadále k dispozici. Možností **Aktivovat** restartujete automatické aktualizace rozšíření s každou plánovanou aktualizací.
- **Odstranění** rozšíření.

Výběrem ze seznamu můžete spustit nebo deaktivovat více rozšíření najednou. Možnosti zobrazení a úpravy nejsou k dispozici jako hromadná akce a fungují vždy jen pro jedno rozšíření.
