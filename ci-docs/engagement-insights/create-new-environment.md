---
title: Vytvořit nové prostředí
description: Účel prostředí a způsob vytvoření nového.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f82ff588c2ffbe82c3ee7df2498ac2cca2bad31
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225415"
---
# <a name="create-a-new-environment"></a>Vytvořit nové prostředí 

## <a name="overview"></a>Přehled

Prostředí je prostor, kde spravujete své pracovní prostory a připojení. To, jak používáte prostředí, závisí na vaší organizaci a vašem případu použití. Je například možné vytvořit:

- Jedno prostředí.
- Oddělená prostředí pro testování a produkci.
- Oddělená prostředí pro konkrétní týmy nebo oddělení ve vaší organizaci, která obsahují relevantní události pro každou cílovou skupinu.
- Oddělená prostředí pro různé globální pobočky vaší společnosti.
- Připojení k funkci přehledů cílové skupiny Customer Insights.

## <a name="create-a-new-environment"></a>Vytvořit nové prostředí

1. Na pravé straně hlavního banneru vyberte výběr prostředí a poté **+Nový**.

   :::image type="content" source="media/environment-picker.png" alt-text="Vyberte výběr prostředí.":::

1. V podokně **Nastavení** zadejte **Název prostředí**.

1. Zvolte **Typ** účtu, v závislosti na typu vašeho plánu.

1. Zvolte **Oblast** a vyberte **Další**. 

1. Zadejte **Název pracovního prostoru**, což vám umožní shromažďovat data pro konkrétní weby nebo aplikace. Další informace naleznete v tématu [Vytvoření pracovního prostoru](create-workspace.md).

1. Vyberte **typ pracovního prostoru** (webový nebo mobilní), který chcete vytvořit. 

1. Vyberte **Zobrazit pokročilá nastavení** k povolení nebo zakázání těchto volitelných nastavení:

   - Přepněte **Neznámé na známé** na „povoleno“ pro přidružení webových událostí k uživatelům, kteří se dříve autentizovali. Další informace viz [Rozpoznání webových událostí od dříve ověřených návštěvníků](unknown-to-known.md).
   - Přepněte **Filtrovat provoz robotů** na „povoleno“, aby se odstranil webový provoz robotů pro tento pracovní prostor. 

1. Až budete hotovi, vyberte **Dokončit**. 

1. Chcete -li začít přijímat data, nainstalujte fragment kódu a poté vyberte **Dokončit** k vytvoření pracovního prostoru. Další informace naleznete v tématu [Přehled zdrojů pro vývojáře](developer-resources.md).

> [!NOTE]
> Nyní můžete přidávat členy a přiřazovat jim úroveň oprávnění ze seznamu **Role**. Další informace najdete v článku [Role a oprávnění](user-roles.md). 

Další informace viz [Správa a prostředí pracovních prostorů](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Práce s novým prostředím

- [Vytvořte pracovní prostor](../engagement-insights/create-workspace.md) a přidejte členy.
- [Přidejte kód na svůj web](../engagement-insights/instrument-website.md) nebo do [mobilní aplikace](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Zobrazte [sestavu v reálném čase](../engagement-insights/view-reports.md) nebo vytvořte [vlastní sestavy](../engagement-insights/custom-reports.md).
- [Vytvářejte upřesněné události](../engagement-insights/refined-events.md) pro export.
- [Exportujte data](../engagement-insights/export-events.md) do Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
