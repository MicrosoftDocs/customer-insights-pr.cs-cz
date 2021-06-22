---
title: Přehled podporovaných scénářů predikcí
description: Scénáře a možnosti predikcí, se kterými se setkáte v aplikaci Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095695"
---
# <a name="predictions-overview"></a>Přehled predikcí

Dynamics 365 Customer Insights je vybavena řadou možností, které využívají AI a strojové učení k předpovídání dat. 

## <a name="out-of-box-models"></a>Předem připravené modely

Nejjednodušší způsob, jak začít s předpovídáním dat, jsou předem definované modely, často označované jako vestavěné modely. K rychlému generování přehledů vyžadují pouze určitá data a strukturu. Aktuálně jsou k dispozici následující modely: 
- [Celoživotní hodnota zákazníka](predict-customer-lifetime-value.md): Předpovídá potenciální výnos ze zákazníka během jeho celé interakce s firmou. 
- [Doporučení produktu](predict-product-recommendation.md): Navrhuje sady prediktivních doporučení produktů na základě nákupního chování a zákazníků s podobnými nákupními vzory.
- [Úbytek předplatitelů](predict-subscription-churn.md): Předpovídá, zda hrozí ztráta zákazníka, pokud přestane používat produkty nebo služby v rámci předplatného vaší společnosti.
- [Úbytek transakcí](predict-transactional-churn.md): Předpovídá, zda si zákazník v určitém časovém rámci již nebude kupovat vaše produkty nebo služby.

## <a name="azure-machine-learning-integration"></a>Integrace Azure Machine Learning

Pokud organizace již používá scénáře strojového učení založené na experimentech Azure Machine Learning, funkce vlastních modelů v Customer Insights pomáhá propojit jednotlivé tečky. Vytvořte pracovní postupy, které vám pomohou vybrat data, ze kterých chcete generovat přehledy, a namapovat výsledky na vaše sjednocené profily zákazníků. Další informace viz [Vlastní modely strojového učení](custom-models.md).

## <a name="ai-builder-prediction"></a>Predikce AI Builder

Někdy jsou datové sady neúplné a některé hodnoty chybí. Customer Insights může pomoci předpovědět chybějící hodnoty pro entitu a segmenty zákazníka. Další informace najdete v článku [Doplnění dílčích data pomocí predikcí](predictions.md).
