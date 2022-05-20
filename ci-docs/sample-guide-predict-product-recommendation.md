---
title: Průvodce ukázkami predikce doporučení produktů
description: Pomocí tohoto průvodce ukázkami můžete vyzkoušet dodávaný model predikce doporučení produktů.
ms.date: 05/16/2022
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
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762678"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Průvodce ukázkami predikce doporučení produktů

Provedeme vás příkladem predikce doporučení produktů od začátku dokonce s využitím níže uvedených ukázkových dat.

## <a name="scenario"></a>Scénář

Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary, které prodává prostřednictvím svých webových stránek Contoso Coffee. Jejich cílem je pochopit, které produkty by měli doporučit svým vracejícím se zákazníkům. Informovanost, u kterých zákazníků je **pravděpodobnější nákup**, jim může pomoci ušetřit marketingové úsilí zaměřením na konkrétní položky.

## <a name="prerequisites"></a>Požadavky

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.
- Doporučujeme implementovat následující kroky [v novém prostředí](manage-environments.md).

## <a name="task-1---ingest-data"></a>Úkol 1 – Ingestace dat

Prohlédněte si články [o přijímání dat](data-sources.md) a [importu datových zdrojů pomocí konektorů Power Query](connect-power-query.md). Následující informace předpokládají, že jste se seznámili s ingestací dat obecně.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingestace zákaznických dat z platformy eCommerce

1. Vytvořte zdroj dat **eCommerce**, vyberte možnost importu a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/čas/pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformace data narození na datum.":::

1. V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommerceContacts**.

1. **Uložte** zdroj dat.

### <a name="ingest-online-purchase-data"></a>Ingestace dat online nákupu

1. Přidejte další datovou sadu do stejného zdroje dat **eCommerce**. Znovu vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro data **Online nákupy** [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **PurchasedOn**: Datum/čas
   - **TotalPrice**: Měna

1. V poli **Název** v postranním panelu přejmenujte svůj zdroj dat z **Query** na **eCommercePurchases**.

1. **Uložte** zdroj dat.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingestace zákaznických dat z věrnostního schématu

1. Vytvořte zdroj dat **LoyaltyScheme**, vyberte možnost importu a vyberte konektor **Text/CSV**.

1. Zadejte adresu URL pro kontakty eCommerce: [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.

1. Aktualizujte datový typ pro sloupce uvedené níže:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Datum/čas

1. V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **loyCustomers**.

1. **Uložte** zdroj dat.

## <a name="task-2---data-unification"></a>Úkol 2 – Sjednocení dat

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Úkol 3 – Konfigurace predikce doporučení produktů

Se zavedenými sjednocenými zákaznickými profily nyní můžeme spustit predikci doporučení produktu.

1. Přejděte na **Analytické nástroje** > **Predikce** a vyberte **Doporučení produktů**.

1. Vyberte **Začínáme**.

1. Pojmenujte model **Model predikce doporučení produktů OOB** a výstupní entitu **ModelPredikceDoporuceniProduktuOOB**.

1. Definujte tři podmínky pro model:

   - **Počet produktů**: Nastavte tuto hodnotu na **5**. Toto nastavení definuje, kolik produktů chcete svým zákazníkům doporučit.

   - **Očekávány opakované nákupy**: Vyberte **Ano**, čímž naznačíte, že chcete do doporučení zahrnout produkty, které vaši zákazníci zakoupili dříve.

   - **Okno ohlédnutí:** Vyberte alespoň **365 dní**. Toto nastavení definuje, jak daleko do minulosti má model prozkoumat aktivitu zákazníka, aby ji použil jako zdroj pro doporučení.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Předvolby modelu pro model doporučení produktů.":::

1. V kroku **Přidat požadovaná data** vyberte možnost **Přidat data**.

1. V podokně **Přidat data** vyberte **SalesOrderLine** jako entitu historie nákupů. V tuto chvíli pravděpodobně ještě není nakonfigurován. Otevřete odkaz v podokně a vytvořte aktivitu pomocí následujících kroků:
   1. Zadejte **Název aktivity** a zvolte *eCommerceNákupy:eCommerce* jako **Subjekt aktivity**. **Primární klíč** je *ID nákupu*.
   1. Definujte a pojmenujte vztah k *entitě eCommerceContacts:Commerce* a zvolte **ContactId** jako cizí klíč.
   1. Pro sjednocení aktivity nastavte **Aktivita události** jako *TotalPrice* a časové razítko na *PurchasedOn*. Můžete zadat více polí, jak je uvedeno v [Aktivity zákazníka](activities.md).
   1. Jako **Typ aktivity** vyberte *SalesOrderLine*. Namapujte následující pole aktivity.
      - ID řádku objednávky: PurchaseId
      - ID objednávky: PurchaseId
      - Datum objednávky: PurchasedOn
      - ID produktu: ProductId
      - Částka: TotalPrice
   1. Než se vrátíte ke konfiguraci modelu, zkontrolujte a dokončete aktivitu.

1. Až se vrátíte ke kroku **Vyberte aktivity**, vyberte nově vytvořenou aktivitu v sekci **Aktivity**. Vyberte **Další** a mapování atributů je již vyplněno. Vyberte **Uložit**.

1. V tomto vzorovém průvodci přeskočíme nastavení **Přidejte informace o produktu** a **Filtry produktu**, protože nemáme informace o produktech.

1. V kroku **Aktualizace dat** nastavte plán modelu.

   Model musí pravidelně trénovat, aby se naučil nové vzory, když jsou přijímána nová data. V tomto příkladu vyberte položku **Měsíčně**.

1. Po kontrole všech podrobností vyberte **Uložit a spustit**. První spuštění modelu bude trvat několik minut.

## <a name="task-4---review-model-results-and-explanations"></a>Úkol 4 – Kontrola výsledků modelu a vysvětlení

Nechte model dokončit cvičení a bodování dat. Nyní si můžete prohlédnout vysvětlení modelu doporučení produktů. Další informace viz [Kontrola stavu a výsledků predikce](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Úkol 5 – Vytvoření segmentu často kupovaných produktů

Spuštěním produkčního modelu se vytvoří nová entita, ve které se můžete podívat **Data** > **Entity**.

Můžete vytvořit nový segment na základě entity vytvořené modelem.

1. Jděte na **Segmenty**. Vyberte **Nový** a vyberte **Vytvořit z analytických nástrojů.**

   ![Vytvoření segmentu s výstupem modelu.](media/segment-intelligence.png)

1. Vyberte koncový bod **ModelPredikceDoporuceniProduktuOOB** a definujte segment:

   - Pole: ProductID
   - Hodnota: Vyberte první tři ID produktů

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Vytvoření segmentu z výsledků modelu.":::

Nyní máte segment, který se dynamicky aktualizuje a který identifikuje zákazníky, kteří by mohli mít zájem o nákup tří nejvíce doporučovaných produktů.

Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
