---
title: Vytvořit nový pracovní prostor
description: Účel pracovního prostoru a způsob vytvoření nového.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f8922703af506974c8b5b24086b61f05a83609d
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673374"
---
# <a name="create-a-new-workspace-and-add-members"></a>Vytvořte nový pracovní prostor a přidejte členy

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Pracovní prostor je způsob, jakým můžete zobrazit aktivitu uživatelů v reálném čase, abyste lépe porozuměli své cílové skupině. Zde ukládáte a spravujete události a zprávy.

Když vytváříte pracovní prostor, vyberete typ dat, na která se chcete zaměřit. Do stávajícího pracovního prostoru můžete kdykoli přidat další uživatele nebo členy. 

## <a name="create-a-new-workspace"></a>Vytvořit nový pracovní prostor

Proces vytváření pracovního prostoru zahrnuje nastavení *prostředí* k uspořádání pracovního prostoru. Prostředí je prostor, který může obsahovat jeden nebo více pracovních prostorů. Prostředí můžete použít ke správě svých pracovních prostorů a připojení k přehledům cílových skupin.

1. Vyberte **+Nový** z přepínače pracovního prostoru.

   :::image type="content" source="media/new-workspace.png" alt-text="Stránka Customer Insights s popisem v navigačním podokně a popisem.":::

1. V podokně **Pracovní prostor** zadejte **Název pracovního prostoru**.

   :::image type="content" source="media/workspace-name.png" alt-text="Zadejte název pracovního prostoru.":::

1. Vyberte typ platformy (webovou nebo mobilní), kterou chcete měřit.

1. Vyberte **Zobrazit pokročilá nastavení** k povolení nebo zakázání těchto volitelných nastavení:

   - Přepněte **Neznámé na známé** na „povoleno“ pro přidružení webových událostí k uživatelům, kteří se dříve autentizovali. Další informace viz [Rozpoznání webových událostí od dříve ověřených návštěvníků](unknown-to-known.md)
   - Přepněte **Filtrovat provoz robotů** na „povoleno“, aby se odstranil webový provoz robotů pro tento pracovní prostor. 

1. Až budete hotovi, vyberte **Dokončit**. 

1. Chcete -li začít přijímat data, nainstalujte fragment kódu a poté vyberte **Dokončit** k vytvoření pracovního prostoru. Další informace naleznete v tématu [Přehled zdrojů pro vývojáře](developer-resources.md).

> [!NOTE]
> Nyní můžete přidávat členy a přiřazovat jim úroveň oprávnění ze seznamu **Role**. Další informace najdete v článku [Role a oprávnění](user-roles.md). 

Další informace viz [Správa a prostředí pracovních prostorů](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
