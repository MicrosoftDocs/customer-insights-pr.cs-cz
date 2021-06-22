---
title: Průvodce ukázkami predikce doporučení produktů
description: Pomocí tohoto průvodce ukázkami můžete vyzkoušet dodávaný model predikce doporučení produktů.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b136084316da5ae17a8428236381f69e5c21f9ea
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129891"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Průvodce ukázkami predikce doporučení produktů (Preview)

Provedeme vás příkladem predikce doporučení produktů od začátku dokonce s využitím níže uvedených ukázkových dat.

## <a name="scenario"></a>Scénář

Contoso je společnost vyrábějící vysoce kvalitní kávu a kávovary, které prodávají prostřednictvím svého webu Contoso Coffee. Jejich cílem je pochopit, které produkty by měli doporučit svým vracejícím se zákazníkům. Informovanost, u kterých zákazníků je **pravděpodobnější nákup**, jim může pomoci ušetřit marketingové úsilí zaměřením na konkrétní položky.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformace data narození na datum.":::

5. V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommerceContacts**.

6. **Uložte** zdroj dat.

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

## <a name="task-2---data-unification"></a>Úkol 2 – Sjednocení dat

Po příjmu dat nyní zahájíme proces sjednocení dat, abychom vytvořili jednotný profil zákazníka. Další informace naleznete v tématu [Sjednocení dat](data-unification.md).

### <a name="map"></a>Mapovat

1. Po ingestaci dat namapujte kontakty z eCommerce a věrnostní data na běžné datové typy. Přejděte na **Data** > **Sjednocení** > **Mapování**.

2. Vyberte entity, které představují profil zákazníka – **eCommerceContacts** a **loyCustomers**.

   ![Sjednocení zdrojů dat eCommerce a věrnostních bodů.](media/unify-ecommerce-loyalty.png)

3. Vyberte **ContactId** jako primární klíč pro **eCommerceContatcs** a **LoyaltyID** jako primární klíč pro **loyCustomers**.

   ![Sjednocení LoyaltyId jako primární klíč.](media/unify-loyaltyid.png)

### <a name="match"></a>Shoda barev

1. Přejděte na kartu **Párování** a vyberte **Nastavit pořadí**.

2. V rozevíracím seznamu **Primární** vyberte **eCommerceContacts: eCommerce** jako primární zdroj a zahrňte všechny záznamy.

3. V rozevíracím seznamu **Entita 2** vyberte **loyCustomers: LoyaltyScheme** a zahrňte všechny záznamy.

   ![Sjednocení párování dat eCommerce a věrnostních bodů.](media/unify-match-order.png)

4. Vyberte **Vytvořit nové pravidlo**

5. Přidejte svou první podmínku pomocí FullName.

   - Pro eCommerceContacts vyberte **FullName** v rozbalovací nabídce.
   - Pro loyCustomers vyberte **FullName** v rozbalovací nabídce.
   - Vyberte rozevírací seznam **Normalizovat** rozevírací seznam a vyberte **Typ (telefon, jméno, adresa, ...)**.
   - Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.

6. Zadejte jméno **Celé jméno, e-mail** pro nové pravidlo.

   - Přidejte druhou podmínku pro e-mailovou adresu výběrem **Přidat podmínku**
   - Pro entitu eCommerceContacts zvolte **EMail** v rozevíracím seznamu.
   - Pro entitu loyCustomers zvolte **EMail** v rozevíracím seznamu.
   - Ponechejte pole Noramlizovat prázdné.
   - Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.

   ![Sjednocení pravidla párování pro jméno a e-mail.](media/unify-match-rule.png)

7. Zvolte **Uložit** a **Spustit**.

### <a name="merge"></a>Sloučení

1. Přejděte na kartu **Sloučení**.

1. V **ContactId** pro entitu **loyCustomers** změňte zobrazované jméno na **ContactIdLOYALTY**, abyste jej odlišili od ingestovaných ID.

   ![Přejmenování contactid z věrnostního ID.](media/unify-merge-contactid.png)

1. Volbami **Uložit** a **Spustit** zahájíte proces sloučení.

## <a name="task-3---configure-product-recommendation-prediction"></a>Úkol 3 – Konfigurace predikce doporučení produktů

Se zavedenými sjednocenými profily zákazníků nyní můžeme spustit predikci úbytku předplatných.

1. Přejděte na **Analytické nástroje** > **Predikce** a vyberte **Doporučení produktů**.

1. Vyberte **Začínáme**.

1. Pojmenujte model **Model predikce doporučení produktů OOB** a výstupní entitu **ModelPredikceDoporuceniProduktuOOB**.

1. Definujte tři podmínky pro model:

   - **Počet produktů**: Nastavte tuto hodnotu na **5**. Toto nastavení definuje, kolik produktů chcete svým zákazníkům doporučit.

   - **Očekávány opakované nákupy**: Vyberte **Ano**, čímž naznačíte, že chcete do doporučení zahrnout produkty, které vaši zákazníci zakoupili dříve.

   - **Okno ohlédnutí:** Vyberte alespoň **365 dní**. Toto nastavení definuje, jak daleko do minulosti má model prozkoumat aktivitu zákazníka, aby ji použil jako zdroj pro doporučení.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Předvolby modelu pro model doporučení produktů.":::

1. Vyberte **Požadovaná data** a vyberte **Přidat data** pro historii nákupů.

1. Přidejte entitu **eCommercePurchases : eCommerce** entita a mapujte pole z eCommerce na odpovídající pole požadovaná modelem.

1. Připojte se k entitě **eCommercePurchases: eCommerce** pomocí **eCommerceContacts: eCommerce**.

   ![Připojení se k entitám eCommerce.](media/model-purchase-join.png)

1. Vyberte **Další** pro nastavení plánu modelu.

   Model musí pravidelně trénovat, aby se naučil nové vzory, když jsou přijímána nová data. V tomto příkladu vyberte položku **Měsíčně**.

1. Po kontrole všech podrobností vyberte **Uložit a spustit**.


## <a name="task-4---review-model-results-and-explanations"></a>Úkol 4 – Kontrola výsledků modelu a vysvětlení

Nechte model dokončit cvičení a bodování dat. Nyní si můžete prohlédnout vysvětlení modelu doporučení produktů. Další informace viz [Kontrola stavu a výsledků predikce](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Úkol 5 – Vytvoření segmentu často kupovaných produktů

Spuštěním produkčního modelu se vytvoří nová entita, ve které se můžete podívat **Data** > **Entity**.

Můžete vytvořit nový segment na základě entity vytvořené modelem.

1. Jděte na **Segmenty**. Vyberte **Nový** a vyberte **Vytvořit z** > **Analytické nástroje**.

   ![Vytvoření segmentu s výstupem modelu.](media/segment-intelligence.png)

1. Vyberte koncový bod **ModelPredikceDoporuceniProduktuOOB** a definujte segment:

   - Pole: ProductID
   - Operátor: Hodnota
   - Hodnota: Vyberte první tři ID produktů

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Vytvoření segmentu z výsledků modelu.":::

Nyní máte segment, který se dynamicky aktualizuje a který identifikuje zákazníky, kteří jsou ochotnější zakoupit tři nejdoporučovanější produkty. 

Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
