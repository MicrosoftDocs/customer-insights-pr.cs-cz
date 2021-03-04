---
title: Použití zdrojů dat pro ingestaci dat
description: Naučte se, jak importovat data z různých zdrojů.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269690"
---
# <a name="data-sources-overview"></a>Přehled zdrojů dat

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Funkce přehledů cílové skupiny v Dynamics 365 Customer Insights propojuje data ze široké sady zdrojů. Připojení k zdroji dat se často označuje jako proces *příjmu dat*. Po požití dat můžete [sjednotit](data-unification.md) a podniknout s tím kroky.

## <a name="add-a-data-source"></a>Přidat zdroj dat

V závislosti na zvolené možnosti si přečtěte podrobné články o tom, jak přidat zdroj dat.

Zdroj dat můžete přidat třemi hlavními způsoby:

- [Prostřednictvím desítek konektorů Power Query](connect-power-query.md)
- [Ze složky modelu Common Data Model](connect-common-data-model.md)
- [Z vlastního jezera Common Data Service](connect-common-data-service-lake.md)

> [!NOTE]
> Data z místních datových zdrojů zatím nemůžete přidat.

## <a name="review-ingested-data"></a>Zkontrolujte přijatá data

Uvidíte název každého přijatého zdroje dat, jeho stav a poslední čas, kdy byla data pro tento zdroj aktualizována. Seznam zdrojů dat můžete seřadit podle každého sloupce.

> [!div class="mx-imgBorder"]
> ![Přidaný zdroj dat](media/configure-data-datasource-added.png "Přidaný zdroj dat")

|Stav  |Popis  |
|---------|---------|
|Úspěch   |Zdroj dat byl úspěšně ingestován, pokud je v sloupci **Aktualizováno** uveden čas.
|Nezahájeno   |Zdroj dat zatím nemá žádná ingestovaná data nebo je stále v režimu konceptu.         |
|Probíhá aktualizace    |Probíhá příjem dat. Tuto operaci můžete zrušit výběrem **Přestat obnovovat** v sloupci **Akce**. Zastavením aktualizace zdroje dat se vrátíte do posledního stavu obnovy.       |
|Nezdařilo se     |Při přijímání dat došlo k chybám.         |

Vyberte hodnotu ve sloupci **Stav** ve zdroji dat, chcete-li znát další podrobnosti. V podokně **Podrobnosti o průběhu** rozbalte **Zdroje dat**. Volbou **Zobrazit podrobnosti** zobrazíte další informace o stavu aktualizace, včetně podrobností o chybách a následných aktualizacích procesu.

Načtení dat může chvíli trvat. Po úspěšné aktualizaci lze přijatá data zkontrolovat na stránce **Entity**. Další informace najdete v tématu [Entity](entities.md).

## <a name="refresh-a-data-source"></a>Aktualizace zdroje dat

Zdroje dat lze aktualizovat podle automatického plánu nebo ručně na vyžádání. 

Přejděte na **Správce** > **Systém** > [**Plán**](system.md#schedule-tab), ke nakonfigurujte naplánované aktualizace všech ingestovaných zdrojů dat.

Chcete-li aktualizovat zdroj dat na vyžádání, postupujte takto:

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**

2. Vyberte svislé tři tečky vedle zdroje dat, který chcete aktualizovat, a vyberte **Aktualizovat** z rozevíracího seznamu.

3. Zdroj dat je nyní spuštěn pro ruční aktualizaci. Aktualizací zdroje dat aktualizujete jak schéma entity, tak i data pro všechny entity zadané ve zdroji dat.

4. Vyberte **Zastavit aktualizaci**, pokud chcete zrušit existující aktualizaci a zdroj dat se vrátí do svého posledního stavu aktualizace.

## <a name="delete-a-data-source"></a>Odstranit datový zdroj

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2. Vyberte vertikální tři tečky vedle zdroje dat, který chcete odebrat, a vyberte **Odstranit** z rozbalovací nabídky.

3. Odstranění potvrďte.


[!INCLUDE[footer-include](../includes/footer-banner.md)]