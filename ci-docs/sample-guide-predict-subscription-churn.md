---
title: Průvodce ukázkami predikce úbytku předplatných
description: Pomocí tohoto průvodce ukázkami můžete vyzkoušet dodávaný model predikce úbytku předplatných.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741403"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Průvodce ukázkami predikce úbytku předplatných

Provedeme vás příkladem predikce úbytku předplatných od začátku dokonce s využitím níže uvedených ukázkových dat. 

## <a name="scenario"></a>Scénář

Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary, které prodává prostřednictvím svých webových stránek Contoso Coffee. Nedávno zavedla předplatné pro své zákazníky, aby mohli pravidelně dostávat kávu. Jejím cílem je pochopit, kteří zákazníci s předplatným mohou v příštích několika měsících své předplatné zrušit. Informace, který z jejích zákazníků bude **pravděpodobně ztracen**, jí může pomoci ušetřit marketingové prostředky tím, že se soustředí na jeho udržení.

## <a name="prerequisites"></a>Požadavky

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.
- Doporučujeme implementovat následující kroky [v novém prostředí](manage-environments.md).

## <a name="task-1---ingest-data"></a>Úkol 1 – Ingestace dat

Prohlédněte si články [o přijímání dat](data-sources.md) a [importu datových zdrojů pomocí konektorů Power Query](connect-power-query.md). Následující informace předpokládají, že jste se seznámili s ingestací dat obecně. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingestace zákaznických dat z platformy eCommerce

1. Vytvořte zdroj dat **eCommerce**, vyberte možnost importu a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscontacts.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:

   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/čas/pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformace data narození na datum.":::

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommerceContacts**.

1. Uložte zdroj dat.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingestace zákaznických dat z věrnostního schématu

1. Vytvořte zdroj dat **LoyaltyScheme**, vyberte možnost importu a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:

   - **DateOfBirth**: Datum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Datum/čas

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **loyCustomers**.

1. Uložte zdroj dat.

### <a name="ingest-subscription-information"></a>Ingestace informací o předplatném

1. Vytvořte zdroj dat **SubscriptionHistory**, vyberte možnost importu a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadchurnsubscriptionhistory.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:

   - **SubscriptioID**: Celé číslo
   - **SubscriptionAmount**: Měna
   - **SubscriptionEndDate**: Datum/čas
   - **SubscriptionStartDate**: Datum/čas
   - **TransactionDate**: Datum/čas
   - **IsRecurring**: True/false (pravda/nepravda)
   - **Is_auto_renew**: True/false (Pravda/nepravda)
   - **RecurringFrequencyInMonths**: Celé číslo

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **SubscriptionHistory**.

1. Uložte zdroj dat.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingestace zákaznických dat z recenzí na webových stránkách

1. Vytvořte zdroj dat **Website**, vyberte možnost importu a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasswebsite.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:

   - **ReviewRating**: Celé číslo
   - **ReviewDate**: Datum

1. V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Query** na **webReviews**.

## <a name="task-2---data-unification"></a>Úkol 2 – Sjednocení dat

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Úkol 3 – Konfigurace predikce úbytku předplatných

Se zavedenými sjednocenými profily zákazníků nyní můžeme spustit predikci úbytku předplatných. Podrobné kroky viz článek [Predikce úbytku předplatitelů](predict-subscription-churn.md). 

1. Přejděte na **Analytické nástroje** > **Prozkoumat** a vyberte **Model úbytku zákazníků**.

1. Vyberte možnost **Předplatné** a pak **Začít**.

1. Pojmenujte model **Předdefinovaná predikce úbytku předplatných** a výstupní entitu **OOBSubscriptionChurnPrediction**.

1. Definujte dvě podmínky pro model úbytku:

   * **Dny od ukončení předplatného**: **alespoň 60** dnů. Pokud zákazník neobnoví své předplatné během této doby po ukončení předplatného, pak se považuje za ztraceného. 

   * **Definice úbytku**: **alespoň 93** dnů. Doba trvání modelu predikuje, kteří zákazníci by mohli odejít. Čím více hledíte do budoucnosti, tím méně jsou výsledky přesné.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Výběr pák modelu Interval predikce a Definice úbytku.":::

1. Vyberte **Přidat požadovaná data** a vyberte **Přidat data** pro historii předplatného.

1. Přidejte entitu **Předplatné: SubscriptionHistory** entita a mapujte pole z eCommerce na odpovídající pole požadovaná modelem.

1. Přidejte se k entitě **Předplatné: SubscriptionHistory** s **eCommerceContacts: eCommerce**, pojmenujte vztah **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Připojení se k entitám eCommerce.":::

1. V části Aktivity zákazníka přidejte entitu **webReviews: Website** a mapujte pole z webReviews na odpovídající pole požadovaná modelem. 
   - Primární klíč: ReviewId
   - Časové razítko: ReviewDate
   - Událost: ReviewRating

1. Nakonfigurujte aktivitu pro recenze webových stránek. Vyberte aktivitu **Recenze** a připojte se k entitě **webReviews: Website** s **eCommerceContacts: eCommerce**.

1. Vyberte **Další** pro nastavení plánu modelu.

   Model musí pravidelně trénovat, aby se naučil nové vzory, když jsou přijímána nová data. V tomto příkladu vyberte položku **Měsíčně**.

1. Po kontrole všech podrobností vyberte **Uložit a spustit**.

## <a name="task-4---review-model-results-and-explanations"></a>Úkol 4 – Kontrola výsledků modelu a vysvětlení

Nechte model dokončit cvičení a bodování dat. Nyní si můžete prohlédnout vysvětlení modelu úbytku předplatných. Další informace viz [Kontrola stavu a výsledků predikce](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Úkol 5 – Vytvoření segmentu zákazníků s vysokým rizikem ztráty

Spuštěním produkčního modelu se vytvoří nová entita, ve které se můžete podívat **Data** > **Entity**.   

Můžete vytvořit nový segment na základě entity vytvořené modelem.

1.  Jděte na **Segmenty**. Vyberte **Nový** a vyberte **Vytvořit z** > **Analytické nástroje**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Vytvoření segmentu s výstupem modelu.":::

1. Vyberte koncový bod **OOBSubscriptionChurnPrediction** a definujte segment: 
   - Pole: ChurnScore
   - Operátor: větší než
   - Hodnota: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nastavení segmentu úbytku předplatných.":::

Nyní máte segment, který se dynamicky aktualizuje a který identifikuje zákazníky s vysokým rizikem odchodu pro toto podnikání s předplatným.

Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]