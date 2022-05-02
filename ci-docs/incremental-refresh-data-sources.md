---
title: Přírůstková aktualizace pro datové zdroje založené na Power Query
description: Aktualizujte nová a aktualizovaná data pro velké zdroje dat na základě Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645895"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Přírůstková aktualizace pro datové zdroje založené na Power Query

Tento článek popisuje, jak nakonfigurovat přírůstkovou aktualizaci pro zdroje dat na základě Power Query.

Přírůstková aktualizace pro zdroje dat poskytuje následující výhody:

- **Rychlejší aktualizace** – Obnoví se pouze data, která se změnila. Můžete například obnovit pouze posledních pět dní historické množiny dat.
- **Zvýšená spolehlivost** – U menších aktualizací nemusíte udržovat připojení k nestabilním zdrojovým systémům tak dlouho, což snižuje riziko problémů s připojením.
- **Snížená spotřeba zdrojů** – Aktualizace pouze podmnožiny vašich celkových dat vede k efektivnějšímu využití výpočetních zdrojů a snižuje dopad na životní prostředí.

## <a name="configure-incremental-refresh"></a>Konfigurace přírůstkové aktualizace

Customer Insights umožňují přírůstkovou aktualizaci pro zdroje dat importované prostřednictvím Power Query, které podporují přírůstkovou ingestaci. Například databáze Azure SQL s datovými a časovými poli, která označují, kdy byly naposledy aktualizovány datové záznamy.

1. [Vytvořte nový zdroj dat založený na Power Query](connect-power-query.md).

1. Zadejte **Název** zdroje dat.

1. Vyberte zdroj dat, který podporuje přírůstkové aktualizace, například [databázi Azure SQL](/power-query/connectors/azuresqldatabase).

1. Vyberte entity nebo tabulky, které chcete ingestovat.

1. Dokončete kroky transformace a vyberte **Další**.

1. V dialogovém okně **Nastavení přírůstkové aktualizace** volbou **Nastavit** otevřete **Nastavení přírůstkové aktualizace**. Pokud vyberete volbu **Přeskočit**, zdroj dat aktualizuje celou datovou sadu.
   > [!TIP]
   > Můžete také použít přírůstkovou aktualizaci později úpravou existujícího zdroj dat.

1. Na stránce **Nastavení přírůstkové aktualizace** nakonfigurujete přírůstkovou aktualizaci pro všechny entity, které jste vybrali při vytváření zdroje dat.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurace entit ve zdroj dat pro přírůstkovou aktualizaci.":::

1. Vyberte entitu a uveďte následující podrobnosti:

   - **Definujte primární klíč**: Vyberte primární klíč pro entitu nebo tabulku.
   - **Definujte pole „poslední aktualizace“**: Toto pole zobrazí pouze atributy typu datum nebo čas. Vyberte atribut, který označuje, kdy byly záznamy naposledy aktualizovány. Bude se používat k identifikaci záznamů, které spadají do časového rámce přírůstkové aktualizace.
   - **Zkontrolovat aktualizace každých**: Určete, jak velký časový rámec přírůstkové aktualizace chcete.

1. Volbou **Uložit** dokončete vytvoření zdroje dat. Počáteční aktualizace dat bude úplná aktualizace. Poté dochází k přírůstkové aktualizaci dat, jak bylo nakonfigurováno v předchozím kroku.


[!INCLUDE [footer-include](includes/footer-banner.md)]
