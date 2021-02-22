---
title: Průvodce ukázkami predikce úbytku předplatných
description: Pomocí tohoto průvodce ukázkami můžete vyzkoušet dodávaný model predikce úbytku předplatných.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653972"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Průvodce ukázkami (Preview) predikce úbytku předplatných

Provedeme vás příkladem predikce úbytku předplatných od začátku dokonce s využitím níže uvedených ukázkových dat. 

## <a name="scenario"></a>Scénář

Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary, které prodává prostřednictvím svých webových stránek Contoso Coffee. Nedávno zavedla předplatné pro své zákazníky, aby mohli pravidelně dostávat kávu. Jejím cílem je pochopit, kteří zákazníci s předplatným mohou v příštích několika měsících své předplatné zrušit. Informace, který z jejích zákazníků bude **pravděpodobně ztracen**, jí může pomoci ušetřit marketingové prostředky tím, že se soustředí na jeho udržení.

## <a name="prerequisites"></a>Požadavky

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.
- Doporučujeme implementovat následující kroky [v novém prostředí](manage-environments.md).

## <a name="task-1---ingest-data"></a>Úkol 1 – Ingestace dat

Projděte si články [o příjmu (ingestaci) dat](data-sources.md) a [importu zdrojů dat pomocí konektorů Power Query](connect-power-query.md). Následující informace předpokládají, že jste se seznámili s ingestací dat obecně. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingestace zákaznických dat z platformy eCommerce

1. Vytvořte zdroj dat **eCommerce**, vyberte možnost importu a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscontacts.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:

   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/čas/pásmo

   [!div class="mx-imgBorder"]
   ![Transformace pole DateOfBirth na Date](media/ecommerce-dob-date.PNG "Transformace data narození na datum")

1. V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommerceContacts**.

1. Uložte zdroj dat.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingestace zákaznických dat z věrnostního schématu

1. Vytvořte zdroj dat **LoyaltyScheme**, vyberte možnost importu a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:

   - **DateOfBirth**: Datum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Datum/čas

1. V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Query** na **loyCustomers**.

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

1. V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Query** na **SubscriptionHistory**.

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

Po ingestaci dat nyní začínáme s procesem **Mapování, párování, sloučení** pro vytvoření sjednoceného profilu zákazníka. Další informace naleznete v tématu [Sjednocení dat](data-unification.md).

### <a name="map"></a>Mapovat

1. Po ingestaci dat namapujte kontakty z eCommerce a věrnostní data na běžné datové typy. Přejděte na **Data** > **Sjednocení** > **Mapování**.

1. Vyberte entity, které představují profil zákazníka – **eCommerceContacts** a **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Sjednocení zdrojů dat eCommerce a věrnostních bodů.":::

1. Vyberte **ContactId** jako primární klíč pro **eCommerceContatcs** a **LoyaltyID** jako primární klíč pro **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Sjednocení LoyaltyId jako primární klíč.":::

### <a name="match"></a>Shoda barev

1. Přejděte na kartu **Párování** a vyberte **Nastavit pořadí**.

1. V rozevíracím seznamu **Primární** vyberte **eCommerceContacts: eCommerce** jako primární zdroj a zahrňte všechny záznamy.

1. V rozevíracím seznamu **Entita 2** vyberte **loyCustomers: LoyaltyScheme** a zahrňte všechny záznamy.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Sjednocení párování dat eCommerce a věrnostních bodů.":::

1. Vyberte **Vytvořit nové pravidlo**

1. Přidejte svou první podmínku pomocí FullName.

   * Pro eCommerceContacts vyberte **FullName** v rozbalovací nabídce.
   * Pro loyCustomers vyberte **FullName** v rozbalovací nabídce.
   * Vyberte rozevírací seznam **Normalizovat** rozevírací seznam a vyberte **Typ (telefon, jméno, adresa, ...)**.
   * Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.

1. Zadejte jméno **Celé jméno, e-mail** pro nové pravidlo.

   * Přidejte druhou podmínku pro e-mailovou adresu výběrem **Přidat podmínku**
   * Pro entitu eCommerceContacts zvolte **EMail** v rozevíracím seznamu.
   * Pro entitu loyCustomers zvolte **EMail** v rozevíracím seznamu. 
   * Ponechejte pole Noramlizovat prázdné. 
   * Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Sjednocení pravidla párování pro jméno a e-mail.":::

7. Zvolte **Uložit** a **Spustit**.

### <a name="merge"></a>Sloučení

1. Přejděte na kartu **Sloučení**.

1. V **ContactId** pro entitu **loyCustomers** změňte zobrazované jméno na **ContactIdLOYALTY**, abyste jej odlišili od ingestovaných ID.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Přejmenování contactid z věrnostního ID.":::

1. Volbami **Uložit** a **Spustit** zahájíte proces sloučení.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Úkol 3 – Konfigurace predikce úbytku předplatných

Se zavedenými sjednocenými profily zákazníků nyní můžeme spustit predikci úbytku předplatných. Podrobné kroky najdete v části [Predikce úbytku předplatných (Preview)](predict-subscription-churn.md). 

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