---
title: Přizpůsobte svá prostředí na základě dat o známých i neznámých uživatelích
description: Zahrňte informace o dříve neznámých uživatelích, když znáte jejich identitu.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: ff99721bef0004bc8cae1ec14ff9df16cbb0682e
ms.sourcegitcommit: ece8ff732490ecd3b3421ab273f331e6fd46a7f7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/19/2022
ms.locfileid: "9173788"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Přizpůsobte svá prostředí na základě dat o známých i neznámých uživatelích

Správa zákaznických dat není novou výzvou, ale s tím, jak uživatelé procházejí různými digitálními kanály různých značek, je stále obtížnější. Uživatel, který je známý (ověřený) v jednom kanálu, se stává neznámým (neověřeným) v jiném, pokud není přihlášen. Problém je často v tom, že neověření (neznámí) uživatelé nemají stejné ID. To by se dalo použít pro přidružení důležitých atributů profilů a generování sjednocených profilů zákazníků. Customer Insights pomáhá tento problém řešit ingestováním dat z metod sledování ve zdrojových systémech. Konsolidované neznámé a známé profily poskytují organizacím kompletní přehled o aktuálních profilech a jejich historických transakcích, chování a demografických údajích. Naše řešení jde ještě o krok dále, protože poskytuje rozpoznání identity, které vám umožní sjednotit aktivitu zákazníků napříč více kanály, včetně vašeho webu, nákupu v obchodě, věrnostních programů a tak dále.

## <a name="sample-scenario"></a>Ukázkový scénář

Představme si řetězec kaváren, který má širokou zákaznickou základnu, která nakupuje kávu a jídlo v obchodech a objednává produkty online. Online návštěvníci často nejsou při procházení produktů ověřeni, což z nich dělá „neznámé uživatele“. Pro řetězec kaváren je obtížné poskytovat přizpůsobené nabídky a prostředí, pokud jsou uživatelé neznámí. Na druhou stranu se zákazníci mohou přihlásit ke svému účtu a stát se „známými uživateli“ společnosti tím, že se připojí k věrnostnímu systému, který naopak umožňuje přizpůsobit jejich prostředí. Customer Insights může řetězci kaváren pomoci získat přehledy o známých i dříve neznámých uživatelích.

S řešením Customer Insights může společnost kombinovat zákaznické profily s daty aktivit z neověřených (neznámých) relací poté, co se uživatel přihlásí a stane se známým. Kavárenský řetězec může přenášet data z jiných zdrojů dat pomocí vestavěných konektorů do Customer Insights a slučovat identity zákazníků z různých kanálů.

## <a name="prerequisites"></a>Předpoklady

- Jsou shromažďována webová data, která obsahují ID všech návštěvníků.
- Webová data obsahují ověřená ID uživatelů přihlášených návštěvníků. Tato ID jsou propojena s věrnostním systémem.
- Data událostí s vysokou důležitostí, jako je „Zobrazení produktu“ a „Pokladna“, jsou definována a zahrnuta ve zdrojových datech spolu s časovým razítkem a ID události.

Následující tabulka ukazuje zjednodušený příklad toho, jak lze zachytit webové události s vysokou důležitostí.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|0|07-23-2022 10:00:00|abc123|--|Zobrazení produktů|
|2|07-23-2022 10:05:00|abc123|707|Věrnostní přihlášení|
|3|07-23-2022 10:10:00|abc123|707|Pokladna|
|4|07-23-2022 10:20:00|xyz789|--|Zobrazení produktů|

## <a name="data-ingestion"></a>Příjem dat

Data o zákaznících mohou pocházet z vašeho webu jako data událostí a mohou být uchována ve vašich vlastních interních službách nebo službách analýzy dat třetích stran. Webová data obsahují známé a neznámé uživatele, pokud má web ověřovací tok, který se integruje s ověřovací službou. Například systém elektronického obchodu, který vyžaduje, aby uživatelé poskytli své úplné údaje k dokončení nákupní transakce. Nebo věrnostní systém, který vyžaduje ověření k potvrzení platného příjemce slev z odměn.

Data událostí v našem příkladu výše obsahují odlišná ID profilů známých a neznámých uživatelů. V události 1 a 4 jsou uživatelé neznámí, zatímco v události 2 a 3 se uživatel s ID abc123 zaregistruje do věrnostního programu.

:::image type="content" source="media/website-data-source.png" alt-text="Zdroje dat včetně webu Contoso.":::

Další informace o dostupných možnostech ingestace dat naleznete v části [Připojení zdrojů dat](data-sources.md).

## <a name="data-unification"></a>Sjednocení dat

Sloučení neznámých identit se známými identitami pomáhá provést přizpůsobení na základě chování uživatelů bez ohledu na stav jejich profilu (známý nebo neznámý). Přizpůsobený obsah pro všechny uživatele pomáhá zákazníkům rychle se dostat k nejrelevantnějším produktům nebo službám, o které mají v danou chvíli zájem.

Protože někteří uživatelé v našich datech jsou známí, můžeme použít Customer Insights ke sloučení těchto dat s profilem uživatele. Další informace o sjednocení profilů zákazníků naleznete v části [Přehled sjednocení dat](data-unification.md).

1. Z entity webových dat vyberte zdrojová pole. Použijte data profilu, která jsou uložena ve vašich webových datech, a vyberte pole, která představují ID s demografickými údaji.

   :::image type="content" source="media/website-source-fields.png" alt-text="Zdrojová pole pro zdroj webových dat.":::

1. Přidejte pravidla pro sloučení duplicitních záznamů. Pro webová data zvolte nejvíce vyplněná data.

1. Nakonfigurujte pravidla a podmínky shody. Data událostí webových profilů v tomto příkladu budou na ID porovnána s profily z jiných zdrojů dat, které obsahují informace o zákaznících. U jednotlivých ID nastavte pravidla přesné shody jako samostatná pravidla pro každou z dalších entit profilu, které mají odpovídající primární klíč nebo shodu ID. V našem příkladu jsou data profilu webové události použita jako poslední odpovídající entita, takže ostatní data profilu jsou sloučena jako první.
   1. Ponechání políčka **Zahrnout všechny záznamy** jako prázdného vytvoří sjednocené profily známých uživatelů a zahrne jejich odpovídající ID neznámých uživatelů. Je to užitečné v situacích, kdy máte zájem o zobrazení minulých behaviorálních aktivit známých uživatelů, když byli ještě neznámí.
   1. Zaškrtnutí políčka **Zahrnout všechny záznamy** vytvoří samostatné záznamy profilů pro neznámé uživatele. Neznámí uživatelé získají jedinečné ID zákazníka. V budoucnu, když je známý profil přidružen k datům profilu webových událostí, lze zobrazit cestu nově známého uživatele a použít ji pro přizpůsobení také na základě minulých neznámých údajů o chování.

:::image type="content" source="media/website-match-rule.png" alt-text="Pravidlo shody pro entitu webového zdroje dat.":::

## <a name="get-insights"></a>Získat přehledy

Jsou-li profily zákazníků vytvořeny pro neznámé a známé uživatele, lze použít vysoce důležitá data webových událostí, například [aktivity](activities.md). Tyto aktivity lze použít k vytvoření dalších přehledů. Například zákazníci, kteří navštívili web před šesti měsíci (kdy byli ještě neznámí), nebo zákazníci, kteří nemají věrnostní ID, nikdy nedokončili platbu.

:::image type="content" source="media/website-known-unknown.png" alt-text="Screenshot zákaznické stránky se známými a neznámými zákazníky.":::

[Rozšiřte](enrichment-hub.md) svá data, sestavte [míry](measures.md) a vytvořte [segmenty](segments.md) pro další aktivaci.

Můžete například vytvořit segmenty známých uživatelů, kteří si prohlíželi některé produkty, ale nikdy nedokončili platbu.

Další informace najdete v části [Přehled segmentů](segments.md).

## <a name="activate-insights"></a>Aktivace přehledů

Existuje několik způsobů, jak exportovat data a podniknout kroky na základě podkladových přehledů.

Další informace naleznete v tématu [Přehled exportů](export-destinations.md).
