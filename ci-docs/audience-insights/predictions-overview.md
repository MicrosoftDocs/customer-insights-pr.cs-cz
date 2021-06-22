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
# <a name="predictions-overview"></a><span data-ttu-id="83dcd-103">Přehled predikcí</span><span class="sxs-lookup"><span data-stu-id="83dcd-103">Predictions overview</span></span>

<span data-ttu-id="83dcd-104">Dynamics 365 Customer Insights je vybavena řadou možností, které využívají AI a strojové učení k předpovídání dat.</span><span class="sxs-lookup"><span data-stu-id="83dcd-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="83dcd-105">Předem připravené modely</span><span class="sxs-lookup"><span data-stu-id="83dcd-105">Out-of-box models</span></span>

<span data-ttu-id="83dcd-106">Nejjednodušší způsob, jak začít s předpovídáním dat, jsou předem definované modely, často označované jako vestavěné modely.</span><span class="sxs-lookup"><span data-stu-id="83dcd-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="83dcd-107">K rychlému generování přehledů vyžadují pouze určitá data a strukturu.</span><span class="sxs-lookup"><span data-stu-id="83dcd-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="83dcd-108">Aktuálně jsou k dispozici následující modely:</span><span class="sxs-lookup"><span data-stu-id="83dcd-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="83dcd-109">[Celoživotní hodnota zákazníka](predict-customer-lifetime-value.md): Předpovídá potenciální výnos ze zákazníka během jeho celé interakce s firmou.</span><span class="sxs-lookup"><span data-stu-id="83dcd-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="83dcd-110">[Doporučení produktu](predict-product-recommendation.md): Navrhuje sady prediktivních doporučení produktů na základě nákupního chování a zákazníků s podobnými nákupními vzory.</span><span class="sxs-lookup"><span data-stu-id="83dcd-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="83dcd-111">[Úbytek předplatitelů](predict-subscription-churn.md): Předpovídá, zda hrozí ztráta zákazníka, pokud přestane používat produkty nebo služby v rámci předplatného vaší společnosti.</span><span class="sxs-lookup"><span data-stu-id="83dcd-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="83dcd-112">[Úbytek transakcí](predict-transactional-churn.md): Předpovídá, zda si zákazník v určitém časovém rámci již nebude kupovat vaše produkty nebo služby.</span><span class="sxs-lookup"><span data-stu-id="83dcd-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="83dcd-113">Integrace Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="83dcd-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="83dcd-114">Pokud organizace již používá scénáře strojového učení založené na experimentech Azure Machine Learning, funkce vlastních modelů v Customer Insights pomáhá propojit jednotlivé tečky.</span><span class="sxs-lookup"><span data-stu-id="83dcd-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="83dcd-115">Vytvořte pracovní postupy, které vám pomohou vybrat data, ze kterých chcete generovat přehledy, a namapovat výsledky na vaše sjednocené profily zákazníků.</span><span class="sxs-lookup"><span data-stu-id="83dcd-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="83dcd-116">Další informace viz [Vlastní modely strojového učení](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="83dcd-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="83dcd-117">Predikce AI Builder</span><span class="sxs-lookup"><span data-stu-id="83dcd-117">AI Builder prediction</span></span>

<span data-ttu-id="83dcd-118">Někdy jsou datové sady neúplné a některé hodnoty chybí.</span><span class="sxs-lookup"><span data-stu-id="83dcd-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="83dcd-119">Customer Insights může pomoci předpovědět chybějící hodnoty pro entitu a segmenty zákazníka.</span><span class="sxs-lookup"><span data-stu-id="83dcd-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="83dcd-120">Další informace najdete v článku [Doplnění dílčích data pomocí predikcí](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="83dcd-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
