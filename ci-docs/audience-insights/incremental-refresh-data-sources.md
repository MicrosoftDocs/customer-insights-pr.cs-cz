---
title: Přírůstková aktualizace pro zdroje dat založené na Power Query
description: Aktualizujte nová a aktualizovaná data pro velké zdroje dat založené na Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: d204228f8d6881cbf0e7fac6609bf50dd5296610
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377826"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Přírůstková aktualizace pro zdroje dat založené na Power Query

Přírůstková aktualizace pro zdroje dat poskytuje následující výhody:

- **Rychlejší aktualizace** – Obnoví se pouze data, která se změnila. Můžete například obnovit pouze posledních pět dní historické množiny dat.
- **Zvýšená spolehlivost** – U menších aktualizací nemusíte udržovat připojení k nestabilním zdrojovým systémům tak dlouho, což snižuje riziko problémů s připojením.
- **Snížená spotřeba zdrojů** – Aktualizace pouze podmnožiny vašich celkových dat vede k efektivnějšímu využití výpočetních zdrojů a snižuje dopad na životní prostředí.

## <a name="configure-incremental-refresh"></a>Konfigurovat přírůstkovou aktualizaci

Přehledy cílové skupiny umožňují přírůstkovou aktualizaci zdrojů dat importovaných prostřednictvím Power Query, které podporují přírůstkovou ingestaci. Například databáze Azure SQL s datovými a časovými poli, která označují, kdy byly naposledy aktualizovány datové záznamy.

1. [Vytvoření nového zdroje dat na základě Power Query](connect-power-query.md).

1. Zadejte název zdroje dat.

1. Vyberte zdroj dat, který podporuje přírůstkové aktualizace, například databázi Azure SQL.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]