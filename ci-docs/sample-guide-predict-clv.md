---
title: Predikce celoživotní hodnoty zákazníka (CLV) – ukázkový průvodce
description: Pomocí tohoto ukázkového průvodce můžete vyzkoušet model predikce celoživotní hodnoty zákazníka.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609630"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Predikce celoživotní hodnoty zákazníka (CLV) – ukázkový průvodce

Tento průvodce vás provede kompletním příkladem predikce celoživotní hodnoty zákazníka (CLV) v Customer Insights s využitím ukázkových dat. Doporučujeme vyzkoušet tuto predikci [v novém prostředí](manage-environments.md).

## <a name="scenario"></a>Scénář

Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary. Produkty prodávají prostřednictvím svých webových stránek Contoso Coffee. Společnost chce znát hodnotu (výnos), kterou mohou její zákazníci generovat v příštích 12 měsících. Znalost očekávané hodnoty jejich zákazníků v příštích 12 měsících jim pomůže nasměrovat jejich marketingové úsilí na zákazníky s vysokou důležitostí.

## <a name="prerequisites"></a>Předpoklady

- Alespoň [oprávnění Přispěvatel](permissions.md).

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

1. **Uložte** zdroj dat.

### <a name="ingest-online-purchase-data"></a>Ingestace dat online nákupu

1. Přidejte další datovou sadu do stejného zdroje dat **eCommerce**. Znovu vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro data **Online nákupy** https://aka.ms/ciadclassonline.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Ingestace zákaznických dat z recenzí na webových stránkách

1. Vytvořte zdroj dat **Website** a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL recenze webu https://aka.ms/CI-ILT/WebReviews.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **ReviewRating**: Desetinné číslo
   - **ReviewDate**: Datum

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat na **Reviews**.

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

1. Přidejte jinou aktivitu a namapujte její názvy polí na odpovídající pole:
   - **Entita aktivity**: Reviews:Website
   - **Primární klíč**: ReviewId
   - **Časové razítko**: ReviewDate
   - **Aktivita události**: ActivityTypeDisplay
   - **Další podrobnosti**: ReviewRating
   - **Typ aktivity**: Recenze

1. Spusťte aktivitu.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Úkol 4 - Konfigurace predikce celoživotní hodnoty zákazníka

Se zavedenými sjednocenými profily zákazníků a vytvořenou aktivitou nyní můžeme spustit predikci celoživotní hodnoty zákazníka (CLV). Podrobné kroky viz [Predikce hodnoty životního cyklu zákazníka](predict-customer-lifetime-value.md).

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Vytvořit** vyberte **Použít model** na dlaždici **Celoživotní hodnota zákazníka**.

1. Vyberte **Začínáme**.

1. Modelu dejte název **OOB eCommerce CLV Prediction** a výstupní entitě název **OOBeCommerceCLVPrediction**.

1. Definování předvoleb modelu:
   - **Časové období predikce**: **12 měsíců nebo rok**, kterým definujte, jak daleko do budoucnosti chcete predikovat CLV.
   - **Aktivní zákazníci**: **Nechat model vypočítat interval prodeje**, což je časový rámec, ve kterém zákazník musel mít alespoň jednu transakci, aby mohl být považován za aktivního.
   - **Zákazník s vysokou hodnotou**: ručně definujte zákazníky s vysokou důležitostí jako **nejlepších 30 % aktivních zákazníků**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Předvolby v asistovaném prostředí pro model CLV.":::

1. Vyberte **Další**.

1. V kroku **Požadovaná data** vyberte **Přidat data** a zadejte údaje o historii transakcí.

    :::image type="content" source="media/clv-model-required.png" alt-text="Krok přidání požadovaných dat v asistovaném prostředí pro model CLV.":::

1. Vyberte **SalesOrderLine** a entitu eCommercePurchases a vyberte **Další**. Požadované údaje se automaticky doplní z aktivity. Vyberte **Uložit** a pak **Další**.

1. Krok **Další údaje (volitelné)** umožňuje přidat více údajů o aktivitě zákazníka, abyste získali další informace pro interakce se zákazníky. Pro tento příklad vyberte **Přidat data** a přidejte aktivitu webové recenze.

1. Vyberte **Další**.

1. V kroku **Aktualizace dat** nastavte pro plán modelu **Měsíčně**.

1. Vyberte **Další**.

1. Po kontrole všech podrobností vyberte **Uložit a spustit**.

## <a name="task-5---review-model-results-and-explanations"></a>Úkol 5 – Kontrola výsledků modelu a vysvětlení

Nechte model dokončit cvičení a bodování dat. Přečtěte si [výsledky modelu CLV a vysvětlení](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Úkol 6 - Vytvoření segmentu zákazníků s vysokou důležitostí

Spuštěním modelu se vytvoří nová entita, která je uvedena na stránce **Data** > **Entity**. Můžete vytvořit nový segment zákazníků na základě entity vytvořené modelem.

1. Na stránce s výsledky vyberte **Vytvořit segment**.

1. Vytvořte pravidlo s použitím entity **OOBeCommerceCLVPrediction** a definujte segment:
   - **Pole**: CLVScore
   - **Operátor**: větší než
   - **Hodnota**: 1500

1. Vyberte **Uložit** a **Spustit** segment.

Nyní máte segment, který identifikuje zákazníky, u nichž se předpokládá, že v příštích 12 měsících vygenerují více než 1500 USD výnosů. Tento segment se dynamicky aktualizuje, pokud je přijímáno více dat. Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).

> [!TIP]
> Můžete také vytvořit segment pro model predikce na stránce **Segmenty** výběrem **Nový** a výběrem **Vytvořit z** > **Datový analýza**. Další informace viz [Vytvoření nového segmentu pomocí rychlých segmentů](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
