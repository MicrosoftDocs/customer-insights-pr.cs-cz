---
title: Přidání kódu do webu
description: Jak přidat fragment kódu k zachycení událostí Dynamics 365 Customer Insights na vašem webu.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558785"
---
# <a name="install-the-web-sdk-on-a-website"></a>Nainstalujte si webovou sadu SDK na web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento článek popisuje, jak správce nainstaluje sadu nástrojů pro vývoj webového softwaru (SDK) na web. Události se vám začnou zobrazovat ve vašem pracovním prostoru krátce po vytvoření nástroje na vašem webu. Další informace viz [Správa pracovních prostorů a prostředí](manage-environments-workspaces.md). Informace o zachycení událostí v mobilních aplikacích najdete v části [Přehled zdrojů pro vývojáře](developer-resources.md).


### <a name="prerequisites"></a>Požadavky

* K uložení dat musíte mít oprávnění správce pro pracovní prostor.
* Aby bylo možné odesílat údaje o činnosti, musí být váš web nebo projekt hostován online. Data odeslaná z místního souboru nebudou serverem přijata.


## <a name="add-web-sdk-to-your-website"></a>Přidejte SDK na svůj web

Přejděte na **Správce** > **Pracovní prostor** a poté vyberte **Instalační příručka**. Existují dvě možnosti instalace webového SDK. První je použití odkazu ke stažení a druhým je instalace balíčku správce balíčků uzlů (NPM).

### <a name="option-1-using-the-download-link"></a>Možnost 1: Použití odkazu ke stažení

1. Vyberte **Zkopírovat kód** ke zkopírování kódu fragment. Ve výchozím nastavení je klíč příjmu pro váš pracovní prostor vložen do fragmentu kódu.
  :::image type="content" source="media/copy-code.png" alt-text="Screenshot stránky s fragmentem kódu.":::

1. Přidejte zkopírovaný kód na svůj web poblíž <head> tagu a před jakýmkoli jiným skriptem nebo tagy CSS.
1. Publikujte svůj aktualizovaný web a počkejte několik minut, než zachytíte příchozí webový provoz.
1. Chcete-li zobrazit svá data, vyberte svůj pracovní prostor z přepínače pracovního prostoru v navigačním podokně. Poté vyberte jeden z přehledů v části **Zjistit**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Možnost 2: Použití balíčku NPM (doporučeno pro webové aplikace založené na JavaScript)

1. Přejděte na náš [web NPM](https://www.npmjs.com/package/engagementinsights-web) a podle pokynů nainstalujte a nastavte balíček web SDK NPM.
1. Publikujte svůj aktualizovaný web a počkejte několik minut, než zachytíte příchozí webový provoz.
1. Chcete-li zobrazit svá data, vyberte svůj pracovní prostor z přepínače pracovního prostoru v navigačním podokně. Poté vyberte jeden z přehledů v části **Zjistit**.

## <a name="configuration-options"></a>Možnosti konfigurace

Ve fragmentu kódu můžete změnit následující možnosti konfigurace:

- **ingestionKey**: Klíč příjmu používaný k odesílání událostí do vašeho pracovního prostoru. Klíč pro příjem můžete změnit tak, aby se události odesílaly do jiného pracovního prostoru. Klíč pro příjem je jedinečný pro každý pracovní prostor.
- **autoCapture**: Určuje, zda jsou zachycena zobrazení stránek a interakce s webem. Má dvě možnosti:
    - **view** : Nastaven na *true* k zachycení zobrazení stránky. Zobrazení stránek jsou zachycena jako [události](glossary.md#event) *Zobrazit*, typu [základní událost](glossary.md#base-event).
    - **click** : Nastaveno na *true* k zachycení interakcí návštěvníků na webu. Interakce jsou zachyceny jako [události](glossary.md#event) *Akce*, typu [základní událost](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
