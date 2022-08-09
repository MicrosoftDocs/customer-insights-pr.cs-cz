---
title: Hledání podobných zákazníků pomocí AI (Preview) (obsahuje video)
description: Najděte podobné segmenty zákazníků pomocí uměl= inteligence.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170719"
---
# <a name="find-similar-customers-with-ai-preview"></a>Hledání podobných zákazníků pomocí AI (Preview)

Najděte podobné zákazníky ve své zákaznické základně pomocí umělé inteligence. Abyste mohli tuto funkci používat, musíte mít vytvořen alespoň jeden segment. Rozšíření kritérií existujícího segmentu pomůže najít zákazníky podobné tomuto segmentu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> Funkce *Najít podobné zákazníky* využívá automatizované prostředky k vyhodnocování dat a vytváření predikcí na základě těchto dat. Proto ji lze použít jako metodu profilování, jak je tento pojem definován obecným nařízením o ochraně osobních údajů („GDPR“). Použití této funkce zákazníkem ke zpracování dat může podléhat GDPR nebo jiným zákonům nebo předpisům. Zodpovídáte za to, že použití Dynamics 365 Customer Insights, včetně predikcí, je v souladu se všemi příslušnými zákony a předpisy, včetně zákonů týkajících se soukromí, osobních údajů, biometrických údajů, ochrany údajů a důvěrnosti komunikace.

## <a name="find-similar-customers"></a>Najít podobné zákazníky

1. Přejděte na **Segmenty** a vyberte segment, na kterém chcete založit nový segment. To je váš *zdrojový segment*.

1. Vyberte **Najít podobné zákazníky**.

1. Zkontrolujte navrhované jméno nového segmentu a v případě potřeby jej změňte.

1. Volitelně přidejte [značky](work-with-tags-columns.md#manage-tags) do nového segmentu.

1. Zkontrolujte pole, která definují váš nový segment. Tato pole definují základ, na kterém se systém pokusí najít podobné zákazníky ve vašem zdrojovém segmentu. Systém ve výchozím nastavení vybere doporučená pole. V případě potřeby přidejte další pole.
  Pole, která mohou výrazně snížit výkon modelu, jsou automaticky vyloučena:
  
   - Pole s následujícími typy dat: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Pole s mohutností (počet prvků v poli) menší než 2 nebo více než 30

1. Zvolte, zda chcete do svého nového segmentu zahrnout **Všechny zákazníky** kromě zdrojového segmentu nebo pouze zákazníky v **jiném segmentu**.

1. Ve výchozím nastavení systém navrhuje zahrnout do výstupu pouze 20% z velikosti cílové skupiny. Upravte tuto mezní hodnotu podle potřeby. Zvýšení mezní hodnoty sníží přesnost.

1. Zaškrtnutím políčka **K zákazníkům s podobnými atributy přidat členy ze zdrojového segmentu** zahrnete zákazníky do zdrojového segmentu.

1. Vyberte **Spustit** ve spodní části stránky a spusťte [úlohu binární klasifikace](#about-similarity-scores) (metoda strojového učení), která analyzuje datový soubor.

## <a name="view-the-similar-segment"></a>Zobrazit podobný segment

Po zpracování podobného segmentu najdete nový segment uvedený v seznamu na stránce **Segmenty** s typem **Rozšíření**.

Vyberte **Zobrazit**, čímž zobrazíte distribuci výsledků napříč [skóre podobnosti](#about-similarity-scores) a hodnotami skóre podobnosti v sekci **Náhled členů segmentu**.

:::image type="content" source="media/expanded-segment.png" alt-text="Podobný segment zákazníků.":::

## <a name="manage-a-similar-segment"></a>Správa podobného segmentu

[Pracujte a spravujte podobný segment](segments.md#manage-existing-segments) jako u jiných segmentů. Například exportujte segment nebo vytvořte měřítko.

Upravte, aktualizujte, přejmenujte, stáhněte a odstraňte podobný segment. Úpravy podobného segmentu znovu zpracují vaše data. Dříve vytvořený segment se aktualizuje aktualizovanými daty.

## <a name="about-similarity-scores"></a>O skóre podobnosti

Model strojového učení binární klasifikace přiřazuje skóre zákazníkům v podobném segmentu. Skóre je založeno na podobnosti se zákazníky ve zdrojovém segmentu.

- Skóre podobnosti pod 0,55 jsou zákazníci klasifikovaní systémem jako *ne podobní* zákazníkům ve zdrojovém segmentu
- Skóre podobnosti mezi 0,55 - 0,7 se klasifikuje jako *trochu podobné*
- Skóre podobnosti mezi 0,7 - 0,85 se klasifikuje jako *podobné*
- Skóre podobnosti mezi 0,85 - 1 jsou zákazníci klasifikovaní jako *velmi podobní*

Zákazníci s skóre podobnosti pod 0,4 nejsou do výstupu modelu zahrnuti. Systém je nepovažuje za dostatečně podobné zdrojovému segmentu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
