---
title: Přehled rozšíření dat (Preview)
description: Využijte možnosti společnosti Microsoft a dalších služeb třetích stran k rozšíření údajů o zákaznících.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053856"
---
# <a name="data-enrichment-preview-overview"></a>Přehled rozšíření dat (Preview)

K rozšíření svých zákaznických dat použijte data ze zdrojů, jako je Microsoft a další partneři. Rozšíření třetích stran se konfigurují pomocí [připojení](connections.md), které správce nastaví pomocí pověření a poskytne souhlas s datovými přenosy. Připojení mohou používat správci a přispěvatelé ke konfiguraci rozšíření.  

## <a name="multiple-enrichments-of-the-same-type"></a>Více rozšíření stejného typu

Entita, kterou chcete rozšířit, je zadána během konfigurace rozšíření, což vám umožní rozšířit pouze podmnožinu vašich profilů. Například rozšiřte data pouze pro konkrétní segment. Můžete nakonfigurovat několik rozšíření stejného typu a znovu použít stejné propojení . Některá rozšíření budou mít rozšíření počtu rozšíření stejného typu, které lze vytvořit. Limity a aktuální využití lze vidět na každé dlaždici na kartě **Zjistit** stránky **Rozšíření**.

## <a name="enrich-data-sources-before-unification"></a>Rozšíření zdrojů dat před sjednocením

Před sjednocením dat můžete rozšířit zákaznická data, abyste zvýšili kvalitu shody dat. Další informace najdete v tématu [Rozšíření zdroje dat](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Vytvořit obohacení

K vytváření nebo úpravě rozšíření musíte mít [oprávnění](permissions.md) přispěvatele nebo správce.

Přejděte na **Data** > **Rozšíření**. Na kartě **Zjistit** najdete všechny podporované možnosti rozšíření.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra rozšíření.":::

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

- [Identitu AbiliTec](enrichment-liveramp.md) poskytuje společnost LiveRamp AbiliTec
- [Značky](enrichment-microsoft.md) poskytované společností Microsoft
- [Demografické údaje](enrichment-experian.md) poskytované společností Experian
- [Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované společností Microsoft
- [Zájmy](enrichment-microsoft.md) poskytované společností Microsoft
- [Údaje o poloze](enrichment-azure-maps.md) poskytuje Microsoft Azure Maps
- [Údaje o poloze](enrichment-here.md) poskytované společností HERE Technologies
- [Vlastní data SFTP](enrichment-SFTP-custom-import.md) skrze Secure File Transfer Protocol (SFTP)

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

- [Data o zapojení obchodního vztahu](enrichment-office.md) poskytované společností Microsoft
- [Firemní data](enrichment-dnb.md) z Dun & Bradstreet
- [Údaje o společnosti](enrichment-leadspace.md) poskytované společností Leadspace
- [Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované společností Microsoft
- [Vylepšená data společnosti](enrichment-enhanced-company-data.md) poskytnutá společností Microsoft
- [Údaje o poloze](enrichment-azure-maps.md) poskytuje Microsoft Azure Maps
- [Údaje o poloze](enrichment-here.md) poskytované společností HERE Technologies
- [Vlastní data SFTP](enrichment-SFTP-custom-import.md) skrze Secure File Transfer Protocol (SFTP)

---

## <a name="manage-existing-enrichments"></a>Správa existujících rozšíření

Přejděte na **Data** > **Rozšíření**. Na záložce **Moje rozšíření** zobrazte nakonfigurovaná rozšíření, jejich stav, počet rozšířených zákazníků a čas poslední aktualizace dat. Seznam rozšiřování můžete seřadit podle libovolného sloupce nebo pomocí vyhledávacího pole najít rozšiřování, které chcete spravovat.

Vyberte rozšiřování pro zobrazení dostupných akcí.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti správy rozšíření v seznamu rozšíření.":::

- Možností **Zobrazit** zobrazíte podrobnosti o rozšíření s počtem rozšířených profilů zákazníků.
- Možností **Upravit** upravíte konfiguraci rozšíření.
- [**Spusťte**](#run-or-refresh-enrichments) rozšíření k aktualizaci profilů zákazníků o nejnovější data. Spusťte více rozšiřování najednou tak, že je vyberete v seznamu.
- **Aktivujte** nebo **deaktivujte** rozšiřování. Neaktivní rozšiřování se během [plánovaného obnovení](system.md#schedule-tab) neaktualizuje.
- **Odstraňte** rozšíření.

Můžete také vytvořit [segmenty](segments.md) nebo [míry](measures.md) z rozšíření.

## <a name="run-or-refresh-enrichments"></a>Spuštění nebo aktualizace rozšíření

Po spuštění lze rozšiřování obnovovat podle automatického plánu nebo ručně na vyžádání.

1. Chcete-li ručně obnovit jedno nebo více rozšiřování, vyberte je a vyberte **Spustit**. Na záložce [naplánovat automatické obnovení](system.md#schedule-tab) jděte na **Správce** > **Systém** > **Plán**. Doba zpracování závisí na velikosti vašich zákaznických dat.

1. Volitelně [viz pokrok procesu rozšíření](#see-the-progress-of-the-enrichment-process).

1. Po dokončení procesu rozšíření přejděte na **Moje rozšíření** a zkontrolujte data nově rozšířených zákaznických profilů, čas poslední aktualizace a počet rozšířených profilů.

1. Vyberte rozšíření, které chcete zobrazit [výsledky rozšíření](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Podívejte se na průběh procesu rozšíření

Můžete najít podrobnosti o zpracování rozšíření, včetně jeho stavu a potenciálních problémů, v průběhu obnovování nebo po dokončení aktualizace. Pochopte, které procesy jsou zahrnuty pro aktualizaci rozšíření, a jak dlouho trvalo spuštění procesů. Stav rozšíření je podporován pro Experian, Leadspace, HERE Technologies, SFTP Import a Azure Maps.

1. Přejděte na **Data** > **Rozšíření**.
1. Na záložce **Moje rozšíření** vyberte stav rozšíření a otevřete boční panel.
1. V podokně **Podrobnosti o průběhu** rozbalte část **Rozšíření**.
1. Pod rozšířením, pro které chcete vidět průběh, vyberte **Zobrazit podrobnosti**.
1. V podokně **Podrobnosti o úkolu** vyberte **Zobrazit podrobnosti** a zobrazte procesy, které se podílejí na aktualizaci rozšíření, a jejich stav.

## <a name="view-enrichment-results"></a>Zobrazení výsledků rozšiřování

Po dokončení rozšíření můžete zkontrolovat jeho výsledky.

1. Přejděte na **Data** > **Rozšíření**.
1. Na záložce **Moje rozšíření** vyberte rozšíření které chcete zobrazit.

Všechna rozšíření ukazují základní informace, jako je počet rozšířených profilů a počet rozšířených profilů v průběhu času. Dlaždice **Náhled rozšířených zákazníků** ukazuje vzorek generované entity rozšíření. Pokud chcete zobrazit podrobné zobrazení, vyberte možnost **Další informace** a vyberte kartu **Data**.

:::image type="content" source="media/enrichments-results.png" alt-text="Stránka s výsledky rozšíření.":::

Pokud je k dispozici možnost **Počet zákazníků obohacených o pole**, můžete procházet k podrobnostem pokrytí každého rozšířeného pole.

Některá rozšíření také zobrazují informace specifické pro typ rozšíření. Další informace naleznete v související dokumentaci.

[!INCLUDE [footer-include](includes/footer-banner.md)]
