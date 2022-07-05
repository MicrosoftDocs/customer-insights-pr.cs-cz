---
title: Přehled predikcí
description: Scénáře a možnosti predikcí, se kterými se setkáte v aplikaci Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: a87af80fa713a1ac70493345c0c920e416692b0f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081198"
---
# <a name="predictions-overview"></a>Přehled predikcí

Dynamics 365 Customer Insights je vybavena řadou možností, které využívají AI a strojové učení k předpovídání dat. 

## <a name="out-of-box-models"></a>Předem připravené modely

Nejjednodušší způsob, jak začít s předpovídáním dat, jsou předem definované modely, často označované jako vestavěné modely. K rychlému generování přehledů vyžadují pouze určitá data a strukturu. Aktuálně jsou k dispozici následující modely: 

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

- [Celoživotní hodnota zákazníka](predict-customer-lifetime-value.md): Předpovídá potenciální výnos ze zákazníka během jeho celé interakce s firmou.
- [Doporučení produktu](predict-product-recommendation.md): Navrhuje sady prediktivních doporučení produktů na základě nákupního chování a zákazníků s podobnými nákupními vzory.
- [Úbytek předplatitelů](predict-subscription-churn.md): Předpovídá, zda hrozí ztráta zákazníka, pokud přestane používat produkty nebo služby v rámci předplatného vaší společnosti.
- [Úbytek transakcí](predict-transactional-churn.md): Předpovídá, zda si zákazník v určitém časovém rámci již nebude kupovat vaše produkty nebo služby.
- [Analýza postoje](sentiment-analysis.md): Analyzujte postoje zákazníků z jejich názorů a identifikujte obchodní aspekty, které jsou často zmiňovány.

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

- [Úbytek transakcí](predict-transactional-churn.md): Předpovídá, zda si zákazník v určitém časovém rámci již nebude kupovat vaše produkty nebo služby.

---

> [!TIP]
> Doporučujeme, abyste předpřipravené modely pravidelně aktualizovali o aktualizovaná data, abyste zajistili, že budou přesně informovat o vašem případu obchodního použití. Data se aktualizují ad-hoc, když systém ingestuje nové nebo aktualizované zdroje dat. Modely však v tomto případě pouze přehodnotí skóre a nadále budou používat stávající trénovací data.
> 
> V prostředí konfigurace můžete nakonfigurovat **Plán aktualizací** nastavením plánu přeškolení modelu. Model se podle tohoto plánu přeškolí a přehodnotí skóre. Tento plán můžete kdykoli změnit.


## <a name="azure-machine-learning-integration"></a>Integrace Azure Machine Learning

Pokud organizace již používá scénáře strojového učení založené na experimentech Azure Machine Learning, funkce vlastních modelů v Customer Insights pomáhá propojit jednotlivé tečky. Vytvořte pracovní postupy, které vám pomohou vybrat data, ze kterých chcete generovat přehledy, a namapovat výsledky na vaše sjednocené profily zákazníků. Další informace viz [Vlastní modely strojového učení](custom-models.md).

## <a name="ai-builder-prediction"></a>Predikce AI Builderu

Někdy jsou datové sady neúplné a některé hodnoty chybí. Customer Insights může pomoci předpovědět chybějící hodnoty pro entitu a segmenty zákazníka. Další informace najdete v článku [Doplnění dílčích data pomocí predikcí](predictions.md).
