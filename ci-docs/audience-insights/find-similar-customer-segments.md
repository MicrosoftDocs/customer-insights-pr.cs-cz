---
title: Vyhledání podobných zákazníků pomocí AI
description: Najděte podobné segmenty zákazníků pomocí uměl= inteligence.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7c447609bd54de0780dd14aae9f05c7c24b8cce5
ms.sourcegitcommit: fb9f118b4e16b5aabb3e503463efca21718f5d72
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/12/2021
ms.locfileid: "7799674"
---
# <a name="similar-customers-preview"></a>Podobní zákazníci (náhled)

Tato funkce vám umožní najít podobné zákazníky ve vaší zákaznické základně pomocí umělé inteligence. Abyste mohli tuto funkci používat, musíte mít vytvořen alespoň jeden segment. Rozšíření kritérií existujícího segmentu pomůže najít zákazníky podobné tomuto segmentu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Najděte podobné zákazníky* používá automatizované prostředky k vyhodnocování údajů a vytváření předpovědí na základě těchto údajů, a proto má schopnost být použita jako metoda profilování, protože tento pojem je definován obecným nařízením o ochraně údajů („GDPR“). Použití této funkce zákazníkem ke zpracování dat může podléhat GDPR nebo jiným zákonům nebo předpisům. Zodpovídáte za to, že použití Dynamics 365 Customer Insights, včetně predikcí, je v souladu se všemi příslušnými zákony a předpisy, včetně zákonů týkajících se soukromí, osobních údajů, biometrických údajů, ochrany údajů a důvěrnosti komunikace.

## <a name="finding-similar-customers"></a>Najít podobné zákazníky

1. V přehledech cílové skupiny přejděte na **Segmenty** a vyberte segment, na kterém chcete založit svůj nový segment. To je váš *zdrojový segment*.

1. Na panelu akcí vyberte **Najděte podobné zákazníky**.

1. Zkontrolujte navrhované jméno nového segmentu a v případě potřeby jej změňte.

1. Zkontrolujte pole, která definují váš nový segment. Tato pole definují základ, na kterém se systém pokusí najít podobné zákazníky ve vašem zdrojovém segmentu. Systém ve výchozím nastavení vybere doporučená pole.
  Pole, která mohou výrazně snížit výkon modelu, jsou automaticky vyloučena:
  
   - Pole s následujícími typy dat: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Pole s mohutností (počet prvků v poli) menší než 2 nebo více než 30

1. Zvolte, zda chcete zahrnout **Všichni zákazníci** nebo pouze zákazníci v **Specifickém existujícím segmentu** ve vašem novém segmentu.

1. Vyloučte zákazníky ve svém zdrojovém segmentu výběrem zaškrtávacího políčka **Vyloučit všechny ve zdrojovém segmentu**.

1. Ve výchozím nastavení systém navrhuje zahrnout do výstupu pouze 20% z velikosti cílové skupiny. Upravte tuto mezní hodnotu podle potřeby. Zvýšení mezní hodnoty sníží přesnost.

1. Vyberte **Spustit** ve spodní části stránky a spusťte úlohu binární klasifikace (metoda strojového učení), která analyzuje datový soubor.

## <a name="view-the-similar-segment"></a>Zobrazit podobný segment

Po zpracování podobného segmentu najdete nový segment uvedený v seznamu na stránce **Segmenty**.

> [!div class="mx-imgBorder"]
> ![Podobný segment zákazníků.](media/expanded-segment.png "Podobný segment zákazníků")

Vyberte **Pohled** na panelu akcí a otevřete detail segmentu. Toto zobrazení obsahuje informace o distribuci výsledků napříč [skórem podobnosti](#about-similarity-scores). Hodnoty skóre podobnosti najdete také v **Náhledu členů segmentu**.

## <a name="use-the-output-of-a-similar-segment"></a>Použijte výstup podobného segmentu

Můžete [pracovat s výstupem podobného segmentu](segments.md) stejně jako u jiných segmentů. Například exportujte segment nebo vytvořte měřítko.

## <a name="refresh-and-edit-a-similar-segment"></a>Aktualizujte a upravte podobný segment

Chcete-li obnovit podobný segment, vyberte jej na stránce **Segmenty** a vyberte **Obnovit** na panelu akcí.

Úpravy podobného segmentu znovu zpracují vaše data. Dříve vytvořený segment se aktualizuje aktualizovanými daty.    
Chcete-li upravit podobný segment, vyberte jej na stránce **Segmenty** a vyberte **Upravit** na panelu akcí. Použijte své změny a vyberte **Spustit** pro zahájení zpracování.

## <a name="delete-a-similar-segment"></a>Odstranit podobný segment

Vyberte segment an stránce **Segmenty** a vyberte **Odstranit** na panelu akcí. Pak podvrďte odstranění.

## <a name="about-similarity-scores"></a>O skóre podobnosti

Model strojového učení binární klasifikace přiřazuje skóre zákazníkům v podobném segmentu. Skóre je založeno na podobnosti se zákazníky ve zdrojovém segmentu.

- Skóre podobnosti pod 0,55 jsou zákazníci klasifikovaní systémem jako *ne podobní* zákazníkům ve zdrojovém segmentu
- Skóre podobnosti mezi 0,55 - 0,7 se klasifikuje jako *trochu podobné*
- Skóre podobnosti mezi 0,7 - 0,85 se klasifikuje jako *podobné*
- Skóre podobnosti mezi 0,85 - 1 jsou zákazníci klasifikovaní jako *velmi podobní*

Zákazníci s skóre podobnosti pod 0,4 nejsou do výstupu modelu zahrnuti. Systém je nepovažuje za dostatečně podobné zdrojovému segmentu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]