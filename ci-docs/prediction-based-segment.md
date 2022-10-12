---
title: Vytvoření segmentu na základě modelu predikce
description: Vytvořte segmenty na základě výstupní entity modelu predikce.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610412"
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

1. Vyberte model, který chcete zkontrolovat, a vyberte **Zobrazit**.

1. Na stránce s výsledky vyberte **Vytvořit segment**. Další informace o stránce s výsledky najdete v článku o modelu.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Screenshot stránky s výsledky predikce se zvýrazněním akce Vytvořit segment.":::

1. Vytvořte nový segment pomocí atributů z výstupní entity vybraného modelu. Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).

> [!TIP]
> Můžete také vytvořit segment pro model predikce na stránce **Segmenty** výběrem **Nový** a výběrem **Vytvořit z** > **Datový analýza**. Další informace viz [Vytvoření nového segmentu pomocí rychlých segmentů](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
