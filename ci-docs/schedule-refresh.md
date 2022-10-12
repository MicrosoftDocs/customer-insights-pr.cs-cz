---
title: Plánování aktualizace systému
description: Naplánujte čas, kdy má být systém aktualizován
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610320"
---
# <a name="schedule-system-refresh"></a>Plánování aktualizace systému

Naplánujte automatické obnovení všech [přijatých zdrojů dat](data-sources.md). Automatické aktualizace pomáhají zajistit, aby se aktualizace ze zdrojů dat projevily ve vašich sjednocených profilech zákazníků.

> [!NOTE]
> Vámi spravované zdroje dat Power Query se obnovují podle vlastních plánů. Chcete-li naplánovat aktualizaci těchto zdrojů dat Power Query, nakonfigurujte nastavení aktualizace na tomto konkrétním zdroji dat ze stránky **Zdroje dat**. Srovnejte načasování s upstreamovým plánem aktualizace dat tak, aby k aktualizacím nedocházelo najednou.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Nastavení aktualizace toku dat.":::

## <a name="set-system-refresh-schedule"></a>Nastavení plánu aktualizace systému

1. Jděte na **Správa** > **Systém** a vyberte kartu **Plán**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Karta Naplánovat aktualizaci ze stránky Systém.":::

1. Výchozí stav pro plánovanou aktualizaci je **Vypnuto**. Chcete-li povolit naplánované aktualizace, změňte přepínač v horní části obrazovky na **Zapnuto**.

1. Vyberte mezi aktualizacemi **Týdně** (výchozí) a **Denně**. Pokud chcete naplánovat týdenní aktualizace, vyberte jeden nebo více dní, ve kterých chcete aktualizaci spustit.

1. Nastavte své **Časové pásmo**, pak použijte rozbalovací nabídku **Čas** pro nastavení času aktualizace. Pokud chcete naplánovat více aktualizací v jeden den, vyberte **Přidejte další čas**. Můžete přidat až čtyři obnovení.

1. Výběrem možnosti **Uložit** se vaše změny uplatní.

[!INCLUDE [footer-include](includes/footer-banner.md)]
