---
title: Průvodce ukázkami predikce doporučení produktů
description: Pomocí tohoto průvodce ukázkami můžete vyzkoušet dodávaný model predikce doporučení produktů.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610136"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Průvodce ukázkami predikce doporučení produktů

Tento průvodce vás provede příkladem predikce doporučení produktů od začátku dokonce s využitím ukázkových dat. Doporučujeme vyzkoušet tuto predikci [v novém prostředí](manage-environments.md).

## <a name="scenario"></a>Scénář

Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary. Produkty prodávají prostřednictvím svých webových stránek Contoso Coffee. Jejich cílem je pochopit, které produkty by měli doporučit svým vracejícím se zákazníkům. Informovanost, u kterých zákazníků je **pravděpodobnější nákup**, jim může pomoci ušetřit marketingové úsilí zaměřením na konkrétní položky.

## <a name="prerequisites"></a>Předpoklady

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.

## <a name="task-1---ingest-data"></a>Úkol 1 – Ingestace dat

Prohlédněte si články [o přijímání dat](data-sources.md) a [připojení ke zdroji dat Power Query](connect-power-query.md). Následující informace předpokládají, že jste se seznámili s vkládáním dat obecně.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingestace zákaznických dat z platformy eCommerce

1. Vytvořte zdroj dat Power Query s názvem **eCommerce** a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce: https://aka.ms/ciadclasscontacts.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/čas/pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformace data narození na datum.":::

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat na **eCommerceContacts**.

1. **Uložte** zdroj dat.

### <a name="ingest-online-purchase-data"></a>Ingestace dat online nákupu

1. Přidejte další datovou sadu do stejného zdroje dat **eCommerce**. Znovu vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro data online nákupů https://aka.ms/ciadclassonline.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **PurchasedOn**: Datum/čas
   - **TotalPrice**: Měna

1. V poli **Název** v postranním panelu přejmenujte svůj zdroj dat na **eCommercePurchases**.

1. **Uložte** zdroj dat.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingestace zákaznických dat z věrnostního schématu

1. Vytvořte zdroj dat **LoyaltyScheme** a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro věrné zákazníky https://aka.ms/ciadclasscustomerloyalty.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Datum/čas

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat na **loyCustomers**.

1. **Uložte** zdroj dat.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>Úkol 4 – Konfigurace predikce doporučení produktů

Se zavedenými sjednocenými zákaznickými profily a vytvořenou aktivitou nyní můžeme spustit predikci doporučení produktu.

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Vytvořit** vyberte **Použít model** na dlaždici **Doporučení produktů (Preview)**.

1. Vyberte **Začínáme**.

1. Pojmenujte model **Model predikce doporučení produktů OOB** a výstupní entitu **ModelPredikceDoporuceniProduktuOOB**.

1. Vyberte **Další**.

1. Definování předvoleb modelu:
   - **Počet produktů:**: **5** k definování, kolik produktů chcete svým zákazníkům doporučit.
   - **Očekávají se opakované nákupy**: **Ano** pro zahnutí dříve zakoupených produktů do doporučení.
   - **Období pro pohled zpět:** **365 dní** k definování, jak daleko se model ohlédne, než produkt znovu doporučí.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Předvolby modelu pro model doporučení produktů.":::

1. Vyberte **Další**.

1. V kroku **Přidat historii nákupů** vyberte možnost **Přidat data**.

1. Vyberte **SalesOrderLine** a entitu eCommercePurchases a vyberte **Další**. Požadované údaje se automaticky doplní z aktivity. Vyberte **Uložit** a pak **Další**.

1. Přeskočte kroky **Přidejte informace o produktu** a **Filtry produktu**, protože nemáme informace o produktech.

1. V kroku **Aktualizace dat** nastavte pro plán modelu **Měsíčně**.

1. Vyberte **Další**.

1. Po kontrole všech podrobností vyberte **Uložit a spustit**.

## <a name="task-5---review-model-results-and-explanations"></a>Úkol 5 – Kontrola výsledků modelu a vysvětlení

Nechte model dokončit cvičení a bodování dat. Prohlédněte si [vysvětlení modelu doporučení produktů](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Úkol 6 – Vytvoření segmentu často kupovaných produktů

Spuštěním modelu se vytvoří nová entita, která je uvedena na stránce **Data** > **Entity**. Můžete vytvořit nový segment na základě entity vytvořené modelem.

1. Na stránce s výsledky vyberte **Vytvořit segment**.

1. Vytvořte pravidlo s použitím entity **OOBProductRecommendationModelPrediction** a definujte segment:
   - **Pole**: ProductID
   - **Hodnota**: Vyberte první tři ID produktů

1. Vyberte **Uložit** a **Spustit** segment.

Nyní máte segment, který se dynamicky aktualizuje a který identifikuje zákazníky, kteří by mohli mít zájem o nákup pět nejvíce doporučovaných produktů. Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).

> [!TIP]
> Můžete také vytvořit segment pro model predikce na stránce **Segmenty** výběrem **Nový** a výběrem **Vytvořit z** > **Datový analýza**. Další informace viz [Vytvoření nového segmentu pomocí rychlých segmentů](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
