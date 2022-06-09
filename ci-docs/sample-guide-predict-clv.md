---
title: Predikce celoživotní hodnoty zákazníka – ukázkový průvodce
description: Pomocí tohoto ukázkového průvodce můžete vyzkoušet model predikce celoživotní hodnoty zákazníka.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 351946c734f5a1054eb3769b2d9cced3bed48e15
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740803"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Predikce celoživotní hodnoty zákazníka (CLV) – ukázkový průvodce

Tento průvodce vás provede kompletním příkladem predikce celoživotní hodnoty zákazníka (CLV) v Customer Insights s využitím ukázkových dat.

## <a name="scenario"></a>Scénář

Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary. Produkty prodávají prostřednictvím svých webových stránek Contoso Coffee. Společnost chce znát hodnotu (výnos), kterou mohou její zákazníci generovat v příštích 12 měsících. Znalost očekávané hodnoty jejich zákazníků v příštích 12 měsících jim pomůže nasměrovat jejich marketingové úsilí na zákazníky s vysokou důležitostí.

## <a name="prerequisites"></a>Předpoklady

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.
- Doporučujeme implementovat následující kroky [v novém prostředí](manage-environments.md).

## <a name="task-1---ingest-data"></a>Úkol 1 – Ingestace dat

Prohlédněte si články [o přijímání dat](data-sources.md) a [importu datových zdrojů pomocí konektorů Power Query](connect-power-query.md). Následující informace předpokládají, že jste se seznámili s ingestací dat obecně.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingestace zákaznických dat z platformy eCommerce

1. Vytvořte zdroj dat s názvem **eCommerce**, vyberte možnost importu a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/čas/pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformace data narození na datum.":::

1. V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommerceContacts**.

1. **Uložte** zdroj dat.

### <a name="ingest-online-purchase-data"></a>Ingestace dat online nákupu

1. Přidejte další datovou sadu do stejného zdroje dat **eCommerce**. Znovu vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro data **Online nákupy** https://aka.ms/ciadclassonline.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **PurchasedOn**: Datum/čas
   - **TotalPrice**: Měna

1. V poli **Název** v postranním panelu přejmenujte svůj zdroj dat z **Query** na **eCommercePurchases**.

1. **Uložte** zdroj dat.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingestace zákaznických dat z věrnostního schématu

1. Vytvořte zdroj dat **LoyaltyScheme**, vyberte možnost importu a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Datum/čas

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **loyCustomers**.

1. **Uložte** zdroj dat.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingestace zákaznických dat z recenzí na webových stránkách

1. Vytvořte zdroj dat **Website**, vyberte možnost importu a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce https://aka.ms/CI-ILT/WebReviews.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:

   - **ReviewRating**: Desetinné číslo
   - **ReviewDate**: Datum

1. V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Dotaz** na **Recenze**.

1. **Uložte** zdroj dat.

## <a name="task-2---data-unification"></a>Úkol 2 – Sjednocení dat

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Úkol 3 - Konfigurace predikce celoživotní hodnoty zákazníka

Se zavedenými sjednocenými profily zákazníků nyní můžeme spustit predikci celoživotní hodnoty zákazníka. Podrobné kroky viz [Predikce hodnoty životního cyklu zákazníka](predict-customer-lifetime-value.md).

1. Přejděte do nabídky **Analytické nástroje**  > **Predikce** a vyberte **Model celoživotní hodnoty zákazníka**.

1. Projděte si informace v bočním podokně a vyberte položku **Začínáme**.

1. Modelu dejte název **OOB eCommerce CLV Prediction** a výstupní entitě název **OOBeCommerceCLVPrediction**.

1. Definujte předvolby modelu pro model CLV:
   - **Časové období předpovědi**: **12 měsíců nebo 1 rok**. Toto nastavení definuje, jak daleko do budoucnosti lze předpovědět celoživotní hodnotu zákazníka.
   - **Aktivní zákazníci**: Určete, co pro vaši firmu znamená aktivní zákazník. Nastavte historický časový rámec, ve kterém zákazník musel mít alespoň jednu transakci, aby mohl být považován za aktivního. Model bude predikovat CLV pouze pro aktivní zákazníky. Vyberte si, zda necháte model vypočítat časové období na základě historických údajů o transakcích, nebo zda zadáte konkrétní časový rámec. V této ukázkové příručce **necháme model vypočítat interval nákupu**, což je výchozí možnost.
   - **Zákazníci s vysokou důležitostí** : Definujte zákazníky s vysokou důležitostí jako percentil nejlépe platících zákazníků. Model používá tento vstup k vytváření výsledků, které odpovídají vaší obchodní definici zákazníků s vysokou důležitostí. Můžete nechat model definovat zákazníky s vysokou důležitostí. Používá heuristické pravidlo, které odvozuje percentil. Můžete také definovat zákazníky s vysokou důležitostí jako percentil nejlépe platících budoucích zákazníků. V této ukázkové příručce ručně definujeme zákazníky s vysokou důležitostí jako **nejlepších 30% aktivně platících zákazníků** a poté vyberte možnost **Další**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Předvolby v asistovaném prostředí pro model CLV.":::

1. V kroku **Požadovaná data** vyberte **Přidat data** a zadejte údaje o historii transakcí.

1. Přidejte entitu **eCommercePurchases : eCommerce** a mapujte atributy, které model vyžaduje:
   - ID transakce: eCommerce.eCommercePurchases.PurchaseId
   - Datum transakce: eCommerce.eCommercePurchases.PurchasedOn
   - Částka transakce: eCommerce.eCommercePurchases.TotalPrice
   - ID produktu: eCommerce.eCommercePurchases.ProductId

1. Vyberte **Další**.

1. Nastavte vztah mezi entitami **eCommercePurchases : eCommerce** a **eCommerceContacts : eCommerce**.

1. Krok **Další údaje (volitelné)** umožňuje přidat více údajů o aktivitě zákazníka. Tato data mohou pomoci získat více informací o interakcích zákazníků s vaší firmou, což může přispět k CLV. Přidání klíčových interakcí zákazníků, jako jsou webové protokoly, protokoly služeb zákazníkům nebo historie programu odměn, může zlepšit přesnost predikcí. Vyberte položku **Přidat data** a zadejte více údajů o aktivitě zákazníka.

1. Přidejte entitu aktivity zákazníka a namapujte její názvy polí na odpovídající pole vyžadovaná modelem:
   - Entita aktivity zákazníka: Reviews:Website
   - Primární klíč: Website.Reviews.ReviewId
   - Časové razítko: Website.Reviews.ReviewDate
   - Událost (název aktivity): Website.Reviews.ActivityTypeDisplay
   - Podrobnosti (částka nebo hodnota): Website.Reviews.ReviewRating

1. Vyberte položku **Další** a konfigurujte aktivitu a vztah mezi daty transakce a daty zákazníka:  
   - Typ aktivity: Zvolte stávající
   - Popisek aktivity: Review
   - Odpovídající popisek: Website.Reviews.UserId
   - Entita zákazníka: eCommerceContacts:eCommerce
   - Vztah: WebsiteReviews

1. Vyberte **Další** pro nastavení plánu modelu.

   Model potřebuje pravidelně trénovat, aby se naučil nové vzorce, když jsou přijímána nová data. V tomto příkladu zvolte **Měsíční**.

1. Po kontrole všech podrobností vyberte **Uložit a spustit**.

## <a name="task-4---review-model-results-and-explanations"></a>Úkol 4 – Kontrola výsledků modelu a vysvětlení

Nechte model dokončit cvičení a bodování dat. Dále si můžete prohlédnout výsledky a vysvětlení modelu CLV. Další informace viz [Kontrola stavu a výsledků predikce](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Úkol 5 - Vytvoření segmentu zákazníků s vysokou důležitostí

Spuštěním modelu se vytvoří nová entita, která je uvedena na stránce **Data** > **Entity**. Můžete vytvořit nový segment zákazníků na základě entity vytvořené modelem.

1. Jděte na **Segmenty**. 

1. Vyberte **Nový** a vyberte **Vytvořit z** > **Analytické nástroje**.

   ![Vytvoření segmentu s výstupem modelu.](media/segment-intelligence.png)

1. Vyberte entitu **OOBeCommerceCLVPrediction** a definujte segment:
  - Pole: CLVScore
  - Operátor: větší než
  - Hodnota: 1500

1. Vyberte **Zkontrolovat** a **Uložit** segment.

Nyní máte segment, který identifikuje zákazníky, u nichž se předpokládá, že v příštích 12 měsících vygenerují více než 1500 USD výnosů. Tento segment se dynamicky aktualizuje, pokud je přijímáno více dat.

Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).