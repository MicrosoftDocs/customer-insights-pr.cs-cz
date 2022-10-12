---
title: Průvodce ukázkami predikce úbytku předplatných
description: Pomocí tohoto průvodce ukázkami můžete vyzkoušet dodávaný model predikce úbytku předplatných.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609998"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Průvodce ukázkami predikce úbytku předplatných

Tento průvodce vás provede vás příkladem predikce úbytku předplatných od začátku dokonce s využitím ukázkových dat. Doporučujeme vyzkoušet tuto predikci [v novém prostředí](manage-environments.md).

## <a name="scenario"></a>Scénář

Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary. Produkty prodávají prostřednictvím svých webových stránek Contoso Coffee. Nedávno zavedla předplatné pro své zákazníky, aby mohli pravidelně dostávat kávu. Jejím cílem je pochopit, kteří zákazníci s předplatným mohou v příštích několika měsících své předplatné zrušit. Informace, který z jejích zákazníků bude **pravděpodobně ztracen**, jí může pomoci ušetřit marketingové prostředky tím, že se soustředí na jeho udržení.

## <a name="prerequisites"></a>Předpoklady

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.

## <a name="task-1---ingest-data"></a>Úkol 1 – Ingestace dat

Prohlédněte si články [o přijímání dat](data-sources.md) a [připojení ke zdroji dat Power Query](connect-power-query.md). Následující informace předpokládají, že jste se seznámili s vkládáním dat obecně.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingestace zákaznických dat z platformy eCommerce

1. Vytvořte zdroj dat Power Query s názvem **eCommerce** a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscontacts.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/čas/pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformace data narození na datum.":::

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat na **eCommerceContacts**

1. Uložte zdroj dat.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingestace zákaznických dat z věrnostního schématu

1. Vytvořte zdroj dat **LoyaltyScheme** a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro věrné zákazníky https://aka.ms/ciadclasscustomerloyalty.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Datum/čas

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat na **loyCustomers**.

1. Uložte zdroj dat.

### <a name="ingest-subscription-information"></a>Ingestace informací o předplatném

1. Vytvořte zdroj dat **SubscriptionHistory** a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro předplatná https://aka.ms/ciadchurnsubscriptionhistory

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

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat na **SubscriptionHistory**.

1. Uložte zdroj dat.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingestace zákaznických dat z recenzí na webových stránkách

1. Vytvořte zdroj dat **Website** a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL recenze webu https://aka.ms/ciadclasswebsite.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **ReviewRating**: Celé číslo
   - **ReviewDate**: Datum

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat na **webReviews**.

## <a name="task-2---data-unification"></a>Úkol 2 – Sjednocení dat

Projděte článek [o sjednocení dat](data-unification.md). Následující informace předpokládají, že jste obecně obeznámení se sjednocením dat.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Úkol 3 – vytvoření aktivity historie transakcí

Přečtěte si článek [o aktivitách zákazníka](activities.md). Následující informace předpokládají, že jste obecně obeznámení s vytvářením aktivit.

1. Vytvořte aktivitu s názvem **SubscriptionHistory** s entitou *Subscription* a primárním klíčem **CustomerId**.

1. Vytvořte vztah mezi *SubscriptionHistory:Subscription* a *eCommerceKontakty:eCommerce* s **CustomerID** jako cizím klíčem pro spojení dvou entit.

1. Vyberte **SubscriptionType** u **EventActivity** a **SubscriptionEndDate** u **TimeStamp**.

1. Vyberte **Subscription** u **Typ aktivity** a sémanticky namapujte data aktivity.

1. Spusťte aktivitu.

1. Přidejte jinou aktivitu a namapujte její názvy polí na odpovídající pole:
   - Entita aktivity zákazníka: Reviews:Website
   - Primární klíč: Website.Reviews.ReviewId
   - Časové razítko: Website.Reviews.ReviewDate
   - Událost (název aktivity): Website.Reviews.ActivityTypeDisplay
   - Podrobnosti (částka nebo hodnota): Website.Reviews.ReviewRating

1. Spusťte aktivitu.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Úkol 4 – Konfigurace predikce úbytku předplatných

Se zavedenými sjednocenými profily zákazníků a vytvořenou aktivitou nyní můžeme spustit predikci úbytku předplatných. Podrobné kroky viz článek [Predikce úbytku předplatitelů](predict-subscription-churn.md).

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Vytvořit** vyberte **Použít model** na kartě **Model úbytku zákazníků**.

1. Vyberte **Předplatné** pro typ úbytku a pak **Začínáme**.

1. Pojmenujte model **Předdefinovaná predikce úbytku předplatných** a výstupní entitu **OOBSubscriptionChurnPrediction**.

1. Definování předvoleb modelu:
   - **Dny od ukončení předplatného**: **60** dnů, aby bylo uvedeno, že zákazník je považován za zrušeného, pokud neobnoví předplatné v tomto období po ukončení předplatného.
   - **Dny na prozkoumání budoucnosti, aby bylo možné předvídat odchod**: **93** dní, což je doba, po kterou model předpovídá, kteří zákazníci by mohli odejít. Čím více hledíte do budoucnosti, tím méně jsou výsledky přesné.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Výběr předvoleb modelu definice úbytku.":::

1. Vyberte **Další**.

1. V kroku **Požadovaná data** vyberte **Přidat data** a zadejte historii předplatného.

1. Vyberte **Předplatné** a entitu SubscriptionHistory a vyberte **Další**. Požadované údaje se automaticky doplní z aktivity. Vyberte **Uložit**.

1. V části Aktivity zákazníka vyberte **Přidat data**.

1. V tomto příkladu přidejte aktivitu webové recenze.

1. Vyberte **Další**.

1. V kroku **Aktualizace dat** nastavte pro plán modelu **Měsíčně**.

1. Po kontrole všech podrobností vyberte **Uložit a spustit**.

## <a name="task-5---review-model-results-and-explanations"></a>Úkol 5 – Kontrola výsledků modelu a vysvětlení

Nechte model dokončit cvičení a bodování dat. Prohlédněte si vysvětlení modelu úbytku předplatného. Další informace viz [Zobrazení výsledků predikce](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Úkol 6 – Vytvoření segmentu zákazníků s vysokým rizikem ztráty

Spuštěním modelu se vytvoří nová entita, která je uvedena na stránce **Data** > **Entity**. Můžete vytvořit nový segment na základě entity vytvořené modelem.

1. Na stránce s výsledky vyberte **Vytvořit segment**.

1. Vytvořte pravidlo s použitím entity **OOBSubscriptionChurnPrediction** a definujte segment:
   - **Pole**: ChurnScore
   - **Operátor**: větší než
   - **Hodnota**: 0,6

1. Vyberte **Uložit** a **Spustit** segment.

Nyní máte segment, který se dynamicky aktualizuje a který identifikuje zákazníky s vysokým rizikem odchodu pro toto podnikání s předplatným. Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).

> [!TIP]
> Můžete také vytvořit segment pro model predikce na stránce **Segmenty** výběrem **Nový** a výběrem **Vytvořit z** > **Datový analýza**. Další informace viz [Vytvoření nového segmentu pomocí rychlých segmentů](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
