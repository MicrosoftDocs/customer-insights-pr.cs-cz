---
title: Přírůstkové obnovení pro zdroje dat Power Query a Azure Data Lake
description: Obnovte nová a aktualizovaná data pro velké zdroje dat na základě zdrojů dat Power Query nebo Azure Data Lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012017"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Přírůstkové obnovení pro zdroje dat Power Query a Azure Data Lake

Tento článek popisuje, jak nakonfigurovat přírůstkovou aktualizaci pro zdroje dat na základě Power Query nebo Azure Data Lake.

Přírůstková aktualizace pro zdroje dat poskytuje následující výhody:

- **Rychlejší aktualizace** – Obnoví se pouze data, která se změnila. Můžete například obnovit pouze posledních pět dní historické množiny dat.
- **Zvýšená spolehlivost** – U menších aktualizací nemusíte udržovat připojení k nestabilním zdrojovým systémům tak dlouho, což snižuje riziko problémů s připojením.
- **Snížená spotřeba zdrojů** – Aktualizace pouze podmnožiny vašich celkových dat vede k efektivnějšímu využití výpočetních zdrojů a snižuje dopad na životní prostředí.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Konfigurace přírůstkové aktualizace pro zdroje dat založené na Power Query

Customer Insights umožňují přírůstkovou aktualizaci pro zdroje dat importované prostřednictvím Power Query, které podporují přírůstkovou ingestaci. Například databáze Azure SQL s datovými a časovými poli, která označují, kdy byly naposledy aktualizovány datové záznamy.

1. [Vytvořte nový zdroj dat založený na Power Query](connect-power-query.md).

1. Vyberte zdroj dat, který podporuje přírůstkové aktualizace, například [databázi Azure SQL](/power-query/connectors/azuresqldatabase).

1. Vyberte entity nebo tabulky, které chcete ingestovat.

1. Dokončete kroky transformace a vyberte **Další**.

1. V dialogovém okně **Nastavení přírůstkové aktualizace** volbou **Nastavit** otevřete **Nastavení přírůstkové aktualizace**. Pokud vyberete volbu **Přeskočit**, zdroj dat aktualizuje celou datovou sadu.
   > [!TIP]
   > Můžete také použít přírůstkovou aktualizaci později úpravou existujícího zdroj dat.

1. Na stránce **Nastavení přírůstkové aktualizace** nakonfigurujete přírůstkovou aktualizaci pro všechny entity, které jste vybrali při vytváření zdroje dat.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurace nastavení přírůstkového obnovení":::

1. Vyberte entitu a uveďte následující podrobnosti:

   - **Definujte primární klíč**: Vyberte primární klíč pro entitu nebo tabulku.
   - **Definujte pole „poslední aktualizace“**: Toto pole zobrazí pouze atributy typu datum nebo čas. Vyberte atribut, který označuje, kdy byly záznamy naposledy aktualizovány. Bude se používat k identifikaci záznamů, které spadají do časového rámce přírůstkové aktualizace.
   - **Zkontrolovat aktualizace každých**: Určete, jak velký časový rámec přírůstkové aktualizace chcete.

1. Volbou **Uložit** dokončete vytvoření zdroje dat. Počáteční aktualizace dat bude úplná aktualizace. Poté dochází k přírůstkové aktualizaci dat, jak bylo nakonfigurováno v předchozím kroku.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Konfigurace přírůstkového obnovení pro zdroje dat Azure Data Lake

Customer Insights umožňuje přírůstkové obnovení pro zdroje dat připojené k Azure Data Lake Storage. Chcete-li pro entitu použít přírůstkové zpracování a aktualizaci, nakonfigurujte tuto entitu při přidávání zdroje dat Azure Data Lake nebo později při úpravě zdroje dat. Složka dat entity musí obsahovat následující složky:

- **FullData**: Obsahuje datové soubory s počáteční záznamy.
- **IncrementalData**: Složka s hierarchickými složkami data/času **rrrr/mm/dd/hh** obsahující přírůstkové aktualizace. **hh** představuje hodinu UTC aktualizací a obsahuje složky **Upserts** a **Deletes**. **Upserts** obsahuje datové soubory s aktualizacemi stávajících záznamů nebo nových záznamů. **Deletes** obsahuje datové soubory se záznamy, které mají být odstraněny.

1. Při přidávání nebo úpravě zdroje dat přejděte na podokno **Atributy** pro entitu.

1. Zkontrolujte atributy. Ujistěte se, že atribut data vytvoření nebo poslední aktualizace je nastaven na *dateTime* **formát data** a *Calendar.Date* **Sémantický typ**. V případě potřeby atribut upravte a vyberte **Hotovo**.

1. V podokně **Vybrat entity** upravte entitu. Je zaškrtnuto políčko **Postupný příjem**.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Konfigurace entit ve zdroj dat pro přírůstkovou aktualizaci.":::

   1. Přejděte do kořenové složky, která obsahuje soubory .csv nebo .parquet, kde najdete úplná data, přírůstková data upserts a přírůstková data deletes.
   1. Zadejte příponu úplných dat a obou přírůstkových souborů (\.csv nebo \.parquet).
   1. Vyberte **Uložit**.

1. Pro **Naposledy aktualizováno** vyberte atribut časového razítka.

1. Pokud není vybrán **Primární klíč**, vyberte primární klíč. Primární klíč je atribut jedinečný pro entitu. Aby byl atribut platným primárním klíčem, nesmí obsahovat duplicitní hodnoty, chybějící hodnoty nebo hodnoty null. Jako primární klíče jsou podporovány atributy typu String, Integer a GUID.

1. Výběrem **Zavřít** uložte a zavřete podokno.

1. Pokračujte přidáváním nebo úpravou zdroje dat.

[!INCLUDE [footer-include](includes/footer-banner.md)]
