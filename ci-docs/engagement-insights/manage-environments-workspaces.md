---
title: Správa pracovních prostorů a prostředí
description: Jak vytvářet, přejmenovávat a mazat pracovní prostory a prostředí.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486027"
---
# <a name="manage-environments-and-workspaces"></a>Správa prostředí a pracovních prostorů

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Přehled

Pracovní prostor je prostor pro ukládání a správu událostí a sestav. Zde můžete zobrazit aktivitu uživatelů v reálném čase. Když vytváříte pracovní prostor, vyberete typ dat, která se mají do pracovního prostoru odeslat. Aktuálně jsou podporována webová data a mobilní aplikace.

Prostředí je prostor, kde spravujete své pracovní prostory a připojení. To, jak používáte prostředí, závisí na vaší organizaci a vašem případu použití. Je například možné vytvořit:

-   Jedno prostředí.
-   Oddělená prostředí pro testování a produkci.
-   Oddělená prostředí pro konkrétní týmy nebo oddělení ve vaší organizaci, která obsahují relevantní události pro každou cílovou skupinu.
-   Oddělená prostředí pro různé globální pobočky vaší společnosti.
-   Připojení k funkci přehledů cílové skupiny Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Výběr prostředí a vytvoření pracovního prostoru 

Každý pracovní prostor musí být v prostředí. Při vytváření pracovního prostoru můžete vybrat již existující prostředí nebo vytvořit nové. Pak se můžete rozhodnout přidat členy pracovního prostoru a začít sbírat data.

**Vytvoření prvního pracovního prostoru**

1. V přehledu zapojení vyberte **Nový** z přepínače pracovního prostoru. 

   :::image type="content" source="media/New-workspace.png" alt-text="Výběr pracovního prostoru stránky Customer Insights.":::

1. Vyberte prostředí ze seznamu nebo vyberte **Vytvořit nové prostředí**.

1. Zadejte název do **Název pracovního prostoru**. 

1. Vyberte typ prostředí, které chcete vytvořit, podle toho, zda chcete měřit, co se děje na webu nebo v mobilní aplikaci. 

1. Členy můžete přidat a přiřadit jejich úroveň oprávnění ze seznamu **Role**. Poté vyberte **Dokončit** k vytvoření pracovního prostoru nebo **Další** k instalaci kódu. 

1. Nainstalujte fragment kódu, abyste mohli začít přijímat data, a poté vyberte **Hotovo**. 

## <a name="manage-a-workspace"></a>Správa pracovního prostoru

V prostředí můžete udržovat více pracovních prostorů současně. Vaše [role](user-roles.md) určuje, jak v nich můžete pracovat. 

 - Chcete-li spravovat pracovní prostor, musíte být správcem prostředí nebo správcem pracovního prostoru.
 - Jako správce pracovního prostoru můžete stávající pracovní prostory přejmenovat nebo je odstranit. 

### <a name="edit-a-workspace-name"></a>Úprava názvu pracovního prostoru

1. Přejděte na **Správce** > **Pracovní prostor** a vyberte **Nastavení**.

1. Do políčka **Název pracovního prostoru** zadejte nový název.

1. Výběrem možnosti **Uložit** se vaše změny uplatní.

### <a name="delete-a-workspace"></a>Odstranění pracovního prostoru

Odstraněním pracovního prostoru trvale odeberete veškerý jeho obsah, data, nastavení a oprávnění. Tuto akci nelze vrátit zpět.

1. Přejděte na **Správce** > **Pracovní prostor** a vyberte **Nastavení**.

1. Vyberte **Odstranit pracovní prostor**. 

1. Do dialogového okna **Odstranit pracovní prostor** zadejte **POTVRDIT ODSTRANĚNÍ**. 

1. Chcete-li trvale odstranit pracovní prostor, vyberte **Odstranit**.

### <a name="manage-workspace-members"></a>Správa členů pracovního prostoru

1. Přejděte na **Správce** > **Pracovní prostor** a vyberte **Členové**.

1. Vyberte **Přidat členy** k udělení přístupu a [přiřazení rolí](user-roles.md). V současné době je k dispozici pouze **Správce pracovního prostoru**.

1. Vyberte **Přidat členy** a přidejte je do svého pracovního prostoru.

## <a name="manage-an-environment"></a>Spravovat prostředí

Jako správce prostředí můžete do prostředí přistupovat z levého navigačního podokna. Můžete konfigurovat nastavení prostředí, další správce prostředí a pracovní prostory. Vyberte záložky pro přesun mezi různými oblastmi v centru pro správu.

:::image type="content" source="media/New-environment.png" alt-text="Centrum pro správu prostředí.":::

### <a name="create-an-environment"></a>Vytvořit prostředí

1. V nástroji pro výběr pracovního prostoru vyberte **+Nový**.

1. V řízeném prostředí otevřete rozevírací nabídku **Prostředí** a vyberte **Vytvořit nové prostředí**. 

1. Zadejte **Název prostředí**.

   :::image type="content" source="media/create-environment.png" alt-text="Vstupte řízeného prostředí a zadejte podrobnosti o prostředí.":::

1. Zvolte **Oblast** a vyberte **Další**. 

1. Zadejte název pracovního prostoru a vyberte typ pracovního prostoru, který chcete vytvořit. 

1.  Volitelně můžete přidat členy a zkopírovat fragment kódu, čímž dokončíte proces vytváření.

### <a name="rename-an-environment"></a>Přejmenování prostředí

1. Přejděte na **Správce** > **Prostředí** a vyberte **Nastavení**.

1. Aktualizujte **Název prostředí** a vyberte **Uložit** k použití změn.

### <a name="manage-environment-members"></a>Správa členů prostředí

1. Přejděte na **Správce** > **Prostředí** a vyberte **Členové**.

1. Vyberte **Přidat členy** k aktualizaci členů a [přiřazení rolí](user-roles.md). V současné době je k dispozici pouze **Správce prostředí**.

1. Vyberte **Přidat členy** a přidejte je do svého prostředí.

### <a name="delete-an-environment"></a>Odstranění prostředí

Správci prostředí mohou prostředí odstranit. Před odstraněním prostředí musíte odebrat všechny pracovní prostory pod ním.

1. Přejděte na **Správce** > **Prostředí** a vyberte **Nastavení**.

1. Vyberte **Odstranit prostředí**. 

1. Do dialogového okna **Odstranit pracovní prostor** zadejte **POTVRDIT ODSTRANĚNÍ**. 

1. Pokud chcete prostředí trvale odstranit, vyberte **Odstranit**.

## <a name="manage-connections"></a>Spravovat připojení

Navázání připojení k přehledům cílové skupiny vám umožní zobrazit sestavy ve statistikách zapojení na základě jednotných profilů zákazníků. 

Více informací najdete v části [Vytvoření propojení mezi přehledy cílových skupin a přehledy zapojení](integrate-audience-insights-engagement-insights.md)

## <a name="manage-personal-data"></a>Správa osobních údajů

V zájmu ochrany osobních údajů zákazníka můžete odstranit nebo exportovat identifikovatelná data koncového uživatele.

Další informace viz [Odstranění a export dat události obsahující osobní údaje](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
