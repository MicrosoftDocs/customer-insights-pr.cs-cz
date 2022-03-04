---
title: Správa souborů cookie a souhlasu uživatele s ukládáním uživatelských dat do Dynamics 365 Customer Insights
description: Pochopte, jak se cookies a souhlas uživatelů používají k identifikaci návštěvníků webových stránek.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228977"
---
# <a name="manage-cookies-and-user-consent"></a>Správa souborů cookie a souhlasu uživatele

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkce statistik zapojení Dynamics 365 Customer Insights využívá soubory cookie a klíče (`localStorage`) k identifikaci návštěvníků webů.

Cookies jsou malé soubory, které ukládají informace o interakcích uživatele s webem. Jsou uloženy ve webových prohlížečích. Když uživatelé navštíví web, pro který vaši uživatelé uložili soubory cookie, prohlížeč odešle tyto informace na server, který vrátí informace, které jsou pro uživatele jedinečné. Jedná se o technologii, která umožňuje například online nákupnímu košíku uchovat v něm vybrané položky, i když uživatel opustí web.

## <a name="user-consent"></a>Souhlas uživatele

[Obecné nařízení o ochraně osobních údajů (GDPR)](/dynamics365/get-started/gdpr/) je nařízení Evropské unie (EU), které stanoví, jak by organizace měly zacházet s osobními údaji a zabezpečením svých uživatelů. Soubory cookie často ukládají nebo shromažďují „osobní údaje“, například online identifikátor, na který se vztahuje nařízení GDPR. Pokud vaše firma zaměstnává nebo prodává subjektům údajů v EU, GDPR se vás týká. [Přečtěte si další informace o tom, jak vám Microsoft může pomoci dodržovat GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Chcete-li povolit sadě SDK pro interakci s ukládáním souborů cookie nebo jiných citlivých údajů, musíte určit, zda k tomu uživatelé souhlasili. K tomu dochází při inicializaci sady SDK nastavením pole `userConsent` v konfiguraci.

Pokud uvedete, že neexistuje žádný souhlas uživatele, SDK nebude ukládat žádná data a nebude odesílat události, které lze použít ke sledování chování uživatelů. Všechna dříve uložená data budou z prohlížeče odstraněna.

Pokud není zadána žádná hodnota souhlasu uživatele, SDK bude předpokládat, že uživatel souhlasil. To znamená, že pokud (jako náš zákazník) nezadáte hodnotu pro souhlas uživatele v SDK, budou shromážděny údaje. Pokud však určíte, že hodnota souhlasu uživatele musí být „true“, data nebudou shromažďována, pokud uživatel odmítne nebo neposkytne výslovný souhlas.

Níže je uveden fragment kódu pro inicializaci webové sady SDK se souhlasem uživatele:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Ukládání údajů o návštěvnících s funkcí přehledů zapojení

### <a name="cookies"></a>Soubory cookie

- _msei
    - Ukládá anonymní ID uživatele. Tento soubor cookie je nastaven v doméně zákazníka a jeho platnost vyprší za 365 dní.

### <a name="local-storage"></a>Místní úložiště

Funkce statistik zapojení také využívají klíče (`localStorage`) ke sledování necitlivých dat. Tato data jsou plně uložena v samotném prohlížeči, aniž by byl na vaše servery odesílán jakýkoli přenos.

- *EISession.Id*
    - Ukládá informace o probíhající relaci uživatele, například ID relace, kdy byla spuštěna a kdy vyprší.
- *EISession.Previous*
    - Uloží adresu URL dříve navštívené stránky v aktuální relaci.

Klíčům v místním úložišti nevyprší platnost automaticky a resetují se během příští relace SDK.

## <a name="deleting-cookies"></a>Mazání souborů cookies

Vaši zákazníci mohou kdykoli ručně smazat soubory cookie a klíče místního úložiště prostřednictvím nastavení svých prohlížečů.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
