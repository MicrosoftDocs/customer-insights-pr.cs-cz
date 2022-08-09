---
title: Přehled exportů (Preview)
description: Spravujte exporty ke sdílení dat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: a70aadda4fc0eff3ddb4c89665506762613c291a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194960"
---
# <a name="exports-preview-overview"></a>Přehled exportů (Preview)

 Exporty vám umožňují sdílet konkrétní data s různými aplikacemi. Mohou zahrnovat zákaznické profily, entity, schémata a detaily mapování. Každý export vyžaduje [připojení, které nastavil správce, ke správě ověřování a přístupu](connections.md). Stránka **Export** zobrazuje všechny nakonfigurované exporty.

## <a name="export-types"></a>Typy exportu

Existují dva hlavní typy exportu:  

- **Export dat**: export libovolného typu entity dostupného v Customer Insights. Entity, které vyberete pro export, se exportují se všemi datovými poli, metadaty, schématy a podrobnostmi mapování.
- **Exporty segmentů**: export entit segmentů z Customer Insights. Segmenty představují seznam zákaznických profilů. Při konfiguraci exportu vyberete zahrnutá datová pole v závislosti na cílovém systému, do kterého exportujete data.

### <a name="export-segments"></a>Export segmentů

**Export segmentů v prostředích pro obchodní účty (B2B) nebo individuální spotřebitele (B2C)**  
Většina možností exportu podporuje oba typy prostředí. Export segmentů do různých cílových systémů má specifické požadavky. 

**Export segmentů v prostředích pro jednotlivé spotřebitele (B2C)**  
- Segmenty v kontextu prostředí pro jednotlivé zákazníky jsou postaveny na entitě *sjednocený profil zákazníka*. Exportovat lze každý segment, který splňuje požadavky cílových systémů (například e -mailová adresa).

**Segmenty exportu prostředí pro obchodní účty (B2B)**  
- Segmenty v kontextu prostředí pro obchodní účty jsou postaveny na entitě *účet*. Chcete -li exportovat segmenty účtu tak, jak jsou, musí cílový systém podporovat segmenty čistého účtu. To je případ [LinkedIn](export-linkedin-ads.md), když při definování exportu vyberete **společnost**.
- Všechny ostatní cílové systémy vyžadují pole od kontaktní entity. Aby bylo zajištěno, že segmenty účtu mohou načítat data ze souvisejících kontaktů, definice vašeho segmentu potřebuje promítnout atributy entity kontaktu. Další informace o tom, jak [konfigurovat segmenty a atributy projektu](segment-builder.md).

**Limity exportu segmentů**  
- Cílové systémy třetích stran mohou omezit počet zákaznických profilů, které můžete exportovat. 
- U jednotlivých zákazníků uvidíte skutečný počet členů segmentu, když vyberete segment pro export. Pokud je segment příliš velký, zobrazí se upozornění. 
- U obchodních účtů uvidíte počet účtů v segmentu; počet kontaktů, které mohou být promítány, se však nezobrazuje. V některých případech to může vést k tomu, že exportovaný segment skutečně obsahuje více profilů zákazníků, než cílový systém akceptuje. Pokud jsou překročena omezení cílového systému, export je přeskočen.

## <a name="set-up-a-new-export"></a>Nastavení nového exportu

Chcete-li nastavit nebo upravit export, musíte mít k dispozici správná připojení. Propojení závisí na vaší [roli uživatele](permissions.md):
- **Správci** mají přístup ke všem propojením. Mohou také vytvářet nová propojení při nastavování exportu.
- **Přispěvatelé** mohou mít přístup ke konkrétním propojením. Závisí na správcích, kteří konfigurují a sdílejí propojení. Seznam exportů zobrazuje ve sloupci **Vaše oprávnění** údaj o tom, zda mohou přispěvatelé export upravovat nebo pouze zobrazit. Další informace najdete v tématu [Povolit přispěvatelům používat připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Diváci** mohou pouze prohlížet stávající exporty - nikoli je vytvářet.

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte příkaz **Přidat export**.

1. V podokně **Nastavení exportu** vyberte, které [připojení](connections.md) chcete použít.

1. Zadejte požadované podrobnosti a výběrem **Uložit** vytvořte export. Požadované podrobnosti naleznete v dokumentaci k Customer Insights pro konkrétní export.

## <a name="manage-existing-exports"></a>Správa existujících exportů

Jděte na **Data** > **Exporty**, čímž zobrazíte exporty, jejich název připojení, typ připojení a stav. Všechny uživatelské role mohou zobrazit nakonfigurované exporty. Seznam exportů můžete seřadit podle libovolného sloupce nebo pomocí vyhledávacího pole najít export, který chcete spravovat.

Výběrem exportu zobrazíte dostupné akce.

:::image type="content" source="media/exports_showmore.png" alt-text="Stránka exportů.":::

- **Zobrazte** nebo **Upravte** export. Vyberte uživatele bez oprávnění k úpravám **Zobrazit** namísto **Upravit**, abyste mohli zobrazit podrobnosti exportu.
- **Spuštěním** exportu exportujete nejnovější data.
- **Vytvořte duplicitu** exportu.
- **[Naplánujte](#schedule-and-run-exports)** export.
- **Odpojte připojení** pro odebrání připojení pro tento export. Odpojení neodstraní připojení, ale deaktivuje export. Sloupec **Použité připojení** zobrazuje Bez připojení.
- **Odeberte** export.

## <a name="schedule-and-run-exports"></a>Plánování a spuštění exportů

Každý export, který konfigurujete, má plán aktualizace. Během aktualizace systém hledá nová nebo aktualizovaná data, která mají být zahrnuta do exportu. Ve výchozím nastavení jsou exporty spouštěny jako součást každé [plánované aktualizace systému](system.md#schedule-tab). Plán aktualizace můžete upravit nebo jej vypnout, aby se exporty spouštěly ručně.

Plány exportu závisí na stavu vašeho prostředí. Pokud probíhají aktualizace [závislostí](system.md#refresh-processes), když by měl začít plánovaný export, systém nejprve dokončí aktualizace a poté spustí export. Ve sloupci **Aktualizováno** vidíte, kdy byl export naposledy aktualizován.

### <a name="schedule-exports"></a>Plánování exportů

Definujte vlastní plány aktualizací pro jednotlivé exporty nebo několik exportů najednou. Aktuálně definovaný plán je uveden ve sloupci **Plán** seznamu exportů. Oprávnění ke změně plánu je stejné jako u [úpravy a definování exportů](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Vyberte export, který chcete naplánovat.

1. Vyberte **plán**.

1. V podokně **Naplánovat export** nastavte vlastnost **Naplánovat spuštění** na **Zapnuto**, aby byl export spuštěn automaticky. Nastavte tuto možnost na **Vypnuto**, chcete-li aktualizovat ručně.

1. U automaticky aktualizovaných exportů zvolte hodnotu **Opakování** a zadejte její podrobnosti. Definovaný čas platí pro všechny instance opakování. Je to čas, kdy by se měl export začít aktualizovat.

1. Vyberte **Uložit**.

Při úpravách plánu pro několik exportů proveďte výběr v poli **Zachovat nebo přepsat plány**:

- **Zachovat jednotlivé plány**: Zachová dříve definovaný plán pro vybrané exporty a pouze je deaktivuje nebo povolí.
- **Definujte nový plán pro všechny vybrané exporty**: Přepsat existující plány vybraných exportů.

### <a name="run-exports-on-demand"></a>Spuštění exportů na vyžádání

Chcete-li exportovat data bez čekání na plánované obnovení, přejděte na **Data** > **Exporty**.

- Chcete-li spustit všechny exporty, vyberte **Spustit vše** na panelu příkazů. Spuštěny budou pouze exporty, které mají aktivní plán. Chcete-li spustit export, který není aktivní, spusťte jediný export.
- Chcete-li spustit jeden export, vyberte jej v seznamu a v panelu příkazů vyberte **Spustit**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
