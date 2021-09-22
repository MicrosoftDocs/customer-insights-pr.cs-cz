---
title: Přidání kódu do webu
description: Jak přidat fragment kódu k zachycení událostí na vašem webu.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035086"
---
# <a name="install-the-code-snippet-on-a-website"></a>Instalace fragmentu kódu na webu

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento článek popisuje, jak správce nainstaluje kód fragment na web. Události ve svém pracovním prostoru začnete zobrazovat krátce po přidání skriptu na svůj web. Další informace viz [Správa pracovních prostorů a prostředí](manage-environments-workspaces.md). Informace o zachycení událostí v mobilních aplikacích najdete v části [Přehled zdrojů pro vývojáře](developer-resources.md).


### <a name="prerequisites"></a>Požadavky

* K uložení dat musíte mít oprávnění správce pro pracovní prostor.
* Aby bylo možné odesílat údaje o činnosti, musí být váš web nebo projekt hostován online. Data odeslaná z místního souboru nebudou serverem přijata.


## <a name="add-code-to-your-website"></a>Přidání kódu do webu
1.  Přejděte na **Správce** > **Pracovní prostor** a poté vyberte **Instalační příručka**.
1. Vyberte **Zkopírovat kód** ke zkopírování kódu fragment. Ve výchozím nastavení je klíč příjmu pro váš pracovní prostor vložen do fragmentu kódu.
:::image type="content" source="media/copy-code.png" alt-text="Screenshot stránky s fragmentem kódu.":::
3. Přidejte zkopírovaný fragment kódu na svůj web poblíž <head> tagu a před jakýmkoli jiným skriptem nebo tagy CSS.
4.  Publikujte svůj aktualizovaný web a počkejte několik minut, než zachytíte příchozí webový provoz.
5.  Chcete-li zobrazit svá data, vyberte svůj pracovní prostor z přepínače pracovního prostoru v navigačním podokně. Poté vyberte jeden z přehledů v části **Zjistit**.

## <a name="configuration-options"></a>Možnosti konfigurace

Ve fragmentu kódu můžete změnit následující možnosti konfigurace:

- **ingestionKey**: Klíč příjmu používaný k odesílání událostí do vašeho pracovního prostoru. Klíč pro příjem můžete změnit tak, aby se události odesílaly do jiného pracovního prostoru. Klíč pro příjem je jedinečný pro každý pracovní prostor. 
- **autoCapture**: Určuje, zda jsou zachycena zobrazení stránek a interakce s webem. Má dvě možnosti:
    - **view** : Nastaven na *true* k zachycení zobrazení stránky. Zobrazení stránek jsou zachycena jako [události](glossary.md#event) *Zobrazit*, typu [základní událost](glossary.md#base-event).
    - **click** : Nastaveno na *true* k zachycení interakcí návštěvníků na webu. Interakce jsou zachyceny jako [události](glossary.md#event) *Akce*, typu [základní událost](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
