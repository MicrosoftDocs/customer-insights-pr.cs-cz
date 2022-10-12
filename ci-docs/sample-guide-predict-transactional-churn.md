---
title: Průvodce ukázkami predikce úbytku transakcí
description: Pomocí tohoto průvodce ukázkami můžete vyzkoušet dodávaný model predikce úbytku transakcí.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609676"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Průvodce ukázkami predikce úbytku transakcí

Tento průvodce vás provede vás příkladem predikce úbytku transakcí od začátku do konce s využitím ukázkových dat. Doporučujeme vyzkoušet tuto predikci [v novém prostředí](manage-environments.md).

## <a name="scenario"></a>Scénář

Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary. Produkty prodávají prostřednictvím svých webových stránek Contoso Coffee. Jejím cílem je vědět, kteří zákazníci, kteří obvykle nakupují její produkty pravidelně, přestanou být aktivními zákazníky v příštích 60 dnech. Informace, který z jejích zákazníků bude **pravděpodobně ztracen**, jí může pomoci ušetřit marketingové prostředky tím, že se soustředí na jeho udržení.

## <a name="prerequisites"></a>Předpoklady

- Alespoň [oprávnění Přispěvatel](permissions.md).

## <a name="task-1---ingest-data"></a>Úkol 1 – Ingestace dat

Prohlédněte si články [o přijímání dat](data-sources.md) a [připojení ke zdroji dat Power Query](connect-power-query.md). Následující informace předpokládají, že jste se seznámili s vkládáním dat obecně.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingestace zákaznických dat z platformy eCommerce

1. Vytvořte zdroj dat **eCommerce** a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscontacts.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:

   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/čas/pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformace pole DateOfBirth na Date.":::

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat na **eCommerceContacts**

1. Uložte zdroj dat.

### <a name="ingest-online-purchase-data"></a>Ingestace dat online nákupu

1. Přidejte další datovou sadu do stejného zdroje dat **eCommerce**. Znovu vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro data online nákupů https://aka.ms/ciadclassonline.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:

   - **PurchasedOn**: Datum/čas
   - **TotalPrice**: Měna

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat na **eCommercePurchases**.

1. Uložte zdroj dat.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingestace zákaznických dat z věrnostního schématu

1. Vytvořte zdroj dat **LoyaltyScheme** a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:

   - **DateOfBirth**: Datum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Datum/čas

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat na **loyCustomers**.

1. Uložte zdroj dat.

## <a name="task-2---data-unification"></a>Úkol 2 – Sjednocení dat

Projděte článek [o sjednocení dat](data-unification.md). Následující informace předpokládají, že jste obecně obeznámení se sjednocením dat.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Úkol 3 – vytvoření aktivity historie transakcí

Přečtěte si článek [o aktivitách zákazníka](activities.md). Následující informace předpokládají, že jste obecně obeznámení s vytvářením aktivit.

1. Vytvořte aktivitu s názvem **eCommercePurchases** s entitou *eCommercePurchases:eCommerce* a primárním klíčem **PurchaseId**.

1. Vytvořte vztah mezi *eCommercePurchases:eCommerce* a *eCommerceKontakty:eCommerce* s **ContactID** jako cizím klíčem pro spojení dvou entit.

1. Vyberte **TotalPrice** u **EventActivity** a **PurchasedOn** u **TimeStamp**.

1. Vyberte **SalesOrderLine** u **Typ aktivity** a sémanticky namapujte data aktivity.

1. Spusťte aktivitu.

## <a name="task-4---configure-transaction-churn-prediction"></a>Úkol 4 – Konfigurace predikce úbytku transakcí

Se zavedenými sjednocenými zákaznickými profily a aktivitou nyní můžeme spustit převod transakcí predikce.

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Vytvořit** vyberte **Použít model** na **Model úbytku zákazníků**.

1. Vyberte **Transakce** pro typ úbytku a pak **Začínáme**.

1. Pojmenujte model **Předdefinovaná predikce úbytku transakcí eCommerce** a výstupní entitu **OOBeCommerceChurnPrediction**.

1. Vyberte **Další**.

1. Definování předvoleb modelu:

   - **Okno predikce**: **60** dní k definování, jak daleko do budoucna chceme předvídat úbytek zákazníků.

   - **Definice úbytku**: **60** dní k uvedení doby bez nákupu, po které je zákazník považován za ztraceného.

     :::image type="content" source="media/model-levers.PNG" alt-text="Výběr předvoleb modelu Interval predikce a Definice úbytku.":::

1. Vyberte **Další**.

1. Vyberte **Historie nákupů (povinné)** a vyberte **Přidat data** pro historii nákupů.

1. Vyberte **SalesOrderLine** a entitu eCommercePurchases a vyberte **Další**. Požadované údaje se automaticky doplní z aktivity. Vyberte **Uložit** a pak **Další**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Připojení se k entitám eCommerce.":::

1. Přeskočte krok **Další data (volitelné)**.

1. V kroku **Aktualizace dat** nastavte pro plán modelu **Měsíčně**.

1. Po kontrole všech podrobností vyberte **Uložit a spustit**.

## <a name="task-5---review-model-results-and-explanations"></a>Úkol 5 – Kontrola výsledků modelu a vysvětlení

Nechte model dokončit cvičení a bodování dat. Prohlédněte si vysvětlení modelu úbytku. Další informace viz [Zobrazení výsledků predikce](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Úkol 6 – Vytvoření segmentu zákazníků s vysokým rizikem ztráty

Spuštěním produkčního modelu se vytvoří nová entita, která je uvedena na stránce **Data** > **Entity**. Můžete vytvořit nový segment na základě entity vytvořené modelem.

1. Na stránce s výsledky vyberte **Vytvořit segment**.

1. Vytvořte pravidlo s použitím entity **OOBeCommerceChurnPrediction** a definujte segment:
   - **Pole**: ChurnScore
   - **Operátor**: větší než
   - **Hodnota**: 0,6

1. Vyberte **Uložit** a **Spustit** segment.

Nyní máte segment, který se dynamicky aktualizuje a který identifikuje zákazníky s vysokým rizikem odchodu zákazníků. Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).

> [!TIP]
> Můžete také vytvořit segment pro model predikce na stránce **Segmenty** výběrem **Nový** a výběrem **Vytvořit z** > **Datový analýza**. Další informace viz [Vytvoření nového segmentu pomocí rychlých segmentů](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
