---
title: Cíle exportu
description: Exportujte data a spravujte cíle exportu.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643855"
---
# <a name="export-destinations-preview"></a>Cíle exportu (verze Preview)

Stránka **Cíle exportu** zobrazuje všechna umístění, která jste nastavili pro export dat. Můžete také přidat nové cíle pro export. Kromě toho zobrazuje možnosti exportu, které jsou aktuálně k dispozici. Získejte rychlý přehled, popis a zjistěte, co můžete dělat s každou možností rozšíření. Exportujte sjednocené profily, míry a segmenty do podporovaných aplikací relevantních pro vaši firmu.

Přejděte na **Správce** > **Cíle exportu**, kde najdete následující možnosti rozšiřitelnosti:

- [Doplněk karty zákazníka Dynamics 365](customer-card-add-in.md)
- [Konektor Správce reklam na Facebooku](export-facebook.md)
- [Konektor Power Automate](export-power-automate.md)
- [Konektor Power Apps](export-power-apps.md)
- [Konektor Power BI](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob Storage](export-azure-blob-storage.md)
- [Konektor LiveRamp &reg;](export-liveramp.md)
- [Bot pro Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Rozhraní API pro Customer Insights](apis.md)

## <a name="add-a-new-export-destination"></a>Přidání nového cíle exportu

Chcete-li přidat cíle exportu, musíte mít [oprávnění správce](permissions.md). Pokud exportujete do služeb společnosti Microsoft, předpokládáme, že obě služby jsou ve stejné organizaci.

1. Přejděte na **Správce** > **Cíle exportu**.

1. Přepněte na kartu **Moje cíle exportu**.

1. Vyberte **Přidat cíl**, chcete-li vytvořit nový cíl exportu.

1. V podokně **Přidat cíl** vyberte **Typ** cíle exportu v rozevíracím seznamu.

1. Zadejte požadované podrobnosti a vyberte **Další** pro vytvoření cílle exportu.

Můžete také vybrat **Založit** na dlaždici na kartě **Objevit**.

## <a name="view-export-destinations"></a>Zobrazit cíle exportu

Po vytvoření exportních cílů je najdete v tabulce na kartě **Moje cíle exportu**. Tato tabulka má tři sloupce:

- **Zobrazovaný název**: Název, který jste zadali při vytváření cíle.
- **Typ**: Typ cíle exportu, který jste nastavili při vytváření cíle.
- **Vytvořeno**: Datum vytvoření cíle.

## <a name="edit-an-export-destination"></a>Úprava cíle exportu

1. Vyberte vertikální tři tečky pro cíl exportu, který chcete upravit.

   > [!div class="mx-imgBorder"]
   > ![Vertikální tři tečky](media/export-destinations-page-ellipsis.png "Vertikální tři tečky")

1. V rozevírací nabídce vyberte **Upravit**.

1. Změňte hodnoty, které vyžadují aktualizaci, a vyberte **Uložit**.

## <a name="export-data-on-demand"></a>Export dat na vyžádání

Po konfiguraci konektoru pro cíl exportu bude export probíhat při každé [naplánované aktualizaci](system.md#schedule-tab).

Chcete-li exportovat data bez čekání na naplánované obnovení, přejděte na kartu **Moje cíle exportu** na **Správce** > **Exportovat cíle**.

> [!div class="mx-imgBorder"]
> ![Vertikální tři tečky](media/export-destinations-page-ellipsis.png "Vertikální tři tečky")

- Vyberte **Exportovat** nad seznamem, chcete-li spustit export do všech exportních cílů současně.
- Vyberte tři tečky (...) za položkou seznamu a poté vyberte možnost **Exportovat** a spusťte export pro jeden cíl exportu.

## <a name="remove-an-export-destination"></a>Odebrání cíle exportu

Chcete-li odebrat cíl exportu, začněte na hlavní stránce **Cíle exportu**.

1. Vyberte vertikální tři tečky pro cíl exportu, který chcete odebrat.

   > [!div class="mx-imgBorder"]
   > ![Vertikální tři tečky](media/export-destinations-page-ellipsis.png "Vertikální tři tečky")

2. V rozevírací nabídce vyberte možnost **Odebrat**.

3. Potvrďte odebrání výběrem **Odstranit** na potvrzovací obrazovce.
