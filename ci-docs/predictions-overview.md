---
title: Přehled predikcí
description: Scénáře a možnosti predikcí, se kterými se setkáte v aplikaci Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610182"
---
# <a name="predictions-overview"></a>Přehled predikcí

Dynamics 365 Customer Insights je vybavena řadou možností, které využívají AI a strojové učení k předpovídání dat.

## <a name="out-of-box-models"></a>Předem připravené modely

Nejjednodušší způsob, jak začít s předpovídáním dat, jsou předem definované modely, často označované jako vestavěné modely. K rychlému generování přehledů vyžadují pouze určitá data a strukturu. K dispozici jsou následující modely:

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

- [Celoživotní hodnota zákazníka](predict-customer-lifetime-value.md): Předpovídá potenciální výnos ze zákazníka během jeho celé interakce s firmou.
- [Doporučení produktu](predict-product-recommendation.md): Navrhuje sady prediktivních doporučení produktů na základě nákupního chování a zákazníků s podobnými nákupními vzory.
- [Úbytek předplatitelů](predict-subscription-churn.md): Předpovídá, zda hrozí ztráta zákazníka, pokud přestane používat produkty nebo služby v rámci předplatného vaší společnosti.
- [Úbytek transakcí](predict-transactional-churn.md): Předpovídá, zda si jednotlivý zákazník v určitém časovém rámci již nebude kupovat vaše produkty nebo služby.
- [Analýza postoje](sentiment-analysis.md): Analyzuje postoje zákazníků z jejich názorů a identifikuje obchodní aspekty, které jsou často zmiňovány.

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

- [Úbytek transakcí](predict-transactional-churn.md): Předpovídá, zda si účet zákazníka v určitém časovém rámci již nebude kupovat vaše produkty nebo služby.

---

> [!TIP]
> Doporučujeme, abyste předpřipravené modely pravidelně aktualizovali o aktualizovaná data, abyste zajistili, že budou přesně informovat o vašem případu obchodního použití. Data se aktualizují ad-hoc, když systém ingestuje nové nebo aktualizované zdroje dat. Modely však v tomto případě pouze přehodnotí skóre a nadále budou používat stávající trénovací data.
>
> Nakonfigurujte **Plán aktualizací** nastavením plánu přeškolení modelu během konfigurace. Model se podle tohoto plánu přeškolí a přehodnotí skóre. Tento plán můžete kdykoli změnit.

## <a name="azure-machine-learning-integration"></a>Integrace Azure Machine Learning

Pokud organizace již používá scénáře strojového učení založené na experimentech Azure Machine Learning, funkce vlastních modelů v Customer Insights pomáhá propojit jednotlivé tečky. Vytvořte pracovní postupy, které vám pomohou vybrat data, ze kterých chcete generovat přehledy, a namapovat výsledky na vaše sjednocené profily zákazníků. Další informace viz [Vlastní modely strojového učení](custom-models.md).

## <a name="manage-existing-predictions"></a>Správa existujících predikcí

Přejděte na stránku **Analytické nástroje** > **Predikce**. Na kartě **Moje predikce** zobrazte předpovědi, které jste vytvořili, jejich typ predikce, název výstupní entity, stav, poslední úpravu predikce a poslední aktualizaci dat. Seznam predikcí můžete seřadit podle libovolného sloupce.

Výběrem predikce zobrazíte dostupné akce.

:::image type="content" source="media/predictions.png" alt-text="Stránka Moje predikce.":::

- **Upravte** predikci ke změně jeho vlastnosti.
- [**Obnovte**](#refresh-a-prediction) predikci pro zahrnutí nejnovějších dat.
- **Zobrazte** podrobnosti predikce.
- [**Zpráva o použitelnosti vstupních dat**](#view-the-input-data-usability-report) pro zobrazení chyb, varování a doporučení.
- **Odstraňte** predikci.

### <a name="refresh-a-prediction"></a>Aktualizace předpovědi

Predikce lze aktualizovat podle automatického plánu nebo ručně na vyžádání. Chcete-li ručně obnovit všechny predikce, vyberte **Obnovit vše**. Chcete-li ručně obnovit predikci, vyberte ji a vyberte **Obnovit**. Na záložce [naplánovat automatické obnovení](schedule-refresh.md) jděte na **Správce** > **Systém** > **Plán**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Zobrazení sestavy použitelnosti vstupních dat

Sestava použitelnosti vstupních dat poskytuje konsolidovaný pohled na chyby a varování, které mohou generovat vaše předdefinované predikce. Poskytuje také doporučení, jak zlepšit výkon modelu.

Sestava je k dispozici poté, co model dokončí tréninkový proces. Je vytvořena pro každý model samostatně, bez ohledu na to, zda bylo úspěšně provedeno trénování, nebo ne.

Na kartě **Moje předpovědi** vyberte kartu predikce a vyberte **Zpráva o použitelnosti vstupních dat**. Nebo v predikce zobrazení podrobností vyberte **Zpráva o použitelnosti vstupních dat**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Příklad sestavy použitelnosti vstupních dat zobrazující tabulku s chybami, varováními a doporučeními.":::

Sestava obsahuje:

- **Název:** Popisný název chyby, varování nebo doporučení.
- **Krok:** Fáze, školení nebo skóre modelu, které se informace týká.
- **Stav:** Závažnost informací (chyba, varování, doporučení).
- **Název sloupce:** Sloupec v entitě, který je třeba upravit, aby se zlepšil výkon modelu.
- **Název entity:** Název entity, kterou je třeba upravit, aby se zlepšil výkon modelu.
- **Podrobnosti:** Podrobnosti o chybě, varování nebo doporučení.

[!INCLUDE [footer-include](includes/footer-banner.md)]
