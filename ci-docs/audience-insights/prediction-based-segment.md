---
title: Segmenty založené na výstupu predikcí
description: Vytvořte segmenty na základě výstupní entity modelu predikce.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741421"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="c714a-103">Vytvoření segmentu na základě modelu predikce (náhled)</span><span class="sxs-lookup"><span data-stu-id="c714a-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="c714a-104">Výsledky predikcí se někdy vztahují pouze na podmnožinu vašich zákazníků.</span><span class="sxs-lookup"><span data-stu-id="c714a-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="c714a-105">Zvyšte personalizaci doporučení vytvořením segmentů z výsledků modelů predikce.</span><span class="sxs-lookup"><span data-stu-id="c714a-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="c714a-106">Můžete například chtít poskytnout konkrétní doporučení zákazníkům, kteří upřednostňují určitý typ služby.</span><span class="sxs-lookup"><span data-stu-id="c714a-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c714a-107">Požadavky</span><span class="sxs-lookup"><span data-stu-id="c714a-107">Prerequisites</span></span>

- <span data-ttu-id="c714a-108">Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c714a-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="c714a-109">Doporučení produktu, úbytek transakcí, změna předplatného nebo model celoživotní hodnoty zákazníka nakonfigurovaný ve službě Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c714a-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="c714a-110">Zkontrolujte požadavky na nastavení různých modelů:</span><span class="sxs-lookup"><span data-stu-id="c714a-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="c714a-111">Model doporučení produktu</span><span class="sxs-lookup"><span data-stu-id="c714a-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="c714a-112">Model ztracených předplatitelů</span><span class="sxs-lookup"><span data-stu-id="c714a-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="c714a-113">Model úbytku transakcí</span><span class="sxs-lookup"><span data-stu-id="c714a-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="c714a-114">Model Hodnota životnosti zákazníka</span><span class="sxs-lookup"><span data-stu-id="c714a-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="c714a-115">Vytvoření segmentu zákazníků na základě predikcí</span><span class="sxs-lookup"><span data-stu-id="c714a-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="c714a-116">Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.</span><span class="sxs-lookup"><span data-stu-id="c714a-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c714a-117">Vyberte svislé tlačítko se třemi tečkami vedle modelu, který chcete zkontrolovat, a vyberte **Zobrazit**.</span><span class="sxs-lookup"><span data-stu-id="c714a-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="c714a-118">Na stránce s výsledky vyberte **Vytvořit segment**.</span><span class="sxs-lookup"><span data-stu-id="c714a-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="c714a-119">Další informace o stránce s výsledky najdete v článku o modelu.</span><span class="sxs-lookup"><span data-stu-id="c714a-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Screenshot stránky s výsledky predikce se zvýrazněním akce Vytvořit segment.":::

1. <span data-ttu-id="c714a-121">Vytvořte nový segmenty na základě výstupní entity vybraného modelu.</span><span class="sxs-lookup"><span data-stu-id="c714a-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="c714a-122">Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c714a-122">For more information, see [Create and manage segments](segments.md).</span></span>