---
title: Přehled exportů (Preview)
description: Spravujte exporty ke sdílení dat.
ms.date: 11/01/2021
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
ms.openlocfilehash: d983e84e713003610eb27dc9b3f911b62b01d522
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081157"
---
# <a name="exports-preview-overview"></a>Přehled exportů (Preview)

Stránka **Export** zobrazuje všechny nakonfigurované exporty. Exporty sdílejí konkrétní data s různými aplikacemi. Mohou zahrnovat zákaznické profily, entity, schémata a detaily mapování. Každý export vyžaduje [připojení, které nastavil správce, ke správě ověřování a přístupu](connections.md).

Jděte na **Data** > **Exporty** pro zobrazení stránky exportů. Všechny uživatelské role mohou zobrazit nakonfigurované exporty. Pomocí vyhledávacího pole na panelu příkazů vyhledejte exporty podle jejich názvu, názvu připojení nebo typu připojení.

## <a name="export-types"></a>Typy exportu

Existují dva hlavní typy exportu:  

- **Export dat** vám umožní exportovat jakýkoli typ entity dostupný v Customer Insights. Entity, které vyberete pro export, se exportují se všemi datovými poli, metadaty, schématy a podrobnostmi mapování. 
- **Exporty segmentů** vám umožní exportovat entity segmentů z Customer Insights. Segmenty představují seznam zákaznických profilů. Při konfiguraci exportu vyberete zahrnutá datová pole v závislosti na cílovém systému, do kterého exportujete data. 

### <a name="export-segments"></a>Export segmentů

**Export segmentů v prostředích pro obchodní účty (B2B) nebo individuální spotřebitele (B2C)**  
Většina možností exportu podporuje oba typy prostředí. Export segmentů do různých cílových systémů má specifické požadavky. Obecně řečeno, člen segmentu, profil zákazníka, obsahuje kontaktní informace. I když to obvykle platí pro segmenty postavené na individuálních spotřebitelích (B2C), nemusí to nutně platit pro segmenty založené na obchodních účtech (B2B). 

**Segmenty exportu prostředí pro obchodní účty (B2B)**  
- Segmenty v kontextu prostředí pro obchodní účty jsou postaveny na entitě *účet*. Chcete -li exportovat segmenty účtu tak, jak jsou, musí cílový systém podporovat segmenty čistého účtu. To je případ [LinkedIn](export-linkedin-ads.md), když při definování exportu vyberete **společnost**.
- Všechny ostatní cílové systémy vyžadují pole od kontaktní entity. Aby bylo zajištěno, že segmenty účtu mohou načítat data ze souvisejících kontaktů, definice vašeho segmentu potřebuje promítnout atributy entity kontaktu. Další informace o tom, jak [konfigurovat segmenty a atributy projektu](segment-builder.md).

**Export segmentů v prostředích pro jednotlivé spotřebitele (B2C)**  
- Segmenty v kontextu prostředí pro jednotlivé zákazníky jsou postaveny na entitě *sjednocený profil zákazníka*. Exportovat lze každý segment, který splňuje požadavky cílových systémů (například e -mailová adresa).

**Limity exportu segmentů**  
- Cílové systémy třetích stran mohou omezit počet zákaznických profilů, které můžete exportovat. 
- U jednotlivých zákazníků uvidíte skutečný počet členů segmentu, když vyberete segment pro export. Pokud je segment příliš velký, zobrazí se upozornění. 
- U obchodních účtů uvidíte počet účtů v segmentu; počet kontaktů, které mohou být promítány, se však nezobrazuje. V některých případech to může vést k tomu, že exportovaný segment skutečně obsahuje více profilů zákazníků, než cílový systém akceptuje. Překročení limitů výsledků cílových systémů přeskočí export. 

## <a name="set-up-a-new-export"></a>Nastavení nového exportu  
Chcete-li nastavit nebo upravit export, musíte mít k dispozici propojení. Propojení závisí na vaší [roli uživatele](permissions.md):
- **Správci** mají přístup ke všem propojením. Mohou také vytvářet nová propojení při nastavování exportu.
- **Přispěvatelé** mohou mít přístup ke konkrétním propojením. Závisí na správcích, kteří konfigurují a sdílejí propojení. Seznam exportů zobrazuje ve sloupci **Vaše oprávnění** údaj o tom, zda mohou přispěvatelé export upravovat nebo pouze zobrazit. Další informace najdete v tématu [Povolit přispěvatelům používat připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Diváci** mohou pouze prohlížet stávající exporty - nikoli je vytvářet.

### <a name="define-a-new-export"></a>Definování nového exportu

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte příkaz **Přidat export**.

1. V podokně **Nastavit export** vyberte, které propojení chcete použít. [Propojení](connections.md) jsou spravována správci. 

1. Zadejte požadované podrobnosti a výběrem **Uložit** vytvořte export.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definování nového exportu na základě existujícího exportu

1. Přejděte na **Data** > **Exporty**.

1. V seznamu exportů vyberte export, který chcete duplikovat.

1. Výběrem příkazu **Vytvořit duplikát** na panelu příkazů otevřete podokno **Nastavit export** s podrobnostmi vybraného exportu.

1. Zkontrolujte a upravte export a výběrem příkazu **Uložit** vytvořte nový export.

### <a name="edit-an-export"></a>Úprava exportu

1. Přejděte na **Data** > **Exporty**.

1. V seznamu exportů vyberte export, který chcete upravit.

1. V panelu příkazů vyberte **Upravit**.

1. Změňte hodnoty, které chcete aktualizovat, a vyberte **Uložit**.

## <a name="view-exports-and-export-details"></a>Zobrazení exportů a podrobností exportu

Po vytvoření jsou cíle exportu uvedeny v části **Data** > **Exporty**. Všichni uživatelé mohou vidět, která data jsou sdílena, a jejich nejnovější stav.

1. Přejděte na **Data** > **Exporty**.

1. Vyberte uživatele bez oprávnění k úpravám **Zobrazit** namísto **Upravit**, abyste mohli zobrazit podrobnosti exportu.

1. Postranní podokno ukazuje konfiguraci exportu. Bez oprávnění k úpravám nemůžete hodnoty měnit. Vyberte **Zavřít** pro návrat na stránku exportu.

## <a name="schedule-and-run-exports"></a>Plánování a spuštění exportů

Každý export, který konfigurujete, má plán aktualizace. Během aktualizace systém hledá nová nebo aktualizovaná data, která mají být zahrnuta do exportu. Ve výchozím nastavení jsou exporty spouštěny jako součást každé [plánované aktualizace systému](system.md#schedule-tab). Plán aktualizace můžete upravit nebo jej vypnout, aby se exporty spouštěly ručně.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Plány exportu závisí na stavu vašeho prostředí. Pokud probíhají aktualizace [závislostí](system.md#refresh-processes), když by měl začít plánovaný export, systém nejprve dokončí aktualizace a poté spustí export. Ve sloupci **Aktualizováno** vidíte, kdy byl export naposledy aktualizován.

### <a name="schedule-exports"></a>Plánování exportů

Můžete definovat vlastní plány aktualizací pro jednotlivé exporty nebo několik exportů najednou. Aktuálně definovaný plán je uveden ve sloupci **Plán** seznamu exportů. Oprávnění ke změně plánu je stejné jako u [úpravy a definování exportů](export-destinations.md#set-up-a-new-export). 

1. Přejděte na **Data** > **Exporty**.

1. Vyberte export, který chcete naplánovat.

1. V panelu příkazů vyberte možnost **Plánovat**.

1. V podokně **Naplánovat export** nastavte vlastnost **Naplánovat spuštění** na **Zapnuto**, aby byl export spuštěn automaticky. Nastavte tuto možnost na **Vypnuto**, chcete-li aktualizovat ručně.

1. U automaticky aktualizovaných exportů zvolte hodnotu **Opakování** a zadejte její podrobnosti. Definovaný čas platí pro všechny instance opakování. Je to čas, kdy by se měl export začít aktualizovat.

1. Změny použijte a aktivujte výběrem příkazu **Uložit**.

Při úpravách plánu pro několik exportů je třeba provést výběr v poli **Zachovat nebo přepsat plány**:
- **Zachovat jednotlivé plány**: Zachovat dříve definovaný plán pro vybrané exporty a pouze je deaktivovat nebo povolit.
- **Definujte nový plán pro všechny vybrané exporty**: Přepsat existující plány vybraných exportů.

### <a name="run-exports-on-demand"></a>Spuštění exportů na vyžádání

Chcete-li exportovat data bez čekání na plánované obnovení, přejděte na **Data** > **Exporty**.

- Chcete-li spustit všechny exporty, vyberte **Spustit vše** na panelu příkazů. Tato akce spustí pouze exporty, které mají aktivní plán.
- Chcete-li spustit jeden export, vyberte jej v seznamu a v panelu příkazů vyberte **Spustit**. Takto spustíte export bez aktivního plánu. 

## <a name="remove-an-export"></a>Odebrání exportu

1. Přejděte na **Data** > **Exporty**.

1. Vyberte export, který chcete odebrat.

1. V panelu příkazů vyberte příkaz **Odebrat**.

1. Potvrďte odebrání výběrem **Odstranit** na potvrzovací obrazovce.


[!INCLUDE [footer-include](includes/footer-banner.md)]
