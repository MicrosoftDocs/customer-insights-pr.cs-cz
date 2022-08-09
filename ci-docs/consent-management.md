---
title: Použití souhlasu zákazníka
description: Dodržujte předvolby souhlasu vašich zákazníků v Customer Insights importem údajů o souhlasu.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188039"
---
# <a name="use-customer-consent"></a>Použití souhlasu zákazníka

Předpisy o ochraně dat a soukromí poskytují jednotlivcům právo řídit, jak organizace používá jejich osobní údaje. Příkladem takových nařízení je obecné nařízení o ochraně osobních údajů v Evropské unii nebo kalifornský zákon o ochraně soukromí spotřebitelů ve Spojených státech. Tyto předpisy umožňují lidem odmítnout shromažďování, zpracovávání nebo sdílení jejich osobních údajů s třetími stranami.  

Zákazníci se mohou rozhodnout svůj souhlas pro konkrétní formy kontaktu odvolat nebo odmítnout. Mohou také požádat, abyste je odhlásili ze shromažďování, ukládání, používání nebo prodeje jejich osobních údajů. Je důležité, aby vaše organizace respektovala souhlas všech zákazníků a preference ochrany soukromí.  

Dynamics 365 Customer Insights vám pomůže splnit požadavky vašich zákazníků importem a uložením jejich preferencí v rámci sjednocených zákaznických profilů.

Pokud jsou údaje o souhlasu uloženy odděleně od vašich zákaznických profilů, [přidejte údaje o svém souhlasu jako nový zdroj dat](#import-and-unify-consent-data). Zdroj dat, který obsahuje údaje o souhlasu, je přidán do procesu sjednocení údajů. Úspěšné sjednocení údajů o souhlasu a zákaznických profilů pak vede k jednotným zákaznickým profilům, které obsahují informace o souhlasu. U zákaznických profilů, které již obsahují informace o souhlasu, přejděte přímo do oddílu [použití údajů o souhlasu](#use-consent-data) sekce.

## <a name="prerequisites"></a>Předpoklady

Aby bylo možné sjednotit údaje o souhlasu s profily ostatních zákazníků, musí být ve vašich zdrojových datech k dispozici následující informace:

- Alternativní klíč k mapování informací o souhlasu na uživatelské profily v Customer Insights. Například telefonní číslo nebo e-mailová adresa.
- Hodnota souhlasu k určení stavu souhlasu zákazníka.

Zvažte přidání následujících *volitelných* informací:

- Primární klíč pro aktualizaci stavu souhlasu, pokud zákazník požaduje změnu.
- Typ souhlasu, pokud existuje více než jeden způsob zpracování informací o zákaznících.
- Datum udělení souhlasu nebo jakýkoli jiný typ údajů relevantních pro vaše scénáře souhlasu.

Příklad tabulky jednoduché databáze souhlasů s více možnostmi souhlasu:

|ID souhlasu (primární klíč)   |Email (alternativní klíč)  |Možnost souhlasu  |Hodnota souhlasu  |
|---------|---------|---------|---------|
|0    |  holly@contoso.com       |  Bulletin       |  False       |
|2    |  holly@contoso.com       |  Aktualizace produktu       |  True       |
|3    |  frank@contoso.com       |  Bulletin       | True        |
|4    |  frank@contoso.com       |  Aktualizace produktu       |  False       |

## <a name="import-and-unify-consent-data"></a>Import a sjednocení údajů o souhlasu

Údaje o souhlasu importujete stejným způsobem, jakým zpracováváte jiné zdroje dat do Customer Insights. Další informace o podporovaných zdrojích dat a způsobu jejich importu naleznete v části [Přehled zdrojů dat](data-sources.md).

Další informace o sjednocení zdrojů dat naleznete v části [Přehled sjednocení dat](data-unification.md).

## <a name="use-consent-data"></a>Použití dat souhlasu

Jakmile budou údaje o vašem souhlasu součástí vašich sjednocených zákaznických profilů, můžete je použít v Customer Insights. Vytvořte například segment s pravidlem, které zajistí, že budete respektovat preference ochrany soukromí a dat vašich zákazníků. Pravidla podporující předvolby souhlasu se používají k vyloučení uživatelů ze segmentu na základě atributů profilu. Přidejte pravidlo do segmentu, který vylučuje profily zákazníků, kteří neposkytli souhlas s kontaktováním.

S odkazem na ukázkovou tabulku výše by segment mohl obsahovat toto pravidlo: `Consent option=Newsletter & Consent value=True`. Výsledkem této konfigurace je segment, který respektuje předvolby kontaktu pro zasílání zpravodaje.

Další informace o stavebních segmentech viz [Vytvoření segmentů](segment-builder.md).

Jakmile je segment vytvořen, můžete použít některou z mnoha [možností exportu](export-destinations.md) k použití segmentu v jiných aplikacích.

## <a name="ensure-updated-consent-status"></a>Zajistěte aktualizovaný stav souhlasu

Je důležité udržovat stav souhlasu pro vaše zákazníky aktuální. Plánovaná aktualizace v Customer Insights vždy importuje nejnovější stav vašich zdrojů dat. Tyto informace jsou následně zpracovávány prostřednictvím sjednocení dat a výsledkem jsou aktualizované profily zákazníků. Tyto aktualizované profily se pak používají k aktualizaci segmentů, aby bylo zajištěno, že budete pracovat s nejaktuálnějšími informacemi.

Jinými slovy, ujistěte se, že zdrojová data, která se importují do Customer Insights, mají vždy nejnovější informace.

Více informací viz [Ruční obnovení segmentů](segments.md#refresh-segments) nebo [konfigurace plánované aktualizace](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]
