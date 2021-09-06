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
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036411"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Vytvoření segmentu na základě modelu predikce (náhled)

Výsledky predikcí se někdy vztahují pouze na podmnožinu vašich zákazníků. Zvyšte personalizaci doporučení vytvořením segmentů z výsledků modelů predikce. Můžete například chtít poskytnout konkrétní doporučení zákazníkům, kteří upřednostňují určitý typ služby. 

## <a name="prerequisites"></a>Požadavky

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.

- Doporučení produktu, úbytek transakcí, změna předplatného nebo model celoživotní hodnoty zákazníka nakonfigurovaný ve službě Customer Insights. Zkontrolujte požadavky na nastavení různých modelů:

  - [Model doporučení produktu](predict-product-recommendation.md)
  - [Model ztracených předplatitelů](predict-subscription-churn.md)
  - [Model úbytku transakcí](predict-transactional-churn.md)
  - [Model Hodnota životnosti zákazníka](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Vytvoření segmentu zákazníků na základě predikcí

1. Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.

1. Vyberte svislé tlačítko se třemi tečkami vedle modelu, který chcete zkontrolovat, a vyberte **Zobrazit**.

1. Na stránce s výsledky vyberte **Vytvořit segment**. Další informace o stránce s výsledky najdete v článku o modelu.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Screenshot stránky s výsledky predikce se zvýrazněním akce Vytvořit segment.":::

1. Vytvořte nový segmenty na základě výstupní entity vybraného modelu. Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).