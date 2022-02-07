---
title: Použití zdrojů dat pro ingestaci dat
description: 'Naučte se, jak importovat data z různých zdrojů.'
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
---

# <a name="data-sources-overview"></a>Přehled zdrojů dat



Funkce přehledů cílové skupiny v Dynamics 365 Customer Insights propojuje data ze široké sady zdrojů. Připojení k zdroji dat se často označuje jako proces *příjmu dat*. Po požití dat můžete [sjednotit](data-unification.md) a podniknout s tím kroky.

## <a name="add-a-data-source"></a>Přidat zdroj dat

V podrobných článcích se dozvíte, jak přidat zdroj dat v závislosti na zvolené možnosti.

Jako zástupce můžete přidat následující zdroje dat:

- [Konektory Power Query](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Jezero Microsoft Dataverse](connect-dataverse-managed-lake.md)

> [!NOTE]
> Pokud používáte zkušební verzi, sekce s metodami importu obsahuje možnost **Knihovna dat Customer Insights**. Tuto možnost vyberte, chcete-li vybrat ukázkovou datovou sadu dostupnou pro různá odvětví. Další informace viz [Zkušební verze Dynamics 365 Customer Insights](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Přidání dat z místních zdrojů dat

Příjem dat z místních zdrojů dat v cílové skupině přehledů je podporován na základě toků dat Microsoft Power Platform. Datové toky v Customer Insights můžete povolit [zadáním adresy URL prostředí Microsoft Dataverse](create-environment.md) při nastavování prostředí.

Zdroje dat, které jsou vytvořeny po přidružení prostředí Dataverse ke Customer Insights, standardně používají [datové toky Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Datové toky podporují místní připojení pomocí datové brány. Zdroje dat, které existovaly před přidružením prostředí Dataverse, můžete odebrat a znovu vytvořit [pomocí místní bran dat](/data-integration/gateway/service-gateway-app).

Datové brány z existujícího prostředí Power BI nebo Power Apps bude viditelné a můžete jej znovu použít ve službě Customer Insights. Na stránce zdroje dat jsou zobrazeny odkazy, na které chcete přejít v prostředí Microsoft Power Platform, kde můžete prohlížet a konfigurovat místní datové brány.

## <a name="review-ingested-data"></a>Zkontrolujte přijatá data

Uvidíte název každého přijatého zdroje dat, jeho stav a poslední čas, kdy byla data pro tento zdroj aktualizována. Seznam zdrojů dat můžete seřadit podle každého sloupce.

> [!div class="mx-imgBorder"]
> ![Přidaný zdroj dat.](media/configure-data-datasource-added.png "Přidaný zdroj dat")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Načítání dat může nějakou dobu trvat. Po úspěšné aktualizaci lze přijatá data zkontrolovat na stránce **Entity**. Další informace najdete v tématu [Entity](entities.md).

## <a name="refresh-a-data-source"></a>Aktualizace zdroje dat

Zdroje dat lze aktualizovat podle automatického plánu nebo ručně na vyžádání. 

Přejděte na **Správce** > **Systém** > [**Plán**](system.md#schedule-tab), ke nakonfigurujte naplánované aktualizace všech ingestovaných zdrojů dat.

Chcete-li aktualizovat zdroj dat na vyžádání, postupujte takto:

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2. Vyberte svislé tlačítko se třemi tečkami vedle zdroje dat, který chcete aktualizovat, a v rozevíracím seznamu vyberte **Aktualizovat**.

3. Zdroj dat je nyní spuštěn pro ruční aktualizaci. Aktualizací zdroj dat aktualizujete schéma entity i data pro všechny entity uvedené ve zdroji dat.

4. Vyberte **Zastavit aktualizaci**, pokud chcete zrušit existující aktualizaci a zdroj dat se vrátí do svého posledního stavu aktualizace.

## <a name="delete-a-data-source"></a>Odstranit datový zdroj

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2. Vyberte svislé tlačítko se třemi tečkami vedle zdroje dat, který chcete odebrat, a v rozevírací nabídce vyberte **Odstranit**.

3. Odstranění potvrďte.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
