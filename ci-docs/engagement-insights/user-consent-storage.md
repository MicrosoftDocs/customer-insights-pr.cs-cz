---
title: Správa souborů cookie a souhlasu uživatele s ukládáním uživatelských dat
description: Pochopte, jak se cookies a souhlas uživatelů používají k identifikaci návštěvníků webových stránek.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036730"
---
# <a name="manage-cookies-and-user-consent"></a>Správa souborů cookie a souhlasu uživatele

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkce přehledu zapojení Dynamics 365 Customer Insights využívá soubory cookie a místní úložiště (`localStorage`) k identifikaci návštěvníků webových stránek.

Cookies jsou malé soubory, které ukládají informace o interakcích uživatele s webem. Jsou uloženy ve webových prohlížečích. Když uživatelé navštíví web, pro který vaši uživatelé uložili soubory cookie, prohlížeč odešle tyto informace na server, který vrátí informace, které jsou pro uživatele jedinečné. Jedná se o technologii, která umožňuje například online nákupnímu košíku uchovat v něm vybrané položky, i když uživatel opustí web.

## <a name="user-consent"></a>Souhlas uživatele

[Obecné nařízení o ochraně osobních údajů (GDPR)](/dynamics365/get-started/gdpr/) je nařízení Evropské unie (EU), které stanoví, jak by organizace měly zacházet s osobními údaji a zabezpečením svých uživatelů. Soubory cookie často ukládají nebo shromažďují „osobní údaje“, například online identifikátor, na který se vztahuje nařízení GDPR. Pokud vaše firma zaměstnává nebo prodává subjektům údajů v EU, GDPR se vás týká. [Přečtěte si další informace o tom, jak vám Microsoft může pomoci dodržovat GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Chcete-li povolit sadě SDK pro interakci s ukládáním souborů cookie nebo jiných citlivých údajů, musíte určit, zda k tomu uživatelé souhlasili. K tomu dochází při inicializaci SDK.

Pokud uvedete, že neexistuje žádný souhlas uživatele, SDK nebude ukládat žádná data a nebude odesílat události, které lze použít ke sledování chování uživatelů. Všechna dříve uložená data budou z prohlížeče odstraněna.

Pokud není zadána žádná hodnota souhlasu uživatele, SDK bude předpokládat, že uživatel souhlasil. To znamená, že pokud (jako náš zákazník) nezadáte hodnotu pro souhlas uživatele v SDK, budou shromážděny údaje. Pokud však určíte, že hodnota souhlasu uživatele musí být „true“, data nebudou shromažďována, pokud uživatel odmítne nebo neposkytne výslovný souhlas.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Ukládání údajů o návštěvnících s funkcí přehledů zapojení

### <a name="cookies"></a>Soubory cookies

- _msei
    - Ukládá anonymní ID uživatele. Tento soubor cookie je nastaven v doméně zákazníka a jeho platnost vyprší za 365 dní.

### <a name="local-storage"></a>Místní úložiště

Funkce přehledů zapojení také využívá místní úložiště (`localStorage`) ke sledování necitlivých údajů. Tato data jsou plně uložena v samotném prohlížeči, aniž by byl na vaše servery odesílán jakýkoli přenos.

- *EISession.Id* 
    - Ukládá informace o probíhající relaci uživatele, například ID relace, kdy byla spuštěna a kdy vyprší.
- *EISession.Previous*
    - Uloží adresu URL dříve navštívené stránky v aktuální relaci.
    
Platnost klíčů v místním úložišti nevyprší automaticky. Během příští relace je resetuje SDK.

## <a name="deleting-cookies"></a>Mazání souborů cookies

Vaši zákazníci mohou kdykoli ručně smazat soubory cookie a klíče místního úložiště prostřednictvím nastavení svých prohlížečů.


[!INCLUDE[footer-include](../includes/footer-banner.md)]