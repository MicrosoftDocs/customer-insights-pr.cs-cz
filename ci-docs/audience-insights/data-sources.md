---
title: Použití zdrojů dat pro ingestaci dat
description: Naučte se, jak importovat data z různých zdrojů.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 27cbd0346b1219c7812f4b90327dd27b645c2b8e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732119"
---
# <a name="data-sources-overview"></a>Přehled zdrojů dat

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Funkce přehledů cílové skupiny v Dynamics 365 Customer Insights propojuje data ze široké sady zdrojů. Připojení k zdroji dat se často označuje jako proces *příjmu dat*. Po požití dat můžete [sjednotit](data-unification.md) a podniknout s tím kroky.

## <a name="add-a-data-source"></a>Přidat zdroj dat

V závislosti na zvolené možnosti si přečtěte podrobné články o tom, jak přidat zdroj dat.

Zdroj dat můžete přidat třemi hlavními způsoby:

- [Prostřednictvím desítek konektorů Power Query](connect-power-query.md)
- [Ze složky modelu Common Data Model](connect-common-data-model.md)
- [Z vlastního jezera Microsoft Dataverse](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Přidání dat z místních zdrojů dat

Příjem dat z místních zdrojů dat v cílové skupině přehledů je podporován na základě toků dat Microsoft Power Platform. Toky dat lze povolit v nástroji Customer Insights [poskytnutím adresy URL prostředí Microsoft Dataverse](create-environment.md) při nastavování prostředí.

Zdroje dat, které se vytvoří po přidružení prostředí Dataverse k nástroji Customer Insights, budou používat [toky dat Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) ve výchozím stavu. Datové toky podporují místní připojení pomocí datové brány. Odeberte a znovu vytvořte zdroje dat, které existovaly před přidružením prostředí Dataverse k [použití místních bran dat](/data-integration/gateway/service-gateway-app).

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
