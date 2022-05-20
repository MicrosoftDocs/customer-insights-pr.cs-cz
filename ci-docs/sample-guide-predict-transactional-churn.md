---
title: Průvodce ukázkami predikce úbytku transakcí
description: Pomocí tohoto průvodce ukázkami můžete vyzkoušet dodávaný model predikce úbytku transakcí.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741311"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Průvodce ukázkami predikce úbytku transakcí

Tento průvodce vás provede příkladem predikce úbytku transakcí od začátku dokonce v Customer Insights s využitím níže uvedených ukázkových dat. Všechna data použitá v tomto průvodci nejsou skutečná zákaznická data a jsou součástí datové sady Contoso v prostředí *Ukázka* v rámci vašeho předplatného Customer Insights.

## <a name="scenario"></a>Scénář

Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary, které prodává prostřednictvím svých webových stránek Contoso Coffee. Jejím cílem je vědět, kteří zákazníci, kteří obvykle nakupují její produkty pravidelně, přestanou být aktivními zákazníky v příštích 60 dnech. Informace, který z jejích zákazníků bude **pravděpodobně ztracen**, jí může pomoci ušetřit marketingové prostředky tím, že se soustředí na jeho udržení.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformace pole DateOfBirth na Date.":::

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommerceContacts**.

1. Uložte zdroj dat.

### <a name="ingest-online-purchase-data"></a>Ingestace dat online nákupu

1. Přidejte další datovou sadu do stejného zdroje dat **eCommerce**. Znovu vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro data **Online nákupy** https://aka.ms/ciadclassonline.

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:

   - **PurchasedOn**: Datum/čas
   - **TotalPrice**: Měna
   
1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommercePurchases**.

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

## <a name="task-2---data-unification"></a>Úkol 2 – Sjednocení dat

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Úkol 3 – Konfigurace predikce úbytku transakcí

Se zavedenými sjednocenými zákaznickými profily nyní můžeme spustit převod transakcí predikce. Podrobné kroky viz článek [Predikce úbytku transakce](predict-transactional-churn.md). 

1. Přejděte na **Analytické nástroje** > **Prozkoumat** a vyberte **Model úbytku zákazníků**.

1. Vyberte možnost **Transakce** a pak **Začít**.

1. Pojmenujte model **Předdefinovaná predikce úbytku transakcí eCommerce** a výstupní entitu **OOBeCommerceChurnPrediction**.

1. Definujte dvě podmínky pro model úbytku:

   * **Interval predikce**: **alespoň 60** dnů. Toto nastavení definuje, jak daleko do budoucna chceme předvídat úbytek zákazníků.

   * **Definice úbytku**: **alespoň 60** dnů. Doba bez nákupu, po které je zákazník považován za ztraceného.

     :::image type="content" source="media/model-levers.PNG" alt-text="Výběr pák modelu Interval predikce a Definice úbytku.":::

1. Vyberte **Historie nákupů (povinné)** a vyberte **Přidat data** pro historii nákupů.

1. Přidejte entitu **eCommercePurchases : eCommerce** entita a mapujte pole z eCommerce na odpovídající pole požadovaná modelem.

1. Připojte se k entitě **eCommercePurchases: eCommerce** pomocí **eCommerceContacts: eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Připojení se k entitám eCommerce.":::

1. Vyberte **Další** pro nastavení plánu modelu.

   Model musí pravidelně trénovat, aby se naučil nové vzory, když jsou přijímána nová data. V tomto příkladu vyberte položku **Měsíčně**.

1. Po kontrole všech podrobností vyberte **Uložit a spustit**.

## <a name="task-4---review-model-results-and-explanations"></a>Úkol 4 – Kontrola výsledků modelu a vysvětlení

Nechte model dokončit cvičení a bodování dat. Nyní si můžete prohlédnout vysvětlení modelu úbytku. Další informace viz [Kontrola stavu a výsledků predikce](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Úkol 5 – Vytvoření segmentu zákazníků s vysokým rizikem ztráty

Spuštěním produkčního modelu se vytvoří nová entita, ve které se můžete podívat **Data** > **Entity**.   

Můžete vytvořit nový segment na základě entity vytvořené modelem.

1.  Jděte na **Segmenty**. Vyberte **Nový** a vyberte **Vytvořit z** > **Analytické nástroje**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Vytvoření segmentu s výstupem modelu.":::

1. Vyberte koncový bod **OOBeCommerceChurnPrediction** a definujte segment: 
   - Pole: ChurnScore
   - Operátor: větší než
   - Hodnota: 0,6

Nyní máte segment, který se dynamicky aktualizuje a který identifikuje zákazníky s vysokým rizikem odchodu zákazníků.

Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
