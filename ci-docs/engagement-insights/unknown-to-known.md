---
title: Rozpoznávání webových událostí od dříve ověřených návštěvníků s neznámými až známými
description: Funkce neznámého ke známému vám umožňuje přidružit události na webu k návštěvníkům, kteří se dříve ověřili.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036775"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Rozpoznávání webových událostí od dříve ověřených návštěvníků

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkce **neznámý až známý** v rámci schopnosti přehledů zapojení umožňuje přidružit události na webu k návštěvníkům, kteří se dříve ověřili. Pokud je tato funkce deaktivována, návštěvníci, kteří se ověřili během dřívější návštěvy a poté odešli, nejsou identifikováni, pokud se při návratu znovu neověřují. 

Někdo například minulý týden navštívil web, přihlásil se ke svému uživatelskému účtu na webu a procházel katalog produktů. Tato osoba se vrátí následující týden, aby si prohlédla více produktů, aniž by se přihlásila ke svému účtu. Vlastník webu by pomocí funkce **neznámý ke známému** věděl, že se stejná osoba vrátila a co na webu udělala. To umožňuje přesnější vykazování a analýzu aktivit na webových stránkách.

## <a name="enable-unknown-to-known"></a>Povolit neznámé ke známým

Abyste tuto funkci mohli povolit, musíte být [správce pracovního prostoru](user-roles.md). 

1. V přehledech zapojení přejděte na **Správce** > **Pracovní prostor**. 
2. Vyberte kartu **Nastavení**.
3. V sekci **Neznámý ke známému** nastavte přepínač na **Povoleno**.

![Povolit neznámé ke známým](media/U2Ktoggle.png "Povolit neznámé ke známým")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Přidání kódu JavaScript do sledovacího fragmentu webu

Web dokáže zachytit **authID uživatele** s následující ukázkou jazyka JavaScript pomocí [webu SDK přehledů zapojení](advanced-SDK-implementation.md). K tomu aby funkce **neznámý ke známému** fungovala, musíte zachytit authId *a* povolit userMapping: True ve fragmentu jazyka JavaScript jako v ukázce níže.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
