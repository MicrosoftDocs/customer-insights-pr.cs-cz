---
title: Exportování upřesněných událostí
description: Jak exportovat upřesněné události a základní události.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d062e2982c1041454b083630404f2b68f0da9669
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232880"
---
# <a name="export-events"></a>Export událostí

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Událost představuje chování uživatele. Zaznamenává, kdy uživatel zobrazí stránku (aktivita zobrazení) nebo interaguje s obsahem (aktivita Akce). Když se můžete rozhodnout, které vlastnosti dat chcete v sestavě zobrazit, tento virtuální pohled na data se nazývá a *upřesněná událost*. Další informace najdete v tématu o [Vytvoření a správa událostí](refined-events.md).

- Události a upřesněné události můžete exportovat do externího úložiště. 
- Exporty jsou dopředný datový proud. Stream nemůžete znovu naplnit. 
- Exporty mají pevná schémata. Pokud k události přidáte vlastní vlastnosti, nebudou zahrnuty. Budete muset vytvořit nový export.

## <a name="prerequisites"></a>Požadavky

Před nastavením exportu musíte mít přístup a aktivní předplatné na portálu Azure. Během procesu exportu budete potřebovat informace o účtu úložiště. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Vytvoření účtů Azure Data Lake Storage Gen 2

1. Přihlaste se na portál Azure a [vytvořte nový účet úložiště](/azure/storage/common/storage-account-create). 

1. Ujistěte se, že jste povolili **hierarchický obor názvů** na kartě **Rozšířený**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Aktivace hierarchického oboru názvů na kartě rozšířené.":::

1. Po nasazení přejděte do nově vytvořeného účtu úložiště. V podokně navigace vyberte **Nastavení** > **Přístupové klíče**. 

1. Zkopírujte **Název účtu** a **Klíč** k použití při vytváření nového exportu.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Přístupové klíče v účtu úložiště.":::

## <a name="export-events"></a>Exportovat události

Existují dva způsoby, jak vyvolat dialog **Exportovat události**: 
- Přejděte na **Data** > **Exporty** a vyberte **Nový export**.
- Jděte na **Data** > **Události**, vyberte **Více [...]** vedle události, kterou chcete exportovat, a v rozevírací nabídce vyberte **Exportovat**. 

:::image type="content" source="media/new-export.png" alt-text="Vytvoření nového exportu":::

Provedete kroky k vytvoření exportu:

1. Zadejte **Název exportu** a vyberte **Další**.

1. V rozevíracím seznamu **Výběr událostí** vyberte základní události a upřesněné události, které chcete zahrnout do exportu. 

1. V části **Struktura souboru** vyberte kadenci (hodinovou nebo denní) pro vytvoření nových souborů v cílovém úložišti a poté vyberte **Další**. Události se exportují nepřetržitě, jakmile dorazí.

1. V dialogu **Vybrat formát** vyberte formát pro export. Vyberte z formátů **Common Data Model**, **CSV** a **JSON**. Chcete -li export použít s jinými aplikacemi Dynamics 365, doporučujeme formát **Common Data Model**.

1. V dialogu **Zvolit cíl** zadejte umístění Azure Data Lake Storage Gen 2.
    1. **Název účtu ADLS Gen 2** je název účtu úložiště, do kterého chcete export uložit. 
    1. **Cesta ke složce** definuje, kam má být export uložen v systému souborů a adresářové struktuře účtu úložiště.
    1. **Sdílený klíč** je k dispozici na webu Azure Portal pro účet úložiště.

1. Zkontrolujte a potvrďte výběry pro dokončení.

## <a name="view-and-manage-exports"></a>Zobrazení a správa exportů

Jakmile nastavíte export, přejděte na **Data** > **Exporty** k jejich zobrazení. Vyberte **Více [...]** pro jakýkoli existující export, který chcete upravit nebo smazat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
