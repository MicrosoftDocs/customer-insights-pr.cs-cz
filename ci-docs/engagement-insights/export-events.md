---
title: Exportování upřesněných událostí
description: Jak exportovat upřesněné události a základní události.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032377"
---
# <a name="export-events"></a>Export událostí

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Událost představuje chování uživatele. Zaznamenává, kdy uživatel zobrazí stránku (aktivita zobrazení) nebo interaguje s obsahem (aktivita Akce). Když se můžete rozhodnout, které vlastnosti dat chcete v sestavě zobrazit, tento virtuální pohled na data se nazývá a *upřesněná událost*. 

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

Exportovat události lze dvěma způsoby. 
- Přejděte na **Data** > **Exporty** a vyberte **Nový export**.
- Jděte na **Data** > **Události**, vyberte **Více [...]** vedle události, kterou chcete exportovat, a v rozevírací nabídce vyberte **Exportovat**. 

Provedete kroky k vytvoření exportu:

1. Zadejte **Název exportu**.

1. V rozevíracím seznamu **Výběr událostí** vyberte základní události a upřesněné události, které chcete zahrnout do exportu. 

1. V části **Struktura souborů** vyberte kadenci vytváření nových souborů v cílovém úložišti. Události se exportují nepřetržitě, jakmile dorazí.

1. Vyberte formát pro export. Můžete si vybrat mezi formátem **Common Data Model**, **CSV** a **JSON**. Chcete-li použít export s jinými aplikacemi Dynamics 365, doporučujeme použít formát Common Data Model.

1. V kroku **Vybrat cíl** zadejte umístění Azure Data Lake Storage Gen 2.
    1. **Název účtu ADLS Gen 2** je název účtu úložiště, do kterého chcete export uložit. 
    1. **Cesta ke složce** definuje, kam má být export uložen v systému souborů a adresářové struktuře účtu úložiště.
    1. **Sdílený klíč** je k dispozici na webu Azure Portal pro účet úložiště.

1. Zkontrolujte a potvrďte svůj výběr.

## <a name="view-and-manage-exports"></a>Zobrazení a správa exportů

Jakmile nastavíte export, přejděte na **Data** > **Exporty** k jejich zobrazení. Vyberte **Více [...]** pro jakýkoli existující export, který chcete upravit nebo smazat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]